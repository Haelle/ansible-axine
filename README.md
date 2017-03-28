# Ansible Dev
***

Ansible script to deploy my dev env

- install my dotfiles
- configure Vim & plugins
- configure zsh
- Python dev env
- Rails dev env (with RVM)

## Basic command line
ansible localhost

### Test ec2 connection
./ec2.py --list
ansible -i ec2.py -u ubuntu eu-central-1 -m ping

### Requirements

#### for Windows control
pip install "pywinrm>=0.2.2"

#### for AWS control
- boto
- `~/.boto`config file with credentials
