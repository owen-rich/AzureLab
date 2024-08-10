# AzureLab: Create a Virtual Machine and Deploy a Web Server

## Course Objectives

By the end of this course, you will understand how the basic networking architecture in Azure works by creating Virtual Networks, subnets, security groups, and Virtual Machines. You will also learn how to use Bastion to connect to a Linux machine using SSH without exposing an external IP. Additionally, you'll learn how to expose a public IP and an HTTPS port to access your web server.

The following are the eight learning objectives with description of action taken:

1. **Create a Resource Group**  
   Created a Resource group that contains all resources related to my virtual machine.

2. **Create a Virtual Network and a subnet**  
   Created a virtual network and a subnet for my virtual machine.

3. **Protect a subnet using a Network Security Group**  
   Created a Network Security Group to protect the internal subnet of my Virtual Machine.

4. **Deploy Bastion to connect to a Virtual Machine**  
   Created a bastion deployment to connect to the Virtual Machine using SSH.

5. **Create an Ubuntu Server Virtual Machine**  
   Created a Virtual Machine, selected size, and created an SSH key pair.

6. **Install Nextcloud by connecting via SSH using Bastion**  
   - Connected to Ubuntu using Bastion via SSH, then installed NextCloud Server.
   - Connected via SSH with locally saved ssh key.
   - Installed NextCloud: `sudo snap install nextcloud`.
   - Created Admin account: `sudo nextcloud.manual-install [UN:admin] [PW]`.
   - Generated key and self-signed certificate: `sudo nextcloud.enable-https self-signed`.

7. **Publish an IP**  
   - Associated a Public IP to the Nextcloud Server.
   - Tested by typing `https://[Public IP]` (Did not work).
   - Created an Inbound Rule for my IP address to connect to Virtual Machine Private IP via HTTPS port.
   - Tested again and successfully got a response from the NextCloud Server.

8. **Create a DNS label**  
   - Created DNS label.
   - Connected to the server using Bastion via SSH.
   - Configured trusted domains: `sudo nextcloud.occ config:system:set trusted_domains 1 –value=owennextcloud.eastus.cloudapp.azure.com`.
   - Connected via browser typing `https://[DNS address]`.
   - Logged in to Nextcloud with Admin credentials.


**Note:**  
- **ALWAYS stop the VM when not in use to avoid charges.**  
- **When completely done, delete Bastion from the Resource Group to avoid charges.**
