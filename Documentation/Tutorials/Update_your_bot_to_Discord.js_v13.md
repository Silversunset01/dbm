# Updating your bot for Discord.js v13

This page will outline the steps for updating your DBM bot (to Discord.js v13).

## BEFORE YOU BEGIN
You should back up your data folder for your bot. Simply save a copy of the folder elsewhere on your computer *just in case* (this is good practice to begin with but it deserves a special callout here).

## Updating Node.js
Discord.js v13 requires Node.js v16 or later. You can update your Node.js via the website: https://nodejs.org/en/download

## Updating your DBM in Steam (from beta)  

**If you haven't been using beta (or aren't sure what beta is), you can skip this.**

Beta should no longer be used, the main program is currently the most up-to-date version.  To upgrade from the old beta to the updated version follow these steps:  
1. Close DBM
2. Open Steam
3. Open your software library
4. Right-click Discord Bot Maker
5. Select Properties (at the bottom)
6. Select Betas
7. Select NONE
8. DBM should update now. Otherwise restart Steam.

## Update the DBM Project
1. Make sure your `bot.js` is up to date. Go to the `Editor Settings` in the Settings tab then check `Automatically Update Bot.js` and `Automatically Update Modules` if they aren't already checked.
2. Update your actions folder: click `File`, hover `Actions/Events/Extenions` then click `Update and re-read Defaults`
3. Check your discord.js version: click `Project`, then click `Module Manager` - you should just be able to delete anything in the `discord.js` box and it will default to the version that the program supports.

At this point DBM should restart and update.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/DBM2_0Demo.gif)  

## Enabling Intents  
Intents are privileges that allow your bot to receive information from miscellaneous events (such as member joins, text messages sent, etc.). Intents are required for certain events and prefix-based commands (as opposed to slash commands).

**NOTE:** Intents can only be used by unverified bots that are in less than 100 servers. Once your bot reaches 100 or more servers, you will need to request verification from Discord to use intents.

### To enable them:
1. First go to the `Developer Portal -> Bot` and scroll down. You can check the boxes to enable them  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/DBM2_02Intents1.gif)  
2. Second, in Discord Bot Maker, go to `Extensions -> Bot Intents`.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/DBM2_0Intents2.gif)  
3. Enable the intents. You can either select "All Intents", or use "Custom" to toggle which ones you'd like specifically. 

## Enabling Partials 
Similarly to intents, partials allow you to receive certain events with minimal information. You may need to enable "Channel" partial to allow your bot to receive message events from DMs.

### To enable them:
1. Go to `Extensions -> Bot Partials`.
2. Enable partials by selecting "Custom" and selecting each preferred partial.