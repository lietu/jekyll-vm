# -*- mode: ruby -*-
# vi: set ft=ruby :

# Provisioning script
$script = <<SCRIPT
sudo apt-get install ruby ruby-dev make gcc nodejs
sudo gem install jekyll --no-rdoc --no-ri
SCRIPT

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.provision "shell", inline: $script

end
