# Coming soon
This will be populated Soon™ - like when its not 1:30am.

# Bot Client Control
## Get Bot as member
## Leave Server
## Set bot Activity

# Other Stuff

----
## Call Command/Event
This action allows you to call another command or event from the command (or event) you're currently running. For example: say you have an event which logs `${member} ran ${tempVars("command")} in ${tempVars("channel")}` to a logging channel, but you do not want to add the actions to every single command. You could create an event with no trigger, and use **Call Command/Event** to call those actions from any command you wish to log.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/callcommandevent.PNG)  

----
## Control Variable
This action allows you to control the value of a variable.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/controlvariable.PNG)  

----
## End Action Sequence
This action has no agruments, and simply stops the bot from running anything else in the current command. This is useful for running commands with multiple options (like a `!help` command) where you want to run specific actions based on what is input by the user.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/endactionsequence.PNG)  

----
## Generate Random Number
This command will generate a random whole number between the two numbers you specify.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/generaterandomnumber.PNG)  

----
## Run Script
This action allows you to run your own custom script within the bot. You can enter *almost* any valid JavaScript (including Discord.js) into this action to run from within the bot. This is useful for creating your own custom actions for any missing items you wish to use.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/runscript.PNG)  

----
## Store Command Params
This action allows you to store the users input and use it within the command. Additional information on storing command parameters [can be found here](https://silversunset.net/dbm/new/tutorials#store-command-parameters)  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/storecommandparams.PNG)  

----
## Wait
This action tells the bot to pause for an amount of time before continuing.
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/wait.PNG)  

# Role Control
## Create Role
## Delete Role
## Edit Role
## Find Role
## Set Role Permissions
## Store Role Info

# Server Control
## Change Server
## Control Server Data
## Find Server
## Set Server Icon
## Set Server Name
## Set Server Region
## Set Server Splash Screen
## Set Server Verification
## Store Server Info
