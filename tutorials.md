# Tutorials
This section covers various tutorials and things that may be helpful.

## Official Tutorial Videos

* [DBM Tutorial #1 - Setting up the bot](https://youtu.be/5fE1_UqvVPQ)
* [DBM Tutorial #2 - How to use Commands](https://youtu.be/GOQcJ7a-cLc)
* [DBM Tutorial #3 - How to use Variables](https://youtu.be/BOzYGzbJZ8g)
* [DBM Tutorial #4 - Text Evaluations](https://youtu.be/XluYShxVhPI)
* [DBM Tutorial #5 - Obtaining Parameters](https://youtu.be/haAyykGaY_E)
* [DBM Tutorial #6 - How to use Events](https://youtu.be/lBEQBEXe2yQ)
* [DBM Tutorial #7 - How to Export the Bot](https://youtu.be/MNw7anSA06g)

# Data
Information relating to the storage and passing of data between commands or actions.

## Variables

[DBM Tutorial - Obtaining Parameters >](https://www.youtube.com/watch?v=haAyykGaY_E)

There are a few ways to store and reuse information in DBM.

* **Temp variable** - exists only for the duration of the command. Once the command action list is over the variable is 'forgotten' by the bot
* **Server variable** - exists for a single server. The bot will 'remember' these variable between commands but only for the server they were created in.
* **Global variable** - exists for the bot regardless of server or command.

## Store Command Parameters

You can store parameters entered into a command using the "Store command parameters" action. This will assume your parameters are using the default `space` \(`\s+`\) as a separator.

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/storeparams.png)

* Parameter Number:
  * This tells the bot which word to start on. Using 1 would mean "the first word after the command"; 2 would mean "the second word after the command" and so on.
  * DBM defines a "word" as a complete string of characters between your parameter separator
    * ex: If your separator is a space, a "world" would be anything between spaces - `this is four words`
    * ex: if your separator is a comma, a "word" would be anything between commas - `this is, two things`
    * Source Info:

* **One Parameter** - creates a parameter using a single word, beginning at the \# given in the "parameter number" field.
  * ex: `!prune 50 100` - using "One Parameter" and "1" your parameter would be `50`
  * ex: `!prune 50 100` - using "One Parameter" and "2" your parameter would return `100`
* **Multiple Parameters** - creates a parameter using multiple words separated by the character indicated in the bot settings(default space), beginning from the number you specify in "Parameter Number" and going to the end of the command input
  * ex: `!ban @Silversunset You are breaking the rules` - using "Multiple Parameters" and "2" your parameter would be `You are breaking the rules`
  * ex: `!ban @Silversunset You are breaking the rules` - using "Multiple Parameters" and "3" your parameter would be `are breaking the rules`
* **Mentioned Member** - stores the `@username` from a command as a parameter
* **Mentioned Role** - stores the `@role` from a command as a parameter
* **Mentioned Channel** - stores the `#channel` from a command as a parameter

# Miscellaneous Tutorials
## Adding a role on-join
Adding a role to users who join your server is quite simple.

1. **Create an event that is triggered ON MEMBER JOIN**

This event will detect every time someone joins your server, and when you enter a variable name in the box labelled `Temp Variable Name (stores member that joined):` it will store the user that joined. For this example we will call the variable `new-user`

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/autorole1.PNG)

2. **Find the role you want to apply to users** 

To apply a role you must first obtain the role object. Do this with a Find Role action. You can search by Role ID, Role Name, or Role Color (name or ID are the best options for this as they are the least likely to duplicate).

Give this role a variable name that you can easily identify later. Here we will search for the role called `Players` and store it as the variable name `default-role`

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/autorole2.PNG)

3. **Add the role to the member that joined**

You have stored both the member object for the user that joined (variable `new-user`) and the role object for your default role (variable `default-role`). Now you will select a ADD MEMBER ROLE action, and apply the role you stored to the member you stored.

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/autorole3.PNG)

**Thats it!**

Your new user now has a shiny new role.

## Custom Command Categories
![](https://i.imgur.com/Aw9bUbc.png)  
To create a custom command seperator category in DBM you can use HTML codes (_On the command name_). The fivefour pictured above are set as follows:  
`<s><center>--------------------</center></s>`<br/>`<center><b><div style="color:yellow;">MODERATION</div></center>`<br/>`<b><div style="color:red;">LEFT_ALIGNED</div>`<br/>`<b><div style="color:blue;text-align:right;">RIGHT_ALIGNED</div>`<br/>`<hr color=white width=75%>`

## Check variable (CaSe InSeNsItIvE)
When you use the `Check Variable` action DBM requires that it be an EXACT match, including case. That means  
```TeXt LiKe ThIs```  
is not the same as  
```text like this```  
or   
```TEXT LIKE THIS```   

The way to combat this is to convert your variable to the same case (either all upper-case or all lower-case) and compare that to your text. You will need to use `run script` for this to work.  
1. Store Command params  
    - this is the variable you will be testing, however you store it will depend on your command.  
    - For this example we will assume your variable is called `myInput`  
2. Run Script  
    - enter the following script into the box `tempVars("myInput").toLowerCase();`   
    - in the Store-in box underneath, store this as a new temporary variable called `myInputLowerCase`  
3. Check Variable  
    - Source Variable: Temporary Variable  
    - Variable name: `myInputLowerCase`  
    - Comparison Type: equals  
    - Value to compare to: "your text in all lower case with quotes around it"  
    - If True: continue  
    - iF False: end or skip, depending on your command  
   
## Generating a Random Response
A random response generator works for anything from a Magic 8 ball command to a coin toss command, to a random image, joke, phrase, or even paper/scissors/rock command. The bot will generate a random number and select a response based on the number chosen.

### Using Hardcoded Responses
**Action 1: Generate a random number** this will allow the bot to select one of your pre-programmed responses.

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/randtext.png)

**Action 2: Send message based on the number generated** using a switch/case script.

Switch/case basically evaluates the statement defined in `switch(tempVars("rand-num"))` and selects the matching response from the list of `case` items. The last item should always be `default` this is often used for error handling if no `case` match is found. In this case the possible outcomes of the `rand-num` variable are known and such a short list that `default` can be used to indicate the last match rather than an error.

`msg.channel.send("text")` will send a message to the current channel.

`break;` ends the action

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/randtext2.png)

#### Copyable code

#### Send message to the current channel:

```
switch(tempVars("rand-num")){
case 1: msg.channel.send("Answer 1"); break;
case 2: msg.channel.send("Answer 2"); break;
case 3: msg.channel.send("Answer 3"); break;
case 4: msg.channel.send("Answer 4"); break;
default: msg.channel.send("Answer 5"); break;
}
```

#### Save message as a variable to use later:
```
switch(tempVars("rand-num")){
case 1: var resp = "Answer 1"; break;
case 2: var resp = "Answer 2"; break;
case 3: var resp = "Answer 3"; break;
case 4: var resp = "Answer 4"; break;
default: var resp = "Answer 5"; break;
};
this.storeValue(resp, 1 ,"answer", cache);
```
(you would use `tempVars("answer")` to call this variable

### Using an Updatable List
This requires two commands, the first command will let you set up and add text to the list. The second will choose a response and print it.  
Command 1 raw code: https://silversunset.net/paste/120  
Command 2 raw code: https://silversunset.net/paste/121  

**1. command *?rndtext* - set up and edit the list of responses**

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/rndtextlist1.PNG)  

This command will allow you to either create a new list (if the list is deleted), or add items to the list. *Please note:* if you do not have beta you cannot use the Save Variable action, which means the list will be deleted every time the bot restarts. In that case you'll need to recreate and add the text each time. 

After actions 1 and 2 (to store the 'type' and 'text' if any) you'll need to use CHECK VARIABLE to determine what kind of command you're running: 

Action 3: Checks to see if the response = "new", if it does it will create the list named "rndlist" as a server variable (in action 5).    
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/rndtextlist2.PNG)  

Action 4: Checks to see if the response = "add", if it does it adds the text you've input to the list.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/rndtextlist3.PNG)    
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/rndtextlist4.PNG)  

Action 9: this is a catch-all. If you do not enter *?rndtext new* or *?rndtext add* this message will pop up reminding you of the proper syntax  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/rndtextlist5.PNG)

**2. command *?rndresponse* - retrieve random text from the list**  
This command simply pulls a random item from the list you created and prints it to chat

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/rndtextlist7.PNG)  

Make sure to select the SERVER var as your source list

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/rndtextlist6.PNG)  

When you've got that simply print the `${tempVars("rnd_response")}` to a send-message.

## How to Create an Embed Message
Your bot can send two types of message, a normal message (that looks like something you would type) an an embed message.
#### To create an embed you must have at least three actions

**1. Create embed** - you must create an embed first. If you've not created an embed you won't be able to send it.
[THIS IMAGE](https://dbm-mods.xyz/files/opera_2018-03-05_15-51-27.png) is a full explaination of what the fields mean.
For this example we'll use the following settings:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest.png)

**2. Add embed field OR set embed description** - If you want to add more content to your embed you can add a field or description. You can do both if you wish as well. The main difference is that the *Description* field does not have a required header, as the "embed title" is considered the header. the *embed field* item requires both a name and a description.
For this example we'll use the following settings (Both an embed description AND an embed field):

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest2.png)

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest3.png)

**3. Add a footer (with a script)** - If you don't have DBM Mods you can add an embed footer with a script. This will add the authors username and avatar to the embed footer.
If you want to add more text you can modify the script text.

*Script Text:* `tempVars("e").setFooter(member.displayName, msg.author.avatarURL)`

*Modified Script Text:* `tempVars("e").setFooter(member.displayName + " Some Other Text", msg.author.avatarURL)`

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest4.png)

**4. Send the embed** - after you've created the embed with all its fancy fields you must send it!
DBM Defaults to "Same Channel" which will send the embed to the same channel as the command message. You've got the same options here as you do a normal send-message. (If you send the message to a user the user will recieve a DM unless they have those blocked)

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest5.png)

**THE RESULT**:
If you've copied all of the steps above you should end up with an embed like this:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest6.png)

## How to create a SAY command
If you'd like to be able to type a message and speak as the bot its quite simple. This example makes the assumption that you will make the bot speak in *another* channel from the one you type into. The command would be `?say #channel <message>`

**1. Store the text you'd like the bot to repeat**  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/say1.PNG)

**2. Send the message to the #channel you mentioned**  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/say2.PNG)

## How do I set my bot's activity to "... on X servers"

Without mods, you can set the bot's activity to playing or streaming. Using mods, you can also set it to watching and listening.
So, the only thing you'll need is a `Set Bot Game` (using mods) or a `Set Bot Activity` (using mods) action. Create one of them, and set the text to: `${this.getDBM().Bot.bot.guilds.array().length} servers`. And.. that's it! Now run the command or put the action inside a On Bot Initialization event!  
![](https://i.imgur.com/zjSkZ56.png)

## Lists & Loops
### Lists
A list in DBM is nothing more than what JavaScript calls [an array](https://www.w3schools.com/js/js_arrays.asp), which is a special type of item that can be used to store multiple values within a single variable.  

For example: Say you have a list of roles:

- Role 1: Moderator
- Role 2: Streamer
- Role 3: Player  

And you want to do something with the roles, for example - search through all roles and find out if you have one called "Streamer". To do this,  you would put the roles into a list (array) and search through that for your matching item  
`var serverMembers = ["Moderator", "Streamer", "Player"];`

There are some lists that DBM stores for you automatically:  

- Server Members
- Server Channels
- Server Roles
- Server Emojis
- All bot servers
- Mentioned roles
- Command author roles  

**Creating Lists & Adding Items**
To create your own lists in DBM with the `Create List` action.  

To add items to the list you have created, you would use the `Add Item To List` action, select your list variable, and put the value you want to add to the list in the VALUE box  

**To add a value from another variable**, you *do not* need to use `${}` brackets, simply right click into the box and choose your variable, or type `tempVars("variableName")`  

**To add TEXT to your list** make sure to put the value in "quotation marks"

### Loops
Loops are very handy if you want to run the same code over and over, it saves you from having to type up the code for each instance.  

*For example:* Without using a loop, you would have to write five lines of code *for each role*, to do the following:
```
- Find the FIRST member in my server
- Find Role
- Add Role To Member
- Find Channel - my logging channel
- Send Message - [USER] now has [ROLE]

- Find the SECOND member in my server
- Find Role
- Add Role To Member
- Find Channel - my logging channel
- Send Message - [USER] now has [ROLE]

- Find the THIRD member in my server
- Find Role
- Add Role To Member
- Find Channel - my logging channel
- Send Message - [USER] now has [ROLE]
```  
While this may not be bad for a handful or roles, what happens if you have 20. Or 200? Or 500? Using a loop, you would only need to write the code a single time; it would look like this:  
```
- Get all of my MEMBERS in an array
- Loop through the array, and FOR EACH MEMBER
   - Find Role
   - Add Role To Member
   - Find Channel - my logging channel
   - Send Message - [USER] now has [ROLE]
```
Another way of looking at what a loop does is to say it like this:  
```
FOR EACH member IN ServerMembers DO myEvent

myEvent:
- Find Role
- Add Role To Member
- Find Channel
- Send Message
```

#### How to use a LOOP in DBM  
Adding a loop in DBM can be a little confusing. It requires TWO actions. 
**ACTION 1:** LOOP THROUGH LIST  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/loops.PNG)  
**Source list:** this is the list (array) you want to cycle through  
**Temp Variable Name:** When performing a LOOP in DBM, the software needs to create a temporary variable to save the "current item" in, and you can use that variable to perform tasks.  
**Event:** This is the name of the event that holds all of the actions you want the bot to perform on each item in your list.  
**Call Type:** Synchronous = "Only run one item at a time, and finish it before moving on to the next"; Asynchronous = "Try to run all items at the same time  

**ACTION 2:** An EVENT that contains all of the actions you want to perform during the loop. In this case you would use "Find Role", "Add Role to Member", "Find Channel", "Send Message" -> In the *add role to member* action, you would use the variable you created in your "Loop through list" action as your user role.  

**NOTE:** Because of the way DBM uses TEMPORARY variables, this will NOT show up in your right-click list. **YOU MUST TYPE THIS VARIABLE MANUALLY** by typing `tempVars("currentMember")` (or whatever you've named it). IT WILL STILL WORK. Just trust me.

### Synchronous or Asynchronous
Thread: the flow of actions, starting from one until it ends

These keywords refer to how the thread is treated and how the program flows. Whenever the call type is Sync, it waits until it recieves a callback or when the thread ends. Meaning that when the event or command is called, the main thread starts first, and if it is ever interrupted by a call, it does that action and if that action ends, returns to the main thread. Async is similar to Sync however, it runs alongside with the main thread.  

Purpose: This is useful in multithreading. Take this example:  

`Main Thread:
ControlVariable(A to 1)
CallCommand(Called, Sync)
ControlVariable(A to 7)
${A + 1}`

`Called Thread:
ControlVariable(A o 4)`

This would output 8, However take this example with Asynchronous:
`ControlVariable(A to 1)
CallCommand(Called, Async)
ControlVariable(A to 7)
${A + 1}`

Called Thread:
ControlVariable(A to 4)

This would either output 5 or 8, depends on which thread changes the variable's value last.
Async has its purpose, you need to think about how to use which callback function or call type to use in which case.

See [dbm/raw/callback.txt](https://github.com/ArztVielfrass/dbm/blob/master/raws/callback.txt) for actual dbm raw

**Silver's Stealth Edit:** _Synchronous in the context of a loop action basically means "stop everything and run this item, and when it finishes run the next. Do not process anything else at all until this is done." while asynchronous means "attempt process all of the items in my loop at the same time, whenever you have a free minute to do it, no big deal"_

## Using @botname to trigger the bot
To call the bot via @botname instead of using a command you can follow these steps:

**1. create an EVENT that triggers on ANY MESSAGE**  
This event will evaluate each message and look for a mention that matches the bot's ID  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/ping1.png)

**2. Store the text of the message**

**3. use Check Variable to see if the messsage contains the ping for your bot**  
If it contains the ping you're checking for, continue the actions. Otherwise have it stop or your bot will just process on every message sent which is crazy.  
*protip: you can use any ping here if you wanted to have it look for a specific user or role*    
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/ping3.PNG)  

**4. Store any other information that you want from the message**  
At the very least i reccomend storing the channel so you can send a response in the same channel.  
If you're using the @botname to trigger a command you'd then need to parse the text of your message for the rest of the command. That can be a bit complicated and will require you to learn some JS.  

**5. Send a message (or whatever else you want)**  
The rawcode for this example can be found here https://silversunset.net/paste/86  
*make sure you add it as an EVENT, not a command.*

## Working with Time
**Time is an illusion. Lunchtime doubly so. **
Trying to code things with time in javascript will most likely set your hair on fire. Please proceed with caution.

First, go [to this site](https://www.w3schools.com/jsref/jsref_obj_date.asp), bookmark it, and make it your new best friend. This will give you all the bits and pieces of time you could ever want.

### Basic Timestamps
* Getting the current time
Getting the current time in javascript is easy.
`${new Date()}` is all you really need. When you run this you're going to get something that looks like `Wed Apr 04 2018 20:18:02 GMT-0400 (Eastern Daylight Time)`
**but be careful** - this will give you the time in the bot's timezone. So if you're running it on your home computer you'll get your local time, but when you save it out to a VPS you'll get whatever the servers 'local time' is.

### Getting the current UTC time

This is a bit more tricky, and will take multiple steps. All of this is done in a single `run script` action in DBM.<br/>
`var now = new Date();` = this will get the current time and create the variable "now" to use<br/>
`var year = now.getUTCFullYear();` = stores the UTC Year<br/>
`var month = now.getUTCMonth() + 1;` = stores the UTC month (months are 0-11 so you have to add 1)<br/>
`var day = now.getUTCDate();` = stores the UTC Date<br/>
`var hour = now.getUTCHours();` = stores the UTC Hour<br/>
`var minutes = now.getUTCMinutes();` = stores the UTC Minutes<br/>

You can then add:
`msg.channel.send("The time is: " + month + "/" + day + "/" + year + "; " + hour + ":" + minutes)`
to display the following:
`The time is: 4/4/2018; 23:23`

**but** what if the minutes are < 10, you'd see the time as `23:1` instead of `23:01`
And how can you tell if the date is month/day/year or day/month/year (different countries have different conventions)

### Formatting Current UTC Time
The final change to our script is going to be to add formatting to the month, to display "April" instead of "4", as well as padding leading zeros in the hour/minutes of the time.

**this is the full run-script action code**

```
var now = new Date();
var year = now.getUTCFullYear();
var month = now.getUTCMonth() + 1;
var day = now.getUTCDate();
var hour = now.getUTCHours();
var minutes = now.getUTCMinutes();

switch(month){
case 1: var monthname = "January"; break;
case 2: var monthname = "February"; break;
case 3: var monthname = "March"; break;
case 4: var monthname = "April"; break;
case 5: var monthname = "May"; break;
case 6: var monthname = "June"; break;
case 7: var monthname = "July"; break;
case 8: var monthname = "August"; break;
case 9: var monthname = "September"; break;
case 10: var monthname = "October"; break;
case 11: var monthname = "November"; break;
case 12: var monthname = "December"; break;
}

msg.channel.send("The time is: " + monthname + " " + day + ", " + year + "; " + (hour > 9 ? hour : "0" + hour) + ":" + (minutes > 9 ? minutes : "0" + minutes))
```

we're using a few javascript tricks here.
1. A [switch statement](https://www.w3schools.com/js/js_switch.asp) is being used to display the month name instead of the number
2. A [conditional operator](https://www.w3schools.com/jsref/jsref_operators.asp) is being used to pad the zeros on the date

### Using .toLocaleString()
**WARNING WARNING WARNING**
If you use this method in DBM you WILL NOT be able to run your bot directly in DBM. It will be fine on your vps or running via cmd locally.
**YOU HAVE BEEN WARNED**

[.toLocaleString()](https://www.w3schools.com/jsref/jsref_tolocalestring.asp) allows you to display a string using location-specific formatting. If your string is a date, it will show the current time as `4/4/2018, 7:40:32 PM` since that is the local settings for where the bot is currently running. **AGAIN** if you save the bot to a VPS it will use the bots server settings instead, BUT you can tell the program which settings you want it to use rather than the 'local' ones. 
`new Date().toLocaleString("en-US", {timeZone: "UTC"})` will show the current UTC time in an American format
`new Date().toLocaleString("en-US", {timeZone: "America/Chicago"})` will show the current CST time in an American format.
[This Document](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toLocaleString) has more information on locale string settings.

### Finding the time between actions
Another common use for time in javascript is determining "when the last time something was done"

To do this you'll need to store the last time something was run and compare it to the current time.
**[This link](https://pastebin.com/EaBjackY) is the raw-data for the below command tutorial.**

The real magic however is this script:
```
var duration = tempVars("time_var");
var ms = parseInt((duration%1000)/100);
var s = parseInt((duration/1000)%60);
var m = parseInt((duration/(1000*60))%60);
var h = parseInt((duration/(1000*60*60))%24);

var timeoutput = h + "h:" + m + "m:" + s + "s:" + ms + "ms";
this.storeValue(timeoutput,1,"donetime",cache)
```
which converts the # of milliseconds between "current run" and "last run" to a human readable format.

For this example, we'll time "when was the last time [User] ran [Command]"

**...ASSUMING YOUVE INSTALLED THE RAW DATA...**
This is what each action is doing:

**Action 1**: **required** Checks the last time the command was run, using store-member-data. This will be stored in milliseceonds. *note: if this is the first time the command was run you may get a NaN error, or some weird number.

**Action 2**: **required** Checks the difference between the "Current Time" and "The Last Time The Command Was Run" - this will return a number in MILLISECONDS

**Action 3**: OPTIONAL: Format the time from milliseconds to a human-readable format. This will output your time as `0h:2m:34s:4ms`

**Action 4**: Send some message with the information (Or do whatever else you want with it really). For the purposes of this tutorial you should get two lines, one in milliseconds and one formatted.

**Action 5**: **required** Save the new current time to the member data, overwriting the old one and storing the new 'last time this command was run for that user.

## Finding a user with some parts of their name
To make this, you'll require a simple Run Script action.<br/>
`var search = tempVars("parameters").toLowerCase()`<br/>`var member = msg.guild.members.find(member => member.name.toLowerCase().startsWith(search) || member.name.toLowerCase().endsWith(search) || member.name.toLowerCase().includes(search))`<br/>`this.storeValue(member, 1, "member", cache)`<br/>
_the `tempVars("parameters")` would be your input, and, to use the output, use `tempVars("member")`_

## Running via Command Prompt 
This allows you to run your bot outside of DBM using command prompt (aka CMD). Please remember when you close the window the bot will shut down.  
1. Open project directory  
2. Click into the address bar  
3. At the beginning type "cmd" and hit enter (this will open a cmd prompt in this folder)  
4. type `node bot.js` <br/>Note: If you use a restart script (see [Restarting Automatically](#running-your-bot-247-restarting-automatically) this step may be different)  

## Stopping the Bot

Sometimes you need to stop your bot. If you're running a script like `forever` this may automatically restart your bot, otherwise it will just shut the whole bot down.

**Action 1: send a message** to the channel so you know the bot has recognized the command

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/stopping.png)

**Action 2: stop the bot using a script**. Its good practice to log to console that the bot is stopping, again to confirm that the action is recognized.

`console.log("text")` is used to print text directly to the bots console logs. Anything inside the `" "` will be printed directly. If you choose to use a variable instead you would use `console.log(tempVars("name"))`

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/stopping2.png)

## Restarting Automatically

### Linux

* Go into your bot folder with : `cd BotFolderLocation`
* Use `nano start.sh` to create a file called `start.sh` and start editing.
* Paste the code below :

```bash
# /bin/sh
while true
do
echo Starting Bot
node bot.js
echo Restarting Bot in 5 Seconds...
sleep 5
done
```

* Press CTRL+C then Y and ENTER to save the start.sh file.
* Use `chmod 777 start.sh` to give the file executable permission.
* Done! Now you can start your bot by executing that file with : `./start.sh`

**Tutorial Video** _\(Click on image to watch it\)_

[![](https://asciinema.org/a/Gjc27yyaid3LxAIDlc8AqM4Z3.png)](https://asciinema.org/a/Gjc27yyaid3LxAIDlc8AqM4Z3)

### Windows


* Create a file with `.bat` extension.
* Paste the code below and save it.

```
@echo off
echo Starting..
:main
node bot.js
echo Restarting Bot..
goto main
```

* Done! Now you can run your bot just executing that file.

[**Tutorial Video **_\(Click to watch it\)_](https://youtu.be/1ZDE3z_Fsi4)

### Forever.js

You can install a script called **Forever.js** that will automatically restart your bot if it crashes. 

* `npm install --no optional -g forever`
* `chmod -R a+rwx <bot folder>`- Give the bot folder permission to be read/write and executable
* `cd <bot folder>` - Change to the bots directory
* `forever start bot.js` - Start the bot program using "Forever" \(this will keep the bot running and restart it if it crashes\)

### Nodemon

`node bot.js` will have to be restarted every time you make changes. You can use Nodemon to do this automatically

1. Install nodemon with `npm i -g nodemon`
2. Open project directory
3. Click into the address bar
4. At the beginning type "cmd" and hit enter (this will open a cmd prompt in this folder)
5. Type `nodemon --inspect --watch actions --watch data/commands.json --watch data/events.json --watch node_modules --watch js --watch data/settings.json bot.js`


# Running your bot 24/7
By now you may have noticed that when you close DBM your bot shuts down - this is *normal and expected behavior*, the bot can only stay online when the program running it is online.  
  
You have three options to keep the bot running 24/7  
1. **Keep DBM open all the time** - This is not recommended because the bot *will* crash periodically and DBM does not automatically restart  
2. **Run the bot on your computer via Command Prompt (CMD)** - This is *slightly* better than running directly with DBM, because you *can* create a restart script to handle the bot crashing. HOWEVER most home internet providers are not designed for this sort of always-running access, if your internet has caps you may hit them for larger (or music) bots. Using this method you can technically run the bot on any computer that will allow you to run node.js, which means you could run it on a Mac or Raspberri Pi machine should you have access to those.<br/>[Click for Command Prompt (CMD) Tutorial](#miscellaneous-tutorials-stopping-the-bot)<br/>[Click for Restart Script Tutorials](#miscellaneous-tutorials-restarting-automatically)  
3. **Host the bot on a VPS** - A VPS (Virtual Private Server) is a more 'correct' way to host a bot. These servers are generally located in data centers designed for always-on use, and can often be found for a couple of dollars per month. There *are* some 'free' versions (i.e. Heroku and Glitch), but they are NOT designed for bot hosting, they are designed for things like websites and if you choose to use them be aware that they are unstable and your bot will have problems.  
[Click for VPS Tutorials](#vps-tutorials)  
	
# VPS Tutorials

## Digital Ocean

This bit assumes you are going to use `forever.js` to run the bot. You can choose another method but you'll have to check out those tutorials for further instruction)

#### Initial Server Setup

* Start a digital ocean instance (with node as your image) - the $5/month one is perfectly fine
* [Generate an SSH key](https://www.siteground.com/kb/how_to_generate_an_ssh_key_on_windows_using_putty/) and and add it to the droplet on creation (Its much easier than doing it after)
* get server IP address
* connect via PuTTY
* Run commands:
* `apt install unzip`
* `npm install --no optional -g forever`

#### Unpackage and Start the bot

* Upload the bot file to your droplet using something like [WinSCP](https://winscp.net/eng/download.php)
* If you're uploading the bot for the first time it may be faster to upload is as a zip file and then unzip it on the dropletby typing `unzip <yourbot>.zip -d <bot folder>`
* If you've already uploaded the bot and you're just making a change to the command.json/events.json file you can JUST upload those without zipping them
* in PuTTY type: `chmod -R a+rwx <bot folder>`- Give the bot folder permission to be read/write and executable (you only need to do this the first time you set things up)
* in PuTTY type: `cd <bot folder>` - Change to the bots directory
* in PuTTY type: `forever start bot.js` - Start the bot program using "Forever" \(this will keep the bot running and restart it if it crashes\)

#### Stop the bot

* `forever list`
* `forever stop 0`_ - Where 0 is the index of your code in the forever list._

#### Server Maintenance
When you log into Digital Ocean you'll see an MOTD telling you if there are package updates. If you want/need to install them do the following:

#### Install Updates
When updates are available:

- `sudo apt update` - update package index
- `sudo apt upgrade` - install updates
- `sudo reboot` - reboots the system (server will indicate if its needed)

#### add SSH key to server file manually
If you want to add an SSH key after you've set up your droplet you can edit the authorized_keys file

- edit directly in PuTTY
- `nano /root/.ssh/authorized_keys`
- enter `ssh-rsa <key>` (the section that starts with AAAA[gibberish] - do not use begin, end, or comment line)

```
---- BEGIN SSH2 PUBLIC KEY ----
Comment: "rsa-key-[date]"
[a whole lot of gibberish]
---- END SSH2 PUBLIC KEY ----
```

- `ctrl + O`, then at the bottom says "filename to write"
- `ctrl + x`
- set up PuTTY to connect automatically
- in PuTTY - open the connection details
- choose DATA
- Fill in the Auto Login username
- Putty should now connect automatically when the server is connected to

## Raspberry Pi

### Installing Node.js on a Raspberry pi
First of all I made this guide using Raspberry Pi 3, however it should work with Raspberry Pi 2 too. But not with a Raspberry Pi Zero because it doesn't support node.js - You can just google if the your pi supports node.js. 
_Tresmos\#2135_

Connect your Raspberry Pi using [PuTTY](https://www.putty.org/), or using [VNC ](https://howtoraspberrypi.com/raspberry-pi-vnc/)and type these commands in order to install Node.js:

### **for Node.js LTS:**

If you have any other version of Node.js installed please uninstall them now before continuing 
```
sudo apt purge node.js npm
``` 

ARM Version:
```
uname -m
```

output will look like: `armv#X`. \
navigate to [nodejs.org](https://nodejs.org/en/download/) downloads page, right click on the `Linux Binaries (ARM)` version that correlates with your version (`armv#X`), click `Copy Link Address`, then go back to terminal.

Getting Node.js package:
```
wget <Ctrl+Shift+V>
ls (note the downloaded file `node-vx.x.x-linux-armv#X.tar.xz`)
tar -xJf <filename>
```

Copy Node.js to /usr/local:
```
cd node-vx.x.x-linux-armv#X/
sudo cp -R * /usr/local/
```

Reboot RPi
```
reboot
``` 

### **for Node.js 8:**

```
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
```

### **for Node.js 9:**

```
curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
sudo apt-get install -y nodejs
```

After everything is done, check if Node.js is installed correctly or not with these commands:

```
node -v
npm -v
```

it should give you an output like this:

```
pi@raspberrypi:~ $ node -v
v9.10.0
pi@raspberrypi:~ $ npm -v
5.6.0
```

[This is an example](https://asciinema.org/a/173263) if you want to watch it.

#### Uploading Bot Files to Raspberry Pi

Before uploading your bot files you need to export it first watching [this video](https://www.youtube.com/watch?v=MNw7anSA06g). _**\(If you're using beta DO NOT use built in export feature because its still buggy. Please export it manually watching the video\)**_

After that you have a couple options to upload your bot files to Raspberry Pi:

* [FileZilla](https://filezilla-project.org/)
* [VNC Viewer](https://www.realvnc.com/en/connect/download/viewer/)

##### FileZilla

Download and install FileZilla using this [link](https://filezilla-project.org/). Now before uploading bot files, we need to connect our Raspberry Pi. To do that we need to open **Site Manager **and add our Raspberry Pi:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/filezilla_2018-03-29_15-21-09.png)

Just click **New Site**

* Host = IP of Raspberry Pi
* Protocol = SFTP - SSH File Transfer Protocol **\(thats really important\)**
* Logon Type = Normal
* User = pi
* Password = Your SSH Password

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/filezilla_2018-03-29_15-24-25.png)

After saving that and connecting, you can upload your bot files with just simple drag&drop to right side


##### VNC Viewer

First you need to activate VNC and connect to Raspberry Pi using this [guide](https://howtoraspberrypi.com/raspberry-pi-vnc/).

Then for transfer files click here at the top:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/vncviewer_2018-03-29_15-44-49.png)

After that you'll see a window, click **Send Files**, go **into** your bot folder, and press **Use Entire Folder**:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/vncviewer_2018-03-29_15-47-11.png)

as we can see it started to upload files to Raspberry Pi:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/vncviewer_2018-03-29_15-48-51.png)

#### Running The Bot

There is two ways to run your bot:

* with PuTTY

* with VNC Connection

##### Running With PuTTY

1. Connect to your Raspberry Pi using PuTTY
2. cd into your bot folder \(if your bot folder is in Desktop, type "cd Desktop/**YourBotFolderName"\)**
3. and finally type "node bot.js" to run your bot.

Thats it!

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/putty_2018-03-29_15-59-08.png)

_In this way if you close PuTTY, your bot will stop working too._

##### Running With VNC Connection

1. Connect to your Raspberry Pi using VNC Viewer
2. Open your bot folder
3. Press **F4** to open terminal window in your project folder
4. and type "node bot.js" to run your bot

Thats it!

_In this way you can close VNC Viewer and your bot will still run, however if you close that terminal window bot will stop working._

## Heroku

### Disclaimers
From R. Danny (Discord's API server bot)

* Bots are not what the platform is designed for. Heroku is designed to provide web servers (like Django, Flask, etc). This is why they give you a domain name and open a port on their local emulator.
* Heroku's environment is heavily containerized, making it quite significantly underpowered (this is reason 1 why voice doesn't work properly on heroku)
* Heroku's environment is volatile. In order to handle the insane amount of users trying to use it for their own applications, Heroku will dispose your environment every time your application dies unless you pay.
* Heroku does not let you control system dependencies barely at all. This means if any of your requirements need C bindings (pynacl, lxml, etc), they'll probably not work. (this is reason 2 why voice doesn't work properly on heroku)
* Heroku only offers a limited amount of time on their free programme for your applications. If you exceed this limit (which you probably will), they'll shut down your application until your free credit resets.

If you need help with Heroku hosting please do not ask on our discord servers. You can just ask [here using our support system](https://dbm-support.site/).

### YouTube Tutorials

* [HOW TO HOST YOUR DISCORD BOT FOR FREE! (Heroku)](https://www.youtube.com/watch?v=d8INsGl28xw) - Published on May 29, 2018 **most recent**
* [Discord Bot | Host your bot for free! (using heroku)](https://www.youtube.com/watch?v=kpIFnZ0zbsw) - Published on Mar 22, 2018
* [HOW TO HOST A DISCORD BOT FOR FREE USING HEROKU!](https://www.youtube.com/watch?v=diq7INoHqh4) - Published on Nov 15, 2017
* [Host your Discord bot on Heroku 24/7!](https://www.youtube.com/watch?v=NM8IMyqpvqU) - Published on Sep 10, 2017

## Glitch
Glitch is a **free** service that is generally used to run low to medium end applications and in general testing. Discord bots can be ran on this however, there are some limits to glitch you must watch out for. This can be a great option for small to some medium bots. It's a much better option then **heroku**. It is also **compatible with dbm beta.** This is a far better alternative then **android** and **heroku**. 

If you would like to use this service follow the tutorial link here: [https://dbotmaker.io/forums/threads/glitch-hosting-free-compatible-with-beta-saves-data.305/](https://dbotmaker.io/forums/threads/glitch-hosting-free-compatible-with-beta-saves-data.305/ "Glitch Tutorial")

#### **Limits**
* Projects have a limit of around **200MB of disk space** on the project however node modules don't count towards it.
* Projects have a limit of **512MB of RAM**.
* Projects sleep after 5 minutes (tutorial shows how to fix it) and after 12 hours of constant running before being rebooted.

#### **Comparison to Heroku**
* Glitch will save your bot files and data. This is an actual storage system compared to heroku which erases after each reboot.
* Glitch has an easier interface compared to heroku's
* Glitch is more focused and better supported on Javascript/node.js and NPM packages. Hence why node modules are unlimited storage space
* Glitch has no actual "hour counter", bots will reboot after 12 hours and can run again up to 12 hours. Heroku however will shut down your bot for the rest of the month.
