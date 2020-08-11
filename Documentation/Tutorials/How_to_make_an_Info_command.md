# How to create an Info/Help command
[DBM Only - No Script](#dbm-only) | [With Javascript - Switch/Case](#with-javascript-switch-case) | [With Javascript - JSON](#with-javascript-json)

## DBM Only
This method of an Info/Help command uses ONLY DBM actions, but it can be tricky to update as your info changes.  
For this example we will be using an EMBED message with the following parameters:  
   * `!info [topic]`  
   * available topics: `server`, `bot`, `commands`  
   
1. Plan out the topics you want to cover. For each topic you will need the following actions:  
   - **a)** Check Variable   
   - **b)** Set Embed Description  
   - **c)** Send Embed Message  
   - **d)** End action sequence    
2. Set up your command actions  
   - **Action 1)** Store command parameters -> one parameter starting at 1 -> save as Temp Variable "topic"  
   - **Action 2)** Create embed message -> variable `e`, title `Info`  
   - **Action 3)** Check variable -> if `tempVars("topic")` equals `"server"` jump to action 6, if not continue  
   - **Action 4)** Check variable -> if `tempVars("topic")` equals `"bot"` jump to action 9, if not continue  
   - **Action 5)** Check variable -> if `tempVars("topic")` equals `"commands"` jump to action 12, jump to action 15  
   - **Action 6)** Set embed description -> variable `e` -> text "Whatever you want here for the **server** info"  
   - **Action 7)** Send embed message `e`  
   - **Action 8)** End action sequence  
   - **Action 9)** Set embed description -> variable `e` -> text "Whatever you want here for the **bot** info"  
   - **Action 10)** Send embed message `e`  
   - **Action 11)** End action sequence  
   - **Action 12)** Set embed description -> variable `e` -> text "Whatever you want here for the **commands** info"  
   - **Action 13)** Send embed message `e`  
   - **Action 14)** End action sequence  
   - **Action 15)** Set embed description -> variable `e` -> text "The syntax for this command is `!info [topic]`. Valid topics are: `server`, `bot`, `commands`"  
   - **Action 16)** Send embed message `e`  
   - **Action 17)** End action sequence  

## With JavaScript - Switch/Case
This method of an Info/Help command uses DBM actions as well as javascript, and can be very simple to update as your info expands.  
For this example we will be using an EMBED message with the following parameters:  
   - `!info [topic]`  
   - available topics: `server`, `bot`, `commands`  
   
1. Command actions:  
   - **Action 1)** Store command parameters -> one parameter starting at 1 -> save as Temp Variable "topic"  
   - **Action 2)** Create embed message -> variable `e`, title `Info`  
   - **Action 3)** Run Script (Evaluate Text Directly):  
   
   ```
   if (!tempVars("topic")) {var t = "X";} else {var t = tempVars("topic").toUpperCase()};
   var e = tempVars("e");

   switch(t) {
      case "SERVER": e.setDescription("whatever text you want for the SERVER info"); break;
      case "BOT": e.setDescription("whatever text you want for the BOT info"); break;
      case "COMMANDS": e.setDescription("whatever text you want for the COMMANDS info"); break;
      default: e.setDescription("The syntax for this command is `!info [topic]`. Valid topics are: `server`, `bot`, `commands`"); break;
   }
   ```
   - **Action 4)** Send embed message `e`  
2. To add items to this list, simply copy & paste each `case` line (make sure to end with `break;`) and update the new line with your new information. Make sure to add the new `info` to your `Default` case as well.  

## With JavaScript - JSON
This method of an Info/Help command uses DBM actions as well as javascript, and can be very simple to update as your info expands.   
For this example we will be using an EMBED message with the following parameters:  
   - `!info [topic]`  
   - available topics: `server`, `bot`, `commands`  
   
1. Command actions:  
   - **Action 1)** Store command parameters -> one parameter starting at 1 -> save as Temp Variable "topic"  
   - **Action 2)** Create embed message -> variable `e`, title `Info`  
   - **Action 3)** Run Script (Evaluate Text Directly):
   
   ```
   var e = tempVars("e");

   var myInfo = {
   "SERVER":"Whatever you want here for **SERVER** info",
   "BOT":"Whatever you want here for **BOT** info",
   "COMMANDS":"Whatever you want here for **COMMANDS** info"
   };

   if (!tempVars("topic")) {
   	  var validTopics = Object.keys(myInfo);
	     e.setDescription("Please enter a valid topic: " + validTopics.toString());
   } else {
	     var t = tempVars("topic").toUpperCase()
	     e.setDescription(myInfo[t]);
   };
   ```
   - **Action 4)** Send embed message `e`  
2. To add items to this list you can add items to the `myInfo` section.  
    - Insert a new line and add a comma to the end of the previous line  
    - Add a new info pair using this syntax: `"NAME":"Your text here"`   
    - **NOTE:** Make sure the last line DOES NOT have a comma at the end!!!