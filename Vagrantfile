# -*- mode: ruby -*-
# vi: set ft=ruby :

hostname = ENV['HOSTNAME'] ? ENV['HOSTNAME'] : 'st2test'

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    config.vm.network "public_network"
    # config.vm.network "private_network", ip: "172.168.90.65"
    config.vm.hostname = "#{hostname}"

    config.vm.define "u14" do |u14|
      u14.vm.box = 'puppetlabs/ubuntu-14.04-64-nocm'
    end

    config.vm.define "el6" do |el6|
      el6.vm.box = 'puppetlabs/centos-6.6-64-nocm'
    end

    config.vm.define "el7" do |el7|
      el7.vm.box = 'puppetlabs/centos-7.0-64-nocm'
    end

    config.vm.provider :virtualbox do |vb|
      vb.name = "#{hostname}"
      vb.memory = 2048
      vb.cpus = 2
    end

    # Configure a private network

    config.vm.provision "shell", inline: "curl -sSL https://install.stackstorm.com/ | sudo su"

end
