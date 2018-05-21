# Creating your own scripts in DBM
Most things that are not available as actions can be run as a script either in the `run script` action or in any box that allows for text entry using `${ }`.

![](https://github.com/Silversunset01/dbm/raw/master/screenshots/scriptex.png)


### Handy Scripting Resources
* [W3Schools](https://www.w3schools.com/js/) - basic javascript reference
* [Discord.js](https://discord.js.org/#/) - discord's custom JS library

### Scripting Cheat Sheets
* [Basic Javascript](/creating-your-own-scripts/basic-javascript.md)
* [Identifiers](/creating-your-own-scripts/identifiers.md)
* [Math and Calculations](/creating-your-own-scripts/math-and-calculations.md)
* [Storing Information](/creating-your-own-scripts/store-info.md)
* [Messaging](/creating-your-own-scripts/messaging.md)
* [Miscellaneous](/creating-your-own-scripts/miscellaneous.md)

## Basic Javascript
Usage | Script
:- | :-
Force Lower case | `.toLowerCase()`
Force Upper case | `.toUpperCase()`
Force string | `.toString()`
Replace | `.replace("old text","new text")`
Switch | `switch(thing to eval) {` <br /> `case "OPT1": action to execute on match; break;` <br />`case "OPT2": action to execute on match; break;` <br />`case "OPT3": action to execute on match; break;` <br />`default: action to execute on match; break;` <br /> `}`
If/Then (Ternery) | `(A < 1 ? "value if true" : "value if false")`
If/Then (Normal) | `if(thing to evaluate) {value if true} else {value if false}`

## DBM Identifiers
| Usage | Script |
| :--- | :--- |
| get the bot as a client (user) | `${this.getDBM().Bot.bot` |
| the command message | `${msg` |
| the current server | `${msg.guild` |
| the command channel | `${msg.channel` |

## Lists
Usage | Script
:- | :-
Create a list out of items that have data following them | `.array}`
Count items in the specified array | `.array().length}`
Count items in the specified list <br/> **or** <br/> count the length of a string | `.length}`
Find position of item in a list | `${tempVars("yourList").indexOf(tempVars("yourItemToFind"))}`
Remove item from list | `${tempVars("yourList").splice(# to remove, 1)}`
Return the last # of items in a list | `tempVars("your variable").slice(Math.max(tempVars("your variable").length - 5, 1))` <br/> *where 5 is the number of items to return*
Return item at [position] from [list] | `tempVars("list").slice(tempVars("pos_num")-1,tempVars("pos_num"))`

## Math & Operations
Usage | Script
:- | :-
round down | `${Math.floor(yourvariable)}`
Round to the nearest Integer | `${Math.round(yourvariable [, decimals])`
Force variable to be read as a number | `${parseInt(yourvariable)}`
Translate (date) milliseconds to days | `${Math.floor((tempVars("uptime-ms") % 31536000) / 86400)}`
Translate (date) milliseconds to hours (up to 24) | `${Math.floor((tempVars("uptime-ms") % 86400) / 3600)} `
Translate (date) milliseconds to minutes (up to 60) | `${Math.floor((tempVars("uptime-ms") % 3600) / 60)}`
Translate (date) milliseconds to seconds (up to 60) | `${Math.round(tempVars("uptime-ms") % 60)}`
Translate (duration) milliseconds to a human readable format | `var duration = tempVars("time_var");` <br/> `var ms = parseInt((duration%1000)/100);` <br/> `var s = parseInt((duration/1000)%60);` <br/> `var m = parseInt((duration/(1000*60))%60);` <br/> `var h = parseInt((duration/(1000*60*60))%24);` <br/> `var timeoutput = h + "h:" + m + "m:" + s + "s:" + ms + "ms";`

## Messaging - Embeds
Usage | Script
:- | :-
Add Field to Embed message | `tempVars("test").addField("Test Name","Test Value",[inline]);` <br/> `[inline]` = True or False
Add Footer to Embed message | `tempVars("test").setFooter(member.displayName, msg.author.avatarURL)`

## Messaging - Miscellaneous
Usage | Script
:- | :-
Send a message (hard coded text) | `msg.channel.send("your message here")`
Send a message (variable) | `msg.channel.send(tempVars("some_variable"))`
Send a message (with mixed text & variables) | `msg.channel.send("some text here " + tempVars("some_variable") + " and some more text")`
Send a message (to another channel)| `msg.guild.channels.find("name","bot-logs").send("test in another channel")` <br/>*can use "ID" instead of "Name"*
Log to console | `console.log("your text here")`
Add reactions to message <br/> *works on normal messages or embeds* | `msg.channel.send(tempVars("test"))` <br /> `.then(function (message) {` <br /> `message.react("👍")` <br /> `message.react("👎")` <br /> `}).catch(function() {` <br /> `msg.channel.send("is broke yo")` <br /> `});`

## Miscellaneous
Usage | Script
:- | :-
Unban User <br/><i>requires user's ID</i> | `msg.guild.unban(tempVars("user_id"))`<br/>`.then(user => console.log("Unbanned ${user.username} from ${msg.guild.name}"))`<br/>`.catch(console.error);`
Find Emoji | `client.emojis.find("name", "NameOfTheEmoji")`
skip ahead some number<br/>_there are kinks to this still_ | `this.callNextAction(#)`
Show current date/time in timezone | `new Date().toLocaleString("en-US", {timeZone: "America/New_York"})`
Create server invite | `msg.channel.createInvite({temporary: true}," Showing the usage").then(invite=> msg.channel.send(invite.url))`
Add role to cmd author | `member.addRole(tempVars("newrolename"));`
Stop the bot | `process.exit(0);`
Change nickname (command author) | `msg.member.setNickname(tempVars("new_nick"))`<br/>`.then(console.log)`<br/>`.catch(console.error);`
Get Variable value | `this.getVariable(1,"varname",cache);`
Store Variables via script | `this.storeValue(output, 1 ,"totalUsers", cache)` <br /> (*1 = temp, 2 = server, 3 = global*)

## Bot Info

| Usage | Script |
| :--- | :--- |
| Return Count of Members in all Bot Guilds | `${this.getDBM().Bot.bot.users.array().length}` |
| Return Count of all Bot Guilds | `${this.getDBM().Bot.bot.guilds.array().length}` |
| Return List of all Bot Guilds | `${this.getDBM().Bot.bot.guilds.array()}` |
| Program memory usage \(in MB\) | `${Math.floor((process.memoryUsage().heapUsed / 1024)/1024)} MB` |
|Store the bot as a user (using the message sent)| `${msg.guild.me}`

## User Info

| Usage | Script |
| :--- | :--- |
|Author Tag|`${msg.author.tag}`
|Author Discriminator|`${msg.author.discriminator}`
|Author Username|`${msg.author.username}`
|Author Display Name (Nick)|`${member.displayName}`
|Author Avatar URL|`${msg.author.avatarURL}`
|User (variable) Tag|`${tempVars("user_object").user.tag}`
|User (variable) Discriminator|`${tempVars("user_object").user.discriminator}`
|User (variable) Username|`${tempVars("user_object").user.username}`
|User (variable) Display Name (Nick)|`${tempVars("user_object").displayName}`
|User (variable) Avatar URL|`${tempVars("user_object").user.avatarURL}`

## Server Info

| Usage | Script |
| :--- | :--- |
| Return Server Icon URL | `${msg.guild.iconURL}` |
| Return Server Verification Level | `${msg.guild.verificationLevel}` |
| Return Server Explicit Content Filter | `${msg.guild.explicitContentFilter}` |
| Return Server Creation Date | `${msg.guild.createdAt}` |
| Return Server Name | `${msg.guild.name}` |
| Return Server Owner Display Name | `${msg.guild.owner.displayName}` |
| Return Server Available Status | `${msg.guild.available}` |
| Return Server Region | `${msg.guild.region}` |
| Return Server Creation Date | `${msg.guild.createdAt}` |
| Return Server Emojis List | `${msg.guild.emojis.array()}` |
| Return Server Emojis Count | `${msg.guild.emojis.array().length}` |
| Return Server Count of Roles | `msg.guild.roles.array().length` |
| Return Server Member Count | `${msg.guild.memberCount}` |
| Return Server Online members | `${msg.guild.members.filter(m => m.user.presence.status == \"online\").size}` |
| Return Server Offine members | `${msg.guild.members.filter(m => m.user.presence.status == \"offline\").size}` |
| Return Server Idle members | `${msg.guild.members.filter(m => m.user.presence.status == \"idle\").size}` |
| Return Server DND members | `${msg.guild.members.filter(m => m.user.presence.status == \"dnd\").size}` |
| Return Server Count of Channels | `${msg.guild.channels.array().length}` |
| Return Server Count of Text Channels | `${msg.guild.channels.findAll('type', 'text').length}` |
| Return Server Count of Voice Channels | `${msg.guild.channels.findAll('type', 'voice').length}` |
| Return Server AFK Channel | `${msg.guild.afkChannel}` |
| Return Server AFK Timeout \(in seconds\) | `${msg.guild.afkTimeout}` |
| Store members in a role | `${tempVars("role").members.array().length}`|

# Tutorials
## Generating a Random Response
A random response generator works for anything from a Magic 8 ball command to a coin toss command, to a random image, joke, phrase, or even paper/scissors/rock command. The bot will generate a random number and select a response based on the number chosen.

**Action 1: Generate a random number** this will allow the bot to select one of your pre-programmed responses.

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/randtext.png)

**Action 2: Send message based on the number generated** using a switch/case script.

Switch/case basically evaluates the statement defined in `switch(tempVars("rand-num"))` and selects the matching response from the list of `case` items. The last item should always be `default` this is often used for error handling if no `case` match is found. In this case the possible outcomes of the `rand-num` variable are known and such a short list that `default` can be used to indicate the last match rather than an error.

`msg.channel.send("text")` will send a message to the current channel.

`break;` ends the action

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/randtext2.png)

### Copyable code \(by request\)

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

## Stopping the bot
Sometimes you need to stop your bot. If you're running a script like `forever` this may automatically restart your bot, otherwise it will just shut the whole bot down.

For information on how to \*restart\* the bot [check out this article on restarting the bot automatically](/running-24-7/automatic-restart-when-bot-crashes.md)

**Action 1: send a message** to the channel so you know the bot has recognized the command
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/stopping.png)

**Action 2: stop the bot using a script**. Its good practice to log to console that the bot is stopping, again to confirm that the action is recognized.

`console.log("text")` is used to print text directly to the bots console logs. Anything inside the `" "` will be printed directly. If you choose to use a variable instead you would use `console.log(tempVars("name"))`

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/stopping2.png)

## Working with Time
**Time is an illusion. Lunchtime doubly so. **
Trying to code things with time in javascript will most likely set your hair on fire. Please proceed with caution.

First, go [to this site](https://www.w3schools.com/jsref/jsref_obj_date.asp), bookmark it, and make it your new best friend. This will give you all the bits and pieces of time you could ever want.

### Basic Timestamps
* Getting the current time
Getting the current time in javascript is easy.
`${new Date()}` is all you really need. When you run this you're going to get something that looks like `Wed Apr 04 2018 20:18:02 GMT-0400 (Eastern Daylight Time)`
**but be careful** - this will give you the time in the bot's timezone. So if you're running it on your home computer you'll get your local time, but when you save it out to a VPS you'll get whatever the servers 'local time' is.

* Getting the current UTC time
This is a bit more tricky, and will take multiple steps. All of this is done in a single `run script` action in DBM.
`var now = new Date();` = this will get the current time and create the variable "now" to use
`var year = now.getUTCFullYear();` = stores the UTC Year
`var month = now.getUTCMonth() + 1;` = stores the UTC month (months are 0-11 so you have to add 1)
`var day = now.getUTCDate();` = stores the UTC Date
`var hour = now.getUTCHours();` = stores the UTC Hour
`var minutes = now.getUTCMinutes();` = stores the UTC Minutes

You can then add:
`msg.channel.send("The time is: " + month + "/" + day + "/" + year + "; " + hour + ":" + minutes)`
to display the following:
`The time is: 4/4/2018; 23:23`

**but** what if the minutes are < 10, you'd see the time as `23:1` instead of `23:01`
And how can you tell if the date is month/day/year or day/month/year (different countries have different conventions)

#### Getting the Current UTC Time AND FORMATTING IT
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
1) A [switch statement](https://www.w3schools.com/js/js_switch.asp) is being used to display the month name instead of the number
2) A [conditional operator](https://www.w3schools.com/jsref/jsref_operators.asp) is being used to pad the zeros on the date

#### Give up and use .toLocaleString()
**WARNING WARNING WARNING**
If you use this method in DBM you WILL NOT be able to run your bot directly in DBM. It will be fine on your [vps or running via cmd locally](/running-24-7.md).
**YOU HAVE BEEN WARNED**

[.toLocaleString()](https://www.w3schools.com/jsref/jsref_tolocalestring.asp) allows you to display a string using location-specific formatting. If your string is a date, it will show the current time as `4/4/2018, 7:40:32 PM` since that is the local settings for where the bot is currently running. **AGAIN** if you save the bot to a VPS it will use the bots server settings instead, BUT you can tell the program which settings you want it to use rather than the 'local' ones. 
`new Date().toLocaleString("en-US", {timeZone: "UTC"})` will show the current UTC time in an American format
`new Date().toLocaleString("en-US", {timeZone: "America/Chicago"})` will show the current CST time in an American format.
[This Document](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toLocaleString) has more information on locale string settings.

#### Finding the time between actions
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





