# Using @botname to trigger the bot
To call the bot via @botname instead of using a command you can follow these steps:

**1. create a command with the command type "Any Message"**
This command will evaluate each message and look for a mention that matches the bot's ID  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/ping1.png)

**2. Store the text of the message**
This can be done using the Store Command Params action (parameter 1).

**3. use Check Variable to check if the message contains the ping for your bot**
If it starts with the ping you're checking for, continue the actions. Otherwise, have it stop the action sequence.
*protip: you can use any ping here if you wanted to have it look for a specific user or role*  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/ping3.PNG)

**4. Store any other information that you want from the message**
You can store the other text of message using the Store Command Params action again (with another parameter number that isn't 1).

**5. Send a message (or whatever else you want)**
Add any other actions that you would use for a normal command, such as Send Message.