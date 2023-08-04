# Create users with this role
NOTE: For this role to work
1. add the ssh keys in /user-mgmt/files/
2. add or remove users in /inventory/group_vars/all.yaml
3. edit the inventory file
4. install mkpasswd so you can hash a password and use ansible-vault to encrypt the passwords. 
mkpass command: mkpasswd --method=sha-512

Ansible folder: 
run the add-users.yaml to start the process, here's the vault file is also specified as a variable. 

Files folder:
In the files folder you put the public ssh keys and the vault file with the name "my_vault.yaml" now the vault file looks like this

---
username_password: "sha-512"
username2_password: "sha-512"

Task folder: 
Here's the main yaml file where the magick happens


