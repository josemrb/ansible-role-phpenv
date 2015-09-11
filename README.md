# Ansible Role: Phpenv

[![Build
 Status](http://img.shields.io/travis/pablocrivella/ansible-role-phpenv.svg?style=flat)](http://travis-ci.org/pablocrivella/ansible-role-phpenv)
[![Ansible
Galaxy](http://img.shields.io/badge/galaxy-pablocrivella.phpenv-660198.svg?style=flat)](https://galaxy.ansible.com/list#/roles/2332)

Role to install phpenv and multiple ruby versions.

## Requirements

Tested with Ansible 1.8.4.

## Role Variables

```yaml
---
# This could be set to 'user' to support user installs.
phpenv_env: system

phpenv_version: v0.4.0

# This sets the phpenv global ruby version.
phpenv_global: 2.2.3

# List of ruby versions to install.
phpenv_rubies:
  - 2.2.3

# List of defaults gem to install on each ruby version.
phpenv_default_gems:
  - bundler

# List of users to install phpenv and ruby versions to.
# Ignored if phpenv_env is set to 'system'
phpenv_users: []

# Example:
# phpenv_users: []
#   - user1
#   - user2
```

## Dependencies

- ANXS.git
- ANXS.build-essential

## Example Playbook

```yaml
- hosts: ruby-devbox
  roles:
    - pablocrivella.phpenv
```

For a more detailed example check this [Playbook](https://github.com/pablocrivella/apps-forge/blob/master/provisioning/ruby.yml).

## License

MIT

## Author Information

Pablo Crivella Backend Engineer @ NobelBiz.
