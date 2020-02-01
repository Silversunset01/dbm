 Action  | Category  |  Description  |  Img
:- | :- | :- | :-:
 Clear Queue  | Audio Control  |   |  
 Control Audio  | Audio Control  |   |  
 Join Voice Channel  | Audio Control  |   |  
 Leave Voice Channel  | Audio Control  |   |  
 Play File  | Audio Control  |   |  
 Play URL  | Audio Control  |   |  
 Play YouTube Video  | Audio Control  |   |  
 Set Audio Volume  | Audio Control  |   |  
 Skip Queue  | Audio Control  |   |  
 Get Bot as Member  | Bot Client Control  |  Get the bot member object  |  
 Set Bot AFK Status  | Bot Client Control  |  Changes the bots status between AFK/Not AFK  |  
 Set Bot Avatar  | Bot Client Control  |  Changes the bots avatar image  |  
 Set Bot Game  | Bot Client Control  |  Changes the bots game to `Playing [your text here]`  |  
 Set Bot Nickname  | Bot Client Control  |  Changes the bots nickname on the server  |  
 Set Bot Status  | Bot Client Control  |  Changes the bots status between Online/Idle/Invisible/DND  |  
 Set Bot Username  | Bot Client Control  |  Changes the bots username  |  
 Create Text Channel  | Channel Control  |   |  
 Create Invite  | Channel Control  |   |  
 Create Voice Channel  | Channel Control  |   |  
 Delete Channel  | Channel Control  |   |  
 Find Channel  | Channel Control  |  Get a channel object for a text channel  |  
 Find Voice Channel  | Channel Control  |  Get a channel object for a voice channel  |  
 Set Channel Permissions  | Channel Control  |  Set the permissions of a specified channel  |  
 Set Member Channel Perms  | Channel Control  |   |  
 Set Role Channel Perms  | Channel Control  |  Set the permissions of a specified role  |  
 Store Channel Info  | Channel Control  |  Store information about a text channel, i.e. Name, Topic, Last Message, Position, etc  |  
 Store Voice Channel Info  | Channel Control  |  Store information about a voice channel, i.e. Name, Topic, Last Message, Position, etc  |  
 Check if Member Has Role   | Conditions  |  Check if the specified user has a role, often used with `Find Role`  |  
 Check is Bot in Voice Channel  | Conditions  |   |  
 Check Member Permissions  | Conditions  |   |  
 Check Parameters  | Conditions  |  Verify user input by checking the number/type of parameters entered on a command  |  
 Check Variable  | Conditions  |  Check the value of a variable, things like "variable includes" or "variable equals". In JavaScript this is an `if... then...`  |  
 Check Variable Type  | Conditions  |  Check the type of a variable, things like "variable is number" or "variable is channel". In JavaScript this is an `if... then...`  |  
 Check Member Data  | Deprecated  |  Compare member data from `data/players.json` to a specified value   |  
 Check Server Data  | Deprecated  |  Compare server data from `data/servers.json` to a specified value  |  
 Control Member Data  | Deprecated  |  Saves member data to the `data/players.json` file  |  
 Control Server Data  | Deprecated  |  Saves server data to the `data/servers.json` file  |  
 Store Member Data  | Deprecated  |  Reads member data from the `data/players.json` file  |  
 Store Server Data  | Deprecated  |  Reads server data from the `data/servers.json` file  |  
 Create Emoji  | Emoji Control  |   |  
 Delete Emoji  | Emoji Control  |   |  
 Find Custom Emoji  | Emoji Control  |   |  
 Create Image  | Image Editing  |   |  
 Create Image from Avatar  | Image Editing  |   |  
 Draw Image on Image  | Image Editing  |   |  
 Draw Text on Image  | Image Editing  |   |  
 Apply Image Effect  | Image Editing  |   |  
 Resize Image  | Image Editing  |   |  
 Rotate Image  | Image Editing  |   |  
 Send Image  | Image Editing  |   |  
 Add Item to List  | Lists and Loops  |  Adds an item to a previously created list.  |  
 Convet List to Text  | Lists and Loops  |  Transforms a list from JSON format `["item","item","item"]` to something more friendly like <br/>`- item`<br/>`- item`<br/>`- item`  |  
 Create List  | Lists and Loops  |  Creates a list, in JavaScript this is referred to as an Array  |  
 Get Item from List  | Lists and Loops  |  Retrieve an item from a previously created list  |  
 Get List Length  | Lists and Loops  |  Count the number of items in a previously created list  |  
 Loop Through All Servers  | Lists and Loops  |   |  
 Loop Through List  | Lists and Loops  |  Cycle through a previously created list and perform actions for each item, requires an event as well that contains all actions to perform for each object. See [this tutorial](https://silversunset.net/dbm/tutorials#miscellaneous-tutorials-lists-loops) for more info  |  
 Remove Item from List  | Lists and Loops  |  Removes an item from a previously created list  |  
 Transform List  | Lists and Loops  |   |  
 Add Member Role  | Member Control  |  Adds a role to a specified member  |  
 Ban Member  | Member Control  |  Bans a member from the server  |  
 Find Member  | Member Control  |  Obtains the member object  |  
 Kick Member  | Member Control  |  Kicks a member from the server  |  
 Remove Member Role  | Member Control  |  Removes a role from a specificed member  |  
 Set Member Deafen  | Member Control  |  **Audio** deafens a user in a voice chat  |  
 Set Member Mute  | Member Control  |  **Audio** mutes a member in a voice chat  |  
 Set Member Nickname  | Member Control  |  Changes the users nickname on the server  |  
 Set Member Permissions  | Member Control  |   |  
 Set Member Voice Channel  | Member Control  |   |  
 Store Member Info  | Member Control  |  Stores information about the member, things like username, nickname, avatar URL, game, color, etc  |  
 Unban Member  | Member Control  |  Unbans a member from the server  |  
 Add Embed Field  | Messaging  |   |  
 Add Reaction  | Messaging  |   |  
 Create Embed Message  | Messaging  |   |  
 Delete Bulk Messages  | Messaging  |  Deletes multiple messages. Due to Discords API limits you may only delete 2-100 messages at a time and they must be < 14 days old  |  
 Delete Message  | Messaging  |  Delete a single message  |  
 Edit Message  | Messaging  |  Edit the content of a message  |  
 Pin Message  | Messaging  |  Pin a message to a channel  |  
 Send Embed Message  | Messaging  |  Sends an embed message. Requires `Create Embed Message` before being used  |  
 Send File  | Messaging  |   |  
 Send Message  | Messaging  |  Sends a text message to the specified channel  |  
 Send TTS Message  | Messaging  |   |  
 Set Embed Description  | Messaging  |   |  
 Store Message Info  | Messaging  |  Stores information about a specified message. **DO NOT use this if you are trying to store parameters** -> instead you should use `Store Command Parameters`  |  
 Call Command/Event  | Other Stuff  |  Run another command / event from the current command / event  |  [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/callcommandevent.PNG) 
 Control Variable  | Other Stuff  |  Sets the value of a variable  |  [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/controlvariable.PNG)
 End Action Sequence  | Other Stuff  |  Stops all actions in the current command / event (often used in conjunction with `Check Variable`  |  [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/endactionsequence.PNG)
 Generate Random Number  | Other Stuff  |  Chooses a random number within a specified range  |  [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/generaterandomnumber.PNG)
 Run Script  | Other Stuff  |  Run custom JavaScript code directly within DBM  |  [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/runscript.PNG)
 Save Variable  | Other Stuff  |  Saves a variable to a data file, so the information will be retained when the bot restarts  |  
 Store Command Params  | Other Stuff  |  Stores parameters for a command. See [this tutorial](https://silversunset.net/dbm/tutorials#data-store-command-parameters) for more info  |  [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/storecommandparams.PNG)
 Store Time Info  | Other Stuff  |   |  
 Transfer Variable  | Other Stuff  |   |  
 Wait  | Other Stuff  |   |  [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/wait.PNG)
 Create Role  | Role Control  |   |  
 Delete Role  | Role Control  |   |  
 Edit Role  | Role Control  |   |  
 Find Role  | Role Control  |   |  
 Stor Role Info  | Role Control  |   |  
 Find Server  | Server Control  |   | 
 Set Server Icon  | Server Control  |   | 
 Set Server Name  | Server Control  |   | 
 Set Server Region  | Server Control  |   | 
 Set Server Splash Screen  | Server Control  |   | 
 Set Server Verification  | Server Control  |   | 
 Store Server Info  | Server Control  |   | 
