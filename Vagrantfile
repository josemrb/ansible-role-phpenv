Vagrant.configure('2') do |config|
  config.vm.define 'ansible-role-rbenv' do |c|
    c.vm.box = 'ubuntu/trusty64'
    c.vm.network :private_network, ip: '192.168.40.3'
    c.vm.hostname = 'ansible-role-rbenv.local'

    c.vm.provider :virtualbox do |vb|
      vb.name = 'ansible-role-rbenv'
    end

    c.vm.provision :ansible do |ansible|
      ansible.playbook = 'test.yml'
      ansible.sudo = true
      ansible.inventory_path = 'vagrant-inventory'
      ansible.host_key_checking = false
      ansible.verbose = 'vvv'
      ansible.extra_vars = {
        rbenv_env: ENV['RBENV_ENV'],
        rbenv_users: ['vagrant']
      }
    end
  end
end
