# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.box_check_update = false
  # config.vm.network "forwarded_port", guest: 80, host: 80

  config.vm.provision "file" do |file|
    file.source=".ssh"
    file.destination="$HOME/"
  end

  config.vm.provision "shell" do |shell|
    shell.inline="chmod 600 $HOME/.ssh/config"
    shell.privileged = false
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
  end
end
