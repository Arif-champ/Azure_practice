##Created a Resource Group
                         
                         Resource Group Name → azure-beginner-rg

                         Region → Central India
                         
                         A resource group is a microsoft service that rpovides the logical container to manage and organize the resource

##Created a Virtual-Network (V-net)

                         Resource Group → azure-beginner-rg

                         Name → azure-vnet
 
                         Region → Same as RG

                         And IP Address space we have added private IP class A

                         Address space → 10.0.0.0/16

                         Subnet name → web-subnet

                         To securely connect azure resoutrce to each other

##Created a NSG (Network security group)

                         We created NSG to control inbound and outbound traffic

                         And added some inbound rule which need to be allowed (SSH, HTTP & HTTPS)

                         Resource Group → azure-beginner-rg

                         Name → web-nsg

                         Region → Same

##Created a Virtual Machine (VM)

                         Created a Virtual Machine with details mentioned below

                         Resource Group → azure-beginner-rg
                         
                         VM Name → web-vm
                         
                         Region	→ Same
                         
                         Image → Ubuntu (free eligible)
                         
                         Size →	Standard B series (free eligible)
                         
                         Username → azureuser

                         VNet, Subnet & NSG → we created one

			 And Downloaded the pem key

And connected VM through CLI with the command "ssh -i key.pem azureuser@<Public-IP>"

##Installed web server through Command line interface (CLI) with the cmd runned below

                         sudo apt update - for package updation

                         sudo apt install apache2 -y

			 systemctl status apache2

                         cd /var/www/html

                         sudo nano index.html

                         "<h1>Azure Beginner Project</h1>
                         <p>Web server running successfully</p>"

                         ctrl+x → Y → enter (for saving the page)

			 run the following command "http://PublicIP" for the status checking

##Created a storage account

			 Move to the storage account with the same Resource group followed the below step

			 Name →	azstore12345

			 Performance →	Standard

			 Redundancy →	LRS

##Created a Blob container in the storage account we created and uploaded a image

			 Open Storage Account

			 Containers → Create

			 Name → webfiles

			 Public access → Private

##Accessed Storage from VM 

			 curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash (through this command we installed Azure CLI in silent mode and redirect to nxt command)
 			
			 az login

			 az storage blob upload (Blob - Binary Large Object)

##Created LogAnalytics

			 Created a new workspace in Log Analytics(used to collect store and analyse from the centralized storage location) 

			 Connect VM - Monitoring → Insights → Enabled

##Enabled Backup & Snapshot

			 Opened VM

			 Backup → Enable

			 Created Recovery Vault

			 And for taking snapshot

			 Disks → OS Disk → Snapshot

##Output Test

			 Stoped VM

			 Started VM

			 Check website.
