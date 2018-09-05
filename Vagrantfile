# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|

  #Virtual mashine 
  config.ssh.private_key_path = "/root/.ssh/id_rsa"
  config.vm.synced_folder '.', '/vagrant', disable: true

  config.vm.provider :digital_ocean do |provider, override|
    override.vm.box = 'digital_ocean'
    override.vm.box_url = "https://github.com/devopsgroup-io/vagrant-digitalocean/raw/master/box/digital_ocean.box"

    provider.token = '***********'
    provider.image = 'ubuntu-16-04-x64'
    provider.region = 'sgp1'
    provider.size = '512mb'
    provider.ssh_key_name = '**********'
  end

  #Provisioning
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end

end
