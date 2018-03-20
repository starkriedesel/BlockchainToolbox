# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define "cli", primary: true do |cli|
    cli.vm.box = "bento/ubuntu-16.04"
    cli.vm.hostname = "toolbox"

    cli.vm.provider "virtualbox" do |vb|
      vb.memory = "4096"
    end
  end

  # Core CLI tools
  config.vm.provision "core-cli", type: "ansible_local" do |ansible|
    ansible.playbook = "core-cli.yml"
  end

  # Customization for CLI
  config.vm.provision "customization-cli", type: "ansible_local" do |ansible|
    ansible.playbook = "customization-cli.yml"
  end

  # Ethereum CLI tools
  config.vm.provision "ethereum-cli", type: "ansible_local" do |ansible|
    ansible.playbook = 'ethereum-cli.yml'
  end

  # Bitcoin CLI tools
  config.vm.provision "bitcoin-cli", type: "ansible_local" do |ansible|
    ansible.playbook = 'bitcoin-cli.yml'
  end

  # Hyperledger Fabric (CLI)
  config.vm.provision "hlfabric", type: "ansible_local" do |ansible|
    ansible.playbook = 'hlfabric.yml'
  end

  config.vm.define "gui", primary: false, autostart: false do |gui|
    gui.vm.box = "viruzzo/xubuntu-xenial64"
    gui.vm.hostname = "toolbox"

    gui.vm.provider "virtualbox" do |vb|
      vb.gui = true
      vb.memory = "4096"
      vb.customize ["modifyvm", :id, "--vram", "64"]
    end

    # Core GUI tools
    config.vm.provision "core-gui", type: "ansible_local" do |ansible|
      ansible.playbook = 'core-gui.yml'
    end

    # Ethereum GUI tools
    config.vm.provision "ethereum-gui", type: "ansible_local" do |ansible|
      ansible.playbook = 'ethereum-gui.yml'
    end
  end
end
