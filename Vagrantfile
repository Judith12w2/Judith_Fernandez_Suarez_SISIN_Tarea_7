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

    # Generar archivo SQL con los registros de horarios
    echo "-- Insertar datos de ejemplo en la tabla 'horarios'" > /home/vagrant/datos_horarios.sql
    echo "INSERT INTO gestion_modulos_profesionales.horarios (nombre, apellido, salario, asignatura) VALUES" >> /home/vagrant/datos_horarios.sql
    echo "('Diego', 'Alonso', 4000.00, 'SISIN')," >> /home/vagrant/datos_horarios.sql
    echo "('Bea', 'López', 3800.00, 'LMSGI')," >> /home/vagrant/datos_horarios.sql
    echo "('Lorena', 'Franco', 3920.00, 'LEUP')," >> /home/vagrant/datos_horarios.sql
    echo "('Tomás', 'Huerta', 3920.00, 'BADAT')," >> /home/vagrant/datos_horarios.sql
    echo "('Diego', 'Mateos', 3990.00, 'PROG')," >> /home/vagrant/datos_horarios.sql
    echo "('Guillermo', 'Román', 3800.00, 'ENDES');" >> /home/vagrant/datos_horarios.sql

  SHELL

end
