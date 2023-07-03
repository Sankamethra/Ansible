# Ansible

A IT Automation Tool.
Used to configure, deploy multiple servers at a time using playbooks
Uses Open SSH protocol for connecting servers

1) Installation:
     If it a new system, first install pip
          ==>python3 get-pip.py --user
   Now, Install Ansible:
          ==>python3 -m pip install --user ansible-core==2.13.7
2) Connecting servers through ssh for vms:
     Connect the multiple servers from the Hosts by using the ip address
          ==> ssh localhost/ipaddress
     Using keys to make more secure connections:
        To generate keys:
         ==>ls -ls .ssh
              It shows all the keys that we created. To create a new key or default key, use the command
         ==> ssh-keygen -t ed25519 -C "default"
              (public and private keys will be created)
         Add the key to the server
         ==>ssh-copy-id -i ~/.ssh/id_ed25519.pub localhost

3) Setting Git Repository commands:
    ==>git clone ""
    ==>cd ____
    ==>git add .
    ==>git commit -m "first commit"
    ==>git push origin master

4)Creatory a Inventory File:
    In this type the Ip address of the servers
    
     
   
   
