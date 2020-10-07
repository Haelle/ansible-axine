# Ansible Axine

#### TODO
add Oh My Zsh support:
https://github.com/robbyrussell/oh-my-zsh

add zsh completion support:
https://github.com/zsh-users/zsh-completions

Grub theme:
https://github.com/lfelipe1501/Atomic-GRUB2-Theme

add Rbenv support

install some gems => seeing_is_believing

## Introduction
This Ansible configures:

- personnal desktop
- master server (for dev)
- slave website server

## Basic command lines
````
ansible-playbook axine-vps-playbook.yml
ansible-playbook bxine-vps-playbook.yml
ansible-playbook desktop-playbook.yml
````

## Post playbook install
NodeJS installation is not handled by the role.

Run : `nvm install 9.3`

Install **Private** encrypted directory:

`ecryptfs-setup-private`

### Gnome Shell Extension
Open it with `gnome-shell-extension-prefs`:

- System monitor
- Dash to Dock
- Alt Tab Workspace
- Pomodoro

### Python virtual env
Virtual envs are created in `~/.virtualenvs` and can be created with :

`mkvirtualenv -p python3 <virtualenv_name>`

When you want to use a virtualenv just do:

`workon <virtualenv_name>`

To stop using it:

`deactivate`

## Grub: Informations complémentaires
Grub is a bit touchy it's not done by Ansible yet...

### Change keyboard
For a fr grub :

`sudo grub-kbdcomp -o /boot/grub/fr.gkb fr`

In `/etc/default/grub` :

`GRUB_TERMINAL_INPUT="at_keyboard"`

In `/etc/grub.d/40_custom` :

````
#!/bin/sh
exec tail -n +3 $0

insmod keylayouts
keymap /boot/grub/fr.gkb
````
### Remove memtest
`sudo apt-get remove memtest86+`

### And update grub
And finally :

`sudo update-grub`

### Requirements
Python on target server
Allow ssh connection for root user:
`sudo vim /etc/ssh/sshd_config`
Set: PermitRootLogin yes
Reload sshd config
`sudo service sshd reload`
