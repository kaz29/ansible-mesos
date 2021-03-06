# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :box
  end

  config.vm.box = "opscode-ubuntu-14.04"
  config.vm.box_url = "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-14.04_chef-provisionerless.box"

  config.vm.define :master01 do |server|
    server.vm.hostname = "master01"
    server.vm.network :private_network, ip: "192.168.39.10"
    server.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
    end
    
#    server.vm.provision :ansible_local do |ansible|
#      ansible.limit = 'all'
#      ansible.install = true
#      ansible.inventory_path = "ansible/hosts/vagrant"
#      ansible.playbook = "ansible/vagrant-master01.yml"
#    end

# host 
    server.vm.provision :ansible do |ansible|
      ansible.limit = 'all'
      ansible.inventory_path = "ansible/hosts/vagrant"
      ansible.playbook = "ansible/vagrant-master01.yml"
    end
  end

  config.vm.define :master02 do |server|
    server.vm.hostname = "master02"
    server.vm.network :private_network, ip: "192.168.39.11"
    server.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
    end
    server.vm.provision :ansible do |ansible|
      ansible.limit = 'all'
      ansible.inventory_path = "ansible/hosts/vagrant"
      ansible.playbook = "ansible/vagrant-master02.yml"
    end
  end

  config.vm.define :master03 do |server|
    server.vm.hostname = "master03"
    server.vm.network :private_network, ip: "192.168.39.12"
    server.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
    end
    server.vm.provision :ansible do |ansible|
      ansible.limit = 'all'
      ansible.inventory_path = "ansible/hosts/vagrant"
      ansible.playbook = "ansible/vagrant-master03.yml"
    end
  end

  config.vm.define :slave01 do |server|
    server.vm.hostname = "slave01"
    server.vm.network :private_network, ip: "192.168.39.13"
    server.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
    end
    server.vm.provision :ansible do |ansible|
      ansible.limit = 'all'
      ansible.inventory_path = "ansible/hosts/vagrant"
      ansible.playbook = "ansible/vagrant-slave01.yml"
    end
  end

  config.vm.define :slave02 do |server|
    server.vm.hostname = "slave02"
    server.vm.network :private_network, ip: "192.168.39.14"
    server.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
    end
    server.vm.provision :ansible do |ansible|
      ansible.limit = 'all'
      ansible.inventory_path = "ansible/hosts/vagrant"
      ansible.playbook = "ansible/vagrant-slave02.yml"
    end
  end
end