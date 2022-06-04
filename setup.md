# Slovakia Universal Setup

This tutorial will show you how to setup Slovakia with the aim of connecting to it and syncing attacks.
Commands with `$bash` in front of it means you need to run it in your ssh terminal running bash.
Commands with `$sql` in front of it means you need to run it in mysql which can be access by typing $bash `sudo mysql`.

Things to note. This tutorial is secure by default. The options here will make sure your server is setup correctly and securely.
All sensitive fields are randomly generated just for you, the mysql login is setup so secure by default even by having the password you still can not login remotely.
Your config.json has already been setup for you automatically with the database credentials.

Compiled: `November 20, 2021`
Version: `v1.98.3`
Customer: `haribo`

# Step One - SQL Database

Make sure to update.
Debain based distros (ubuntu): `sudo apt update && sudo apt upgrade`

### Install MYSQL for Debian/Ubuntu

$bash

```
sudo apt install mysql-server
```

$bash

```
sudo mysql_secure_installation
```

> Create a new secure root password and say yes to all the future questions.

### Install MYSQL for RHEL/RedHat/CentOs 7

**THIS IS FOR CENTOS ONLY!** **IF YOU ARE ON UBUNTU OR DEBIAN DO NOT USE THIS!**

$bash

```
sudo yum localinstall https://dev.mysql.com/get/mysql80-community-release-el7-1.noarch.rpm
```

$bash

```
sudo yum install mysql-community-server
```

$bash

```
sudo systemctl enable mysqld
```

$bash

```
sudo systemctl start mysqld
```

$bash

```
sudo grep 'temporary password' /var/log/mysqld.log
```

> Get the temp mysql root password by running the command above

$bash

```
sudo mysql_secure_installation
```

> Create a new secure root password and say yes to all the future questions.

### Open MYSQL

$bash `sudo mysql`

> If this doesn't work and tells you "permission denied" try:

$bash `sudo mysql -p`

> This will prompt you to input the root password for mysql which you just set in the setup of mysql_secure_installation

# Configuring the SQL server

The last step should have now left you in MYSQL's interpreter.

$sql

```
CREATE DATABASE `slov-2090462268`;
```

> Create the database, the database name can be anything but must be set the same in the config.json file.

$sql `CREATE USER 'slovidb-44097'@'localhost' IDENTIFIED BY 'rEF8mew8jKIvEM9IyO3ZZg_SLOV';`

$sql `GRANT ALL PRIVILEGES ON * . * TO 'slovidb-44097'@'localhost';`

$sql`FLUSH PRIVILEGES;`

> Create the database user. This will be used by Slovakia to access the database. Do not use root!
> Please note this password has automatically been put into your config file and is uniquely generated just for you.

# Step Two Upload & Run

In the ./slovakia/ folder you will find a variety of files and a folder. Upload all of them onto the server. $bash `chmod +x *.sh` then make sure you have screen installed.

### Installing screen Debian/Ubuntu

$bash `sudo apt install screen`

### Installing screen for RHEL/RedHat/CentOs

$bash `yum install screen`

## Give perms to listen on privileged ports (NOT REQUIRED BY DEFAULT)

$bash `sudo setcap 'cap_net_bind_service=+ep' ./slovakia`

## Run

$bash `./start-ubuntu-20.sh`

> Run the script correlating to your os

## OR

$bash `screen -L ./slovakia`

# Step Three Login

When you first run Slovakia it create the database tables and a user with randomly generated credentials.
The username is `root`. The password will be displayed on the terminal on first boot but only on first boot, any time after it will never show again.

The username and password will also be added to a text file called: "default-login-information.txt".

Enjoy Slovakia, haribo.
