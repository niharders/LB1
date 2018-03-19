#Niall Harders

BOX_IMAGE = "bento/ubuntu-16.04"
BOX_IMAGE1 = "ubuntu/xenial64"
NODE_COUNT = 2

Vagrant.configure("2") do |config|
  config.vm.define "master" do |subconfig|
    subconfig.vm.box = BOX_IMAGE1
    subconfig.vm.hostname = "master"
    subconfig.vm.network :private_network, ip: "192.168.1.10"
    subconfig.vm.network "forwarded_port", guest:80, host:8080 
    subconfig.vm.synced_folder ".", "/var/www/html"
    config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update -y
    sudo apt-get install -y apache2 
    sudo apt-get install -y php
    sudo su
    cd /var/www/html/
  

SHELL
  end
  
  (1..NODE_COUNT).each do |i|
    config.vm.define "client#{i}" do |subconfig|
      subconfig.vm.box = BOX_IMAGE
      subconfig.vm.hostname = "client#{i}"
      subconfig.vm.network :private_network, ip: "192.168.1.#{i + 10}"
    end
  end

  # Install avahi on all machines  
  config.vm.provision "shell", inline: <<-SHELL
    apt-get install -y avahi-daemon libnss-mdns
  SHELL
end