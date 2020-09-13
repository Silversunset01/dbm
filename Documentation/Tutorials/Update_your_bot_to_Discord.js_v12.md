# Updating your bot for Discord.js v12
Discord.js has updated from v11 to v12. From their [update guide](https://discordjs.guide/additional-info/changes-in-v12.html#before-you-start)
> After a long time in development, Discord.js v12 has been formally released, meaning it's time to update from v11 to get new features for your bots! However, with those new features comes a lot of changes to the library that will break code written for v11.

This page will outline the steps for updating your DBM bot. This change is REQUIRED or your bot will stop working.

## BEFORE YOU BEGIN
You should back up your data folder for your bot. Simply save a copy of the folder elsewhere on your computer *just in case* (this is good practice to begin with but it deserves a special callout here).

## Updating your DBM in Steam (from beta)  
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
1. Make sure your `bot.js` is up to date. Go to `Options` then check `Automatically Update Bot.js` if it isn't already.
2. Update your actions folder: click `File`, then click `Update Default Actions/Events/Extensions`
3. Check your discord.js version: click `Project`, then click `Module Manager` - you should just be able to delete anything in the `discord.js` box and it will default to "the most recent"

At this point DBM should restart and update.  
![](https://cdn.discordapp.com/attachments/481550058387537920/722119085386760202/DBM1_6_0Demo.gif)  

## Enabling Intents  
**From SRD:** 
> Another thing Discord is adding is "bot intents". Long story short, you must enable certain "event categories" on your bot in the Discord Developer Portal for them to work. Furthermore, you also must specify which categories you wish to use in your bot itself.   
> In order to comply with this system, the `v1.6.5` update has provided a "Bot Intents" extension. By default, it will simply enable all the event categories except for the two special ones: "Server Member Events" and "Server Presence Events". These control events like "Member Join Server" and "Member Leave Server".  
> The reason they are special is because they turned off by default and must be turned on in the Developer Portal. Furthermore, your bot either must be in less than 100 servers or whitelisted to enable them (in the near future).  

### To enable them:
1. First go to the `Developer Portal -> Bot` and scroll down. You can check the boxes to enable them  
![](https://cdn.discordapp.com/attachments/481550058387537920/732970924592070687/FqovuRfUlc.gif)  
2. Second, in Discord Bot Maker, go to `Extensions -> Bot Intents` (If it does not appear, first do `File -> Update Default Actions/Events/Extensions`).  
![](https://cdn.discordapp.com/attachments/481550058387537920/732970955751686234/QAt3KKpoqZ.gif)  
3. Enable the intents. You can either select "All Intents", or use "Custom" to toggle which ones you'd like specifically. 
