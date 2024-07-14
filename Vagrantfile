Vagrant.configure("2") do |config|

  config.vm.define "web1" do |web1|
    web1.vm.box = "ubuntu/bionic64"  # Usamos Ubuntu 18.04 LTS
    web1.vm.network "private_network", ip: "192.168.50.11", virtualbox__intnet: true
    web1.vm.hostname = "web1"

    # Provisionamiento para instalar Apache
    web1.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y apache2
      sudo systemctl enable apache2
    SHELL

    # Compartir carpeta local con directorio de Apache
    web1.vm.synced_folder ".", "/var/www/html", type: "virtualbox"
  end

 
  config.vm.define "web2" do |web2|
    web2.vm.box = "ubuntu/bionic64"  # Usamos Ubuntu 18.04 LTS
    web2.vm.network "private_network", ip: "192.168.50.12", virtualbox__intnet: true
    web2.vm.hostname = "web2"

    # Provisionamiento para instalar Apache
    web2.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y apache2
      sudo systemctl enable apache2
    SHELL

    # Compartir carpeta local con directorio de Apache
    web2.vm.synced_folder ".", "/var/www/html", type: "virtualbox"
  end
end
