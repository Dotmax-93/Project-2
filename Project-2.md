# Installing the Nginx sever

`sudo apt update`

[^3] this is always done to update our server's package index

`sudo apt install nginx`

`sudo systemctl status nginx`

![installing_nginx](./Images/installed%20nginx%20server.png)

[^9] this is done to confirm if our server is up and runnning

# Installing mySQL Database for our server

`sudo apt install mysql-server`

[^17]: This code is used to install database for webserver

`sudo mysql`

[^21]: This is used to log into mysql to set up a password

`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';`

[^25]: Used to change the password of the local root user

`sudo mysql_secure_installation`

`sudo mysql -p`

[^31]; used to test our new password

# Installing php

`sudo apt install php-fpm php-mysql`

![installing php](./Images/Screen%20Shot%202023-01-11%20at%2014.28.42.png)

# Configuring NGINX to use php processor

`sudo mkdir /var/www/projectLEMP`

[^41]: We'll create a new directory for our domain

`sudo chown -R $USER:$USER /var/www/projectLEMP`

[^45]: This command will configure the new directory with the user of the current system

`sudo nano /etc/nginx/sites-available/projectLEMP`

`sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/`

[51]:Used to activate the new directory to NGINX

`sudo nginx -t`

[^53]: Used to check for syntax error in our configuration

`sudo unlink /etc/nginx/sites-enabled/default`

`sudo systemctl reload nginx`

# Testing the new php with NGINX

`sudo nano /var/www/projectLEMP/info.php`

[^65]: DOne to set up a file for PHP

`sudo rm /var/www/your_domain/info.php`

[^69]: It is advisable to remove the file created to test for PHP as it reveals information about the PHP server

# Retreiving data from MYSQL database using PHP

`sudo mysql -p`

`CREATE DATABASE `example_database`;`

[^77]: This is used to create a new database on MYSQL

`CREATE USER 'example_user'@'%' IDENTIFIED WITH mysql_native_password BY 'password';`

`GRANT ALL ON example_database.* TO 'example_user'@'%';`

[^83]: This command is run to give the new user permission on our database

`mysql -u example_user -p`

[^87]: Used to confirm if the new database has permission

`SHOW DATABASES;`

`nano /var/www/projectLEMP/todo_list.php`

[^93]: This command is run to create a php that will connect to our database to get content

![output of php from database](./Images/Screen%20Shot%202023-01-12%20at%2013.55.48.png)















