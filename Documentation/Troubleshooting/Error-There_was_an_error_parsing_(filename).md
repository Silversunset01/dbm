# Error: There was an error parsing `filename.json`
Navigate to your bots folder > DATA > and open the file that is unable to parse in a text editor.  

_note: this also applies to server.json, serverVars.json, and globalVars.json_  

## Bot Encryption
You might also get these errors if you have encrypted your bot.
You can disable the encryption from the **Settings** tab.

## If your file is empty

1. Open the bots project folder  
2. Open the DATA folder  
3. Open the file that is erroring (`players.json` etc)  
4. Enter `{ }`, save and close the file  
5. Restart your bot  

## If your file is not empty
1. Launch Steam  
2. Open Software Library section  
3. Right-click on DBM and select Properties from the menu  
4. Select the Local files tab  
5. Click the Verify integrity of game files button.  
6. Steam will verify the game's files - this process may take several minutes.  

_note: if you have mods installed you will need to reinstall them after this process_  

## Crypto.createDecipher is deprecated
```
There was issue parsing commands.json!  
(node:10416) [DEP0106] DeprecationWarning: crypto.createDecipher is deprecated.  
There was issue parsing events.json!  
There was issue parsing players.json!  
There was issue parsing settings.json!  
There was issue parsing serverVars.json!  
There was issue parsing globalVars.json!   
There was issue parsing servers.json!
```

Occasionally you may get this error.  
If you get this error, either delete your encryption key under the settings page, or insert anything and delete it from the encryption key field.
