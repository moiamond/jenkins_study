# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ci_win7_dev"
  config.vm.box_url = "http://192.168.11.77:8090/ci_windows_7_virtualbox.box"

  config.ssh.username = "vagrant"
  config.ssh.password = "vagrant!"
  config.vm.network "forwarded_port", guest: 3389, host: 3389, id: "rdp", auto_correct: true
  config.vm.network "forwarded_port", guest: 5985, host: 5985, id: "winrm", auto_correct: true
  config.vm.network "forwarded_port", guest: 22, host: 22, id: "ssh", auto_correct: true

  config.vm.provider "virtualbox" do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--vram", "128"]
    vb.customize ["modifyvm", :id,  "--cpus", "2"]
    vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    vb.customize ["guestproperty", "set", :id, "/VirtualBox/GuestAdd/VBoxService/--timesync-set-threshold", 10000]
  end
end
