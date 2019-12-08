# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "Bassualdo/raspberryDesktop"
  config.vm.box_version = "1.0.0"
  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    # vb.gui = true
 
    # Customize the amount of memory on the VM:
    vb.memory = "2048"
  end

  config.ssh.password = "raspberry"
  config.ssh.username = "pi"

  config.vm.provision "shell", inline: "ansible-galaxy role install --force -r /vagrant/requirements.yml"

  config.vm.provision "shell", inline: "ansible-playbook --connection=local --inventory 127.0.0.1, /vagrant/main.yml"


  config.vm.provision "shell", inline: "sudo cp /vagrant/splash.png /usr/share/plymouth/themes/pix/splash.png"


  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
end
