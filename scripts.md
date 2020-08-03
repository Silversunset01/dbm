# Creating your scripts
Most things that are not available as actions can be run as a script either in the `Run Script` action or in any box that allows for text entry using `${}`.  

Sidenote: If you are trying to use a script in a text-entry field you'll need to surround it with `${}` brackets so the program understands that it is a script and not text. However, when using a Run Script action you *should not* use the brackets.  
![](https://github.com/Silversunset01/dbm/raw/master/screenshots/scriptex.png)  

## Handy Scripting Resources
* [W3Schools](https://www.w3schools.com/js/) - basic javascript reference  
* [Discord.js](https://discord.js.org/#/) - discord's custom JS library  

# How to use Scripts in DBM
There are three main ways to use scripts within DBM.  

## Print a value
For scripts that display information, you can simply put the script into your send message or embed, ensuring it is surrounded by `${}`. Within DBM anything in `${}` will evaluate as javascript and in this context will print the results.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/HowToScript1.PNG)  

## Use as a variable for other actions
You can also use simple scripts in other actions as a value rather than using other actions to create the value first. An example of this would be creating an Embed message, instead of having to use "Store member info" or "Store server info" for the username, guild icon, user avatar, etc you can reduce the number of actions you use by using the script version to pull the information.  
**Note:** Sometimes you will need to enclose the script in brackets `${}`, but other times you will not. You can test this by right-clicking into the field and inserting *any* variable. If the variable inserts with brackets you'll _probably_ need them for the scripts as well.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest.png)  

## Run complex JavaScript
You can run JavaScript (including Discord.js) within DBM by using the RUN SCRIPT action. This allows you to create custom actions that the bot does not already have (either in the vanilla/beta version or via mods).  
When using this method **do not** put brackets `${}` around the data. A run-script action will run anything within it as a script, so adding the brackets is overkill (and will cause DBM to not understand what you're doing and the script may fail).  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/HowToScript2.PNG)  

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
Replace | `.replace("old text", "new text")`
Switch | `switch(thing to eval) {` <br /> `case "OPT1": action to execute on match; break;` <br />`case "OPT2": action to execute on match; break;` <br />`case "OPT3": action to execute on match; break;` <br />`default: action to execute on match; break;` <br /> `}`
If/Then (Ternary) | `(A < 1 ? "value if true" : "value if false")`
If/Then (Normal) | `if(thing to evaluate) {value if true} else {value if false}`

# Information Storage
## Bot Info

| Usage | Script |
| :--- | :--- |
| Return Count of Members in all Bot Guilds | `${client.users.cache.size}` |
| Return Count of all Bot Guilds | `${client.guilds.cache.size}` |
| Return List of all Bot Guilds | `${client.guilds.cache.array()}` |
| Program memory usage \(in MB\) | `${Math.floor((process.memoryUsage().heapUsed / 1024)/1024)} MB` |
| Store the bot as a guild member (using the message sent) | `${msg.guild.me}`
| Store the client (using the message sent) | `${msg.guild.client}`
| Bot Ping | `${client.ws.ping}`
| Bot Rounded Ping | `${Math.floor(client.ws.ping)}` |
| Bots CPU | `${(process.cpuUsage().user / 1000000).toFixed(2)} Seconds`
| Bots Prefix | `${this.getDBM().Files.data.settings.tag}`
| Count of Commands in Bot | `${this.getDBM().Files.data.commands.length}`
| Count of Events in Bot | `${this.getDBM().Files.data.events.length}`
| Bot uptime<br/>_use tempVars("uptime-ms") to display this_ | `var uptime = process.uptime();`<br/>`var days = Math.floor((uptime % 31536000) / 86400);`<br/>`var hours = Math.floor((uptime % 86400) / 3600);`<br/>`var minutes = Math.floor((uptime % 3600) / 60);`<br/>`var seconds = Math.round(uptime % 60);`<br/>`var botuptime = (days > 0 ? days + " days, ":"") + (hours > 0 ? hours + " hours, ":"") + (minutes > 0 ? minutes + " minutes, ":"") + (seconds > 0 ? seconds + " seconds":"")`<br/>`this.storeValue(botuptime, 1, "uptime-ms", cache)`

## User Info

| Usage | Script |
| :--- | :--- |
|Author Username|`${msg.author.username}`
|Author Display Name (Nick)|`${member.displayName}`
|Author Created At| `${msg.author.createdAt}`
|Author Id|`${msg.author.id}`
|Author Tag|`${msg.author.tag}`
|Author Discriminator|`${msg.author.discriminator}`
|Author Avatar URL|`${msg.author.displayAvatarURL({ dynamic: true })}`
|Author Role List | `${member.roles.cache.array()}`
|Author Role List (truncated after 3 roles) <br/>*enter `${tempVars("role_list")}` into your send-message to view this output.*<br/>*output will display as `@role1,@role2,@role3 + # more roles!`* | `var roles = member.roles.cache.array();`<br/>`var len = roles.length;`<br/>`if (len > 3) {`<br/>`   var answer = roles.slice(0,3) + " + " + (len - 3) + " more!"`<br/>`} else {`<br/>`   var answer = roles`<br/>`};`<br/>`this.storeValue(answer, 1 ,"role_list", cache);`
|User (variable) Username|`${tempVars("user_object").user.username}`
|User (variable) Display Name (Nick)|`${tempVars("user_object").displayName}`
|User (variable) Id|`${tempVars("user_object").user.id}`
|User (variable) Tag|`${tempVars("user_object").user.tag}`
|User (variable) Discriminator|`${tempVars("user_object").user.discriminator}`
|User (variable) Avatar URL|`${tempVars("user_object").user.displayAvatarURL({ dynamic: true })}`

## Server Info

| Usage | Script |
| :--- | :--- |
| Return Server Name | `${msg.guild.name}` |
| Return Server Id | `${msg.guild.id}` |
| Return Server Icon URL | `${msg.guild.iconURL({ dynamic: true })}` |
| Return Server Region | `${msg.guild.region}` |
| Return Server Creation Date | `${msg.guild.createdAt}` |
| Return Server Verification Level | `${msg.guild.verificationLevel}` |
| Return Server Explicit Content Filter | `${msg.guild.explicitContentFilter}` |
| Return Server Owner Display Name | `${msg.guild.owner.displayName}` |
| Return Server Available Status | `${msg.guild.available}` |
| Return Server Member Count | `${msg.guild.memberCount}` |
| Return Server Emojis Count | `${msg.guild.emojis.cache.size}` |
| Return Server Count of Roles | `${msg.guild.roles.cache.size}` |
| Return Server Count of Channels | `${msg.guild.channels.cache.size}` |
| Return Server Count of Text Channels | `${msg.guild.channels.cache.find(c => c.type === 'text').length}` |
| Return Server Count of Voice Channels | `${msg.guild.channels.cache.find(c => c.type === 'voice').length}` |
| Store Count members in a role | `${tempVars("role").members.cache.size}`|
| Return List of Members in a Role | `tempVars("role").members.cache.map(m => m.user.tag)`
| Return Server Emojis List | `${msg.guild.emojis.cache.array()}` |
| Return # of Bot Accounts | `${msg.guild.members.cache.filter(m => m.user.bot).size}` |
| Return # of non-Bot Accounts | `${msg.guild.members.cache.filter(m => !m.user.bot).size}`
| Return Server Online members | `${msg.guild.members.cache.filter(m => m.user.presence.status === "online").size}` |
| Return Server Offine members | `${msg.guild.members.cache.filter(m => m.user.presence.status === "offline").size}` |
| Return Server Idle members | `${msg.guild.members.cache.filter(m => m.user.presence.status === "idle").size}` |
| Return Server DND members | `${msg.guild.members.cache.filter(m => m.user.presence.status === "dnd").size}` |
| Return Server AFK Channel | `${msg.guild.afkChannel}` |
| Return Server AFK Timeout \(in seconds\) | `${msg.guild.afkTimeout}` |

# Messaging
## Embeds
Usage | Script
:- | :-
Add Field to Embed message | `tempVars("test").addField("Test Name", "Test Value", [inline]);` <br/> `[inline]` = true or false (Defaults to false)
Add Blank Field to Embed Message | `tempVars("test").addField('\u200B', '\u200B', [inline])` <br/> `[inline]` = true or false (Defaults to false)
Add Footer to Embed message | `tempVars("test").setFooter(member.displayName, msg.author.avatarURL({ dynamic: true }))` <br/> or for plain text <br/> `tempVars("test").setFooter("your text here")`

## Miscellaneous
Usage | Script
:- | :-
Send a message (hard coded text) | `msg.channel.send("your message here")`
Send a message (variable) | `msg.channel.send(tempVars("some_variable"))`
Send a message (with mixed text & variables) | `msg.channel.send("some text here " + tempVars("some_variable") + " and some more text")`
Send a message (to another channel)| `msg.guild.channels.cache.find(c => c.name === "bot-logs").send("test in another channel")` <br/>*can use "id" instead of "name"*
Log to console | `console.log("your text here")`
Add reactions to message <br/> - *works on normal messages or embeds*<br/>- *If using this on an embed, you do not need the "send embed message" action, this will replace it* | `msg.channel.send(tempVars("test"))` <br /> `.then(async function(message) {` <br /> `await message.react("👍")` <br /> `await message.react("👎")` <br /> `}).catch(function() {` <br /> `msg.channel.send("is broke yo")` <br /> `});`
Collect reactions to a message | ```const filter = (reaction, user) => reaction.emoji.name === '👍'; tempVars("your_message").awaitReactions(filter, { time: 15000 }).then(collected => msg.channel.send(`Collected ${collected.size} 👍 reactions`)).catch(console.error);```

# Miscellaneous
## Identifiers
| Usage | Script |
| :--- | :--- |
| Get the bot as a client | `${client` or `${bot` |
| Get the bot as a guild member | `${msg.guild.me` or `${me` |
| The command message | `${msg` |
| The current server | `${msg.guild` or `${server` |
| The command channel | `${msg.channel` |
| The command author | `${msg.author` or `${user` |
| The command author as a guild member | `${msg.member` or `${member` |

## Lists
Usage | Script
:- | :-
Create a list out of items that have data following them | `.array()}`
Count items in the specified array | `.array().length}` or `.size}`
Count items in the specified list <br/> **or** <br/> count the length of a string | `.length}`
Find position of item in a list <br/>_If the bot returns -1 that means the item is not on the list. 0 means its the first item, 1 is the second etc_ | `${tempVars("yourList").indexOf(tempVars("yourItemToFind"))}`
Remove item from list | `${tempVars("yourList").splice(# to remove, 1)}`
Return the last # of items in a list | `tempVars("your variable").slice(Math.max(tempVars("your variable").length - 5, 1))` <br/> *where 5 is the number of items to return*
Return item at [position] from [list] | `tempVars("list").slice(tempVars("pos_num") - 1, tempVars("pos_num"))`

## Webhooks
Usage | Script
:- | :-
Create Webhook | `msg.channel.createWebHook('Webhook Name', { avatar: 'https://i.imgur.com/9kgJteG.png' })` <br/> The avatar is optional
Edit Webhook Name | `const hook = new DiscordJS.WebhookClient('webhook_id', 'webhook_token');`<br/>`hook.edit({ name: 'A very cool nickname' })`
Edit Webhook Avatar | `const hook = new DiscordJS.WebhookClient('webhook_id', 'webhook_token');`<br/>`hook.edit({ avatar: 'https://i.imgur.com/9kgJteG.png' })`
Edit Webhook Name & Avatar | `const hook = new DiscordJS.WebhookClient('webhook_id', 'webhook_token');`<br/>`hook.edit({ avatar: 'https://i.imgur.com/9kgJteG.png', name: 'a very cool name' })`
Send Message to Webhook | `const hook = new DiscordJS.WebhookClient('webhook_id', 'webhook_token');`<br/>`hook.send('a very cool message');`
Send Embed to Webhook | `const hook = new DiscordJS.WebhookClient('webhook_id', 'webhook_token');`<br/>`hook.send(tempVars("embed"));`

## Uncategorized
Usage | Script
:- | :-
Ban User <br/><i>requires user's ID</i> | `msg.guild.members.ban(tempVars("user_id"))`<br/>`.then(user => console.log("Banned " + user.username + " from" + msg.guild.name))`<br/>`.catch(console.error);`
Unban User <br/><i>requires user's ID</i> | `msg.guild.members.unban(tempVars("user_id"))`<br/>`.then(user => console.log("Unbanned " + user.username + " from" + msg.guild.name))`<br/>`.catch(console.error);`
Find Emoji | `client.emojis.cache.find(c => c.name === "NameOfTheEmoji")`
Jump to a specific action #<br/>_in this example you will jump to action #22_ | `let jumpTo = 22`<br/>`const index = Math.max(jumpTo - 1, 0);`<br/>`cache.index = index - 1;`<br/>`this.callNextAction(cache)`
Show current date/time in timezone | `new Date().toLocaleString("en-US", { timeZone: "America/New_York" })`
Create server invite | `msg.channel.createInvite({ maxAge: 0 }).then(invite => msg.channel.send(invite.url))`
Create server invite (Variable) | `msg.guild.channels.cache.find(c => c.name === tempVars("channel_name")).createInvite({ maxAge: 0 }).then(invite => msg.channel.send(invite.url))` <br/>*can use "ID" instead of "Name"*
Add role to cmd author | `member.roles.add(tempVars("newroleid"));`
Stop the bot | `process.exit();`
Change nickname (command author) | `msg.member.setNickname(tempVars("new_nick"))`<br/>`.then(console.log)`<br/>`.catch(console.error);`
Get Variable value | `this.getVariable(1, "varname", cache);`
Store Variables via script | `this.storeValue(output, 1, "totalUsers", cache)` <br /> (*1 = temp, 2 = server, 3 = global*)
Set Bot Username via script | `this.getDBM().Bot.bot.user.setUsername('a very cool username')`
Set Bot Avatar via script | `this.getDBM().Bot.bot.user.setAvatar('image_link')`
Set Server Name via script | `msg.guild.setName('a very cool name')`
Set Server Icon via script | `msg.guild.setIcon('image_link')`

# Advanced Scripts
## Select items from List (no dups)
This script will select the specified number of items from a list (array), without any duplicates, and puts them into a new list. These items are usable in DBM by entering `${tempVars("newList")}`  
**TO USE**  
- put this entire code block into a RUN SCRIPT action, set the "Interpretation Style" to "Evaluate Text Directly", and leave the "Store in" option as "Nothing"  
- Change the words "Your List Variable" to the variable name of the list you wish to use.  
- Change the value of `sel = 5` to be however many items you want to select  

```
//count how many items are in the list  
var myList = tempVars("Your List Variable");  
var myListLen = myList.length;  
var sel = 5;  

//Select # random numbers from the total length of the list of items  
var arr = []  
var ckarr = []  
while(arr.length < sel){  
    var r = Math.floor(Math.random()*myListLen) + 1;  
    if(ckarr.indexOf(r) === -1) {  
        arr.push(myList.slice(r-1,r));  
        ckarr.push(r);  
    };  
}  
this.storeValue(arr, 1, "newList", cache);  
console.log("I have selected " + sel + " items from your list: " + arr);  
```  

## Select items from List (dups)
This script will select the specified number of items from a list (array), and may have duplicates, and puts them into a new list. These items are usable in DBM, by entering `${tempVars("newList")}`  
**TO USE**  
- put this entire code block into a RUN SCRIPT action, set the "Interpretation Style" to "Evaluate Text Directly", and leave the "Store in" option as "Nothing"  
- Change the words "Your List Variable" to the variable name of the list you wish to use.  
- Change the value of `sel = 5` to be however many items you want to select  

```  
// Count how many items are in the list  
var myList = tempVars("Your List Variable");  
var myListLen = myList.length;  
var sel = 5;  

// Select # random numbers from the total length of the list of items  
var arr = []  
while(arr.length < sel){  
    var r = Math.floor(Math.random()*myListLen) + 1;  
    arr.push(myList.slice(r-1,r));  
}  
this.storeValue(arr, 1, "newList", cache);  
console.log("I have selected " + sel + " items from your list: " + arr);  
```  

## List all of the bot commands (names)
This script will get all the names of your bot's commands and will store them onto a temp variable called `commands`.  

```  
const array = this.getDBM().Files.data.commands.filter((c) => c && c.name).map((c) => c.name);  
this.storeValue(array.join(', '), 1, 'commands', cache);  
```  

## List all of the bot events (names)
This script will get all the names of your bot's events and will store them onto a temp variable called `events`.  

```  
const array = this.getDBM().Files.data.events.filter((c) => c && c.name).map((c) => c.name);  
this.storeValue(array.join(', '), 1, 'events', cache);  
```  

## Display a missing variable with alt text
This script will display some alternative text instead of "undefined" if a variable is missing.  
Copy this into a `Run Script` action, and make sure to choose `Evaluate Text Directly` from the dropdown.  
```  
var reason = tempVars("variable"); //change this to be your variable  
if (typeof reason == 'undefined') {  
    reasonType = "no reason"  
} else {  
   reasonType = reason  
};  
this.storeValue(reasonType, 1 ,"newVariableName", cache);  
```  
Replace `tempVars("variable")` with the variable you want to evaluate.  
Replace `newVariableName` with whatever you want to call the new variable (or leave it blank if you want).  
To call this new variable in your command/event type in `tempVars("newVariableName")`  
