# Error: Member Join/Leave events arent working
If your Member Join/Leave Server events aren't being triggered or if you're getting a [GUILD_MEMBERS_TIMEOUT]: Members didn't arrive in time. error (keep in mind this error could be related with your internet connection as well), do the following:
1. Make sure your Discord Bot Maker is up to date in Steam (just make sure it has no updates pending)
2. Inside DBM: File > Update Default Actions/Events/Extensions
3. Restart DBM
4. Extensions > Bot Intents
5. Select the Server Member Events (it won't make your bot crash yet, read below)
6. Go to the Developer Portal https://discord.com/developers/applications/
7. Click on your application
8. On the left, click Bot
9. Scroll down to "Privileged Gateway Intents"
10. Enable "SERVER MEMBERS INTENT"
That should do it.

As it says in the Bot Intents extension, you will need to verify (whitelist) your bot for the Server Member Events intent, otherwise your bot will be limited to 100 servers (this will only take effect after October this year).
To verify (whitelist) your bot, do the following (your bot needs to be in more than 75 servers):
1. Go to the Developer Portal https://discord.com/developers/applications/
2. Click on your application
3. On the left, click Bot
4. At the top there should be a button to start the verification