# JM Dev Namespace - Dev Env Setup

This role is to make setting up my preferred development environment - git, bash profile, installations and configs - easy.
Starting with a bash theme and profile, supplying a global git config for a new dev user, and a Poetry managed Python and Ansible development stack.

## About the dev environment

**bash**
- Themes and plugins that look cool like zsh, but don't steal programmer array indexing with [bash-it](https://github.com/Bash-it/bash-it)
- Git prompting with [bash-git-prompt](https://github.com/magicmonty/bash-git-prompt)
- Git command and other handy autocomplete with [bash-completion](https://github.com/GArik/bash-completion)
- .bashrc in templates

**git config**
- VS Code usage configs for default editor, diff and difftool, merge and merge tool
- .gitconfig in templates

**Python**
- [Poetry](https://python-poetry.org/) and [Tox](https://tox.wiki/) installation via [pipx](https://pipx.pypa.io/stable/) to work with Python virtualenvs
- To use one or the other, maybe [both](https://www.keenformatics.com/tox-poetry/)? Probably depends on the project

## Tested Systems

**AWS**
- RHEL-9.6.0_HVM-20250618-x86_64
- RHEL-10.0.0_HVM-20250618-x86_64

## Role Variables

- bash_it_theme:    Use this [Bash-it theme](https://bash-it.readthedocs.io/en/latest/themes) in dev user's .bashrc
- dev_git_email     Set this email in dev user's global gitconfig
- dev_git_name      Set this name in dev user's global gitconfig
- dev_user:         Create this dev user and install the dependencies and bash profile with it
- dev_user_groups:  Add the dev user to this comma delimited list of groups

## Dependencies

community.general.pipx: `ansible-galaxy collection install community.general`, `python3 -m pip install pipx~=1.7.1`

## Example Playbook
```
---
- hosts: servers
    roles:
        - { role: {{ playbook_dir }}, dev_user: JohnDoe, bash_it_theme: pure }
```

## License

**BSD**

## Author

**Github.com/Jmangle93**
