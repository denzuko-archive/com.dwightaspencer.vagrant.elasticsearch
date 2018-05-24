# elasticsearch
Elastic Search base image with CentOS 7, EPEL, Ansible, and ElasticSearch 6.x


# Dependencies
------------

 * [cmprescott/jre](https://galaxy.ansible.com/cmprescott/jre/) from ansible galaxy

## Deploy

Setup ones environment to ensure the have all the dependecies:

`ansible-galaxy install -r requirements.yml`

First login to atlas:

`vagrant login`

Then initize a new Vagrantfile and startup the instance:

`vagrant init denzuko/elasticsearch; vagrant up`

To access ElasticSearch visit http://localhost:80/
