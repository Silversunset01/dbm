# Frequently Asked Questions

# What...
## ...language is DBM/my bot written in?
DBM uses JavaScript, HTML and CSS, while your bot uses [Node.js](https://nodejs.org/en/) and [Discord.js](https://www.npmjs.com/package/discord.js) to interact with the [Discord API](https://discordapp.com/developers/docs/intro).  

## ...is the airspeed velocity of an unladen swallow? 
An unladen European swallow travels at approx 24mph (or 11 meters per second). You're welcome.  

# How...
## ...can I add actions to my bot that do not already exist? 
You can use the Run Script action to create your custom actions using JavaScript. Or you can download mods which are user-created actions that are available for use. You can type `!info mods` in the discord server or visit https://dbm-network.org/mods.  

# Why...
## ...won't my bot do what I am telling it to do.
You may have created a command that it can't interpret, or there is a corrupted file in the folder.  

**The first thing you should do is check your bot's log** (under the Project menu, choose Open Bot Log) and see what sort of errors it gives you. Often the error will tell you exactly what the problem is. Some errors can be found [here](https://silversunset.net/dbm/troubleshooting) with their resolutions.  

If the bot is still not working as expected after you've checked the log and attempted to troubleshoot, you can ask in the `support` channel of the main DBM guild (or the DBM Mods guild if your error relates to a mod).  

** To get a good answer from the helpers in Discord** you should provide the following information:  

* What is your command. **Example:** `My command is !ping`  
* What is your command supposed to do. **Example:** `It is supposed to tell me the ping of the bot in milliseconds`  
* What is it *actually* doing. **Example:** `Instead, it is saying "false"`  
* What does your bots log show. **Example:** `I checked my bot log and it says "client is not defined"`  

## ...does my bot keep shutting off? 
When you close DBM your bot will shut down. If you want your bot to run always you'll need to keep DBM running, run the bot via command prompt (which you must also keep on and running), or host it externally on a VPS (virtual private server).  
You can run `!info vps` in the discord server for some VPS options, and some hosting tutorials can be found [here](https://silversunset.net/dbm/tutorials#running-your-bot-247).  

## ...won't anyone help me make a kick/ban/dm all command?
Inviting your bot to a server and then using it to kick, ban, or DM all users is an abuse of your bot and violates the Discord TOS.  see below for more info.  

# Can I ...
## ...have my bot DM all users in a server?
No, this is a violation of the Discord TOS and may result in your account being banned. Please see this helpful communication from Discord staff regarding this:  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/image.png)

## ...run two bots at the same time? 
Sort of. You cannot run two bots in DBM at the same time, but you can run a second instance of your bot via command prompt. [Click Here](https://silversunset.net/dbm/tutorials#running-your-bot-247-running-your-bot-with-cmd) for instructions.  

## ...make rainbow roles? 
No. This is API abuse and is not allowed by the Discord API. [More information on rate limits can be found here](https://discordapp.com/developers/docs/topics/rate-limits). More specifically because of [this](https://discordapp.com/developers/docs/legal) from the Discord TOS:  

`2.7 Rate Limits. You will not attempt to exceed or circumvent limitations on access to and use of the SDK or API, exceed or circumvent any limitation on the API calls you may make, or otherwise use the SDK or API in a manner that exceeds reasonable request volume, or constitutes excessive or abusive usage (“Rate Limits”). If Discord, in its sole discretion, determines that you have attempted to exceed or circumvent Rate Limits, or other controls that limit use of the SDK or API, then your ability to use the SDK or API may be temporarily suspended or permanently blocked.`  
![](https://i.imgur.com/JAL0vNl.png)

## ...have a space between my prefix & command? 
Sort of. The way the bot is coded you cannot have a space between the prefix/command or in the command itself. The only way around this is to do an "any message" event (or command if you have beta), and evaluate the message to see if your desired string is included in the text and if so run the command. You may also want to add logic to see if your string is at the beginning of the message to avoid false triggers.  
So yes, you **can** do it, but not simply by throwing a space in the command name.  
