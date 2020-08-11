# Lists & Loops
[Lists](#lists) | [Loops](#loops) | [How to Loop in DBM](#how-to-use-a-loop-in-dbm) | [Synchronous or Asynchronous](#synchronous-or-asynchronous)

## Lists
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
To create your lists in DBM with the `Create List` action.

To add items to the list you have created, you would use the `Add Item To List` action, select your list variable, and put the value you want to add to the list in the VALUE box

**To add a value from another variable**, you *do not* need to use `${}` brackets, simply right click into the box and choose your variable, or type `tempVars("variableName")`

**To add TEXT to your list** make sure to put the value in "quotation marks"

## Loops
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
While this may not be bad for a handful of roles, what happens if you have 20. Or 200? Or 500? Using a loop, you would only need to write the code a single time; it would look like this:
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

### How to use a LOOP in DBM
Adding a loop in DBM can be a little confusing. It requires TWO actions.  
**ACTION 1:** LOOP THROUGH LIST  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/loops.PNG)  
**Source List:** this is the list (array) you want to cycle through  
**Temp Variable Name:** When performing a LOOP in DBM, the software needs to create a temporary variable to save the "current item" in, and you can use that variable to perform tasks.  
**Event:** This is the name of the event that holds all of the actions you want the bot to perform on each item on your list.  
**Call Type:** Synchronous = "Only run one item at a time, and finish it before moving on to the next"; Asynchronous = "Try to run all items at the same time  

**ACTION 2:** An EVENT that contains all of the actions you want to perform during the loop. In this case, you would use "Find Role", "Add Role to Member", "Find Channel", "Send Message" -> In the *add role to member* action, you would use the variable you created in your "Loop through list" action as your user role.  

**NOTE:** Because of the way DBM uses TEMPORARY variables, this will NOT show up in your right-click list. **YOU MUST TYPE THIS VARIABLE MANUALLY** by typing `tempVars("currentMember")` (or whatever you've named it). IT WILL STILL WORK. Just trust me.  

## Synchronous or Asynchronous
Thread: the flow of actions, starting from one until it ends  

These keywords refer to how the thread is treated and how the program flows. Whenever the call type is Sync, it waits until it receives a callback or when the thread ends. Meaning that when the event or command is called, the main thread starts first, and if it is ever interrupted by a call, it does that action and if that action ends, returns to the main thread. Async is similar to Sync however, it runs alongside the main thread.  

Purpose: This is useful in multithreading. Take this example:

`Main Thread:
ControlVariable(A to 1)
CallCommand(Called, Sync)
ControlVariable(A to 7)
${A + 1}`

`Called Thread:
ControlVariable(A to 4)`

This would output 8, however, take this example with Asynchronous:
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