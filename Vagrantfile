# -*- mode: ruby -*-
# vi: set ft=ruby :

=begin
ModernIE VMs
config.vm.box = "modernIE/vista-ie7"
config.vm.box = "modernIE/w7-ie8"
config.vm.box = "modernIE/w7-ie9"
config.vm.box = "modernIE/w7-ie10"
config.vm.box = "modernIE/w7-ie11"
config.vm.box = "modernIE/w8-ie10"
config.vm.box = "modernIE/w8.1-ie11"
config.vm.box = "modernIE/w10-edge"
System Account Credentials
Username: IEUser
Password: Passw0rd!
=end

Vagrant.configure("2") do |config|
  config.vm.box = "modernIE/w7-ie11"

  config.ssh.username = "IEUser"
  config.ssh.password = "Passw0rd!"
  config.vm.network "forwarded_port", guest: 22, host: 22, id: "ssh", auto_correct: true

  config.vm.provider "virtualbox" do |vb|
    vb.customize ["modifyvm", :id, "--memory", "1024"]
    vb.customize ["modifyvm", :id, "--vram", "128"]
    vb.customize ["modifyvm", :id,  "--cpus", "2"]
    vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    vb.customize ["guestproperty", "set", :id, "/VirtualBox/GuestAdd/VBoxService/--timesync-set-threshold", 10000]
  end
end
