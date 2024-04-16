# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure ("2") do |config|
	config.vm.box = "centos/7"
	config.vm.hostname = "demo"
	config.vm.network :private_network, ip: "192.168.33.10"
	config.vm.synced_folder ".", "/home/vagrant/sync", disabled: true
	config.vm.provision "shell", inline: <<-SHELL
    sudo yum -y install epel-release
    sudo yum -y install nginx
	echo "hello, park seungkyu" > /usr/share/nginx/html/index.html
    sudo systemctl start nginx
	SHELL
end
