# Bootcamp-App-Ansible

---

### Ansible Architecture Overview:

![tree](https://user-images.githubusercontent.com/90255849/139579677-2b136369-7af0-4170-b479-f5df58121ada.png)

---

### Important Note 1:

In this repository there are neither the vault.yml for the production nor the vault.yml for staging.  

Those files will be provided privately.

---

## The Following steps are mendatory:

### Install Ansible

In order to install Ansible on a linux machine, **enter** the following commands (execute one command at a time):
```
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
```

### Install Nodejs

In order to install Nodejs on a linux machine, **enter** the following commands (execute one command at a time):
```
sudo apt-get install curl
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt-get install nodejs
```

In order to check the version (must be 14 or higher) **enter**:

```node --version```

### Install community.general.ipify_facts

In order to install community.general.ipify_facts on a linux machine, **enter** the following command:

```
ansible-galaxy collection install community.general
```

### Enable ssh communication between controller/agent and target machines:

1. In order to enable such connection on a linux machine, **generate** an ssh key by executing:

   ```
   ssh-keygen
   ```
   After doing so, keep the default settings by pressing "Enter" on your keyboard as many times as required.
   
2. **Copy** the key to the target machines by executing:

   ```
   ssh-copy-id -i (username)@(node machine ip)
   ```   
---


## Running The Playbook

In order to run the ansible playbook execute the following command:

1. For staging:
   ```
   ansible-playbook -i ./environments/staging/inventory playbook.yml
   ```
   
2. For production:
   ```
   ansible-playbook -i ./environments/production/inventory playbook.yml
   ```













