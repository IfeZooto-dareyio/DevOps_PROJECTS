# WEB STACK IMPLEMENTATION (LAMP STACK) IN AWS

## LAMP STACK IMPLEMENTATION (Linux, Apache, MySQL and PHP)

## PREREQUISITES

- Cloud Service Provider - AWS, Azure, GCP etc.
- Launch a Linux Instance (Ubuntu preferably).
- Priot knowlwdge on how to SSH into a virtual host.

## STEP 1 - INSTALLING APACHE AND UPDATING THE FIREWALL

We install Apache using using Ubuntu's package manager.

`apt`

Update a list of packages in package manager.

`sudo apt update`

Run Apache2 package installation.

`sudo apt install apache2`

![Alt text](images/3.1.png)

![Alt text](images/3.2.png)

After running the above processes, we need to verify that apache2 is running as a service in our OS. To do that we use this command;

`sudo systemctl status apache2`

![Alt text](images/3.3.png)

Our server is running and we can access it locally and from the internet. Now we need to check how we can access it locally in our ubuntu shell. To do that we use the command;

`curl http://localhost:80` or `curl http://127.0.0.1:80`

![Alt text](images/3.4.png)

Now, we have to test how our Apache HTTP server can respond to requests from the internet, to do so we go to any browser and use the below command; 

`http://<Public-IP-Address>:80`

![Alt text](images/3.5.png)

To get the ip address other than to check it on our AWS Web console, the command below is used;

`curl -s http://169.254.169.254/latest/meta-data/public-ipv4`

![Alt text](images/3.6.png)

## STEP 2 - INSTALLING MySQL [DATABASE MANAGEMENT SYSTEM]

We install MySQL using using Ubuntu's package manager.

`sudo apt install mysql-server`

![Alt text](images/3.7.png)

After installation, we log in to the MySQL console by typing;

`sudo mysql`

![Alt text](images/3.8.png)

It is also recommended to run a security script that comes pre-installed with the MySQL. Before running the script, we have to set a password for the root user, using mysql_native_password as default authentication method. To do that the command below is used;

`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';`

![Alt text](images/3.9.png)

After running the security script, we'll have to start the interactive script by running the command below;

`sudo mysql_secure_installation`

![Alt text](images/3.10.png)

When finished with the script process, the next step is to test if we're able to log in to the MySQL console by typing;

`sudo mysql -p`

![Alt text](images/3.11.png)

Then we exit the console by typing;

`mysql> exit`

![Alt text](images/3.12.png)

## STEP 3 - INSTALLING PHP

To install php and other packages together, we use the command below;

`sudo apt install php libapache2-mod-php php-mysql`

![Alt text](images/3.13.png)

Once the installation is finished, we gave to check the PHP version by using the command below;

`php -v`

![Alt text](images/3.14.png)

## STEP 4 - CREATING A VIRTUAL HOST FOR THE WEBSITE USING APACHE

We'll set up a domain called **projectlamp** using the command below;

`sudo mkdir /var/www/projectlamp`

![Alt text](images/3.15.png)

Next we assign ownership of the directory user using the command below;

`sudo chown -R $USER:$USER /var/www/projectlamp`

![Alt text](images/3.16.png)

Then we create and open a new configuration file in Apache's site-available directory using the command below;

`sudo vi /etc/apache2/sites-available/projectlamp.conf`

And paste the following command in the file;

<VirtualHost *:80>

    ServerName projectlamp

    ServerAlias <www.projectlamp>

    ServerAdmin webmaster@localhost

    DocumentRoot /var/www/projectlamp

    ErrorLog ${APACHE_LOG_DIR}/error.log

    CustomLog ${APACHE_LOG_DIR}/access.log combined

</VirtualHost>

![Alt text](images/3.17.png)

Then we use the ls command to show the new file in the present directory;

`$ sudo ls /etc/apache2/sites-available`

![Alt text](images/3.18.png)

Now, we enable the new virtual host using the command below;

`sudo a2ensite projectlamp`

![Alt text](images/3.19.png)

Next, we have to disable apache's default website using the command below;

`sudo a2dissite 000-default`

![Alt text](images/3.20.png)

To make sure our configuration file doesn't contain syntax errors, we use the command below;

`sudo apache2ctl configtest`

![Alt text](images/3.21.png)

Finally, we reload apache so the changes can take effect using the command below;

`sudo systemctl reload apache2`

![Alt text](images/3.22.png)

After that, we go to our browser to confirm if the website is now active.

![Alt text](images/3.23.png)

The image above indicates that the website is active.

## STEP 5 - ENABLE PHP ON THE WEBSITE

To do this we have to change the default behaviour by editing the dir.conf file using the command below;

`sudo vim /etc/apache2/mods-enabled/dir.conf`

And changing the values from this;

![Alt text](images/3.24.png)

To this;

![Alt text](images/3.25.png)

After saving and closing the file, we'll have to reload apache so the changes can take effect by using the command below;

`sudo systemctl reload apache2`

![Alt text](images/3.26.png)

Finally, we'll create a php script to test that it is correctly installed and configured on our server using the command below;

`vim /var/www/projectlamp/index.php`

And pasting the following text in it;

**<?php

phpinfo();**

![Alt text](images/3.27.png)

When finished, we go to our browser and refresh the page and a page similar to this will be displayed;

![Alt text](images/3.28.png)

Last but not least, after checking the relevant information, it is best to remove the file created cause it contains sensitive information about our PHP environment and Ubuntu server. To do so, we use the below command;

`sudo rm /var/www/projectlamp/index.php`

![Alt text](images/3.29.png)