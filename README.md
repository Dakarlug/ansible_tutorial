#Ansible
##Ansible c’est quoi?
Ansible est un « Configuration Management Tool »comme Chef, Puppet. Il permet entre autre de :
* éviter les tâches répétitives* automatiser le déploiment de scripts* déploier un parc de machines en un rien de temps
Ansible, c'est des commandes exécutées sur une ou plusieurs machine(s) locale(s) ou distante(s), via SSH.
##￼Installation
###Sources :
```
$ git clone git://github.com/ansible/ansible.git 
$ cd ./ansible$ source ./hacking/env-setup
```
###Python et gestionnaires de packages linux
[http://docs.ansible.com/intro_installation.html][1]


##￼Configurations

###Les SSH keys:
ssh-copy-id hosts_ssh_path
###Inventory files
* default : /etc/ansible/hosts* custom : option -i path_inventory_file
######Contenu du fichier Inventory :mail.example.com 
[webservers] 
foo.example.com 
bar.example.com
[test_servers]

192.168.33.10 ansible_ssh_user=root
jumper ansible_ssh_port=5555 ansible_ssh_host=192.168.1.50
##Les commandes Ad-HocsUne commande Ad-Hoc est une commande qu’on exécute à la volée sans la sauvegarder.
```$ ansible va_host -m ping -i hosts$ ansible va_host -m copy -a "src=./hosts dest=/tmp/ hosts" –i hosts
```##￼Les modules
Ansible dispose de plusieurs librairies appelé modules. Chaque module est utilisé pour un besoin spécifique. 
Quelques modules :ping,command,copy,apt,yum .....
Exemple :
```$ ansible va_hosts -m yum -a "name=acme state=installed"
```
##￼Le playbook
Un playbook est un fichier YAML
Un playbook contient les “tasks” à effectuer.
###Les hosts et les users: 


[1]:http://docs.ansible.com/intro_installation.html