VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box     = 'ubuntu14-base_20141028'
  config.vm.box_url = 'https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box'

  config.vm.define :consul1 do |conf|
    conf.vm.hostname = 'consul1'
    conf.vm.network :private_network, ip: '192.168.10.101'
    config.vm.provider :virtualbox do |v|
      v.name   = config.vm.hostname
      v.cpus   = 1
      v.memory = 1024
    end
    config.vm.provision :ansible do |ansible|
      ansible.playbook = 'consul1.yml'
      ansible.verbose  = 'vvv'
    end
  end

  config.vm.define :consul2 do |conf|
    conf.vm.hostname = 'consul2'
    conf.vm.network :private_network, ip: '192.168.10.102'
    config.vm.provider :virtualbox do |v|
      v.name   = config.vm.hostname
      v.cpus   = 1
      v.memory = 1024
    end
    config.vm.provision :ansible do |ansible|
      ansible.playbook = 'consul2.yml'
      ansible.verbose  = 'vvv'
    end
  end
end
