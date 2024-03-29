# How To Install LAMP On CentOS6 

# Step One—Install Apache:
```
yum install httpd

service httpd start
```
find your Server’s IP address
```
ip addr(or ifconfig)
```
To check if Apache is installed, direct your browser to your server’s IP address (eg. http://12.34.56.789). The page should display.


# Step Two—Install MySQL:
```
yum update

yum install mysql-server

service mysqld start
```
During the installation, MySQL will ask you for your permission twice. After you say Yes to both, MySQL will install.
```
sudo mysql_secure_installation
```
Then the prompt will ask you if you want to set a root password. Go ahead and choose Y and follow the instructions.
Enter current password for root (enter for none)


# Step Three—Install PHP:
```
yum install php php-mysql

yum search php-

yum info php-fpm

yum install php-fpm
```
To set this up, first create a new file:
```
vi /var/www/html/info.php
```
Add in the following line:
```
<?php

phpinfo();

?>
```

press ESC and input:wq!,enter.
```
service httpd restart
```
Finish up by visiting your php info page (make sure you replace the example ip address with your correct one): http://12.34.56.789/info.php
