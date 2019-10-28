# -*- mode: ruby -*-
# vim: set ft=ruby :

Vagrant.configure("2") do |config|

  ## Escolha da Box
  config.vm.box = "ubuntu/bionic64"

  ## Configuração de Rede
  config.vm.hostname = "ubuntulab"
  #config.vm.network "forwarded_port", guest: 80, host: 8080
  #config.vm.network "private_network", ip: "192.168.X.X"

  ## Configurações de Size da VM
  config.vm.provider "virtualbox" do |v|
     v.name = "ubuntu"
     v.memory = 512
     v.cpus = 2
  end
  
  ## Integrando o Ansible no Provisionamento

  config.vm.provision :ansible_local do |ansible|
     ansible.install_mode = "pip"
     ansible.playbook = "playbook.yml"
     ansible.verbose  = true
     ansible.install  = true
     ansible.limit    = "all"
  end

end
