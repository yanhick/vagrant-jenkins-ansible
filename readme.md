#Vagrant - Jenkins - Ansible

Test of setting up a Jenkins master and slave using Vagrant and provisioning with Ansible

##Install

On debian-based distrib:

Install [Vagrant](https://www.vagrantup.com/) and [virtualbox](https://www.virtualbox.org/)
```
sudo apt-get install vagrant virtualbox -y
```

Install [Ansible](http://docs.ansible.com/index.html)
```
sudo apt-get install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt-get update
sudo apt-get install ansible
```

Clone this repo
```
git clone https://github.com/yanhick/vagrant-jenkins-ansible
```

##Run

To start the virtual machines and start the Jenkins instances, cd into the cloned repo, then:
```
vagrant up
```

##Test

Open this url in a browser to test the Jenkins instance:
```
http://localhost:1234
```
You should see that that Jenkins has a “test” job as well as a slave configured
