# -*- mode: ruby -*-
# vim: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.provider "virtualbox" do |v|
    v.memory = 512
    v.cpus = 1
  end
  config.vm.define "inetrouter" do |inetr|
    inetr.vm.network "private_network", ip: "192.168.255.1", netmask: "255.255.255.252", virtualbox__intnet: "router-net"
    inetr.vm.hostname = "inetrouter"
  end
  config.vm.define "centralrouter" do |centr|
    centr.vm.network "private_network", ip: "192.168.255.2", netmask: "255.255.255.252", virtualbox__intnet: "router-net"
    centr.vm.network "private_network", ip: "192.168.0.1", netmask: "255.255.255.240", virtualbox__intnet: "dir-net"
    centr.vm.network "private_network", ip: "192.168.0.33", netmask: "255.255.255.240", virtualbox__intnet: "hw-net"
    centr.vm.network "private_network", ip: "192.168.0.65", netmask: "255.255.255.192", virtualbox__intnet: "mgt-net"
    centr.vm.hostname = "centralrouter"
  end
  config.vm.define "centralserver" do |cents|
    cents.vm.network "private_network", ip: "192.168.0.2", netmask: "255.255.255.240", virtualbox__intnet: "dir-net"
    cents.vm.hostname = "centralserver"
  end
#  config.vm.define "inetrouter2" do |inetr2|
#    inetr2.vm.network "private_network", ip: "192.168.56.10"
#    inetr2.vm.hostname = "inetrouter2"
#  end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "main.yml"
    ansible.inventory_path = "hosts"
  end
end
