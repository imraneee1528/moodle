# How to install Apache2 on Ubuntu Linux
 
 sudo apt update 
 sudo apt-get install apache2
 sudo systemctl stop apache2.service
 sudo systemctl start apache2.service
 systemctl enable apache2.service
 
 # How to Install Mysqldb 
 
 sudo apt-get install mysql-server-5.7 
 
 # Mysql password Set
 
 sudo mysql -u root –p
 USE mysql;
 SET PASSWORD FOR 'root'@'localhost' = PASSWORD('B@ngladesh'); 
 sudo systemctl enable mysql
 
 #How to Install PHP 
 
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:ondrej/php
sudo apt install php7.4-fpm php7.4-common php7.4-mysql php7.4-gmp php7.4-curl php7.4-intl php7.4-mbstring php7.4-xmlrpc php7.4-gd php7.4-xml php7.4-cli php7.4-zip

# how to configure 

sudo nano /etc/php/7.4/fpm/php.ini


# Change to look like this 
files_upload = On
allow_url_fopen =On
short_open_tag = On
memory_limit = 256M
post_max_size = 100M  
cgi.fix_pathinfo = 0
upload_max_filesize = 100M
max_execution_time = 360
date.timezone = Asia/Dhaka

# How to create moodle database 

sudo mysql -u root -p
CREATE DATABASE moodle;
GRANT ALL ON moodle.* TO 'root'@'localhost' WITH GRANT OPTION;

FLUSH PRIVILEGES;
EXIT;

# Source Code 

sudo apt install git curl
cd /var/www/html
sudo git clone -b MOODLE_36_STABLE git://git.moodle.org/moodle.git example.com

# or your source deployed in below location

sudo mv moodle /var/www/html/

sudo mkdir -p /var/www/moodledata
sudo chown -R www-data:www-data /var/www/
sudo chmod -R 755 /var/www/

# Restart Apache Service 

sudo service apache2 reload
sudo service apache2 restart

#Configure file change 

cd /var/www/html/moodle
sudo nano config.php
sudo service apache2 restart





