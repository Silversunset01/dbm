# How do I set my bot's activity to "... on X servers"

Without mods, you can set the bot's activity to playing or streaming. Using mods, you can also set it to watching and listening.
So, the only thing you'll need is a `Set Bot Game` or a `Set Bot Activity` action. Create one of them, and set the text to: `${client.guilds.cache.size} servers`. And... that's it! Now run the command or put the action inside an On Bot Initialization event!  
![](https://i.imgur.com/zjSkZ56.png)