#Niall Harders

BOX_IMAGE = "bento/ubuntu-16.04"
NODE_COUNT = 2

Vagrant.configure("2") do |config|
  config.vm.define "master" do |subconfig|
    subconfig.vm.box = BOX_IMAGE
    subconfig.vm.hostname = "master"
    subconfig.vm.network :private_network, ip: "192.168.1.10"
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