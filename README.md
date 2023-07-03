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
    To establish a connection between servers
       ==>ansible-inventory -i inventory --list
5) Create a playbooks:
        create a playbook.yml file and typle the basic yaml language code
        - name: My first play
          hosts: localhost
          tasks:
             - debug:
                 msg: "Hello World"


6)Ansible Roles:
    Consistes of many playbooks. Group many tasks together and do the automation.
    We can resue and modify the files.
    ansible-galaxy to create a roles
       ==> ansible-galaxy init ansible/roles/apache --offline
    8 files will be created and each of them contains main.yml files
      1) default: default variables for the roles, in yml file we can declare the variables.
      2)files: contains the files which needs to be deployed
      3)handles: contains handler sections which can be used within the roles or outside the roles
      4)meta: it defines the info about roles
      5)tasks: list of tasks to be executed by roles
      6)templates: it contains the templates that is to be deployed 
      7)tests: test directories
      8) vars: for declaring the variables 

How to convert the playbook into ansible roles: 
      =>
              
    
     
   
   
