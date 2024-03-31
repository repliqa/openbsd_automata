# vagrantfile for testing automation

# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
  config.vm.box = "obsd"

  config.vm.network "private_network", ip: "10.20.30.40", network: "_vagrantnet"
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.provider "libvirt" do |lv|
    lv.memory = "8196"
    lv.cpus = 10
  end
  config.ssh.shell = "sh -l"
  config.vm.provision "shell", inline: <<-SHELL
    sysupgrade -f 
    echo "Run `vagrant reload`"
  SHELL
end
