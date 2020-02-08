Action | Category | Description | IMG
:-  |  :-  |  :-  |  :-:
Add Embed Field | Messaging | Adds a new field to an embed message, requires `Create Embed Message` | 
Add Item to List | Lists and Loops | Adds an item to a previously created list. | 
Add Member Role | Member Control | Adds a role to a specified member | 
Add Reaction | Messaging | Adds an emoji reaction to the specified message | 
Apply Image Effect | Image Editing | Applies effects to an image (grayscale, invert, transparancy, blur, dither) | 
Ban Member | Member Control | Bans a member from the server | 
Call Command/Event | Other Stuff | Run another command / event from the current command / event | [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/callcommandevent.PNG)
Change Server | Server Control | If the bot is in multiple servers, allows you to switch to a specified server prior to doing further actions | 
Check if Member Has Role | Conditions | Check if the specified user has a role, often used with `Find Role` | 
Check is Bot in Voice Channel | Conditions | Check if the bot is in any voice channel | 
Check Member Data | Deprecated | Compare member data from `data/players.json` to a specified value | 
Check Member Permissions | Conditions | Check if a member has specific permissions (things like ban user, manage messages, etc) | 
Check Parameters | Conditions | Verify user input by checking the number/type of parameters entered on a command | 
Check Server Data | Deprecated | Compare server data from `data/servers.json` to a specified value | 
Check Variable | Conditions | Check the value of a variable, things like "variable includes" or "variable equals". In JavaScript this is an `if... then...` | 
Check Variable Type | Conditions | Check the type of a variable, things like "variable is number" or "variable is channel". In JavaScript this is an `if... then...` | 
Clear Queue | Audio Control | Clears the bots music queue | 
Control Audio | Audio Control | Stop / Pause / Resume playback of audio | 
Control Member Data | Deprecated | Saves member data to the `data/players.json` file | 
Control Server Data | Deprecated | Saves server data to the `data/servers.json` file | 
Control Variable | Other Stuff | Sets the value of a variable | [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/controlvariable.PNG)
Convet List to Text | Lists and Loops | Transforms a list from JSON format `["item","item","item"]` to something more friendly like <br/>`- item`<br/>`- item`<br/>`- item` | 
Create Embed Message | Messaging | Creates a rich embed message. See [this tutorial](https://silversunset.net/dbm/tutorials#miscellaneous-tutorials-how-to-create-an-embed-message) for more information. | 
Create Emoji | Emoji Control | Creates an emoji on the server | 
Create Image | Image Editing | Creates an image from a local file or web URL | 
Create Image from Avatar | Image Editing | Creates an image from a users avatar | 
Create Invite | Channel Control | Creates an invite for the specified channel | 
Create List | Lists and Loops | Creates a list, in JavaScript this is referred to as an Array | 
Create Role | Role Control | Creates a new role | 
Create Text Channel | Channel Control | Creates a new text channel | 
Create Voice Channel | Channel Control | Creates a new voice channel | 
Delete Bulk Messages | Messaging | Deletes multiple messages. Due to Discords API limits you may only delete 2-100 messages at a time and they must be < 14 days old | 
Delete Channel | Channel Control | Deletes a channel from the server | 
Delete Emoji | Emoji Control | Deletes an emoji from the server | 
Delete Message | Messaging | Delete a single message | 
Delete Role | Role Control | Deletes a role from the server | 
Draw Image on Image | Image Editing | Combines two images (using Overlay/Mask/Replace options) | 
Draw Text on Image | Image Editing | Adds text to an image | 
Edit Message | Messaging | Edit the content of a message | 
Edit Role | Role Control | Edits an existing role (hoisted / mentionable) | 
End Action Sequence | Other Stuff | Stops all actions in the current command / event (often used in conjunction with `Check Variable` | [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/endactionsequence.PNG)
Find Channel | Channel Control | Get a channel object for a text channel | 
Find Custom Emoji | Emoji Control | Finds a custom emoji on the server, searches by ID or Name | 
Find Member | Member Control | Obtains the member object | 
Find Role | Role Control | Gets the role object of a specified role | 
Find Server | Server Control | Gets the server object of a specified server | 
Find Voice Channel | Channel Control | Get a channel object for a voice channel | 
Generate Random Number | Other Stuff | Chooses a random number within a specified range | [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/generaterandomnumber.PNG)
Get Bot as Member | Bot Client Control | Get the bot member object | 
Get Item from List | Lists and Loops | Retrieve an item from a previously created list | 
Get List Length | Lists and Loops | Count the number of items in a previously created list | 
Join Voice Channel | Audio Control | Makes the bot Join a specified voice channel | 
Kick Member | Member Control | Kicks a member from the server | 
Leave Voice Channel | Audio Control | Makes the bot leave a specified voice channel | 
Loop Through All Servers | Lists and Loops | Cycles through all of the bots servers to perform actions. Requires an event that contains the actions to perform. | 
Loop Through List | Lists and Loops | Cycle through a previously created list and perform actions for each item, requires an event as well that contains all actions to perform for each object. See [this tutorial](https://silversunset.net/dbm/tutorials#miscellaneous-tutorials-lists-loops) for more info | 
Pin Message | Messaging | Pin a message to a channel | 
Play File | Audio Control | Plays an audio file located within the bots file system | 
Play URL | Audio Control | Plays an audio file located on the internet | 
Play YouTube Video | Audio Control | Plays a youtube video | 
Remove Item from List | Lists and Loops | Removes an item from a previously created list | 
Remove Member Role | Member Control | Removes a role from a specificed member | 
Resize Image | Image Editing | Resizes the image (px or percent) | 
Rotate Image | Image Editing | Rotate the image (by degrees / mirror) | 
Run Script | Other Stuff | Run custom JavaScript code directly within DBM | [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/runscript.PNG)
Save Variable | Other Stuff | Saves a variable to a data file, so the information will be retained when the bot restarts | 
Send Embed Message | Messaging | Sends an embed message. Requires `Create Embed Message` before being used | 
Send File | Messaging | Sends a file from a local folder | 
Send Image | Image Editing | Sends the image in channel | 
Send Message | Messaging | Sends a text message to the specified channel | 
Send TTS Message | Messaging | Sends a **T**ext **T**o **S**peach message | 
Set Audio Volume | Audio Control | Sets the bots audio volume for playback | 
Set Bot AFK Status | Bot Client Control | Changes the bots status between AFK/Not AFK | 
Set Bot Avatar | Bot Client Control | Changes the bots avatar image | 
Set Bot Game | Bot Client Control | Changes the bots game to `Playing [your text here]` | 
Set Bot Nickname | Bot Client Control | Changes the bots nickname on the server | 
Set Bot Status | Bot Client Control | Changes the bots status between Online/Idle/Invisible/DND | 
Set Bot Username | Bot Client Control | Changes the bots username | 
Set Channel Permissions | Channel Control | Set the permissions of a specified channel | 
Set Embed Description | Messaging | Sets the desription field of an embed. Requires `Create Embed Message` | 
Set Member Channel Perms | Channel Control | Sets a members permissions for a specific channel | 
Set Member Deafen | Member Control | **Audio** deafens a user in a voice chat | 
Set Member Mute | Member Control | **Audio** mutes a member in a voice chat | 
Set Member Nickname | Member Control | Changes the users nickname on the server | 
Set Member Permissions | Member Control | Add or Remove discord permissions from a specific user | 
Set Member Voice Channel | Member Control | Move member to a specified voice channel | 
Set Role Channel Perms | Channel Control | Set the permissions of a specified role | 
Set Server Icon | Server Control | Changes the servers icon image | 
Set Server Name | Server Control | Changes the servers name | 
Set Server Region | Server Control | Changes the servers region | 
Set Server Splash Screen | Server Control | Changes the servers splash screen **Requires a discord-verified server** | 
Set Server Verification | Server Control | Changes the servers verification level | 
Skip Queue | Audio Control | Skips [number] of items in the bots queue | 
Store Channel Info | Channel Control | Store information about a text channel, i.e. Name, Topic, Last Message, Position, etc | 
Store Command Params | Other Stuff | Stores parameters for a command. See [this tutorial](https://silversunset.net/dbm/tutorials#data-store-command-parameters) for more info | [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/storecommandparams.PNG)
Store Member Data | Deprecated | Reads member data from the `data/players.json` file | 
Store Member Info | Member Control | Stores information about the member, things like username, nickname, avatar URL, game, color, etc | 
Store Message Info | Messaging | Stores information about a specified message. **DO NOT use this if you are trying to store parameters** -> instead you should use `Store Command Parameters` | 
Store Role Info | Role Control | Stores information about a role (ID, Color, Position, etc) | 
Store Server Data | Deprecated | Reads server data from the `data/servers.json` file | 
Store Server Info | Server Control | Stores information about a server (Name, Region, Icon URL, Verification Level, etc) | 
Store Time Info | Other Stuff | Stores components of the current time (month, day, year, hour, etc) | 
Store Voice Channel Info | Channel Control | Store information about a voice channel, i.e. Name, Topic, Last Message, Position, etc | 
Transfer Variable | Other Stuff | Transfer the value of one variable to another | 
Transform List | Lists and Loops |  | 
Unban Member | Member Control | Unbans a member from the server | 
Wait | Other Stuff | Wait a specified amount of time (minutes, seconds, etc) | [link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/wait.PNG)
