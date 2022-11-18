# vm-cloud
Tutorial to make a Always Free VM on Oracle Cloud and Setup a RDP connection to access for all devices. <br>
4 OCPUs <br>
24GB RAM <br>
200 GB SSD <br>

Steps: <br>
1) Create a Oracle Account <br>
2) Setup a VM Instance <br>
3) Installing and configuring a VM <br>

## 1) Create a Oracle Account.
To request an Oracle Account from the Oracle Cloud website: <br>
Go to the [Oracle Cloud](https://www.oracle.com/) website. <br>
Click Sign in to Oracle Cloud Account View Accounts. <br>
Click Create an Account. <br>
Enter your email address and other details in the appropriate fields. Be sure to complete all the required fields. <br>
Click Create Account. <br>
After your account is created, you'll receive a confirmation email at the email address that you provided. <br>

Follow the instructions in the email to verify your email address. <br>

## 2) Setup a VM Instance Always Free
Login to [Oracle Cloud](https://cloud.oracle.com/) <br>
Go to Home Region. <br>

### Create a Network Infrastructure
---------------------------------
Click to hamburguer menu, Networking and Virtual Cloud Network <br>
Click to Start VCN Wizard <br>
Choose Create VCN with Internet Connectivity and click on Start VCN Wizard <br>
Set VCN Name and click to Next <br>
Review information and click to Create <br>
Waiting a Oracle Stup your Network Infrastructure <br>
All Done click View Virtual Cloud Network <br>

### Create a Compute
---------------------------------
Click to hamburguer menu, Compute and Instances <br>
Click to Create instance <br>
Set Name of Instance <br>
At Image and shape group click on Edit button <br>
Click Change image button <br>
Select Canonical Ubuntu (Always Free-eligible) <br>
Click Select image <br>
Click Change shape <br>
At Shape series select Ampere <br> 
Select VM.Standard.A1.Flex (Always Free-eligible) <br>
Select Number of OCPUs to 4 and Amount of memory (GB) automatically set to 24 <br>
Click Select shape <br>
At Add SSH keys group choose Generate a key pair for me and click to Save private key and public key <br>
At Boot volume group choose Specify a custom boot volume size <br>
Put Boot volume size (GB) to 200 <br>
Click on Create <br>

## 3) Installing and configuring a VM
Click to hamburguer menu, Compute and Instance <br>
Click to resource name <br>
Copy Public IP address and Username <br>

### CONNECT A INSTANCE WITH SSH
---------------------------------
Open the terminal and connect to instance. <br>
sh ``` ssh -i privite-key download path username-copied@public-ip-copied``` for example: sh ``` ssh -i /tmp/ssh-key-2022-11-18.key ubuntu@1.1.1.1 ```

### THE FIVE CONFIGURATION COMMANDS
---------------------------------
1. sudo apt update && sudo apt upgrade -y
2. sudo apt-get install ubuntu-desktop xrdp stacer -y
3. sudo cp /etc/iptables/rules.v4 /etc/iptables/rules.v4.bak && sudo truncate -s 0 /etc/iptables/rules.v4
4. sudo rm /usr/share/polkit-1/actions/org.freedesktop.color.policy
5. sudo passwd ubuntu      Example password : t6y1x9n6h7j1  so long,complex and not in a dictionary <br>
then <br>
sudo reboot

### CONNECT A INSTANCE WITH RDP
---------------------------------
Click to hamburguer menu, Compute and Instance <br>
Click to resource name <br>
Click to Subnet <br>
At Security Lists group, click on Default Security List <br>
At Ingress Rules click to Add Ingress Rules <br>
Set Source CIDR to 0.0.0.0/0 <br>
Set Destination Port Range to 3389 <br>
Click Add Ingress Rules <br>
Open to RDP client <br>
Digit a Public IP for Instance <br>
Click to Connect <br>
Put Username and Password <br>

Have Fun!
