## vm-mgmt
# Requirements
- ansible-core
- commmunity
- kubernetes.core 
# To add a user to a Linux system, This role works for Debian,Ubuntu and OpenSUSE Leap. 
First modify the var file under inventory/group_vars/all.yaml and save it ctrl + c, example;
---
users:
  - { name: NewUserAdam }

---
in the inventory/hosts.ini
add the server and replace the server groupname "db_servers" to your liking :)  

# Ansible




