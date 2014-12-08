# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  config.vm.network :public_network

  config.vm.define "master" do |master|
      master.vm.box = "trusty64"
      master.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
      master.vm.hostname = "master"
      master.vm.network :forwarded_port, guest: 8080, host: 1234
      master.vm.network "private_network", ip: "192.168.50.4"
      master.vm.provision "ansible" do |ansible|
          ansible.playbook = "master.yml"
      end
  end

  config.vm.define "slave" do |slave|
      slave.vm.box = "trusty64"
      master.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
      slave.vm.hostname = "slave"
      slave.vm.network "private_network", ip: "192.168.50.5"
      slave.vm.provision "ansible" do |ansible|
          ansible.playbook = "slave.yml"
      end
  end

end
