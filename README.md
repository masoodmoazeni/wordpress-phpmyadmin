# wordpress-phpmyadmin

In this repo, I am going to put the installation steps of Wordpress, with docker or onsite phpmyadmin

We are going to install it in two ways
Connecting WordPress Docker with MySQL Docker
Connecting WordPress Docker with MySQL installed on the host

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
sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf
[mysqld]
bind-address = 0.0.0.0
sudo ufw allow 3306/tcp
sudo systemctl restart mysql
```

```
mysql -usammy -h 192.168.0.1 -p
```

```
docker inspect php | grep Gateway
```

```
docker network create -d bridge --subnet 192.168.0.0/24 --gateway 192.168.0.1 dockernet
https://stackoverflow.com/questions/44543842/how-to-connect-locally-hosted-mysql-database-with-the-docker-container
```
