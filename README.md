# vm-cloud
Tutorial to make a Always Free VM on Oracle Cloud and Setup a RDP connection to access for all devices.

Steps:
1) Create a Oracle Account
2) Setup a VM Instance
3) Installing and configuring a VM

## 1) Create a Oracle Account.
To request an Oracle Account from the Oracle Cloud website:
Go to the [Oracle Cloud](https://www.oracle.com/) website.
Click Sign in to Oracle Cloud Account View Accounts.
Click Create an Account.
Enter your email address and other details in the appropriate fields. Be sure to complete all the required fields.
Click Create Account.
After your account is created, you'll receive a confirmation email at the email address that you provided.

Follow the instructions in the email to verify your email address.

## 2) Setup a VM Instance Always Free
Login to [Oracle Cloud](https://cloud.oracle.com/)
Go to Home Region.

### Create a Network Infrastructure
Click to hamburguer menu, Networking and Virtual Cloud Network
Click to Start VCN Wizard
Choose Create VCN with Internet Connectivity and click on Start VCN Wizard
Set VCN Name and click to Next
Review information and click to Create
Waiting a Oracle Stup your Network Infrastructure
All Done click View Virtual Cloud Network

### Create a Compute
Click to hamburguer menu, Compute and Instances
Click to Create instance
Set Name of Instance
At Image and shape group click on Edit button
Click Change image button
Select Canonical Ubuntu (Always Free-eligible)
Click Select image
Click Change shape
At Shape series select Ampere
Select VM.Standard.A1.Flex (Always Free-eligible)
Select Number of OCPUs to 4 and Amount of memory (GB) automatically set to 24
Click Select shape
At Add SSH keys group choose Generate a key pair for me and click to Save private key and public key
At Boot volume group choose Specify a custom boot volume size
Put Boot volume size (GB) to 50
Click on Create

## 3) Installing and configuring a VM
Click to hamburguer menu, Compute and Instance
Click to resource name
Copy Public IP address and Username
Open the terminal and connect to instance.
sh ``` ssh -i privite-key download path username-copied@public-ip-copied``` for example: ssh -i /tmp/ssh-key-2022-11-18.key ubuntu@1.1.1.1

