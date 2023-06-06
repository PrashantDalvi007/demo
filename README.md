############################################################################################################################
#demo
#for hosting this on ec2 machine (linux server) add below script to the user data while launching new instance.
############################################################################################################################


#!/bin/bash

#To update & install the required packages
sudo yum update -y
sudo yum install git -y
sudo yum install httpd -y

#Clonning the GitHub repo to the local directory.
sudo git clone https://github.com/PrashantDalvi007/demo.git

#Copying the index.html file to the html directory. (hosting the web-page)
sudo cp demo/index.html /var/www/html

#Starting the httpd service & enabling it to auto-start after the re-boot.
sudo systemctl start httpd
sudo systemctl enable httpd
