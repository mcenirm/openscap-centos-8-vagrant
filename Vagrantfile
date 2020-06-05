# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.define "centos8" do |x|
    x.vm.box = "bento/centos-8"
  end
  config.vm.define "centos7" do |x|
    x.vm.box = "bento/centos-7"
  end
  config.vm.provision "ansible_local" do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "playbook.yml"
  end
end
