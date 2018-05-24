# elasticsearch [![Open in Cloud9](https://img.shields.io/badge/Open%20in-Cloud9-blue.svg?style=flat-square)](https://c9.io/auth/github?r=https%3A%2F%2Fc9.io%2Fopen%2F%3Fclone_url%3Dhttps%253A%252F%252Fgithub.com%252Fdenzuko%252Fcom.dwightaspencer.vagrant.elasticsearch.git) [![Analytics](https://ga-beacon.appspot.com/UA-110571074-1/denzuko/ansible-roles/com.dwightaspencer.vagrant.elasticsearch?flat)](https://github.com/denzuko/com.dwightaspencer.vagrant.elasticsearch) [![CiCD](https://img.shields.io/travis/denzuko/com.dwightaspencer.vagrant.elasticsearch.svg?style=flat-square)](https://travis-ci.org/denzuko/com.dwightaspencer.vagrant.elasticsearch)

Elastic Search base image with CentOS 7, EPEL, Ansible, and ElasticSearch 6.x


# Dependencies
------------

 * [denzuko-ansible-roles/elasticsearch](https://galaxy.ansible.com/denzuko-ansible-roles/elasticsearch/) from ansible galaxy


## Deploy

Setup ones environment to ensure the have all the dependecies:

`ansible-galaxy install -r requirements.yml`

First login to atlas:

`vagrant login`

Then initize a new Vagrantfile and startup the instance:

`vagrant init denzuko/elasticsearch; vagrant up`

To access ElasticSearch visit http://localhost:80/
