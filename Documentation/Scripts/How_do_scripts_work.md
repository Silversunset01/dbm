# Creating your scripts
Most things that are not available as actions can be run as a script either in the `Run Script` action or in any box that allows for text entry using `${}`.  

Sidenote: If you are trying to use a script in a text-entry field you'll need to surround it with `${}` brackets so the program understands that it is a script and not text. However, when using a Run Script action you *should not* use the brackets.  
![](https://github.com/Silversunset01/dbm/raw/master/screenshots/scriptex.png)  

## Handy Scripting Resources
* [W3Schools](https://www.w3schools.com/js/) - basic javascript reference  
* [Discord.js](https://discord.js.org/#/) - discord's custom JS library  

# How to use Scripts in DBM
There are three main ways to use scripts within DBM.  

## Print a value
For scripts that display information, you can simply put the script into your send message or embed, ensuring it is surrounded by `${}`. Within DBM anything in `${}` will evaluate as javascript and in this context will print the results.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/HowToScript1.PNG)  

## Use as a variable for other actions
You can also use simple scripts in other actions as a value rather than using other actions to create the value first. An example of this would be creating an Embed message, instead of having to use "Store member info" or "Store server info" for the username, guild icon, user avatar, etc you can reduce the number of actions you use by using the script version to pull the information.  
**Note:** Sometimes you will need to enclose the script in brackets `${}`, but other times you will not. You can test this by right-clicking into the field and inserting *any* variable. If the variable inserts with brackets you'll _probably_ need them for the scripts as well.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest.png)  

## Run complex JavaScript
You can run JavaScript (including Discord.js) within DBM by using the RUN SCRIPT action. This allows you to create custom actions that the bot does not already have (either in the vanilla/beta version or via mods).  
When using this method **do not** put brackets `${}` around the data. A run-script action will run anything within it as a script, so adding the brackets is overkill (and will cause DBM to not understand what you're doing and the script may fail).  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/HowToScript2.PNG)  
