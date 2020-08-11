# Messaging
[Embeds](#embeds) | [Misc](#miscellanous)  

## Embeds
Usage | Script
:- | :-
Add Field to Embed message | `tempVars("test").addField("Test Name", "Test Value", [inline]);` <br/> `[inline]` = true or false (Defaults to false)
Add Blank Field to Embed Message | `tempVars("test").addField('\u200B', '\u200B', [inline])` <br/> `[inline]` = true or false (Defaults to false)
Add Footer to Embed message | `tempVars("test").setFooter(member.displayName, msg.author.avatarURL({ dynamic: true }))` <br/> or for plain text <br/> `tempVars("test").setFooter("your text here")`

## Miscellaneous
Usage | Script
:- | :-
Send a message (hard coded text) | `msg.channel.send("your message here")`
Send a message (variable) | `msg.channel.send(tempVars("some_variable"))`
Send a message (with mixed text & variables) | `msg.channel.send("some text here " + tempVars("some_variable") + " and some more text")`
Send a message (to another channel)| `msg.guild.channels.cache.find(c => c.name === "bot-logs").send("test in another channel")` <br/>*can use "id" instead of "name"*
Log to console | `console.log("your text here")`
Add reactions to message <br/> - *works on normal messages or embeds*<br/>- *If using this on an embed, you do not need the "send embed message" action, this will replace it* | `msg.channel.send(tempVars("test"))` <br /> `.then(async function(message) {` <br /> `await message.react("👍")` <br /> `await message.react("👎")` <br /> `}).catch(function() {` <br /> `msg.channel.send("is broke yo")` <br /> `});`
Collect reactions to a message | ```const filter = (reaction, user) => reaction.emoji.name === '👍'; tempVars("your_message").awaitReactions(filter, { time: 15000 }).then(collected => msg.channel.send(`Collected ${collected.size} 👍 reactions`)).catch(console.error);```