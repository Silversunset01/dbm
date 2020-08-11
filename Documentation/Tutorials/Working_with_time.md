# Working with Time
[Basic Timestamps](#basic-timestamps)  
[Getting the Current UTC Time](#getting-the-current-utc-time)  
[Formatting the Current UTC Time](#formatting-the-current-utc-time)  
[Using .toLocaleString()](#using-tolocalestring)  
[Finding the time between actions](#finding-the-time-between-actions)  

**Time is an illusion. Lunchtime doubly so.**
Trying to code things with time in javascript will most likely set your hair on fire. Please proceed with caution.

First, go [to this site](https://www.w3schools.com/jsref/jsref_obj_date.asp), bookmark it, and make it your new best friend. This will give you all the bits and pieces of time you could ever want.

## Basic Timestamps
* Getting the current time
Getting the current time in javascript is easy.
`${new Date()}` is all you need. When you run this you're going to get something that looks like `Wed Apr 04 2018 20:18:02 GMT-0400 (Eastern Daylight Time)`
**but be careful** - this will give you the time in the bot's timezone. So if you're running it on your home computer you'll get your local time, but when you save it out to a VPS you'll get whatever the servers 'local time' is.

## Getting the current UTC time

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

## Formatting Current UTC Time
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

## Using .toLocaleString()
**WARNING WARNING WARNING**
If you use this method in DBM you WILL NOT be able to run your bot directly in DBM. It will be fine on your VPS or running via cmd locally.
**YOU HAVE BEEN WARNED**

[.toLocaleString()](https://www.w3schools.com/jsref/jsref_tolocalestring.asp) allows you to display a string using location-specific formatting. If your string is a date, it will show the current time as `4/4/2018, 7:40:32 PM` since that is the local settings for where the bot is currently running. **AGAIN** if you save the bot to a VPS it will use the bots server settings instead, BUT you can tell the program which settings you want it to use rather than the 'local' ones.
`new Date().toLocaleString("en-US", {timeZone: "UTC"})` will show the current UTC time in an American format
`new Date().toLocaleString("en-US", {timeZone: "America/Chicago"})` will show the current CST time in an American format.
[This Document](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toLocaleString) has more information on locale string settings.

## Finding the time between actions
Another common use for the time in javascript is determining "when the last time something was done"

To do this you'll need to store the last time something was run and compare it to the current time.
**[This link](https://pastebin.com/EaBjackY) is the raw-data for the below command tutorial.**

The real magic, however, is this script:
```
var duration = tempVars("time_var");
var ms = parseInt((duration%1000)/100);
var s = parseInt((duration/1000)%60);
var m = parseInt((duration/(1000*60))%60);
var h = parseInt((duration/(1000*60*60))%24);

var timeoutput = h + "h:" + m + "m:" + s + "s:" + ms + "ms";
this.storeValue(timeoutput,1,"donetime",cache)
```
which converts the # of milliseconds between "current run" and "last run" to a human-readable format.

For this example, we'll time "when was the last time [User] ran [Command]"

**...ASSUMING YOUVE INSTALLED THE RAW DATA...**
This is what each action is doing:

**Action 1**: **required** Checks the last time the command was run, using store-member-data. This will be stored in milliseconds. *note: if this is the first time the command was run you may get a NaN error or some weird number.

**Action 2**: **required** Checks the difference between the "Current Time" and "The Last Time The Command Was Run" - this will return a number in MILLISECONDS

**Action 3**: OPTIONAL: Format the time from milliseconds to a human-readable format. This will output your time as `0h:2m:34s:4ms`

**Action 4**: Send some message with the information (Or do whatever else you want with it really). For this tutorial, you should get two lines, one in milliseconds and one formatted.

**Action 5**: **required** Save the new current time to the member data, overwriting the old one and storing the new 'last time this command was run for that user.