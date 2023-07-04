# Error: The application did not respond
When using application commands (slash commands, buttons, etc), you might get an error on Discord that says "The application did not respond".
This can be caused by a variety of reasons.

## Unknown Interaction
If your bot log contains an error like this: `DiscordAPIError: Unknown interaction` 
It means that your interaction has expired before your bot could respond to it. 

If your command takes longer than an interaction's short time period to execute, you may need a "Start Thinking" action.
This way, your bot can let Discord, and the user, know that your bot is still executing the command and will respond when ready.
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/thinking.PNG)

Just like with interaction replies, you can enable the ephemeral option to make the "thinking" message hidden to other users.

To update the thinking message with your final reply, use a Send Message action with `Reply to Interaction if possible` checked. 
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/thinking2.PNG)

Your thinking message should change to your final reply in Send Message once ready.
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/thinking3.PNG)

## Cannot send an empty message
If your bot log contains an error like this: `DiscordAPIError: Cannot send an empty message` 
It means that your Send Message is either empty or failed to evaluate.

Just like with regular messages, interactions cannot receive an empty message. They must also be responded to, whether it is via sending a message or editing the message the interaction was called from (like a button).

The error can also be caused if your message has code and returns a value that signals nothing (such as "undefined"). Check if all of your code (text in `${}`) is valid. You could even try adding any regular text to prevent the error and see what returned undefined in the message.

## Other bot error
The "The application did not respond" error could also be a result in your command failing to run. Check your bot logs for any errors caused by other actions.