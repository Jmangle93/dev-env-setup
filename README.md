# JM Dev Namespace - Dev Env Setup
=========

This role is to make setting up my preferred development environment - git, bash profile, installations and configs - easy.
Starting with a [bash-it](https://github.com/Bash-it/bash-it) and [bash-git-prompt](https://github.com/magicmonty/bash-git-prompt) profile, and a Poetry managed Python and Ansible development stack.

## Tested Systems
------------

**AWS**
- RHEL-9.6.0_HVM-20250618-x86_64

## Role Variables
--------------

- bash_it_theme:    [Bash-it theme](https://bash-it.readthedocs.io/en/latest/themes) supplied to .bashrc
- dev_user:         Username to create and install the dependencies and bash profile to

## Dependencies
------------

community.general.pipx

## Example Playbook
----------------
```
- hosts: servers
    roles:
        - { role: {{ playbook_dir }}, dev_user: JohnDoe, bash_it_theme: pure }
```

## License
-------

BSD

## Author
------------------

Github.com/Jmangle93
