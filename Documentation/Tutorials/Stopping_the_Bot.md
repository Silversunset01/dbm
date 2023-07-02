# Stopping the Bot

Sometimes you need to stop your bot. If you're running a script like `forever`, this may automatically restart your bot; otherwise, it will just shut the whole bot down.

**Action 1: send a message** to the channel so you know the bot has recognized the command.

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/stopping.png)

**Action 2: stop the bot using a script**. We will achieve this using the `process.exit()` method (with "0" as the parameter, meaning that the process exited with no errors). It's also good practice to log to console that the bot is stopping, again to confirm that the action is recognized.


![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/stopping2.png)
