# vm-mgmt
## Requirements
- ansible-core
- commmunity
- kubernetes.core 
## To add a user to a Linux system, This role works for Debian,Ubuntu and OpenSUSE Leap. 
- Modify host in add-users.yaml 
- Replace the IP/s in inventory/hosts.ini
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
- run the playbook: ansible-playbook -i inventory/hosts.ini add-users.yaml -u "usernameONremoteSERVER" 
## Remove user
## Do the following
- run playbook: ansible-playbook -i inventory/hosts.ini delete-users.yaml -u "usernameONremoteSERVER"

## Dist-files 
- Here you can distribute the sysctl.conf file and the hosts file which can come in handy. 

## Do the following
- Modify host in dist-files-yaml 
- Replace the IP/s in inventory/hosts.ini
- Modify the hosts file at role/dist-files/files/hosts 
- Run playbook: ansible-playbook 

