Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  config.vm.network "private_network", ip: "10.71.13.18"
end
config.vm.provision "shell", inline: <<-SHELL
apt-get update
apt-get install -y apache2
SHELL

config.vm.provision "shell", inline: <<-SHELL
apt-get update
apt-get install -y ufw gufw
ufw allow ssh
ufw allow 80/tcp
yes Y | ufw enable
SHELL
  
end