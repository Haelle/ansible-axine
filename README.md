# Ansible Axine

### TODO
add Oh My Zsh support
https://github.com/robbyrussell/oh-my-zsh

add zsh completion support
https://github.com/zsh-users/zsh-completions

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

## Informations complémentaires
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

### Set a password


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