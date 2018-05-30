# Tutorials
This section covers various tutorials and things that may be helpful.

## Official Tutorial Videos

* [DBM Tutorial #1 - Setting up the bot](https://youtu.be/5fE1_UqvVPQ)
* [DBM Tutorial #2 - How to use Commands](https://youtu.be/GOQcJ7a-cLc)
* [DBM Tutorial #3 - How to use Variables](https://youtu.be/BOzYGzbJZ8g)
* [DBM Tutorial #4 - Text Evaluations](https://youtu.be/XluYShxVhPI)
* [DBM Tutorial #5 - Obtaining Parameters](https://youtu.be/haAyykGaY_E)
* [DBM Tutorial #6 - How to use Events](https://youtu.be/lBEQBEXe2yQ)
* [DBM Tutorial #7 - How to Export the Bot](https://youtu.be/MNw7anSA06g)

# Data
Information relating to the storage and passing of data between commands or actions.

## Variables

[DBM Tutorial - Obtaining Parameters >](https://www.youtube.com/watch?v=haAyykGaY_E)

There are a few ways to store and reuse information in DBM.

* **Temp variable** - exists only for the duration of the command. Once the command action list is over the variable is 'forgotten' by the bot
* **Server variable** - exists for a single server. The bot will 'remember' these variable between commands but only for the server they were created in.
* **Global variable** - exists for the bot regardless of server or command.

## Store Command Parameters

You can store parameters entered into a command using the "Store command parameters" action. This will assume your parameters are using the default `space` \(`\s+`\) as a seperator.

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/storeparams.png)

* Parameter Number:
  * This tells the bot which word to start on. Using 1 would mean "the first word after the command"; 2 would mean "the second word after the command" and so on.
  * DBM defines a "word" as a complete string of characters between your parameter seperator
    * ex: If your seperator is a space, a "world" would be anything between spaces - `this is four words`
    * ex: if your seperator is a comma, a "word" would be anything between commas - `this is, two things`
    * Source Info:

* **One Parameter** - creates a parameter using a single word, beginning at the \# given in the "parameter number" field.
  * ex: `!prune 50 100` - using "One Parameter" and "1" your parameter would be `50`
  * ex: `!prune 50 100` - using "One Parameter" and "2" your parameter would return `100`
* **Multiple Parameters** - creates a parameter using multiple words, beginning from the number you specify in "Parameter Number" and going to the end of the command input
  * ex: `! ban @Silversunset You are breaking the rules` - using "Multiple Parameters" and "2" your parameter would be `You are breaking the rules`
  * ex: `! ban @Silversunset You are breaking the rules` - using "Multiple Parameters" and "3" your parameter would be `are breaking the rules`
* **Mentioned Member** - stores the `@username` from a command as a parameter
* **Mentioned Role** - stores the `@role` from a command as a parameter
* **Mentioned Channel** - stores the `#channel` from a command as a parameter

# Running your bot 24/7
By now you may have noticed that when you close DBM your bot shuts down. [This tutorial](https://www.youtube.com/watch?v=MNw7anSA06g&t=2s) will explain how to export your bot to run in a command terminal.

## Running your bot with cmd

1. Open project directory
2. Click into the address bar
3. At the beginning type "cmd" and hit enter (this will open a cmd prompt in this folder)
4. type `node bot.js`

## Running your bot with NODEMON

`node bot.js` will have to be restarted every time you make changes. You can use Nodemon to do this automatically

1. Install nodemon with `npm i -g nodemon`
2. Open project directory
3. Click into the address bar
4. At the beginning type "cmd" and hit enter (this will open a cmd prompt in this folder)
5. Type `nodemon --inspect --watch actions --watch data/commands.json--watch data/events.json --watch node_modules --watch js bot.js`

## VPS Hosting - Digital Ocean
#### **Initial Server Setup**

* Start a digital ocean instance \(with node as your image\)
* Generate and add SSH keys before creating \(then you dont have to do it after\)
* get server IP address
* connect via PuTTY
* Run commands:
* `apt install unzip`
* `npm install --no optional -g forever`

#### **Unpackage and Start the bot**

* Upload the bot file to your droplet using something like [WinSCP](https://winscp.net/eng/download.php)
* If you're uploading the bot for the first time it may be faster to upload is as a zip file and then unzip it on the dropletby typing `unzip <yourbot>.zip -d <bot folder>`
* If you've already uploaded the bot and you're just making a change to the command.json/events.json file you can JUST upload those without zipping them
* `chmod -R a+rwx <bot folder>`- Give the bot folder permission to be read/write and executable
* `cd <bot folder>` - Change to the bots directory
* `forever start bot.js` - Start the bot program using "Forever" \(this will keep the bot running and restart it if it crashes\)

#### Stop the bot

* `forever list`
* `forever stop 0`_ - Where 0 is the index of your code in the forever list._

#### Server Maintenance
When you log into Digital Ocean you'll see an MOTD telling you if there are package updates. If you want/need to install them do the following:

#### **Install Updates**
When updates are available:

- `sudo apt update` - update package index
- `sudo apt upgrade` - install updates
- `sudo reboot` - reboots the system (server will indicate if its needed)

#### **add SSH key to server file manually**
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

- `ctrl + O`, then at the bottom says "filename to write"
- `ctrl + x`
- set up PuTTY to connect automatically
- in PuTTY - open the connection details
- choose DATA
- Fill in the Auto Login username
- Putty should now connect automatically when the server is connected to

## Installing Node.js on a Raspberry Pi
First of all i made this guide using Raspberry Pi 3, however it should work with Raspberry Pi 2 too, but i have no idea if things here are working for Raspberry Pi 1 or Raspberry Pi Zero. If you tried to use this guide on Raspberry Pi 1 or Raspberry Pi Zero, let me know if its working or not by messaging me on Discord. _Tresmos\#2135_

Connect your raspberry pi using [PuTTY](https://www.putty.org/), or using [VNC ](https://howtoraspberrypi.com/raspberry-pi-vnc/)and type these commands in order to install Node.js:

for Node.js 8:

```
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
```

for Node.js 9:

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

Before uploading your bot files you need to export it first watching [this video](https://www.youtube.com/watch?v=MNw7anSA06g). _**\(If you're using beta DO NOT use built in export feature because its still buggy. Please export it manually watching the video\)**_

After that you have a couple options to upload your bot files to Raspberry Pi:

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

After saving that and connecting, you can upload your bot files with just simple drag&drop to right side

![](https://i.hizliresim.com/W7vZ4m.gif)

##### VNC Viewer

First you need to activate VNC and connect to Raspberry Pi using this [guide](https://howtoraspberrypi.com/raspberry-pi-vnc/).

Then for transfer files click here at the top:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/vncviewer_2018-03-29_15-44-49.png)

After that you'll see a window, click **Send Files**, go **into** your bot folder, and press **Use Entire Folder**:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/vncviewer_2018-03-29_15-47-11.png)

as we can see it started to upload files to Raspberry Pi:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/vncviewer_2018-03-29_15-48-51.png)

#### Running The Bot

There is two ways to run your bot:

* with PuTTY

* with VNC Connection

##### Running With PuTTY

1. Connect to your Raspberry Pi using PuTTY
2. cd into your bot folder \(if your bot folder is in Desktop, type "cd Desktop/**YourBotFolderName"\)**
3. and finally type "node bot.js" to run your bot.

Thats it!

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/putty_2018-03-29_15-59-08.png)

_In this way if you close PuTTY, your bot will stop working too._

##### Running With VNC Connection

1. Connect to your Raspberry Pi using VNC Viewer
2. Open your bot folder
3. Press **F4** to open terminal window in your project folder
4. and type "node bot.js" to run your bot

Thats it!

_In this way you can close VNC Viewer and your bot will still run, however if you close that terminal window bot will stop working._

![](https://i.hizliresim.com/PlWorb.gif)

## Stopping the bot
Sometimes you need to stop your bot. If you're running a script like `forever` this may automatically restart your bot, otherwise it will just shut the whole bot down.

**Action 1: send a message** to the channel so you know the bot has recognized the command
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/stopping.png)

**Action 2: stop the bot using a script**. Its good practice to log to console that the bot is stopping, again to confirm that the action is recognized.

`console.log("text")` is used to print text directly to the bots console logs. Anything inside the `" "` will be printed directly. If you choose to use a variable instead you would use `console.log(tempVars("name"))`

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/stopping2.png)

## Restarting the bot Automatically
In this guide I'll show how to create a script that will restart the bot automatically. This script restarts your bot when it crashes. You can even make a command to restart your bot with this script.

### Linux

* Go into your bot folder with : `cd BotFolderLocation`
* Use `nano start.sh` to create a file called `start.sh` and start editing.
* Paste the code below :

```bash
# /bin/sh
while true
do
echo Starting Bot
node bot.js
echo Restarting Bot in 5 Seconds...
sleep 5
done
```

* Press CTRL+C then Y and ENTER to save the start.sh file.
* Use `chmod 777 start.sh` to give the file executable permission.
* Done! Now you can start your bot by executing that file with : `./start.sh`

**Tutorial Video** _\(Click on image to watch it\)_[![](https://asciinema.org/a/Gjc27yyaid3LxAIDlc8AqM4Z3.png)](https://asciinema.org/a/Gjc27yyaid3LxAIDlc8AqM4Z3)

### Windows

* Create a file with `.bat` extension.
* Paste the code below and save it.

```
@echo off
echo Starting..
:main
node bot.js
echo Restarting Bot..
goto main
```

* Done! Now you can run your bot just executing that file.

[**Tutorial Video **_\(Click to watch it\)_](https://youtu.be/1ZDE3z_Fsi4)

### Forever.js
You can install a script called **Forever.js** that will automatically restart your bot if it crashes. 

* `npm install --no optional -g forever`
* `chmod -R a+rwx <bot folder>`- Give the bot folder permission to be read/write and executable
* `cd <bot folder>` - Change to the bots directory
* `forever start bot.js` - Start the bot program using "Forever" \(this will keep the bot running and restart it if it crashes\)

# Miscellaneous Tutorials
## Generating a Random Response
A random response generator works for anything from a Magic 8 ball command to a coin toss command, to a random image, joke, phrase, or even paper/scissors/rock command. The bot will generate a random number and select a response based on the number chosen.

**Action 1: Generate a random number** this will allow the bot to select one of your pre-programmed responses.

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/randtext.png)

**Action 2: Send message based on the number generated** using a switch/case script.

Switch/case basically evaluates the statement defined in `switch(tempVars("rand-num"))` and selects the matching response from the list of `case` items. The last item should always be `default` this is often used for error handling if no `case` match is found. In this case the possible outcomes of the `rand-num` variable are known and such a short list that `default` can be used to indicate the last match rather than an error.

`msg.channel.send("text")` will send a message to the current channel.

`break;` ends the action

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/randtext2.png)

#### Copyable code

#### Send message to the current channel:

```
switch(tempVars("rand-num")){
case 1: msg.channel.send("Answer 1"); break;
case 2: msg.channel.send("Answer 2"); break;
case 3: msg.channel.send("Answer 3"); break;
case 4: msg.channel.send("Answer 4"); break;
default: msg.channel.send("Answer 5"); break;
}
```

#### Save message as a variable to use later:
```
switch(tempVars("rand-num")){
case 1: var resp = "Answer 1"; break;
case 2: var resp = "Answer 2"; break;
case 3: var resp = "Answer 3"; break;
case 4: var resp = "Answer 4"; break;
default: var resp = "Answer 5"; break;
};
this.storeValue(resp, 1 ,"answer", cache);
```
(you would use `tempVars("answer")` to call this variable

## Working with Time
**Time is an illusion. Lunchtime doubly so. **
Trying to code things with time in javascript will most likely set your hair on fire. Please proceed with caution.

First, go [to this site](https://www.w3schools.com/jsref/jsref_obj_date.asp), bookmark it, and make it your new best friend. This will give you all the bits and pieces of time you could ever want.

### Basic Timestamps
* Getting the current time
Getting the current time in javascript is easy.
`${new Date()}` is all you really need. When you run this you're going to get something that looks like `Wed Apr 04 2018 20:18:02 GMT-0400 (Eastern Daylight Time)`
**but be careful** - this will give you the time in the bot's timezone. So if you're running it on your home computer you'll get your local time, but when you save it out to a VPS you'll get whatever the servers 'local time' is.

### Getting the current UTC time

This is a bit more tricky, and will take multiple steps. All of this is done in a single `run script` action in DBM.<br/>
`var now = new Date();` = this will get the current time and create the variable "now" to use<br/>
`var year = now.getUTCFullYear();` = stores the UTC Year<br/>
`var month = now.getUTCMonth() + 1;` = stores the UTC month (months are 0-11 so you have to add 1)<br/>
`var day = now.getUTCDate();` = stores the UTC Date<br/>
`var hour = now.getUTCHours();` = stores the UTC Hour<br/>
`var minutes = now.getUTCMinutes();` = stores the UTC Minutes<br/>

You can then add:
`msg.channel.send("The time is: " + month + "/" + day + "/" + year + "; " + hour + ":" + minutes)`
to display the following:
`The time is: 4/4/2018; 23:23`

**but** what if the minutes are < 10, you'd see the time as `23:1` instead of `23:01`
And how can you tell if the date is month/day/year or day/month/year (different countries have different conventions)

### Formatting Current UTC Time
The final change to our script is going to be to add formatting to the month, to display "April" instead of "4", as well as padding leading zeros in the hour/minutes of the time.

**this is the full run-script action code**

```
var now = new Date();
var year = now.getUTCFullYear();
var month = now.getUTCMonth() + 1;
var day = now.getUTCDate();
var hour = now.getUTCHours();
var minutes = now.getUTCMinutes();

switch(month){
case 1: var monthname = "January"; break;
case 2: var monthname = "February"; break;
case 3: var monthname = "March"; break;
case 4: var monthname = "April"; break;
case 5: var monthname = "May"; break;
case 6: var monthname = "June"; break;
case 7: var monthname = "July"; break;
case 8: var monthname = "August"; break;
case 9: var monthname = "September"; break;
case 10: var monthname = "October"; break;
case 11: var monthname = "November"; break;
case 12: var monthname = "December"; break;
}

msg.channel.send("The time is: " + monthname + " " + day + ", " + year + "; " + (hour > 9 ? hour : "0" + hour) + ":" + (minutes > 9 ? minutes : "0" + minutes))
```

we're using a few javascript tricks here.
1. A [switch statement](https://www.w3schools.com/js/js_switch.asp) is being used to display the month name instead of the number
2. A [conditional operator](https://www.w3schools.com/jsref/jsref_operators.asp) is being used to pad the zeros on the date

### Using .toLocaleString()
**WARNING WARNING WARNING**
If you use this method in DBM you WILL NOT be able to run your bot directly in DBM. It will be fine on your vps or running via cmd locally.
**YOU HAVE BEEN WARNED**

[.toLocaleString()](https://www.w3schools.com/jsref/jsref_tolocalestring.asp) allows you to display a string using location-specific formatting. If your string is a date, it will show the current time as `4/4/2018, 7:40:32 PM` since that is the local settings for where the bot is currently running. **AGAIN** if you save the bot to a VPS it will use the bots server settings instead, BUT you can tell the program which settings you want it to use rather than the 'local' ones. 
`new Date().toLocaleString("en-US", {timeZone: "UTC"})` will show the current UTC time in an American format
`new Date().toLocaleString("en-US", {timeZone: "America/Chicago"})` will show the current CST time in an American format.
[This Document](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toLocaleString) has more information on locale string settings.

### Finding the time between actions
Another common use for time in javascript is determining "when the last time something was done"

To do this you'll need to store the last time something was run and compare it to the current time.
**[This link](https://pastebin.com/EaBjackY) is the raw-data for the below command tutorial.**

The real magic however is this script:
```
var duration = tempVars("time_var");
var ms = parseInt((duration%1000)/100);
var s = parseInt((duration/1000)%60);
var m = parseInt((duration/(1000*60))%60);
var h = parseInt((duration/(1000*60*60))%24);

var timeoutput = h + "h:" + m + "m:" + s + "s:" + ms + "ms";
this.storeValue(timeoutput,1,"donetime",cache)
```
which converts the # of milliseconds between "current run" and "last run" to a human readable format.

For this example, we'll time "when was the last time [User] ran [Command]"

**...ASSUMING YOUVE INSTALLED THE RAW DATA...**
This is what each action is doing:

**Action 1**: **required** Checks the last time the command was run, using store-member-data. This will be stored in milliseceonds. *note: if this is the first time the command was run you may get a NaN error, or some weird number.

**Action 2**: **required** Checks the difference between the "Current Time" and "The Last Time The Command Was Run" - this will return a number in MILLISECONDS

**Action 3**: OPTIONAL: Format the time from milliseconds to a human-readable format. This will output your time as `0h:2m:34s:4ms`

**Action 4**: Send some message with the information (Or do whatever else you want with it really). For the purposes of this tutorial you should get two lines, one in milliseconds and one formatted.

**Action 5**: **required** Save the new current time to the member data, overwriting the old one and storing the new 'last time this command was run for that user.

## How to Create an Embed Message
Your bot can send two types of message, a normal message (that looks like something you would type) an an embed message.
#### To create an embed you must have at least three actions

**1. Create embed** - you must create an embed first. If you've not created an embed you won't be able to send it.
[THIS IMAGE](https://dbm-mods.xyz/files/opera_2018-03-05_15-51-27.png) is a full explaination of what the fields mean.
For this example we'll use the following settings:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest.png)

**2. Add embed field OR set embed description** - If you want to add more content to your embed you can add a field or description. You can do both if you wish as well. The main difference is that the *Description* field does not have a required header, as the "embed title" is considered the header. the *embed field* item requires both a name and a description.
For this example we'll use the following settings (Both an embed description AND an embed field):

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest2.png)

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest3.png)

**3. Add a footer (with a script)** - If you don't have DBM Mods you can add an embed footer with a script. This will add the authors username and avatar to the embed footer.
If you want to add more text you can modify the script text.

*Script Text:* `tempVars("e").setFooter(member.displayName, msg.author.avatarURL)`

*Modified Script Text:* `tempVars("e").setFooter(member.displayName + " Some Other Text", msg.author.avatarURL)`

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest4.png)

**4. Send the embed** - after you've created the embed with all its fancy fields you must send it!
DBM Defaults to "Same Channel" which will send the embed to the same channel as the command message. You've got the same options here as you do a normal send-message. (If you send the message to a user the user will recieve a DM unless they have those blocked)

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest5.png)

**THE RESULT**:
If you've copied all of the steps above you should end up with an embed like this:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest6.png)

## Synchronous or Asynchronous
Thread: the flow of actions, starting from one until it ends

These keywords refer to how the thread is treated and how the program flows. Whenever the call type is Sync, it waits until it recieves a callback or when the thread ends. Meaning that when the event or command is called, the main thread starts first, and if it is ever interrupted by a call, it does that action and if that action ends, returns to the main thread. Async is similar to Sync however, it runs alongside with the main thread.  

Purpose: This is useful in multithreading. Take this example:  

Main Thread:
ControlVariable(A to 1)
CallCommand(Called, Sync)
ControlVariable(A to 7)
${A + 1}

Called Thread:
ControlVariable(A o 4)

This would output 8, However take this example with Asynchronous:
ControlVariable(A to 1)
CallCommand(Called, Async)
ControlVariable(A to 7)
${A + 1}

Called Thread:
ControlVariable(A to 4)

This would either output 5 or 8, depends on which thread changes the variable's value last.
Async has its purpose, you need to think about how to use which callback function or call type to use in which case.
