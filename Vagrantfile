# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "centos/7"

  config.vm.box_download_insecure = true
  
  config.vm.provider :virtualbox do |vb|
    vb.gui = false
    vb.memory = "4098"
    vb.cpus = 2
  end

  config.vm.network :forwarded_port, guest: 80, host: 9300

  config.vm.provision	:file,
			source: "inventory.ini",
			destination: "/tmp/inventory.ini"

  config.vm.provision   :file,
			source: "requirements.yml",
			destination: "/tmp/requirements.yml"

  config.vm.provision	:file,
			source: "provisioning.yml",
			destination: "/tmp/provisioning.yml"

  config.vm.provision 	:file,
			source: "elasticsearch.repo",
			destination: "/tmp/elasticsearch.repo"

  config.vm.provision 	:file,
		      	source: "elasticsearch.yml",
		      	destination: "/tmp/elasticsearch.yml"

  config.vm.provision :shell, inline: <<-SHELL
    sudo yum -y install epel-release 
    sudo sed -i 's/https/http/' /etc/yum.repos.d/epel.repo
    sudo yum --enablerepo=epel -y update
    sudo yum -y install ansible
    if [ -x /etc/ansible ]; then
    	sudo install --mode=644 /tmp/inventory.ini /etc/ansible/hosts
	sudo ansible-playbook /tmp/provisioning.yml
     fi
  SHELL

end
