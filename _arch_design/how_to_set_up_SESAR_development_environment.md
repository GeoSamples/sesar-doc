---
name: how_to_set_up_SESAR_development_environment
title: How to Set Up SESAR Development Environment
date: 01/12/2020
layout: default
---

This document describes how to set up SESAR on a developer's local system (Ubuntu 11.10 to 14.01 LTE) for development purpose.

## 1.SESAR requires PHP5 installed. Several extensions are also required.
* sudo yum install apt-get
* sudo apt-get install php5
* sudo apt-get install php-pear
* sudo apt-get install php5-pgsql
* sudo pear install MDB2
* sudo pear install pear/MDB2#MySQL
* sudo pear install MDB2_Driver_pgsql
* sudo pear install Mail
* sudo apt-get install imagemagick libmagickwand-dev
* sudo apt-get install php5-imagick
* sudo apt-get install php5-gd
* sudo apt-get install git

## 2. Install Apache2 on developer's local machine.

* sudo apt-get install apache2
* sudo apt-get install libapache2-mod-php5
* sudo /etc/init.d/apache2 restart

## 3. If the system clock is not update right, do the following.

* usermod \-a \-G apache nobody
* vi /etc/cron.daily/ntpdate

```
  #!/bin/sh
  ntpdate ntp.ubuntu.com
```
* chmod 755 /etc/cron.daily/ntpdate

* yum install ntp

## 4. configure PHP.ini. Set the timezone as following.

```
date.timezone = "America/New_York"
```

## 5. Check out SESAR source code at $HOME directory.

* -svn co- -[http://svn.geoinfogeochem.org/svn/prod/sesarv3/trunk/]- -sesar3-
* At your home directory, 
  `git clone https://github.com/iedadata/sesar.git`
 The source code tree will be at $HOME/sesar .

* cd sesar
* git pull origin development
* git checkout development

****Please do not use 'master' branch for development . It is only used for production releases.****

If you failed to checkout sesar from Github, Please follow the link [https://help.github.com/articles/generating-ssh-keys/] to set up your sshkeys. That maybe the reason you failed to checkout.

## 6. Set up 'uploads' directory.

* create the following directories at the same level of 'sesar' dir.
** uploads
** uploads/batch
** uploads/batch_archive
** uploads/batch_validated
** uploads/qr
** uploads/img
* chown www-data:www-data uploads (www-data is user of Apache, sometimes the user name is 'apache', replaced with 'apache')

## 7. Configure Apache2.

```
$HOME=/home/song
```

Edit /etc/apache2/http.conf . Add the following block to the file http.conf

```
<VirtualHost \*:80>
  DocumentRoot "/home/song/sesar"
  Servername 127.0.1.1
    <Directory /home/song/sesar>
      Allow from all
      Options \+Includes \+Indexes \+FollowSymLinks
      AllowOverride all
    </Directory>
   Alias "/uploads"   "/home/song/uploads"
  <Directory "/home/song/uploads">
             Options None
             AllowOverride None
             Order allow,deny
            Allow from all
  </Directory>

ErrorLog  /var/log/apache2/sesar_error.log
LogFormat "%h %l %u %t \"%r\" %>s %b" common

</VirtualHost>
```  

* Newer versions of Ubuntu use sites-available/sites-enabled etc. to set up Apache virtual host. Please refer to Ubuntu documentation.
```
  Modify /etc/apache2/sites-available/000-default.conf.
  Modify DocumentRoot /etc/apach2/apahce2.conf
  a2ensite
```
## 7. Configure the database and GFZ connection.

```
At $HOME/sesar/conf directory, create the following directories.    
       conf/auth    
       conf/dbinfo
       Please contact Lulin Song to set up the following files.
       conf/auth/Creds.php
       conf/dbinfo/DBCreds.php
       config.php
```
****Creds.php and DBCreds.php should never check into Github repository.****

## 8. Start or restart apache2 server.

* service apache2 start&nbsp; or
* service apache2 restart

## 9. Launch VPN

* openvpn \--config client.ovpn

Read [here|http://wiki.iedadata.org/pages/viewpage.action?pageId=983289] about how to set up VPN.


## 10. Launch Firefox from ubuntu then go to the following URL where SESAR is running.

[http://localhost/|http://localhost/index.php]

It will go to GeoPass login page to ask user login then redirect to MySesar. The user should create a GeoPass account before continuing.


