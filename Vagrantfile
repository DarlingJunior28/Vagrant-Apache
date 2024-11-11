# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    # Configuración de la VM
    config.vm.box = "ubuntu/bionic64" # Puedes elegir otra versión o sistema si prefieres
    
    # Configuración de recursos
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.cpus = 1
    end
    
    # Configuración de red y sincronización de carpetas
    config.vm.network "private_network", type: "dhcp"
    config.vm.synced_folder ".", "/var/www/html" # Sincroniza el directorio local con el de Apache
    
    # Provisión para instalar Apache
    config.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y apache2
    SHELL
  end
  