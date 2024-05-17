Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"
  config.vm.network "private_network", ip: "192.168.50.55"

  # Configuración de las carpetas sincronizadas
  # Sincronizar carpeta desde el host a la VM
  config.vm.synced_folder ".", "/vagrant_data"

  # Configuración de provisión con shell
  config.vm.provision "shell", inline: <<-SHELL
    # Instalación de los binarios de PHP y el driver de conexión a la BBDD
    sudo apt-get update
    sudo apt-get install -y php php-mysqli

  SHELL

end
