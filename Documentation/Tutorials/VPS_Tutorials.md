# VPS Tutorials
[Digital Ocean](#digital-ocean) | [Raspberry Pi](#raspberry-pi) | [Heroku](#heroku) | [Glitch](#glitch)

## Digital Ocean

This bit assumes you are going to use `forever.js` to run the bot. You can choose another method but you'll have to check out those tutorials for further instruction)

#### Initial Server Setup

* Start a digital ocean instance (with node as your image) - the $5/month one is perfectly fine
* [Generate an SSH key](https://www.siteground.com/kb/how_to_generate_an_ssh_key_on_windows_using_putty/) and add it to the droplet on creation (It's much easier than doing it after)
* get the server IP address
* connect via PuTTY
* Run commands:
* `apt install unzip`
* `npm install --no-optional -g forever`

#### Unpackage and Start the bot

* Upload the bot file to your droplet using something like [WinSCP](https://winscp.net/eng/download.php)
* If you're uploading the bot for the first time it may be faster to upload it as a zip file and then unzip it on the droplet by typing `unzip <yourbot>.zip -d <bot folder>`
* If you've already uploaded the bot and you're just making a change to the command.json/events.json file you can JUST upload those without zipping them
* in PuTTY type: `chmod -R a+rwx <bot folder>`- Give the bot folder permission to be read/write and executable (you only need to do this the first time you set things up)
* in PuTTY type: `cd <bot folder>` - Change to the bots directory
* in PuTTY type: `forever start bot.js` - Start the bot program using "Forever" \(this will keep the bot running and restart it if it crashes\)

#### Stop the bot

* `forever list`
* `forever stop 0`_ - Where 0 is the index of your code in the forever list._

#### Server Maintenance
When you log in to Digital Ocean you'll see a MOTD telling you if there are package updates. If you want/need to install them do the following:

#### Install Updates
When updates are available:

- `sudo apt update` - update the package index
- `sudo apt upgrade` - install updates
- `sudo reboot` - reboots the system (server will indicate if it's needed)

#### add the SSH key to server file manually
If you want to add an SSH key after you've set up your droplet you can edit the authorized_keys file

- edit directly in PuTTY
- `nano /root/.ssh/authorized_keys`
- enter `ssh-rsa <key>` (the section that starts with AAAA[gibberish] - do not use begin, end, or comment line)

```
---- BEGIN SSH2 PUBLIC KEY ----
Comment: "rsa-key-[date]"
[a whole lot of gibberish]
---- END SSH2 PUBLIC KEY ----
```

- `Ctrl + O`, then at the bottom says "filename to write"
- `ctrl + x`
- set up PuTTY to connect automatically
- in PuTTY - open the connection details
- choose DATA
- Fill in the Auto Login username
- Putty should now connect automatically when the server is connected to

## Raspberry Pi

### Installing Node.js on a Raspberry pi
First of all, I made this guide using Raspberry Pi 3, however, it should work with Raspberry Pi 2 too. But not with a Raspberry Pi Zero because it doesn't support node.js - You can just google if your pi supports node.js.
_Tresmos\#2135_

Connect your Raspberry Pi using [PuTTY](https://www.putty.org/), or using [VNC ](https://howtoraspberrypi.com/raspberry-pi-vnc/)and type these commands in order to install Node.js:

### **for Node.js LTS:**

If you have any other version of Node.js installed please uninstall them now before continuing
```
sudo apt purge node.js npm
```

ARM Version:
```
uname -m
```

the output will look like: `armv#X`. \
navigate to [nodejs.org](https://nodejs.org/en/download/) downloads page, right-click on the `Linux Binaries (ARM)` version that correlates with your version (`armv#X`), click `Copy Link Address`, then go back to the terminal.

Getting Node.js package:
```
wget <Ctrl+Shift+V>
ls (note the downloaded file `node-vx.x.x-linux-armv#X.tar.xz`)
tar -xJf <filename>
```

Copy Node.js to /usr/local:
```
cd node-vx.x.x-linux-armv#X/
sudo cp -R * /usr/local/
```

Reboot RPi
```
reboot
```

### **for Node.js 8:**

```
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
```

### **for Node.js 9:**

```
curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
sudo apt-get install -y nodejs
```

After everything is done, check if Node.js is installed correctly or not with these commands:

```
node -v
npm -v
```

it should give you an output like this:

```
pi@raspberrypi:~ $ node -v
v9.10.0
pi@raspberrypi:~ $ npm -v
5.6.0
```

[This is an example](https://asciinema.org/a/173263) if you want to watch it.

#### Uploading Bot Files to Raspberry Pi

Before uploading your bot files you need to export it first watching [this video](https://www.youtube.com/watch?v=MNw7anSA06g). _**\(If you're using beta DO NOT use the built-in export feature because it's still buggy. Please export it manually watching the video\)**_

After that you have a couple of options to upload your bot files to Raspberry Pi:

* [FileZilla](https://filezilla-project.org/)
* [VNC Viewer](https://www.realvnc.com/en/connect/download/viewer/)

##### FileZilla

Download and install FileZilla using this [link](https://filezilla-project.org/). Now before uploading bot files, we need to connect our Raspberry Pi. To do that we need to open **Site Manager **and add our Raspberry Pi:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/filezilla_2018-03-29_15-21-09.png)

Just click **New Site**

* Host = IP of Raspberry Pi
* Protocol = SFTP - SSH File Transfer Protocol **\(thats really important\)**
* Logon Type = Normal
* User = pi
* Password = Your SSH Password

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/filezilla_2018-03-29_15-24-25.png)

After saving that and connecting, you can upload your bot files with just simple drag&drop to the right side


##### VNC Viewer

First, you need to activate VNC and connect to Raspberry Pi using this [guide](https://howtoraspberrypi.com/raspberry-pi-vnc/).

Then for transfer files click here at the top:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/vncviewer_2018-03-29_15-44-49.png)

After that you'll see a window, click **Send Files**, go **into** your bot folder, and press **Use Entire Folder**:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/vncviewer_2018-03-29_15-47-11.png)

as we can see it started to upload files to Raspberry Pi:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/vncviewer_2018-03-29_15-48-51.png)

#### Running The Bot

There are two ways to run your bot:

* with PuTTY

* with VNC Connection

##### Running With PuTTY

1. Connect to your Raspberry Pi using PuTTY
2. cd into your bot folder \(if your bot folder is in Desktop, type "cd Desktop/**YourBotFolderName"\)**
3. and finally type "node bot.js" to run your bot.

That's it!

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/putty_2018-03-29_15-59-08.png)

_In this way if you close PuTTY, your bot will stop working too._

##### Running With VNC Connection

1. Connect to your Raspberry Pi using VNC Viewer
2. Open your bot folder
3. Press **F4** to open a terminal window in your project folder
4. and type "node bot.js" to run your bot

That's it!

_In this way you can close VNC Viewer and your bot will still run, however if you close that terminal window bot will stop working._

## Heroku

### Disclaimers
From R. Danny (Discord's API server bot)

* Bots are not what the platform is designed for. Heroku is designed to provide web servers (like Django, Flask, etc). This is why they give you a domain name and open a port on their local emulator.
* Heroku's environment is heavily containerized, making it quite significantly underpowered (this is reason 1 why voice doesn't work properly on Heroku)
* Heroku's environment is volatile. To handle the insane amount of users trying to use it for their applications, Heroku will dispose your environment every time your application dies unless you pay.
* Heroku does not let you control system dependencies barely at all. This means if any of your requirements need C bindings (pynacl, lxml, etc), they'll probably not work. (this is reason 2 why voice doesn't work properly on Heroku)
* Heroku only offers a limited amount of time on their free program for your applications. If you exceed this limit (which you probably will), they'll shut down your application until your free credit resets.

If you need help with Heroku hosting please do not ask on our discord servers. You can just ask [here using our support system](https://dbm-support.site/).

### YouTube Tutorials

* [HOW TO HOST YOUR DISCORD BOT FOR FREE! (Heroku)](https://www.youtube.com/watch?v=d8INsGl28xw) - Published on May 29, 2018 **most recent**
* [Discord Bot | Host your bot for free! (using Heroku)](https://www.youtube.com/watch?v=kpIFnZ0zbsw) - Published on Mar 22, 2018
* [HOW TO HOST A DISCORD BOT FOR FREE USING HEROKU!](https://www.youtube.com/watch?v=diq7INoHqh4) - Published on Nov 15, 2017
* [Host your Discord bot on Heroku 24/7!](https://www.youtube.com/watch?v=NM8IMyqpvqU) - Published on Sep 10, 2017

## Glitch
Glitch is a **free** service that is generally used to run low to medium end applications and in general testing. Discord bots can be run on this however, there are some limits to glitch you must watch out for. This can be a great option for small to medium bots. It's a much better option then **heroku**. It is also **compatible with DBM beta.** This is a far better alternative then **android** and **heroku**.

If you would like to use this service follow the tutorial link here: [https://dbotmaker.io/forums/threads/glitch-hosting-free-compatible-with-beta-saves-data.305/](https://dbotmaker.io/forums/threads/glitch-hosting-free-compatible-with-beta-saves-data.305/ "Glitch Tutorial")

#### **Limits**
* Projects have a limit of around **200MB of disk space** on the project however node modules don't count towards it.
* Projects have a limit of **512MB of RAM**.
* Projects sleep after 5 minutes (tutorial shows how to fix it) and after 12 hours of constant running before being rebooted.

#### **Comparison to Heroku**
* Glitch will save your bot files and data. This is an actual storage system compared to Heroku which erases after each reboot.
* Glitch has an easier interface compared to Heroku's
* Glitch is more focused and better supported on Javascript/node.js and NPM packages. Hence why node modules are unlimited storage space
* Glitch has no actual "hour counter", bots will reboot after 12 hours and can run again up to 12 hours. Heroku, however, will shut down your bot for the rest of the month.