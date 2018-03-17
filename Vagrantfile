# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
  config.vm.define  "nagios" do |host|
    host.vm.box = "centos/7"
    host.vm.hostname = "nagios"
    host.vm.network "private_network", ip: "192.168.50.89"
    host.vm.provision "shell", path: "strap_nagios"
    host.vm.network "forwarded_port", guest: 80, host: 7777 
  #  host.vm.provision :reload
  end
  config.vm.define  "agent" do |host|
    host.vm.box = "centos/7"
    host.vm.hostname = "agent"
    host.vm.network "private_network", ip: "192.168.50.88"
    host.vm.provision "shell", path: "strap_agent"
    host.vm.network "forwarded_port", guest: 80, host: 7778 
  #  host.vm.provision :reload
  end
end
