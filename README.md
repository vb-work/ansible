# Ansible Automation

Ansible to run a Python script on a remote server using environment variables stored in a Vault.

## Prerequisites

- Ubuntu machine (local or remote)
- Ansible installed on the local machine

## Installation

### Step 1: Install Ansible on Ubuntu

```sh
sudo apt update
sudo apt upgrade
sudo apt install ansible ansible-core
```

### Step 2: Create SSH Key

```sh
ssh-keygen -t rsa -b 4096 -C "email@address.com" -f ~/path/path
```
Copy the public key to the remote server

### Step 2: Create an Ansible Vault

```sh
ansible-vault create vault.yml
```

add these 

```yaml
ansible_host: "HOST_IP_ADDRESS"
ansible_user: "HOST_USERANME"
ansible_become_pass: "password"
ansible_ssh_private_key_file: "/path/path"
admin_username: ""
admin_password: ""
python_command: ""
```

### Step 3: Run the play book
```sh
ansible-playbook -i inventory run_python.yml --ask-vault-pass --ask-become-pass
```
