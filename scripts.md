# Discord Bot Maker
DBM allows users to create bots using a graphical user interface that gives coders of all levels a head start on building their bots. You can find this software [on steam](https://store.steampowered.com/app/682130/Discord_Bot_Maker/)

# Creating your own scripts
Most things that are not available as actions can be run as a script either in the `run script` action or in any box that allows for text entry using `${ }`. 

Sidenote: If you are trying to use a script in a text-entry field you'll need to surround it with `${ }` brackets so the program understands that it is a script and not text. However when using a run-script action you *should not* use the brackets.

![](https://github.com/Silversunset01/dbm/raw/master/screenshots/scriptex.png)

### Handy Scripting Resources
* [W3Schools](https://www.w3schools.com/js/) - basic javascript reference
* [Discord.js](https://discord.js.org/#/) - discord's custom JS library

# Basic Javascript
## Math & Operations
Usage | Script
:- | :-
Force variable to be read as a number | `${parseInt(yourvariable)}`
Add two variables | `${parseInt(tempVars("var1")) + parseInt(tempVars("var2"))}`
Subtract two variables | `${parseInt(tempVars("var1")) - parseInt(tempVars("var2"))}`
Multiply two variables | `${parseInt(tempVars("var1")) * parseInt(tempVars("var2"))}`
Divide two variables | `${parseInt(tempVars("var1")) / parseInt(tempVars("var2"))}`
Round down | `${Math.floor(yourvariable)}`
Round to the nearest Integer | `${Math.round(yourvariable [, decimals])`
Translate (date) milliseconds to days | `${Math.floor((tempVars("uptime-ms") % 31536000) / 86400)}`
Translate (date) milliseconds to hours (up to 24) | `${Math.floor((tempVars("uptime-ms") % 86400) / 3600)} `
Translate (date) milliseconds to minutes (up to 60) | `${Math.floor((tempVars("uptime-ms") % 3600) / 60)}`
Translate (date) milliseconds to seconds (up to 60) | `${Math.round(tempVars("uptime-ms") % 60)}`
Translate (duration) milliseconds to a human readable format | `var duration = tempVars("time_var");` <br/> `var ms = parseInt((duration%1000)/100);` <br/> `var s = parseInt((duration/1000)%60);` <br/> `var m = parseInt((duration/(1000*60))%60);` <br/> `var h = parseInt((duration/(1000*60*60))%24);` <br/> `var timeoutput = h + "h:" + m + "m:" + s + "s:" + ms + "ms";`

## Miscellaneous Javascript
Usage | Script
:- | :-
Force Lower case | `.toLowerCase()`
Force Upper case | `.toUpperCase()`
Force string | `.toString()`
Replace | `.replace("old text","new text")`
Switch | `switch(thing to eval) {` <br /> `case "OPT1": action to execute on match; break;` <br />`case "OPT2": action to execute on match; break;` <br />`case "OPT3": action to execute on match; break;` <br />`default: action to execute on match; break;` <br /> `}`
If/Then (Ternery) | `(A < 1 ? "value if true" : "value if false")`
If/Then (Normal) | `if(thing to evaluate) {value if true} else {value if false}`

# Information Storage
## Bot Info

| Usage | Script |
| :--- | :--- |
| Return Count of Members in all Bot Guilds | `${this.getDBM().Bot.bot.users.array().length}` |
| Return Count of all Bot Guilds | `${this.getDBM().Bot.bot.guilds.array().length}` |
| Return List of all Bot Guilds | `${this.getDBM().Bot.bot.guilds.array()}` |
| Program memory usage \(in MB\) | `${Math.floor((process.memoryUsage().heapUsed / 1024)/1024)} MB` |
|Store the bot as a user (using the message sent)| `${msg.guild.me}`
|Bot Ping | `${this.getDBM().Bot.bot.ping}` <br/>or<br/> `${client.ping}`
|Bots CPU | `${(process.cpuUsage().user / 1000000).toFixed(2)} Seconds`
|Count of Commands in Bot| `${this.DBM.Files.data.commands.length}`
|Count of Events in Bot| `${this.DBM.Files.data.events.length}`


## User Info

| Usage | Script |
| :--- | :--- |
|Author Tag|`${msg.author.tag}`
|Author Discriminator|`${msg.author.discriminator}`
|Author Username|`${msg.author.username}`
|Author Display Name (Nick)|`${member.displayName}`
|Author Avatar URL|`${msg.author.avatarURL}`
|Author Role List | `${member.roles.array()}`
|Author Role List (truncated after 3 roles) <br/>*enter `${tempVars("role_list")}` into your send-message to view this output.*<br/>*output will display as `@role1,@role2,@role3 + # more roles!`* | `var roles = member.roles.array();`<br/>`var len = roles.length;`<br/>`if (len > 3) {`<br/>`   var answer = roles.slice(0,3) + " + " + (len - 3) + " more!"`<br/>`} else {`<br/>`   var answer = roles`<br/>`};`<br/>`this.storeValue(answer, 1 ,"role_list", cache);`
|User (variable) Tag|`${tempVars("user_object").user.tag}`
|User (variable) Discriminator|`${tempVars("user_object").user.discriminator}`
|User (variable) Username|`${tempVars("user_object").user.username}`
|User (variable) Display Name (Nick)|`${tempVars("user_object").displayName}`
|User (variable) Avatar URL|`${tempVars("user_object").user.avatarURL}`



## Server Info

| Usage | Script |
| :--- | :--- |
| Return List of Members in a Role | `tempVars("role").members.map(m=>m.user.tag)`
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
| Store Count members in a role | `${tempVars("role").members.array().length}`|

# Messaging
## Embeds
Usage | Script
:- | :-
Add Field to Embed message | `tempVars("test").addField("Test Name","Test Value",[inline]);` <br/> `[inline]` = True or False
Add Footer to Embed message | `tempVars("test").setFooter(member.displayName, msg.author.avatarURL)`

## Miscellaneous
Usage | Script
:- | :-
Send a message (hard coded text) | `msg.channel.send("your message here")`
Send a message (variable) | `msg.channel.send(tempVars("some_variable"))`
Send a message (with mixed text & variables) | `msg.channel.send("some text here " + tempVars("some_variable") + " and some more text")`
Send a message (to another channel)| `msg.guild.channels.find("name","bot-logs").send("test in another channel")` <br/>*can use "ID" instead of "Name"*
Log to console | `console.log("your text here")`
Add reactions to message <br/> *works on normal messages or embeds* | `msg.channel.send(tempVars("test"))` <br /> `.then(function (message) {` <br /> `message.react("👍")` <br /> `message.react("👎")` <br /> `}).catch(function() {` <br /> `msg.channel.send("is broke yo")` <br /> `});`
Collect reactions to a message | `const filter = (reaction, user) => reaction.emoji.name === '👍'`<br/>`tempVars("your_message").awaitReactions(filter, { time: 15000 })`<br/>`.then(collected => msg.channel.send("Collected ${collected.size} 👍 reactions"))`<br/>`.catch(console.error);`

# Miscellaneous
## Identifiers
| Usage | Script |
| :--- | :--- |
| get the bot as a client (user) | `${this.getDBM().Bot.bot` |
| get the bot as a client (user) | `${client` |
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

## Uncategorized
Usage | Script
:- | :-
Ban User <br/><i>requires user's ID</i> | `msg.guild.ban(tempVars("user_id"))`<br/>`.then(user => console.log("Banned " + user.username + " from" + msg.guild.name))`<br/>`.catch(console.error);`
Unban User <br/><i>requires user's ID</i> | `msg.guild.unban(tempVars("user_id"))`<br/>`.then(user => console.log("Unbanned " + user.username + " from" + msg.guild.name))`<br/>`.catch(console.error);`
Find Emoji | `client.emojis.find("name", "NameOfTheEmoji")`
skip ahead some number<br/>_there are kinks to this still_ | `this.callNextAction(#)`
Show current date/time in timezone | `new Date().toLocaleString("en-US", {timeZone: "America/New_York"})`
Create server invite | `msg.channel.createInvite({temporary: true}," Showing the usage").then(invite=> msg.channel.send(invite.url))`
Add role to cmd author | `member.addRole(tempVars("newrolename"));`
Stop the bot | `process.exit(0);`
Change nickname (command author) | `msg.member.setNickname(tempVars("new_nick"))`<br/>`.then(console.log)`<br/>`.catch(console.error);`
Get Variable value | `this.getVariable(1,"varname",cache);`
Store Variables via script | `this.storeValue(output, 1 ,"totalUsers", cache)` <br /> (*1 = temp, 2 = server, 3 = global*)
