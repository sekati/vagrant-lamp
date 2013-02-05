# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|

  config.vm.customize ["modifyvm", :id, "--memory", 384]

  config.vm.box = "squeeze64"
  config.package.name = "squeeze64"
  config.vm.host_name = "squeeze64"

  config.vm.box_url = "http://cdn.sekati.com/vagrant/squeeze64.box"

  config.vm.network :hostonly, "192.168.33.10"

  config.vm.forward_port 80, 8080
  config.vm.forward_port 443, 4430
  config.vm.forward_port 3306, 3306
  config.vm.forward_port 1025, 1025
  config.vm.forward_port 1080, 1080

  # loosen permissions for www-data @see http://serverfault.com/questions/398414/vagrant-set-default-share-permissions
  config.vm.share_folder("v-root", "/vagrant", ".", :extra => 'dmode=770,fmode=770')

  #config.vm.provision :shell, :inline => "echo \"America/New_York\" | sudo tee /etc/timezone && dpkg-reconfigure --frontend noninteractive tzdata"
  #config.vm.provision :shell, :inline => "apt-get update --fix-missing"

end