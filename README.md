# vm-mgmt
## Requirements
- ansible-core
- commmunity
- kubernetes.core 
## To add a user to a Linux system, This role works for Debian,Ubuntu and OpenSUSE Leap. 
- Modify hosts in add-users.yaml 
- Modify the var file under inventory/group_vars/all.yaml and save it ctrl + c, example;
---
users:
  - { name: NewUserAdam }

---
in the inventory/hosts.ini
add the server and replace the server groupname "db_servers" to your liking :)  
- hash the password you want to use in the cli: openssl passwd -6 -stdin
  type in your password and copy the hash to role/add-user/vars/main.yml
  and change the "username" before the "_" with the user in all.yaml 
- run the playbook: ansible-playbook add-users.yaml -i inventory/hosts.ini -u vagrant 
# Remove user
## Do the following
- run playbook: ansible-playbook delete-users.yaml -i inventory/hosts.ini -u vagrant

# Dist-files 
## Here you can distribute the sysctl.conf file and the hosts file which can come in handy. 

## Do the following
- Modify host in dist-files-yaml 
- Replace the IP/s in inventory/hosts.ini
- Modify the hosts file at role/dist-files/files/hosts 
- Run playbook: ansible-playbook dist-files.yaml -i inventory/hosts.ini -u vagrant 

# Rolling Vm upgrade
This role can be used to patch and upgrade OpenSuse nodes, even Ubuntu (but for Ubuntu OS upgrade it ain't perfect). Best of all it works on Kubernetes nodes too :). You may want to tweak the tasks where Ansible reboot the machine, some machines are fast and some are slow. 
## Do the following

- Replace the IP/s in inventory/hosts.ini
- Set the vars to your needs roles/rolling-vm-upgrade/vars/main.yaml
- Run playbook: ansible-playbook vm-update.yaml -i inventory/hosts.ini -u vagrant 