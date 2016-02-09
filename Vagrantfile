# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|
  config.vm.provider "virtualbox" do |v|
  v.memory = 1024
  v.cpus = 2
end

  config.vm.define 'anxs' do |c|
    c.vm.box = 'ubuntu/trusty64'
    c.vm.network :private_network, ip: '192.168.88.15'
    c.vm.hostname = 'anxs.local'
    c.vm.provision 'ansible' do |ansible|
      ansible.playbook = 'tests/test.yml'
      ansible.sudo = true
      ansible.inventory_path = 'vagrant-inventory'
      ansible.host_key_checking = false
      ansible.verbose = "vvvv"
    end
  end
end
