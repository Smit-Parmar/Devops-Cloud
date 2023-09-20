```bash
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Configuration for the first virtual machine (Ubuntu-based)
  config.vm.define "web_server" do |web_config|
    web_config.vm.box = "ubuntu/bionic64"
    web_config.vm.network "private_network", type: "dhcp"
    web_config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
    end
    web_config.vm.provision "shell", inline: "echo 'This is the web server'"
  end

  # Configuration for the second virtual machine (Ubuntu-based)
  config.vm.define "database_server" do |db_config|
    db_config.vm.box = "ubuntu/bionic64"
    db_config.vm.network "private_network", type: "dhcp"
    db_config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
    end
    db_config.vm.provision "shell", inline: "echo 'This is the database server'"
  end

  # Configuration for the third virtual machine (Fedora-based)
  config.vm.define "fedora_server" do |fedora_config|
    fedora_config.vm.box = "generic/fedora34" # Use a Fedora box
    fedora_config.vm.network "private_network", type: "dhcp"
    fedora_config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
    end
    fedora_config.vm.provision "shell", inline: "echo 'This is the Fedora server'"
  end
end
```