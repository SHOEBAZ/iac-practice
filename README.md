# iac-practice
Ansible
- it's agent less and controller node wo jis pe ansible install rehta aur manage node wo jispe ansible play book hum run karte 
1 ansible server(controller node)=100 manage node
- uses tu ye use hota for provisioning, configuration,cicd like take artifact and deploy to target server, network management 

Shell scripting, python or ansible sab se configuration kaunsa use kare tu kare ansible as it is
If need to talk to api then python
-vs code me extension dalo yaml air ansible bas
Day 2
- passwordless authentication cmd: ssh Keygen
In simple words for passwordless authentication is copying public ip of ansible server to Authorize key of target servers
Controller node ko manage node se baat karne authentication lagte it can be through ssh or password
It's like you tell VM A to not ask password while connecting to other VM B 
Tu ssh key ya password first time Dene ka then we are good
There few step and command to enable the passwordless authentication on chatgpt
- Ansible inventory 
It's a file and store data for manage nodes (username and password)
Type:  inventory.ini or yaml in control node path /etc/ansible/hosts
It's heart of ansible aur extention .ini rehega
Com: ansible -i inventory -m ping all
All jagah hum user@ip dalke ek server ko ping kar sakte hai
-Adhoc command wo hai jab single command use karna hai aur jab set of command use karna hai use playbook
Syntax: ansible  (location of inventory file) -m (module u wanna right) -a (any argument wanna add) and add servername or all
Learn Adhoc command from documentation for 2-3 hours
+
Day 3
- Yaml is human readable and is a data serlization 
Text or json me thodi mushkil hoti samjhene aur bahut bada data Raha tu aur complex hota 
-  ---
name: shoeb
age: 32
Work: true
task 
- play game
- takecare family 
address
city: Aurangabad 
Street: central
Remember is yaml list is written with hyphen and dictionary is in key value pair
- Ansible playbook is set of plays and in each plays
Ye niche ke jese likhte playbook
---
- play
-play


Har play me pehla humaara rehta 'host' jaha playbook execute hongi aur phir 'remote' ye root ya Ubuntu rehta Jo excute karta aur last me 'tasks'
Playbook me main module rehte Jo adhoc command chalate aur module hi ye command execute karne
Playbook-plays- hosts,remote_user,task-modules
become: true matlab run with root user 
---
Roles : ansible role matlab playbook ke sections ko alag alag files me rakhna in a folder
Readiablity and modularity badti usse
Agar role create karne ka use below cmd
ansible-galaxy role init test
files and tamplte l me difference hai ke template me dynamic content dalte jo change kar sakte while executing 
Agar variable define nahi tu take jo default me hai wo Lelo isliye default file banate
Handlers file me wo dalte jsme task hai jo action lenge