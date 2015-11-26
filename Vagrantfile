# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  config.vm.define :charlotte do |charlotte|
    charlotte.vm.box = 'heroku/trusty64'
    charlotte.vm.box_url = 'https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box'
    charlotte.vm.network 'private_network', ip: '192.168.44.55'
    charlotte.vm.network 'forwarded_port', guest: 8000, host: 8000, auto_correct: true
    charlotte.vm.provision 'ansible' do |ansible|
      ansible.sudo = true
      ansible.playbook = 'provisioning/playbook.yml'
    end

    charlotte.vm.provider 'virtualbox' do |v|
      v.memory = 2048
    end
  end
end
