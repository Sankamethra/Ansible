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
   In roles create a yml files in tasks directory 
   =>In main.yml copy the plybook file
   =>install.yml- keep the name 
   =>config.yml- copy the details of the html files details
   =>service.yml
   
   
   
TASK 1: CREATE A SH FILE OF DATE AND TIME AND EXECUTE IT IN YML FILE 

Create a sh files
=>in sh file  sample.sh==> date +"Current date and Time: %d %T"
              new.sh==> "Hello_World"

Create a play in playbook yml file:
In yml file, create a builtin module as ansible.builtin.shell
=>- name: Executing the current date and time
  hosts: localhost
  tasks:
    - name: Run date and time
      ansible.builtin.shell:
        ./sample.sh;
        ./new.sh
      register: result

    - name: debug
      ansible.builtin.debug:
        msg: "{{result.stdout_lines}}"

TASK 2: COPY the contents of the sh files and store it in text file using ansible

Create two text files
In playbook, create a plays like:
  - name: Save in text file
      copy: 
        content: "{{result.stdout_lines[0]}}"
        dest: "./file.txt"

    - name: Save Hello World in Text file 
      copy:
        content: "{{result.stdout_lines[1]}}"
        dest: "./hello.txt"

TASK 3: Merge the contents in the two text file and store it in the new file
set_fact is a module used to set or update the variables.
 - name: Merge Two text files
      set_fact:
         combined_content: "{{result.stdout_lines[0]}} {{result.stdout_lines[1]}}"

    - name: Save the merged files in new file
      copy:
        content: "{{combined_content}}"
        dest: "./mergedfile.txt"

LOOPS: 
-> Generating Random numbers in loop
-> Generating through variables
-> Add the names and print the debug and store that in new file
-> Get to know about nested loops and debugging that
-> Looping over a directory
-> printing the file name and path and content of the file through loops



 

 
     
     
   
   
