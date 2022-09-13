Action|Category|Description|IMG
-----|-----|-----|-----
Action Anchor|Other Stuff|Creates an Action Anchor in its position to allow your bot to jump back to and run any actions below it|
Action Container|Other Stuff|Holds a sequence of actions inside of a container|
Add Embed Field|Messaging|Adds a new field to an embed message, requires `Create Embed Message`|
Add Embed to Message Data|Embed Message|Adds an Embed object to Message Data|
Add Item to List|Lists and Loops|Adds an item to a previously created list|
Add Member Role|Member Control|Adds a role to a specified member|
Add Reaction|Messaging|Adds an emoji reaction to the specified message|
Apply Image Effect|Image Editing|Applies effects to an image (grayscale, invert, transparancy, blur, dither)|
Archive Thread|Channel Control|Archives a channel thread|
Await Message from Member|Messaging|Await a specified amount of messages from a member|
Ban Member|Member Control|Bans a member from the server|
Call Command/Event|Other Stuff|Run another command / event from the current command / event|[link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/callcommandevent.PNG)
Change Server|Server Control|If the bot is in multiple servers, allows you to switch to a specified server prior to doing further actions|
Check Member Data|Data|Compare member data from `data/players.json` to a specified value|
Check Member Permissions|Conditions|Check if a member has specific permissions (things like ban user, manage messages, etc)|
Check Message Data|Data|Compare message data from `data/messages.json` to a specified value|
Check Parameters|Conditions|Verify user input by checking the number/type of parameters entered on a command|
Check Server Data|Data|Compare server data from `data/servers.json` to a specified value|
Check Variable|Conditions|Check the value of a variable, things like "variable includes" or "variable equals". In JavaScript, this is an `if... then...`|
Check Variable Type|Conditions|Check the type of a variable, things like "variable is number" or "variable is channel". In JavaScript, this is an `if... then...`|
Check if Member Has Role|Conditions|Check if the specified user has a role, often used with `Find Role`|
Check is Bot in Voice Channel|Conditions|Check if the bot is in any voice channel|
Clear Queue|Audio Control|Clears the bots music queue|
Control Audio|Audio Control|Stop / Pause / Resume playback of audio|
Control Member Data|Data|Saves member data to the `data/players.json` file|
Control Message Data|Data|Saves message data to the `data/messages.json` file|
Control Server Data|Data|Saves server data to the `data/servers.json` file|
Control Variable|Other Stuff|Sets the value of a variable|[link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/controlvariable.PNG)
Convert List to Text|Lists and Loops|Transforms a list from JSON format `["item","item","item"]` to something more friendly like <br/>`- item`<br/>`- item`<br/>`- item`|
Create Embed Message|Messaging|Creates a rich embed message. See [this tutorial](https://silversunset.net/dbm/tutorials?topic=Embed_Messages) for more information|
Create Emoji|Emoji/Sticker Control|Creates an emoji on the server|
Create Image|Image Editing|Creates an image from a local file or web URL|
Create Image from Avatar|Image Editing|Creates an image from a users avatar|
Create Invite|Channel Control|Creates an invite for the specified channel|
Create List|Lists and Loops|Creates a list, in JavaScript this is referred to as an Array|
Create Role|Role Control|Creates a new role|
Create Sticker|Emoji/Sticker Control|Creates a sticker on the server|
Create Text Channel|Channel Control|Creates a new text channel|
Create Thread|Channel Control|Creates a thread for the specified channel|
Create Voice Channel|Channel Control|Creates a new voice channel|
Delete Bulk Messages|Messaging|Deletes multiple messages. Due to Discords API limits you may only delete 2-100 messages at a time and they must be < 14 days old|
Delete Channel|Channel Control|Deletes a channel from the server|
Delete Emoji|Emoji/Sticker Control|Deletes an emoji from the server|
Delete Message|Messaging|Delete a single message|
Delete Role|Role Control|Deletes a role from the server|
Delete Sticker|Emoji/Sticker Control|Deletes a sticker from the server|
Disable Buttons and Selects|Messaging|Disable or Re-enable buttons and select menu components from the specified message (must be sent by the bot)|
Disable Command|Other Stuff|Disable a slash command or context menu for a certain role or user|
Draw Image on Image|Image Editing|Combines two images (using Overlay/Mask/Replace options)|
Draw Text on Image|Image Editing|Adds text to an image|
Edit Any Channel|Channel Control|Edit any channel or thread|
Edit Message|Messaging|Edit the content of a message|
Edit Role|Role Control|Edits an existing role (hoisted / mentionable)|
Edit Select Menu Options|Messaging|Edit the options for the specified select menu|
End Action Sequence|Other Stuff|Stops all actions in the current command / event (often used in conjunction with `Check Variable`|[link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/endactionsequence.PNG)
Find Channel|Channel Control|Get a channel object for a text/voice channel|
Find Custom Emoji/Sticker|Emoji/Sticker Control|Finds a custom emoji or sticker on the server, searches by ID or Name|
Find Member|Member Control|Obtains the member object|
Find Role|Role Control|Gets the role object of a specified role|
Find Server|Server Control|Gets the server object of a specified server|
Find Thread|Channel Control|Get a channel object for a thread channel|
Find Voice Channel|Channel Control|Get a channel object for a voice channel|
Generate Random Number|Other Stuff|Chooses a random number within a specified range|[link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/generaterandomnumber.PNG)
Get Bot as Member|Bot Client Control|Get the bot member object|
Get Item from List|Lists and Loops|Retrieve an item from a previously created list|
Get List Length|Lists and Loops|Count the number of items in a previously created list|
Go to Action Anchor|Other Stuff|Jumps to an Action Anchor|
Join Voice Channel|Audio Control|Makes the bot Join a specified voice channel|
Kick Member|Member Control|Kicks a member from the server|
Leave Voice Channel|Audio Control|Makes the bot leave a specified voice channel|
Loop Through All Servers|Lists and Loops|Cycles through all of the bots servers to perform actions. Requires an event that contains the actions to perform.|
Loop Through List|Lists and Loops|Cycle through a previously created list and perform actions for each item, requires an event as well that contains all actions to perform for each object. See [this tutorial](https://silversunset.net/dbm/tutorials#miscellaneous-tutorials-lists-loops) for more info|
Loop Through Numbers|Lists and Loops|Loop/repeat an action sequence through a specified range of numbers|
Multi-Check Variable|Conditions|Run multiple checks of the value of a variable. In Javascript, this is an `if... elseif...` or `switch`|
Pin Message|Messaging|Pin a message to a channel|
Play File|Audio Control|Plays an audio file located within the bots file system|
Play URL|Audio Control|Plays an audio file located on the internet|
Play YouTube Video|Audio Control|Plays a youtube video|
Remove Buttons and Selects|Messaging|Remove buttons and select menu components from the specified message (must be sent by the bot)|
Remove Item from List|Lists and Loops|Removes an item from a previously created list|
Remove Member Role|Member Control|Removes a role from a specificed member|
Resize Image|Image Editing|Resizes the image (px or percent)|
Rotate Image|Image Editing|Rotate the image (by degrees / mirror)|
Run Script|Other Stuff|Run custom JavaScript code directly within DBM|[link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/runscript.PNG)
Save Variable|Other Stuff|Saves a variable to a data file, so the information will be retained when the bot restarts|
Send Embed Message|Messaging|Sends an embed message. Requires `Create Embed Message` before being used|
Send File|Messaging|Sends a file from a local folder|
Send Image|Image Editing|Sends the image in channel|
Send Message|Messaging|Sends a text message to the specified channel|
Send TTS Message|Messaging|Sends a **T**ext **T**o **S**peach message|
Set Audio Volume|Audio Control|Sets the bots audio volume for playback|
Set Bot AFK Status|Bot Client Control|Changes the bots status between AFK/Not AFK|
Set Bot Activity|Bot Client Control|Changes the bot's activity to "Watching/Playing/Streaming/Listening to [game name]"|
Set Bot Avatar|Bot Client Control|Changes the bots avatar image|
Set Bot Nickname|Bot Client Control|Changes the bots nickname on the server|
Set Bot Status|Bot Client Control|Changes the bots status between Online/Idle/Invisible/DND|
Set Bot Username|Bot Client Control|Changes the bots username|
Set Channel Permissions|Channel Control|Set the permissions of a specified channel|
Set Embed Description|Messaging|Sets the desription field of an embed. Requires `Create Embed Message`|
Set Member Channel Perms|Channel Control|Sets a members permissions for a specific channel|
Set Member Deafen|Member Control|Audio deafens a user in a voice chat|
Set Member Mute|Member Control|Audio mutes a member in a voice chat|
Set Member Nickname|Member Control|Changes the users nickname on the server|
Set Member Permissions|Member Control|Add or Remove discord permissions from a specific user|
Set Member Voice Channel|Member Control|Move member to a specified voice channel|
Set Role Channel Perms|Channel Control|Set the permissions of a specified role|
Set Role Icon|Role Control|Add a custom image/emoji icon to the specified role (**Requires a high enough server boost level**)|
Set Server Icon|Server Control|Changes the servers icon image|
Set Server Name|Server Control|Changes the servers name|
Set Server Region|Server Control|Changes the servers region|
Set Server Splash Screen|Server Control|Changes the servers splash screen **Requires a discord-verified server**|
Set Server Verification|Server Control|Changes the servers verification level|
Show Modal|Messaging|Sends the user a Modal for text input|
Shuffle Queue|Audio Control|Shuffles the music queue|
Skip Queue|Audio Control|Skips [number] of items in the bots queue|
Start Thinking|Other Stuff|Delay your interaction response and display a `Bot is thinking...` message (This will prevent errors if your action sequence takes too long to send an interaction response)|
Store Channel Info|Channel Control|Store information about a text channel, i.e. Name, Topic, Last Message, Position, etc|
Store Command Params|Other Stuff|Stores parameters for a command. See [this tutorial](https://silversunset.net/dbm/tutorials#data-store-command-parameters) for more info|[link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/storecommandparams.PNG)
Store Member Data|Data|Reads member data from the `data/players.json` file|
Store Member Info|Member Control|Stores information about the member, things like username, nickname, avatar URL, game, color, etc|
Store Message Data|Data|Reads message data from the `data/messages.json` file|
Store Message Info|Messaging|Stores information about a specified message. **DO NOT use this if you are trying to store parameters** -> instead you should use `Store Command Parameters`|
Store Role Info|Role Control|Stores information about a role (ID, Color, Position, etc)|
Store Server Data|Data|Reads server data from the `data/servers.json` file|
Store Server Info|Server Control|Stores information about a server (Name, Region, Icon URL, Verification Level, etc)|
Store Thread Channel Info|Channel Control|Store information about a thread channel|
Store Time Info|Other Stuff|Stores components of the current time (month, day, year, hour, etc)|
Store Voice Channel Info|Channel Control|Store information about a voice channel, i.e. Name, Topic, Last Message, Position, etc|
Timeout Member|Member Control|Timeout a member in the server for a given amount of seconds|
Transfer Variable|Other Stuff|Transfer the value of one variable to another|
Transform List|Lists and Loops||
Unban Member|Member Control|Unbans a member from the server|
Wait|Other Stuff|Wait a specified amount of time (minutes, seconds, etc)|[link](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/actions/wait.PNG)
