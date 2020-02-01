Category | Action | Description | Img
:-|:-|:-|:-:
Audio Control | Clear Queue | | 
Audio Control | Control Audio | | 
Audio Control | Join Voice Channel | | 
Audio Control | Leave Voice Channel | | 
Audio Control | Play File | | 
Audio Control | Play URL | | 
Audio Control | Play YouTube Video | | 
Audio Control | Set Audio Volume | | 
Audio Control | Skip Queue | | 
Bot Client Control | Get Bot as Member | Get the bot member object | 
Bot Client Control | Set Bot AFK Status | Changes the bots status between AFK/Not AFK | 
Bot Client Control | Set Bot Avatar | Changes the bots avatar image | 
Bot Client Control | Set Bot Game | Changes the bots game to `Playing [your text here]` | 
Bot Client Control | Set Bot Nickname | Changes the bots nickname on the server | 
Bot Client Control | Set Bot Status | Changes the bots status between Online/Idle/Invisible/DND | 
Bot Client Control | Set Bot Username | Changes the bots username | 
Channel Control | Create Text Channel | | 
Channel Control | Create Invite | | 
Channel Control | Create Voice Channel | | 
Channel Control | Delete Channel | | 
Channel Control | Find Channel | Get a channel object for a text channel | 
Channel Control | Find Voice Channel | Get a channel object for a voice channel | 
Channel Control | Set Channel Permissions | Set the permissions of a specified channel | 
Channel Control | Set Member Channel Perms | | 
Channel Control | Set Role Channel Perms | Set the permissions of a specified role | 
Channel Control | Store Channel Info | Store information about a text channel, i.e. Name, Topic, Last Message, Position, etc | 
Channel Control | Store Voice Channel Info | Store information about a voice channel, i.e. Name, Topic, Last Message, Position, etc | 
Conditions | Check if Member Has Role  | Check if the specified user has a role, often used with `Find Role` | 
Conditions | Check is Bot in Voice Channel | | 
Conditions | Check Member Permissions | | 
Conditions | Check Parameters | Verify user input by checking the number/type of parameters entered on a command | 
Conditions | Check Variable | Check the value of a variable, things like "variable includes" or "variable equals". In JavaScript this is an `if... then...` | 
Conditions | Check Variable Type | Check the type of a variable, things like "variable is number" or "variable is channel". In JavaScript this is an `if... then...` | 
Deprecated | Check Member Data | Compare member data from `data/players.json` to a specified value  | 
Deprecated | Check Server Data | Compare server data from `data/servers.json` to a specified value | 
Deprecated | Control Member Data | Saves member data to the `data/players.json` file | 
Deprecated | Control Server Data | Saves server data to the `data/servers.json` file | 
Deprecated | Store Member Data | Reads member data from the `data/players.json` file | 
Deprecated | Store Server Data | Reads server data from the `data/servers.json` file | 
Emoji Control | Create Emoji | | 
Emoji Control | Delete Emoji | | 
Emoji Control | Find Custom Emoji | | 
Image Editing | Create Image | | 
Image Editing | Create Image from Avatar | | 
Image Editing | Draw Image on Image | | 
Image Editing | Draw Text on Image | | 
Image Editing | Apply Image Effect | | 
Image Editing | Resize Image | | 
Image Editing | Rotate Image | | 
Image Editing | Send Image | | 
Lists and Loops | Add Item to List | Adds an item to a previously created list. | 
Lists and Loops | Convet List to Text | Transforms a list from JSON format `["item","item","item"]` to something more friendly like <br/>`- item`<br/>`- item`<br/>`- item` | 
Lists and Loops | Create List | Creates a list, in JavaScript this is referred to as an Array | 
Lists and Loops | Get Item from List | Retrieve an item from a previously created list | 
Lists and Loops | Get List Length | Count the number of items in a previously created list | 
Lists and Loops | Loop Through All Servers | | 
Lists and Loops | Loop Through List | Cycle through a previously created list and perform actions for each item, requires an event as well that contains all actions to perform for each object. See [this tutorial](https://silversunset.net/dbm/tutorials#miscellaneous-tutorials-lists-loops) for more info | 
Lists and Loops | Remove Item from List | Removes an item from a previously created list | 
Lists and Loops | Transform List | | 
Member Control | Add Member Role | Adds a role to a specified member | 
Member Control | Ban Member | Bans a member from the server | 
Member Control | Find Member | Obtains the member object | 
Member Control | Kick Member | Kicks a member from the server | 
Member Control | Remove Member Role | Removes a role from a specificed member | 
Member Control | Set Member Deafen | **Audio** deafens a user in a voice chat | 
Member Control | Set Member Mute | **Audio** mutes a member in a voice chat | 
Member Control | Set Member Nickname | Changes the users nickname on the server | 
Member Control | Set Member Permissions | | 
Member Control | Set Member Voice Channel | | 
Member Control | Store Member Info | Stores information about the member, things like username, nickname, avatar URL, game, color, etc | 
Member Control | Unban Member | Unbans a member from the server | 
Messaging | Add Embed Field | | 
Messaging | Add Reaction | | 
Messaging | Create Embed Message | | 
Messaging | Delete Bulk Messages | Deletes multiple messages. Due to Discords API limits you may only delete 2-100 messages at a time and they must be < 14 days old | 
Messaging | Delete Message | Delete a single message | 
Messaging | Edit Message | Edit the content of a message | 
Messaging | Pin Message | Pin a message to a channel | 
Messaging | Send Embed Message | Sends an embed message. Requires `Create Embed Message` before being used | 
Messaging | Send File | | 
Messaging | Send Message | Sends a text message to the specified channel | 
Messaging | Send TTS Message | | 
Messaging | Set Embed Description | | 
Messaging | Store Message Info | Stores information about a specified message. **DO NOT use this if you are trying to store parameters** -> instead you should use `Store Command Parameters` | 
Other Stuff | Call Command/Event | Run another command / event from the current command / event | [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/callcommandevent.PNG) 
Other Stuff | Control Variable | Sets the value of a variable | [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/controlvariable.PNG)
Other Stuff | End Action Sequence | Stops all actions in the current command / event (often used in conjunction with `Check Variable` | [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/endactionsequence.PNG)
Other Stuff | Generate Random Number | Chooses a random number within a specified range | [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/generaterandomnumber.PNG)
Other Stuff | Run Script | Run custom JavaScript code directly within DBM | [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/runscript.PNG)
Other Stuff | Save Variable | Saves a variable to a data file, so the information will be retained when the bot restarts | 
Other Stuff | Store Command Params | Stores parameters for a command. See [this tutorial](https://silversunset.net/dbm/tutorials#data-store-command-parameters) for more info | [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/storecommandparams.PNG)
Other Stuff | Store Time Info | | 
Other Stuff | Transfer Variable | | 
Other Stuff | Wait | | [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/wait.PNG)
Role Control | Create Role | | 
Role Control | Delete Role | | 
Role Control | Edit Role | | 
Role Control | Find Role | | 
Role Control | Stor Role Info | | 
Server Control | Find Server | |
Server Control | Set Server Icon | |
Server Control | Set Server Name | |
Server Control | Set Server Region | |
Server Control | Set Server Splash Screen | |
Server Control | Set Server Verification | |
Server Control | Store Server Info | |
