# Error: Cannot Add Roles to User
[Cannot Find the Role](#cannot-find-the-role)  
[Invalid Permissions](#invalid-permissions)  

A common bot task is to add roles to users either automatically upon joining, or via command. Here we will review some common errors that can occur.  

## Cannot Find the Role
**Error:** From bot logs: _The supplied role is neither a role nor a snowflake_<br/>
**Cause:** Using a role name instead of an object in "Add Member Role" without using the Find options, or the role could not be found.<br/>
**Solution:** Use the Find source role options in Add Member Role and use correct capitalization in the query.<br/>

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/roleexamplenew.png)

## Invalid Permissions
**Error:** From bot logs: _DiscordAPIError: Missing Permissions_<br/>
**Cause:** The bot has insufficient permissions to add roles to users.<br/>
**Solution 1:** Make sure that your bot has the permission to Manage Roles.<br/>
**Solution 2:** Discord does not allow a user to manage a role that is *higher* in the list than the user's highest role. This applies to bots as well as normal users (except server owners). In your server's Role list move the bot's role higher than the roles you are trying to apply.  

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/rolelist1.jpg)