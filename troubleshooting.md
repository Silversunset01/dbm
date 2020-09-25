# Troubleshooting
## Error: [Action] does not exist!
If you are running your bot outside of DBM, you might get this error: `action does not exist` (_"action" being the action name_)  
If you get this error, it means the action is missing inside your project's action folder.  

## Error: Bot token is being overwritten
Navigate to `C:\Users\User-Name\AppData\Local` and delete the DBM2 folder.  

## Error: Cannot Add Roles to User
A common bot task is to add roles to users either automatically upon joining, or via command. Here we will review some common errors that can occur.  

### Cannot Find the Role
**Error:** From bot logs: _The supplied role is neither a role nor a snowflake_<br/>
**Cause:** When adding a role some users will attempt to add the role name directly into the "Add Member Role" field. DBM requires a role object to apply the role to a user.<br/>
**Solution:** Instead of typing directly into the Source Role field, first you should use the Find Role action, store the role as a variable, and then use that variable in the Source Role field.<br/>

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/roleexamplenew.jpg)

### Invalid Permissions
**Error:** From bot logs: _Error with Event "Add Member Role", Action ##: DiscordAPIError: Missing Permissions_<br/>
**Cause:** The bot has insufficient permissions to add roles to users.<br/>
**Solution 1:** Make sure that your bot has the permission to Manage Roles.<br/>
**Solution 2:** Discord does not allow a user to manage a role that is *higher* in the list than the user's highest role. This applies to bots as well as normal users (except server owners). In your server's Role list move the bot's role higher than the roles you are trying to apply.  

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/rolelist1.jpg)

## Error: Cannot find module `discord.js`
1. Delete node_modules  
2. type `npm i discord.js@11.6.1` (this will reinstall the discord.js module)  

## Error: Cannot find module `./constants`
You need to reinstall your node modules from package.json  
### For Windows:
1. In CMD type `CD/your bot directory` (if you're not already in it)  
2. Enter the following exactly `rd /s /q node_modules`  
3. Reinstall modules with `npm i`  

### For Linux
1. From the terminal change directory to your bots folder  
2. type `rm -rf node_modules`  
3. Reinstall modules with `npm i`  

### To install specific modules
1. type `npm i <modulename> --save`  

## Error: DBM won't start
1. Launch Steam  
2. Open Software Library section  
3. Right-click on DBM and select Properties from the menu  
4. Select the Local files tab  
5. Click the Verify integrity of game files button.  
6. Steam will verify the game's files - this process may take several minutes.  

_note: if you have mods installed you will need to reinstall them after this process_  

## Error: FFMPEG Not Working
### "FFMPEG not found"
1. Press Windows + R  
2. Type in the field: cmd  
3. Press Enter  
4. Start DBM  
5. Click on Project -> Open Project Directory  
6. Right-click on the bar at the top with your path  
7. Click on Copy path  
8. Go back to your CMD window  
9. Type cdPasteYourPathHere and press enter  
10. Type npm i  
11. Close everything and restart DBM  

_note: if you have the beta, you can simply press this:_  

![](https://i.need.dbm-support.site/fsot.png)

### Bot connecting, but nothing playing
1. Open your bot directory  
2. Go into the address bar, erase everything and type "cmd"  
3. Type "npm i node-opus --save" when that is complete...  
4. Type "npm i opusscript --save"  
5. Restart your bot  
6. Try your action again!  

## Error: There was an error parsing `players.json` |  `commands.json` | `events.json`
Navigate to your bots folder > DATA > and open the file that is unable to parse in a text editor.  

_note: this also applies to server.json, serverVars.json, and globalVars.json_  

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

## Error: Search bar doesnt work [Beta]
### Reinstall Mods
DBM Beta allows you to search for actions,  but sometimes mods make this break. to fix it:  
1. Close Discord Bot Maker  
2. Open your Steam Library and find Discord Bot Maker on the Software tab  
3. Right-click it → Properties → Local Files → Browse Local Files  
4. Delete the actions folder  
5. Go back to the Properties (Local Files) tab, and press Verify Integrity of Application Files  
6. After the verification is finished and the missing files are reacquired, go back to the DBM folder, refresh it, and copy the actions folder  
7. Open your project folder and delete the actions folder, and paste the one you copied from the DBM folder  

That should have fixed it.
By doing this, your mods will be deleted. So, if you want, you can install them again. Follow the installation guide at https://github.com/dbm-network/mods/tree/beta#installing-mods

### Delete your DBM Cache
For Windows 10:  
1. Exit Discord Bot Maker  
2. Browse to %localappdata%  
3. Delete DBM, DBM2, and any other DBM folders  
4. Start Discord Bot Maker  
5. Search should work  

## Error: Unexpected Token
Unexpected Token has nothing to do with your bots token. It means you've got an unmatched bracket somewhere.  

*  `Unexpected Token (` means you're missing `)`  
*  `Unexpected Token )` means you're missing `(`  
*  `Unexpected Token {` means you're missing `}`<br>
**Note:**
The error `Unexpected Token {` can also mean your Node.js version is below the required version (version 12.8.4+) - update [here](https://nodejs.org/en/)
*  `Unexpected Token }` means you're missing `{`  
*  `Unexpected Token <` means you're missing `>`  
*  `Unexpected Token >` means you're missing `<`  

**Example:**
`${parseInt(tempVars("name")}` will throw an error: `Unexpected Token (` because you're missing a closing `)` after the variable.  

## Error: Uncaught, unspecific "error" event.
This error appears in your console because your hosting service or discord has a few internet problems. That's normal! Problem: It crashes your bot.  
To solve this you can add this easy code into a "Bot Initialization" event. Make sure to put it into a "Run Script" action:  
```js
client.on('error', (error) => {
  if (error.message == 'Unexpected server response: 520') {
    console.error('Cant connect to Discords API, Retrying...')
  } else if (error.message == 'read ECONNRESET') {
    console.error('Connection Reset! Reconnecting...')
  } else {
    console.error(error)
  }
})
```

## Error: with Event "Loop through List"
`with Event "Loop Through List", Action #5: TypeError: Cannot read property '_id' of null`  
This only applies to users who have BETA. The developer is aware of this. In the meantime you can fix it manually:  

1. Click on Project  
2. Click on Open Actions Directory  
3. Download the file below  
4. Copy and paste the file in your folder (Overwrite it!)  
5. Restart DBM.  

(If you run your bot on a VPS or in command line please make sure to update that file too)  
[Download Correct Loop File](https://cdn.discordapp.com/attachments/345696100151459854/486570638018871306/loop_through_list.js)  

## SyntaxError: Block-scoped declarations (let, const, function, class) not yet supported outside strict mode
To stop this error, you must update your [Node.js](https://nodejs.org/en/download/) (The LTS version should be fine.)  
