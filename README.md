# Ubiquiti Unifi Controller for Ubuntu Server 20.04

Ansbile playbook to install the latest ubiquiti unifi controller for ubuntu serve 20.04

## Initial settings

Change username on `inventory/ubiquiti.yml` vars with your username

```bash
vars:
  username: 'ubuntu'
```

Install `ansible` in your system
```bash
sudo apt -y install ansible
```

## Usage and information

Install unifi controller in ubuntu server 20.04
```bash
ansible-playbook -i inventory/ubiquiti.yml playbooks/ubiquiti.yml -K
```
