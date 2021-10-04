# Ubiquiti Unifi Controller for Ubuntu Server 20.04

Ansible playbook to install the latest ubiquiti unifi controller for ubuntu serve 20.04

## Initial settings

Define the variables on `inventory.yml` as per your needs

Change variables on `inventory.yml`
```bash
ansible_host: '<hostname>'
username: '<username>'
```

Ansible connection can be set as `local` or `ssh`
```bash
ansible_connection: '<connection>'
```

SSH private key file needs to be defined when using `ssh` connection
```bash
ansible_ssh_private_key_file: /path/to/your/ssh-key
```

Install `ansible` in your system
```bash
sudo apt -y install ansible
```
> ansible version 2.9.6

## Setup ssh config

Change ssh-key permissions
```bash
chmod 400 ~/.ssh/<ssh-key>
```

Configure ssh config file
```bash
touch ~/.ssh/config
chmod 600 ~/.ssh/config
```

SSH config file sample
```bash
Host alias
  HostName <ip-address>
  User <username>
  Port 22
  IdentityFile ~/.ssh/<ssh-key>
```

## Usage and information

Install only office on ubuntu server 20.04, add **flag** `-K` in case the user has a password
```bash
ansible-playbook -i inventory.yml ubiquiti.yml
```
> Access unifi-controller [localhost:8443](https://localhost:8443) or `https://hostname:8443`

## License

[MIT license](http://opensource.org/licenses/MIT).
