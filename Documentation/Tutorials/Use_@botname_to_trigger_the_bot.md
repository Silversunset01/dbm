# Using @botname to trigger the bot
To call the bot via @botname instead of using a command you can follow these steps:

**1. create an EVENT that triggers on ANY MESSAGE**
This event will evaluate each message and look for a mention that matches the bot's ID  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/ping1.png)

**2. Store the text of the message**

**3. use Check Variable to see if the message contains the ping for your bot**
If it contains the ping you're checking for, continue the actions. Otherwise, have it stop or your bot will just process on every message sent which is crazy.
*protip: you can use any ping here if you wanted to have it look for a specific user or role*  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/ping3.PNG)

**4. Store any other information that you want from the message**
At the very least I recommend storing the channel so you can send a response on the same channel.
If you're using the @botname to trigger a command you'd then need to parse the text of your message for the rest of the command. That can be a bit complicated and will require you to learn some JS.

**5. Send a message (or whatever else you want)**
The raw code for this example can be found here https://silversunset.net/paste/86
*make sure you add it as an EVENT, not a command.*