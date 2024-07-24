HOW TO USED ANSIBLE TO INSTALL DOCKER FROM MY ANSIBLE CONTROL NODE ONTO AN UBUNTU REMOTE SERVER.


Prerequisites:

1.	One Ansible control node: an Ubuntu 22.04 machine with Ansible installed and configured to connect to your Ansible hosts using SSH keys.

2.	A remote server with Ubuntu 20.04: no prior setup is required on this server, but you must have SSH access to this server from the Ansible control node mentioned above. This server will become an Ansible host remote server, which is targeted for automated provisioning by the Ansible control node.

Files i created in order to be able to execute this task as a role.

1.	AnsibleKey1.pem 
2.	Ansible.cfg 
3.	Config 
4.	Docker 
5.	Inventory 
6.	Playbook.yaml

Step 1:
In this AnsibleKey1.pem file it contains the keypair for my Ansible control node Ubuntu Server that will help me to SSH into it, to ping or create a connection to the remote ubuntu server.

Step 2:
In the Ansible.cfg file it contains :
•  Created a new sudo user and set up passwordless sudo.
•  Disable password-based authentication for the root user and other configurations

Step 3:
In the config file, I have the configuration to Installing aptitude, which is preferred by Ansible as an alternative to the apt package manager and Installing required system packages.

Step 4:
Adding Docker Installation Tasks to be recogninse in my Playbook to execute;
This step will install the latest version of Docker from the official repository. The Docker GPG key is added to verify the download, the official repository is added as a new package source, and Docker will be installed. Additionally, the Docker module for Python will be installed as well.

Step 5:
In this inventory file, it contains the list of all the host and children host with their IP address, as well as their keypair, that will allow ping or connection from the Control Host Server.

Step 6:
The playbook.yml file is where all my tasks are defined. A task is the smallest unit of action you can automate using an Ansible playbook.










