# Slovakia

License fingerprint: 7f9f884555690a67f38f79879b1184a0dcbcdfd6767e5336d5341060c6e1dad5
Enjoy your Slovakia, haribo



# Sales pitch

Slovakia CNC is a custom CNC written in Go, for maximum performance. Slovakia is the most advanced and **secure** CNC on the market, no doubt about it.
Supporting **both Mirai and Qbot clients** makes Slovakia **compatible with almost anything** you are to come across. Or just ask me to **implement a custom protocol for you**.
Over **41,000** lines of code and a polymorphic command handler which is all **access over SSH**, this ensures both security and speed. Have a true terminal! Unlike Mirai or Qbot, Slovakia emulates a real terminal. Access command history with the arrow keys, navigate forwards and backwards in your current command to edit it (_your traditional Mirai does not support this_), use **tab complete!** for both commands and its arguments! Never have to type a full word again. Windows resizing is also supported, showing you more information if you can fit it. **Slovakia is the most secure and feature rich CNC out!**

# Performance

- Slovakia's polymorphic design philosophy allows for high performance and easy maintainability.
- Fan out design minimising running go routines
- Delta title update reduces bandwidth consumption
- Ultra fast concurrent handling
- Minimal memory allocation
- Prefers stack allocation over the _slow_ heap
- Benchmark
  - 10 Admin user - CPU `0.00%`
  - 40 Admin users - CPU `0.00%`
  - As you can see, its **extremely** optimised!

# Security

- Slovakia has been built entirely by myself, I can vouch that the code is secure and uncrushable (unlike Mirai's 4 vectors)
- The Mirai defacer vuln I found, yeah good luck trying it on Slovakia
- Native support for DoxyProxy to obtain the true client's IP through a reverse proxy
- Extreme logging! Logs; commands, attacks, logins, slaves, user add/remove
  - View logs in the CNC if your an admin
- Hierarchy role based authentication
  - Mods basically resellers or lower rights version of an admin
  - Admins all powerful godly overlords
- **Live update!** You change a user's account details the change will happen in real time with no need to reload or relogin!
- Manage sessions
  - View
  - Kick
  - Message
  - View IPs
  - Kick all from one user
  - Limit sessions per user
  - DoxyProxy limit per IP
- Disable commands you don't want via the config file
- Ban users
- Regex blacklist
- Permission based auto generated help page and tab complete
  - Only see the commands you can run
- Mfa with a QR CODE IN THE TERMINAL!
- Login with SSH keys!
- SHA256 password hashing or SHA256 + salt
  - Comes with a Mirai migration tool if requested
- Concurrent limit per user
- Attack cool down per user
- Plans system, expire after x amount of time
  - Add time to plan
  - Set plan expire to a indefinite time
- Admin/Mod promotion/demotion
- Broadcast announcements

# Customisation

Making a net yours is something a lot of people here wants. Slovakia accommodates but goes a step beyond. Customising the look of Slovakia is not just easy, but its hot reloadable, see your changes in real time. Custom branding is a key feature of Slovakia. No code required to create or modify stock branding. I legitimately wrote a small language which allows your to access variables and functions just by using simple escape sequences such as; `Hi <<$username>>. Please wait one second. <<sleep(1000)>> <<clear()>>Thank you.`.

There are many other variables and functions you can access, this language is as simple as Markdown.

Custom text commands - Custom text commands are full commands that are loaded from your ./assets/commands/text/\* folder with access to TermFX (the markup custom language) - Create commands without any code! Why? Its quick it simple. Allot of commands people add to nets are just banners or user stats anyway, now you can do it cleanly through Slovakia's plugin system. - Full animation support! - Create animations using ANSI escape sequences and ASCII art along with TermFX (for sleep() and clear()) to easily create custom animated art! - TermFX is supported in all branding options too! Your welcome banner could be animated too!

Custom binary commands - Custom binary commands allow you took hook up real programs! Execute binaries on the host OS on a separate process. - Command arguments are parsed to the command - If the binary crashes the CNC will not be affected - Secure, command line arguments are sanitised - Add extra functionality with powerful programs - Programs such as Hashcat have been tested and worked! Imagine that Hashcat on a CNC! - Run **PHP AS CUSTOM COMMANDS!**

Edit and add attacks to the simple attack.json file
Modify the blacklist via the config.json file

Customise the prompt
Customise the title bar using TermFX!

# TermFX Commands

`clear()`, `sleep(100)`, `slaveCount()`, `onlineMasters()`, `date()`, `time()`, `log(something to be logged)` `$username`, `$mod`, `$admin`, `$mfa` `$slaveHost`, `$cncHost`, `$version`, `$ip`, `$maxSessions`, `$maxTime`, `$maxConcurrents`, `$name`, `$vip`, `$cooldown`

# Monetisation

Slovakia has been built to allow for advanced and complex monetisation of its services.

- User session limit
- Attack cooldown
- Concurrents
- Max Time
- Vip commands
- Vip attacks

Sell custom plans based on these values and charge a premium for highly sort after "account specs".

# Brief Features List

SSH cnc
user management
add user command
remove user command
sessions
sessions management
sessions direct message
live chat
attacks
attack history
auto/tab complete
logging to disk
logging to stout
role based management (mods, admins, members)
custom branding
concurrent limits
attack cool downs
attack blacklist
login logs
command logs
slave logs
live user/master count
unix based commands (passwd, who etc)
SSH keys authentication
Mfa (google auth, authy)
CNC QR readable QR code for MFA registration
limit max open sessions per user
message broadcasts
view/manage open sessions per user
plan management (expire)
plan expire custom message
passwords hashed & salted
user VIP
iplookup
whois lookup
captcha
Custom commands via textfiles
Custom commands via binaries
Port aliases
Stop Command
Admin/Mod user add/remove logs
Kick a user's session or sessions
Custom clear command output
Custom home screen splash
Disable built in (native) commands
TermFX (template file functions & variables)
Dynamically update branding
Pty support, scale content
View command logs in terminal
Ini config file
Json config
live reload
kick message
ban message
php custom command support
users command pager
sessions user idle time

### Video 1

https://d.tube/#!/v/linux0tech0tips/QmQiq3GiH4WRusazJnmZHkG3GAakKyQ2ym2a7LBJdDP9yt

### Video 2

https://d.tube/#!/v/linux0tech0tips/QmQnn7BSXGabsfSdgrgqDa7S4Lb5tMnjZFpoiBiWn1Apme

# License

Do not share your license! Your license is used as a master password for setup and security reasons!
If you share your license you are exposing your self to being hacked!
Note I do not have access to your server.

Sharing Slovakia is against the terms of agreement and will result in your license being revoked or worse.
Charging back is prohibited!
Reselling is prohibited! This includes giving away for free or trading. (the distribution of Slovakia is stickily prohibited!)

By using Slovakia you agree to these terms.

# Extra

Webhooks, import-export-dlc.json, plan-presets and method suggestions are from DLCs. Ignore them if you have not purchased the DLC.
