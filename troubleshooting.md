# Troubleshooting

## Error: Bot token is being overwritten
Navigate to `C:\Users\your-name\AppData\local` and delete folders DBM and DBM2

## Error: Cannot Add Roles to User
A common bot task is to add roles to users either automatically on join, or via command. Here we will review some common errors that can occur.

### Cannot Find the Role
**Error:** From bot logs: _The supplied role is neither a role nor a snowflake_<br/>
**Cause:** When adding a role some users will attempt to add the role name directly into the "Add Member Role" field. DBM requires a role object in order to apply the role to a user.<br/>
**Solution:** Instead of typing directly into the Source Role field, first you should use the Find Role action, store the role as a variable, and then use that variable in the Source Role field.<br/>

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/roleexamplenew.jpg)

### Invalid Permissions
**Error:** From bot logs: _Error with Event "Add Member Role", Action ##: DiscordAPIError: Missing Permissions_<br/>
**Cause:** The bot has insufficient permissions to add roles to users.<br/>
**Solution 1:** Make sure that your bot has the permission to Manage Roles.<br/>
**Solution 2:** Discord does not allow a user to manage a role that is *higher* in the list than the users highest role. This applies to bots as well as normal users (with the exception of server owners). In your server's Role list move the bot's role higher than the roles you are trying to apply.

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/rolelist1.jpg)

## Error: Cannot find module 'discord.js'
1. Delete node_modules 
2. type `npm i` (this will reinstall modules)

## Error: DBM won't start
1. Launch Steam
2. Open Software Library section 
3. Right-click on DBM and select Properties from the menu
4. Select the Local files tab
5. Click the Verify integrity of game files button.
6. Steam will verify the game's files - this process may take several minutes.

_note: if you have mods installed you will need to reinstall them after this process_

## Error: FFMPEG not found
1. Press Windows + R
2. Type in the field: cmd
3. Press Enter
4. Start DBM
5. Click on Project -> Open Project Directory
6. Right click on the bar at the top with your path
7. Click on Copy path
8. Go back to your CMD window
9. Type cdPasteYourPathHere and press enter
10. Type npm i
11. Close everything and restart DBM

## Error: There was an error parsing `players.json` |  `commands.json` | `events.json` 
Navigate to your bots folder > DATA > and open the file that is unable to parse in a text editor. 

### If your file is empty

1. Open the bots project folder 
2. Open the DATA folder 
3. Open the file that is erroring (`players.json` etc) 
4. Enter `{ }`, save and close the file 
5. Restart your bot 

### If your file is not empty
1. Launch Steam
2. Open Software Library section 
3. Right-click on DBM and select Properties from the menu
4. Select the Local files tab
5. Click the Verify integrity of game files button.
6. Steam will verify the game's files - this process may take several minutes.

_note: if you have mods installed you will need to reinstall them after this process_

## Error: Unexpected Token
Unexpected Token has nothing to do with your bots token. It means you've got an unmatched bracket somewhere. 

*  `Unexpected Token (` means you're missing `)`
*  `Unexpected Token )` means you're missing `(`  
*  `Unexpected Token {` means you're missing `}`
*  `Unexpected Token }` means you're missing `{`
*  `Unexpected Token <` means you're missing `>`
*  `Unexpected Token >` means you're missing `<`

**Example:**
`${parseInt(tempVars("name")}` will throw an error: `Unexpected Token (` because you're missing a closing `)` after the variable.
