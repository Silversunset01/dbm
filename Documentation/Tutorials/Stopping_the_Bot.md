# Stopping the Bot

Sometimes you need to stop your bot. If you're running a script like `forever` this may automatically restart your bot, otherwise, it will just shut the whole bot down.

**Action 1: send a message** to the channel so you know the bot has recognized the command

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/stopping.png)

**Action 2: stop the bot using a script**. Its good practice to log to console that the bot is stopping, again to confirm that the action is recognized.

`console.log("text")` is used to print text directly to the bots console logs. Anything inside the `" "` will be printed directly. If you choose to use a variable instead you would use `console.log(tempVars("name"))`

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/stopping2.png)
