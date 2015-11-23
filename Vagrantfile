# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure(2) do |config|

  config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  # Customize the amount of memory on the VM:
      vb.memory = "1024"
  end

  config.vm.define "web1" do |app|
    app.vm.hostname = "web1.dev"
    app.vm.box = "ubuntu/trusty64"
    app.vm.network "private_network", ip: "192.168.33.10"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
  end
end
