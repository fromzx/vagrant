# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.define "web01" do |vb|
    vb.vm.host_name = "web01"
    vb.vm.network "private_network", ip: "192.168.56.101"
    vb.vm.box = "web01"
    vb.vm.box_url = "./virtualbox.box"
    vb.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 1
      v.name = "web01"
    end
    vb.vm.provision "shell", inline: <<-SHELL
      sudo sed -i "s/PasswordAuthentication no/# PasswordAuthentication no/g" /etc/ssh/sshd_config
      sudo systemctl restart sshd
    SHELL
  end

  config.vm.define "app01" do |vb|
    vb.vm.host_name = "app01"
    vb.vm.network "private_network", ip: "192.168.56.102"
    vb.vm.box = "app01"
    vb.vm.box_url = "./virtualbox.box"
    vb.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 1
      v.name = "app01"
    end
    vb.vm.provision "shell", inline: <<-SHELL
      sudo sed -i "s/PasswordAuthentication no/# PasswordAuthentication no/g" /etc/ssh/sshd_config
      sudo systemctl restart sshd
    SHELL
  end

end
