# Coming soon
This will be populated Soon™ - like when its not 1:30am.

# Other Stuff

## Call Command/Event
This action allows you to call another command or event from the command (or event) you're currently running. For example: say you have an event which logs `${member} ran ${tempVars("command")} in ${tempVars("channel")}` to a logging channel, but you do not want to add the actions to every single command. You could create an event with no trigger, and use **Call Command/Event** to call those actions from any command you wish to log.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/callcommandevent.PNG)  

## Control Variable
This action allows you to control the value of a variable.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/controlvariable.PNG)  

## End Action Sequence
This action has no agruments, and simply stops the bot from running anything else in the current command. This is useful for running commands with multiple options (like a `!help` command) where you want to run specific actions based on what is input by the user.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/endactionsequence.PNG)  

## Generate Random Number
This command will generate a random whole number between the two numbers you specify.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/generaterandomnumber.PNG)  

## Run Script
This action allows you to run your own custom script within the bot. You can enter *almost* any valid JavaScript (including Discord.js) into this action to run from within the bot. This is useful for creating your own custom actions for any missing items you wish to use.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/runscript.PNG)  

## Store Command Params
This action allows you to store the users input and use it within the command. Additional information on storing command parameters [can be found here](https://silversunset.net/dbm/tutorials#data-store-command-parameters)  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/storecommandparams.PNG)  

## Wait
This action tells the bot to pause for an amount of time before continuing.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/wait.PNG)  

# Role Control
## Create Role
This action allows you to create a role and optionally use custom options like the name, color, position, and others.  
![](https://i.need.dbm-support.site/g6p6.png)

## Delete Role
This action allows you to delete the specified role.  
![](https://i.need.dbm-support.site/zxtw.png)

## Edit Role
This action allows you to edit a specified role's name, color, position and other options.  
![](https://i.need.dbm-support.site/zxm4.png)

## Find Role
This action is used to find a role by its name, id, or color. This is useful for everything in the roles category such as create/delete/edit role.  
![](https://i.need.dbm-support.site/a3rj.png)

## Set Role Permissions
This action is used to edit any permission that the specified role has. The bot can only edit a role that is under its highest role & if they have the "Manage Roles" permission + the one they wish to edit.  
![](https://i.need.dbm-support.site/s6o4.png)

## Store Role Info
This action is very useful as it allows you to store anything about the role.  

# Server Control
## Change Server
This allows you to change the server the bot is viewing. Be aware you need to find a server first using the Find Server action.  
![](https://i.need.dbm-support.site/nfdt.png)

## Control Server Data
This action is used to control some kind of data in just the server. For example, you can control the servers "member_count" data and that will be put in servers.json in your data folder.  
![](https://i.need.dbm-support.site/ppf7.png)

## Find Server
This action allows you find a server by its name, id, member count, owner id, and a lot more options. It is useful for the Change Server action.  
![](https://i.need.dbm-support.site/xez4.png)

## Set Server Icon
This action allows you to set the current servers or a specified variable's icon.  
![](https://i.need.dbm-support.site/g4fq.png)

## Set Server Name
This action allows you to set the current servers or a specified variable's name.  
![](https://i.need.dbm-support.site/xtxa.png)

## Set Server Region
This action allows you to set the current servers or a specified variable's region.  
![](https://i.need.dbm-support.site/7r2c.png)

## Set Server Splash
This action allows you to set the current servers or a specified variable's splash. (Discord Partners only)  
![](https://i.need.dbm-support.site/vodp.png)

## Set Server Verification
This action allows you to set the current servers or a specified variable's verification level.  
![](https://i.need.dbm-support.site/7scf.png)

## Store Server Info
This action allows you to store 17 different things about a server.  
![](https://i.need.dbm-support.site/jbv6.png)
