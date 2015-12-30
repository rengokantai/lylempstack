#### lylempstack
- LEMP Stack: PHP
```
yum install php
yum install php-fpm
```
change path:
```
cd /etc/php-fpm.d
vim www.conf
```
Edit:
```
listen = /var/run/php-fpm/www.sock
```
```
chown nginx:nginx /var/run/php-fpm/www.sock
chkconfig php-fpm on
service php-fpm start
```
- LEMP Stack: MariaDB
step remi-release first
```
wget ....rpm
rpm -Uvh remi-release-6.rpm
yum update
yum --enablerepo=remi-test --disablerepo=remi install compat-mysql55
cd /etc/yum.repos.d
vi maria.repo
```
Add
```
[meriadb]
name=MariaDB
baseurl=
gpgkey=
gpgcheck=1
```
Then
```
yum upgrade
yum install MadiaDB-devel MariaDB-client MariaDB-server perl-DB-MySQL
service mysql start
mysql_secure_installation
```

