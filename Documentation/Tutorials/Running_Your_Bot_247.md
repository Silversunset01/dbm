# Running your bot 24/7
By now you may have noticed that when you close DBM your bot shuts down - this is *normal and expected behavior*, the bot can only stay online when the program running it is online.  
  
You have three options to keep the bot running 24/7  
1. **Keep DBM open all the time** - This is not recommended because the bot *will* crash periodically and DBM does not automatically restart  
2. **Run the bot on your computer via Command Prompt (CMD)** - This is *slightly* better than running directly with DBM because you *can* create a restart script to handle the bot crashing. HOWEVER, most home internet providers are not designed for this sort of always-running access if your internet has caps you may hit them for larger (or music) bots. Using this method you can technically run the bot on any computer that will allow you to run node.js, which means you could run it on a Mac or Raspberri Pi machine should you have access to those.<br/>
<a href="tutorials?topic=Running_via_Command_Prompt">Click for Command Prompt (CMD) Tutorial</a>  
<a href="tutorials?topic=Restarting_Automatically">Click for Restart Script Tutorials</a>  
3. **Host the bot on a VPS** - A VPS (Virtual Private Server) is a more 'correct' way to host a bot. These servers are generally located in data centers designed for always-on use, and can often be found for a couple of dollars per month. There *are* some 'free' versions (i.e. Heroku and Glitch), but they are NOT designed for bot hosting, they are designed for things like websites and if you choose to use them be aware that they are unstable and your bot will have problems.
<a href="?topic=VPS_Tutorials">Click for VPS Tutorials</a>