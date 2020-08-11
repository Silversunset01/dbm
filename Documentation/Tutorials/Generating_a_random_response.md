# Generating a Random Response
[Using a Hardcoded Reponse](#using-a-hardcoded-response) | [Using an Updatable List](#using-an-updatable-list)

A random response generator works for anything from a Magic 8 ball command to a coin toss command, to a random image, joke, phrase, or even paper/scissors/rock command. The bot will generate a random number and select a response based on the number chosen.

## Using Hardcoded Responses
**Action 1: Generate a random number** this will allow the bot to select one of your pre-programmed responses.

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/randtext.png)

**Action 2: Send message based on the number generated** using a switch/case script.

Switch/case basically evaluates the statement defined in `switch(tempVars("rand-num"))` and selects the matching response from the list of `case` items. The last item should always be `default` this is often used for error handling if no `case` match is found. In this case, the possible outcomes of the `rand-num` variable are known and such a short list that `default` can be used to indicate the last match rather than an error.

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

This command will allow you to either create a new list (if the list is deleted) or add items to the list. *Please note:* if you do not have beta you cannot use the Save Variable action, which means the list will be deleted every time the bot restarts. In that case, you'll need to recreate and add the text each time.

After actions 1 and 2 (to store the 'type' and 'text' if any) you'll need to use CHECK VARIABLE to determine what kind of command you're running:

Action 3: Checks to see if the response = "new", if it does it will create the list named "rndlist" as a server variable (in action 5).
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/rndtextlist2.PNG)

Action 4: Checks to see if the response = "add", if it does it adds the text you've input to the list.  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/rndtextlist3.PNG)  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/rndtextlist4.PNG)

Action 9: This is a catch-all. If you do not enter *?rndtext new* or *?rndtext add* this message will pop up reminding you of the proper syntax  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/rndtextlist5.PNG)

**2. command *?rndresponse* - retrieve random text from the list**
This command simply pulls a random item from the list you created and prints it to chat

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/rndtextlist7.PNG)

Make sure to select the SERVER var as your source list

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/rndtextlist6.PNG)

When you've got that simply print the `${tempVars("rnd_response")}` to a send-message.