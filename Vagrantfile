Vagrant.configure("2") do |config|
  config.vm.box = "debian/bullseye64"
  config.vm.hostname = "gp1f4a7blue.fjeclot.net"
  
  config.vm.provider "virtualbox" do |v|
    v.name = "gp1f4a7"
    v.memory = 2048
    v.cpus = 2
    v.customize ['modifyvm', :id, '--groups', '/ASIX2']
  end

  config.vm.network "public_network", type: "dhcp", bridge: "Intel(R) Wireless-AC 9462"

  config.vm.synced_folder "C:/Users/Pablo Romera/Desktop/ASIX-2/GP1/projectes/gp1f4a7/codi", "/home/vagrant/gp1f4a7/codi"


  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update -y
    sudo apt-get install -y aptitude net-tools git zip unzip
    sudo apt-get install -y docker.io
    sudo usermod -aG docker vagrant
    sudo chown -R vagrant:vagrant /home/vagrant/gp1f4a7
  SHELL
end