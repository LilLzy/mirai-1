# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "debian/jessie64"
  config.vm.synced_folder "files/", "/mnt/vagrant"
  config.vm.synced_folder ".", "/vagrant", type: "rsync", rsync__exclude: "files/"

  config.vm.define "cnc" do |cnc|
    cnc.vm.network "private_network", ip: "10.0.0.10"
    cnc.vm.provision :shell, path: "init_cnc.sh"
    cnc.vm.hostname = "cnc"
  end

  config.vm.define "bot" do |bot|
    bot.vm.network "private_network", ip: "10.0.0.20"
    bot.vm.provision :shell, path: "init_bot.sh"
    bot.vm.hostname = "bot"
  end

end
