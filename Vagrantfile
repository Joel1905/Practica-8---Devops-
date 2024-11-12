Vagrant.configure("2") do |config|
    # Configuración de la máquina virtual
    config.vm.box = "ubuntu/jammy64" # Puedes cambiar la versión de Ubuntu si lo deseas
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"  # RAM
      vb.cpus = 1       # CPU
    end
  
    # Provisión para instalar Apache
    config.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y apache2
    SHELL

    # Configurar el puerto 
    config.vm.network "forwarded_port", guest: 80, host: 8080

  
    # Sincronización de carpetas
    config.vm.synced_folder "src.", "/var/www/html", type: "virtualbox"
  end
  