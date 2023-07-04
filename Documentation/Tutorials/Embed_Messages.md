# How to Create an Embed Message

## Attention
This tutorial uses the Embed Message series of actions. However, you can use the Send Message action to generate embeds more easily using the "Embeds" tab. The embed actions may still work, but they may lack support for sending messages with other components, such as buttons/select menus, etc.


Your bot can send two types of messages, a normal message (that looks like something you would type) and an embed message.
### To create an embed you must have at least three actions

**1. Create embed** - you must create an embed first. If you've not created an embed you won't be able to send it.
[THIS IMAGE](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedexplanation.png) is a full explanation of what the fields mean.
For this example we'll use the following settings:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest.png)

**2. Add embed field OR set embed description** - If you want to add more content to your embed you can add a field or description. You can do both if you wish as well. The main difference is that the *Description* field does not have a required header, as the "embed title" is considered the header. The *embed field* item requires both a name and a description.
For this example we'll use the following actions (Both an embed description AND an embed field):

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest2.png)

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest3.png)

**3. Add a footer** - You can use the Set Embed Footer action to add a footer to your embed.

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest4.png)

**4. Send the embed** - After you've created the embed with all of its fancy fields, you must send it!
DBM defaults to "Same Channel" which will send the embed to the same channel as the command message. You've got the same options here as you do a normal send-message. (If you send the message to a user, the user will receive a DM unless they have those blocked)

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest5.png)

**THE RESULT**:
If you've copied all of the steps above, you should end up with an embed like this:

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/embedtest6.png)
