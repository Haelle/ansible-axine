# Ansible Dev
***

### TODO
add Oh My Zsh support
https://github.com/robbyrussell/oh-my-zsh
add zsh completion support
https://github.com/zsh-users/zsh-completions

add RVM support
install some gems => seeing_is_believing

## Introduction
Ansible script to deploy axine dev server

- install my dotfiles
- configure Vim & plugins
- configure zsh, tmux, ag, git
- basic packages
- Python dev env
- Rails dev env (with RVM)

## Basic command line
`ansible-playbook axine-vps-playbook.yml`

### Requirements
Python on target server
Allow ssh connection for root user:
`sudo vim /etc/ssh/sshd_config`
Set: PermitRootLogin yes
Reload sshd config
`sudo service sshd reload`

#### for Windows control
pip install "pywinrm>=0.2.2"
