# Ansible Role: phpenv

[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-josemrb.phpenv-blue.svg)](https://galaxy.ansible.com/list#/roles/5115)

Role to install custom versions of PHP using [phpenv](https://github.com/CHH/phpenv) and [php-build](https://github.com/php-build/php-build).

## Requirements
- Ansible 1.8.4.

## Dependencies
- [ANXS.git](https://github.com/ANXS/git)
- [ANXS.build-essential](https://github.com/ANXS/build-essential)

## Variables
### phpenv_env
Sets the installation type, `user` or `system`.
```yaml
phpenv_env: system
```

### phpenv_global
Sets the global php version, must be included in the versions to install.
```yaml
phpenv_global: 5.6.29
```

### phpenv_versions
List of versions to install.
```yaml
phpenv_versions:
  - 5.6.29
```

### phpenv_users
List of users to install to.
Ignored if phpenv_env is set to `system`
```yaml
phpenv_users:
  - vagrant
```

## Example

```yaml
---
- hosts: all

  roles:
    - josemrb.phpenv
```

## Testing

This project comes with a Vagrantfile, this is a fast and easy way to test changes to the role.

Launch the guest machine with the following command.
```sh
$ vagrant up
```

To run the provision again you can use:
```sh
$ vagrant provision
```

or you can run ansible directly.

```sh
$ ansible-playbook tests/test.yml -i tests/vagrant-inventory -k
```

Please check the [documentation](http://docs.vagrantup.com/v2/) for more information on Vagrant.

## License

Licensed under the MIT License. See the LICENSE file for details.

## Contributors
[josemrb](https://github.com/josemrb)  
[pablocrivella](https://github.com/pablocrivella)  
[pumazi](https://github.com/pumazi)
