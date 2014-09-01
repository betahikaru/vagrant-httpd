# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

$install = <<SCRIPT
  sudo yum install -y httpd
SCRIPT

$configure = <<SCRIPT
  sudo rm -rf /var/www/html
  sudo cp -r /vagrant_data/html /var/www/html
  sudo chown -R apache.apache /var/www/html
SCRIPT

$network_setting = <<SCRIPT
  sudo systemctl start httpd.service
  sudo systemctl enable httpd.service
  sudo iptables -F
SCRIPT

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "hfm4/centos7"
  config.vm.network :forwarded_port, guest: 80, host: 8081, id:"http"
  config.vm.network :private_network, ip: "192.168.33.10", auto_config: false
  config.ssh.forward_agent = true
  config.vm.synced_folder "./data", "/vagrant_data"

  config.vm.provision "shell", inline: $install
  config.vm.provision "shell", inline: $configure
  config.vm.provision "shell", inline: $network_setting

end

