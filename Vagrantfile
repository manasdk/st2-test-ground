# -*- mode: ruby -*-
# vi: set ft=ruby :

hostname = ENV['HOSTNAME'] ? ENV['HOSTNAME'] : 'u14'
box      = ENV['BOX'] ? ENV['BOX'] : 'puppetlabs/ubuntu-14.04-64-nocm'

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    config.vm.box = "#{box}"
    config.vm.network "public_network"
    # config.vm.network "private_network", ip: "172.168.90.65"
    config.vm.hostname = "#{hostname}"

    config.vm.define "#{hostname}" do |q|
    end

    config.vm.provider :virtualbox do |vb|
      vb.name = "#{hostname}"
      vb.memory = 2048
      vb.cpus = 2
    end

    # Configure a private network

    config.vm.provision "shell", inline: "curl -sSL http://stackstorm.com/install.sh | sudo su"

end
