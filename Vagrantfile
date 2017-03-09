# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "hiroshima-arc/manhattan"
  config.vm.box_version = "1.0.0"

  config.vm.network :forwarded_port, guest:3000, host:3000, id:"Rails"
  config.vm.network :forwarded_port, guest:1234, host:1234, id:"RubyDebuger"
  config.vm.network :private_network, ip:"127.0.0.1"

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  end
end
