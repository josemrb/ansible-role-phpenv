phpenv_env = ENV.key?('PHPENV_ENV') ? ENV['PHPENV_ENV'] : 'system'

Vagrant.configure('2') do |config|
  config.vm.define 'ansible-role-phpenv' do |c|
    c.vm.box = 'debian/jessie64'
    c.vm.network :private_network, ip: '192.168.40.3'
    c.vm.hostname = 'ansible-role-phpenv.local'

    c.vm.provider :virtualbox do |vb|
      vb.name = 'ansible-role-phpenv'
    end

    c.vm.provision :ansible do |ansible|
      ansible.playbook = 'test.yml'
      ansible.sudo = true
      ansible.inventory_path = 'vagrant-inventory'
      ansible.host_key_checking = false
      ansible.verbose = 'v'
      ansible.extra_vars = {
        phpenv_env: phpenv_env,
        phpenv_users: ['vagrant']
      }
    end
  end
end
