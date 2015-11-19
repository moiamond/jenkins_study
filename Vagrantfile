# -*- mode: ruby -*-
# vi: set ft=ruby :

$install_docker_compose = <<SCRIPT
curl -L https://github.com/docker/compose/releases/download/1.5.1/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
SCRIPT

$docker_compose_up = <<SCRIPT
cd /APP
docker-compose up -d
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.network "forwarded_port", guest: 8080, host: 8080, id: "jenkins", auto_correct: true
  config.vm.synced_folder ".", "/APP", create: true

  # run provision
  config.vm.provision "docker"
  config.vm.provision "shell", inline: $install_docker_compose
  config.vm.provision "shell", inline: $docker_compose_up

  config.vm.provider "virtualbox" do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--vram", "128"]
    vb.customize ["modifyvm", :id,  "--cpus", "2"]
    vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    vb.customize ["guestproperty", "set", :id, "/VirtualBox/GuestAdd/VBoxService/--timesync-set-threshold", 10000]
  end
end
