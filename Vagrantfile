# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "gusztavvargadr/ubuntu-server"
  config.vm.network "private_network", ip: "192.168.1.10"

  config.vm.provider "virtualbox" do |vb|
    vb.name = "ubuntu-server"
    vb.check_guest_additions = false

    # Customize the amount of memory on the VM:
    vb.memory = "1024"
    vb.cpus = 2
    vb.gui = true

  #Copy Nginx configuration
  config.vm.synced_folder "config", "/var/www/config", create: true

  #Copy Laravel Project
  config.vm.synced_folder "project", "/var/www/project", create: true, group: "www-data", owner: "www-data"
  end
  
  config.vm.provision "shell", path: "command.sh"

end
