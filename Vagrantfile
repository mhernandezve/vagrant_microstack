# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "peru/ubuntu-18.04-server-amd64"

  config.vm.network "private_network", ip: "10.10.10.10"
  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "8192"
  end

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y net-tools
    apt-get install -y snapd
    snap install microstack --classic --beta
    sudo microstack.init --auto
  SHELL
end
