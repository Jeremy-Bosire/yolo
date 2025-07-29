# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Using ubuntu/focal64 as already configured
  config.vm.box = "ubuntu/focal64"
  
  # Network configuration for e-commerce application
  config.vm.network "forwarded_port", guest: 3000, host: 3000  # Frontend
  config.vm.network "forwarded_port", guest: 5000, host: 5000  # Backend API  
  config.vm.network "forwarded_port", guest: 27017, host: 27017 # MongoDB
  config.vm.network "forwarded_port", guest: 80, host: 8080    # Web server
  
  # Resource allocation for containerized applications
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = 2
    vb.name = "ecommerce-devops-vm"
  end
  
  # Prepare system for Ansible
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y python3 python3-pip git curl
    # Create ansible user if needed
    id -u ansible &>/dev/null || useradd -m -s /bin/bash ansible
  SHELL
  
  # Ansible provisioning using existing playbook
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    # Use existing hosts file or create reference
    ansible.inventory_path = "hosts"
    ansible.verbose = "v"
    # Limit to specific host if needed
    ansible.limit = "all"
  end
end