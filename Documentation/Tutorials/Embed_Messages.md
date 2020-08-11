# How to Create an Embed Message
Your bot can send two types of messages, a normal message (that looks like something you would type) and an embed message.
### To create an embed you must have at least three actions

**1. Create embed** - you must create an embed first. If you've not created an embed you won't be able to send it.
[THIS IMAGE](https://i.imgur.com/F07x5YV.png) is a full explanation of what the fields mean.
For this example we'll use the following settings:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest.png)

**2. Add embed field OR set embed description** - If you want to add more content to your embed you can add a field or description. You can do both if you wish as well. The main difference is that the *Description* field does not have a required header, as the "embed title" is considered the header. the *embed field* item requires both a name and a description.
For this example we'll use the following settings (Both an embed description AND an embed field):

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest2.png)

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest3.png)

**3. Add a footer (with a script)** - If you don't have DBM Mods you can add an embed footer with a script. This will add the author's username and avatar to the embed footer.
If you want to add more text you can modify the script text.

*Script Text:* `tempVars("e").setFooter(member.displayName, msg.author.avatarURL)`

*Modified Script Text:* `tempVars("e").setFooter(member.displayName + " Some Other Text", msg.author.avatarURL)`

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest4.png)

**4. Send the embed** - after you've created the embed with all its fancy fields you must send it!
DBM Defaults to "Same Channel" which will send the embed to the same channel as the command message. You've got the same options here as you do a normal send-message. (If you send the message to a user the user will receive a DM unless they have those blocked)

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest5.png)

**THE RESULT**:
If you've copied all of the steps above you should end up with an embed like this:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest6.png)