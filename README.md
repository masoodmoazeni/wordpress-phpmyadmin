# wordpress-phpmyadmin

```
apt-get update
apt install git unzip ufw docker.io docker-compose
sudo ufw status
sudo ufw enable
```

# innstall phpnyadmin
```
sudo apt install apache2
sudo service apache2 start
sudo apt install php libapache2-mod-php
sudo apt install mysql-server
sudo mysql -u root
USE mysql;
UPDATE user SET plugin='mysql_native_password' WHERE User='root';
SELECT user,authentication_string,plugin,host FROM mysql.user;
ALTER USER 'root'@'localhost' IDENTIFIED WITH caching_sha2_password BY 'PaSS22@@W#rd';
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PaSS22@@W#rd';
CREATE USER 'sammy'@'%' IDENTIFIED WITH caching_sha2_password BY 'PaSS22@@W#rd';
ALTER USER 'sammy'@'%' IDENTIFIED WITH mysql_native_password BY 'PaSS22@@W#rd';
GRANT ALL PRIVILEGES ON *.* TO 'sammy'@'%' WITH GRANT OPTION;
SELECT host, user FROM mysql.user;
FLUSH PRIVILEGES;
exit
sudo service mysql restart
sudo apt install phpmyadmin
yes - - 1.apache
sudo service apache2 restart
```

```
mysql -usammy -h 192.168.0.1 -p
```
