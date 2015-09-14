phpenv_env = ENV.key?('PHPENV_ENV') ? ENV['PHPENV_ENV'] : 'system'

Vagrant.configure('2') do |config|
  config.vm.define 'ansible-role-phpenv' do |c|
    c.vm.box = 'debian/jessie64'
    c.vm.network :private_network, ip: '192.168.40.10'
    c.vm.hostname = 'ansible-role-phpenv.local'

    c.vm.provider :virtualbox do |vb|
      vb.name = 'ansible-role-phpenv'
    end

    c.vm.provision :ansible do |ansible|
      ansible.playbook = 'tests/test.yml'
      ansible.sudo = true
      ansible.inventory_path = 'tests/vagrant-inventory'
      ansible.host_key_checking = false
      ansible.verbose = 'v'
    end
  end
end
