# Orchestrate `Jenkins` Master/Slave with `Docker Compose`

1. Build a `Jenkins` CI system powered by `Docker`. 
2. The slave node has the capability to [run `Docker`](http://container-solutions.com/running-docker-in-jenkins-in-docker/).

## Requirement 

### `Ubuntu` user

1. [`Docker`](https://docs.docker.com/engine/misc/#about-docker) >= 1.9.0
2. [`Docker Compose`](https://docs.docker.com/compose/) >= 1.5.0

### `Mac`/`Windows` user
1. [`VirtualBox`](https://www.virtualbox.org/) >= 5.0
2. [`vagrant`](https://www.vagrantup.com/) >= 1.7.4

## Get started
    git clone https://github.com/moiamond/jenkins_study
    git submodule update --init --recursive

## Launch `Jenkins`
  
### `Ubuntu` user
    docker-compose up
  
### `Windows`/`Mac` user
    vagrant up
    
## Have fun
    http://localhost:8080
