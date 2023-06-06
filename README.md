############################################################################################################################
#demo
#for hosting this on ec2 machine (linux server) add below script to the user data while launching new instance.
############################################################################################################################

#!/bin/bash

#To setting up the hostname. (give hostname as per your's)
sudo hostname Web-Hosting-01
sudo systemctl restart systemd-logind.service

#Updating & installing required packages.
sudo yum update -y
sudo yum install git -y
sudo yum install httpd -y

#Clonning GitHub repo to the local directory.
cd /tmp
sudo git clone https://github.com/PrashantDalvi007/demo.git

#Copying the index.html file to the html directory.
cd /tmp/demo
sudo cp index.html /var/www/html/

#Enabling& Starting the httpd service
sudo systemctl enable httpd
sudo systemctl start httpd
