# How do I set my bot's activity to "... on X servers"

In the "Set Bot Activity" action, set the text to: `${client.guilds.cache.size} servers` and then set the activity type to any that you desire. And... that's it! Now run the command or put the action inside an event!  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/activity.png)

Your ideal options for event triggers are "Bot One-Time Initialization" and "On Interval"

**WARNING:** If you choose to use "On Interval", be sure to use an interval of atleast 5 minutes (300 seconds). If your interval is shorter, it may lead to a [rate limit](https://discord.com/developers/docs/topics/rate-limits) from Discord.