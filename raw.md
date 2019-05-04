# Silver's Raw Data

This section is entirely for my raw code pastes so I dont lose project i've made. I do not use beta, so use at your own risk.
Mostly this was updated because ghostbin keeps dying and i wanted to have all of my raw data hosted on my own pastebin.

Commands are sorted into categories from the Raw Data server. 

# Useful
## Dev Testing Cmd - ?emit
**Bot Dev Testing Command - ?emit &lt;type&gt;**  
This command does not require mods or beta  
https://www.silversunset.net/paste/161  

When run this command will emit an event to mimic certain events for testing purposes. For example: emitting a guildMemberAdd event will simulate a user joining your server without the need for an alt account.  

The current event <type> options are:  
- memberjoin - emitted when a member joins the guild   
- memberleave - emitted when a member leaves the guild (either willingly or via kick)   
- ban - emitted when a member is banned  
- unban - emitted when a member is banned  
- error- throws an uncaught error - if you use Lasse's custom script it will log to console  
  
## Server Info
**Comprehensive Server info command - no mods needed**  
This command uses scripts to return server information and can be run without mods.   

command: https://silversunset.net/paste/94 *converted from ghostbin*  
in action: https://i.imgur.com/w9a6V1m.png  
![](https://i.imgur.com/w9a6V1m.png)

## Bot Info
**Comprehensive Bot Info command - no mods needed**  
command: https://www.silversunset.net/paste/197  
In Action: ![](https://i.imgur.com/yRPzpdr.png)  

## Current Time in Timezone
**Show current time in a specified timezone (mods needed for the bot member items)**  
This command will show you the current time in a requested timezone. It only comes with 8 timezones preconfigured (PST, MST, CST, EST, UTC, GMT, EET, AEST).   
To add more, add them in the 'run script' action, add a new case "ABBR": for each one you'd like.  
Running the command without a timezone will give a syntax message instead.  
Mods are only used in this for the "get bot as member" action for the embed. If you leave that out you should be able to run this without mods as its all scripts.  
command: https://silversunset.net/paste/95 *converted from ghostbin*  
screenshot: https://i.imgur.com/xo39CJJ.png  
![](https://i.imgur.com/xo39CJJ.png)  
**The Bot will need to run via CMD otherwise DBM will error!**

## Time until Specified time
**Display time until "specified time" (mods needed for bot member info)**  
This command will show the time between "now" and "a specified time" that you type in on the command. Typing !timeto without a correct date will give a syntax message.   
Times must be in the following format: March 4, 2018 23:18:00 GMT-0500 (if you leave off GMT-0500 it will assume UTC)  
code: https://silversunset.net/paste/96 *converted from ghostbin*  
screenshot: https://i.imgur.com/4PYckb7.png  
![](https://i.imgur.com/4PYckb7.png)  

## Log bot DM's to Channel
**Log all DM's to the bot to a channel (No mods or beta needed)**  
This is an event that will log all DM's users send to your bot to a single channel in a server.  
These are EVENTS that trigger ON ANY MESSAGE. In order to use them you will need to supply your server id and your desired log channel or the commands will not work. One outputs an embed message, the other a normal bot message, your choice which to use.  
Event (embed version): https://silversunset.net/paste/97 *converted from ghostbin*  
Event (normal version): https://silversunset.net/paste/88 *converted from ghostbin*  
Screenshot: https://i.imgur.com/wd2grr0.png  
![](https://i.imgur.com/wd2grr0.png)  

## Move user to voice channel
**Move User from one voice channel to another**  
command syntax is `.voice <channel name> @user` and will move the mentioned user from their current voice channel to a new one.  
NOTE if they are not currently IN a voice channel this will do nothing.  
https://silversunset.net/paste/71  

## Replace [prefix] with @bot ping
**Activate the bot with an @mention instead of a command**  
This is an event that will let you `@mention` your bot rather than needing a command.  
This does not need beta or mods to function  
In use: copy the raw code from https://silversunset.net/paste/86  
On LINE 16, replace `403205552064430100` with your bot's ID.  

## Display all users with Role
This command `?rolelist <role name>` will display all users in a specified role. If an invalid role is given an error message will be displayed.   
This does not require beta or mods  
Command: https://silversunset.net/paste/87  

# API Use
## Mojang Services Status 
**Mojang Services Status (mods required)** 
This is a combination of one event and one command.  
- The event will ping Mojang's services api's every 60 seconds and save the data (this is to prevent being ip-blocked from too many queries)  
- The command will query the saved data and return "all is well" or "something may be broken" for each service  
This is meant to mirror the Service Status check on https://help.mojang.com/  
Command raw data: https://pastebin.com/s72SWd5r | https://silversunset.net/paste/98  
Event raw data: https://pastebin.com/BdPRDCGH | https://silversunset.net/paste/99  
In action: https://i.imgur.com/l1PBeE7.png  
![](https://i.imgur.com/l1PBeE7.png)

## MCStatus
**MC Status  (mods required)**  
This is one command and one event that work together to prove specific minecraft server status information.   
- The event: pings your desired minecraft servers (currently supports 5 but you can add/remove as needed) every 60 seconds and saves the data to a server variable  
- The command (!mcstatus) pulls the data from the server variables and displays the # of users online (i.e. 10 of 200 users)
You can easily change the output of this by parsing additional fields from the api query, for things like MOTD and Version)  
Code data: https://pastebin.com/F1EPFtXK | https://silversunset.net/paste/53  
Event data: https://pastebin.com/bXAq2Tst | https://silversunset.net/paste/54  
In action: https://i.imgur.com/2cWM3H7.png  
![](https://i.imgur.com/2cWM3H7.png)  

# Moderating
## Nickname moderation
`.nickname <username> <allow|deny>` - https://silversunset.net/paste/58 - allow or deny a user from setting their nickname (default is allow)  
`!nick <username>` - https://silversunset.net/paste/59  - lets a user set their nickname  
`.nick-blacklist (command)` - https://silversunset.net/paste/60 - displays all users who are currently flagged as "deny" for nick changes  
`.nick-blacklist (event)` - https://silversunset.net/paste/61 - required event to be used with the .nick-blacklist command  


