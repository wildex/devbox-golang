# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # --------------------------------------------------------------------
  # Definitions for the VirtualBox machine
  # --------------------------------------------------------------------
  config.vm.define "virtualbox", autostart: false do |vbox|
    vbox.vm.provider "virtualbox" do |v|
      v.memory = 2048
      v.cpus = 2
    end
    vbox.vm.box = "ubuntu/trusty64"
    vbox.vm.network "private_network", ip: "10.0.1.2"
    vbox.vm.provision :ansible do |ansible|
      ansible.playbook = "playbook.yml"
    end
    # Tell the user what to do next
	vbox.vm.provision "shell", inline: "echo 'Finished! Now try logging in with: vagrant ssh virtualbox'"
  end
end
