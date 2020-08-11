# Miscellaneous Javascript
[Formatting](#formatting) | [Identifiers](#identifiers) | [Other](#other)  

## Formatting
Usage | Script
:- | :-
Switch | `switch(thing to eval) {` <br /> `case "OPT1": action to execute on match; break;` <br />`case "OPT2": action to execute on match; break;` <br />`case "OPT3": action to execute on match; break;` <br />`default: action to execute on match; break;` <br /> `}`
If/Then (Ternary) | `(A < 1 ? "value if true" : "value if false")`
If/Then (Normal) | `if(thing to evaluate) {value if true} else {value if false}`

## Identifiers
| Usage | Script |
| :--- | :--- |
| Get the bot as a client | `${client` or `${bot` |
| Get the bot as a guild member | `${msg.guild.me` or `${me` |
| The command message | `${msg` |
| The current server | `${msg.guild` or `${server` |
| The command channel | `${msg.channel` |
| The command author | `${msg.author` or `${user` |
| The command author as a guild member | `${msg.member` or `${member` |

## Other
Usage | Script
:- | :-
Switch | `switch(thing to eval) {` <br /> `case "OPT1": action to execute on match; break;` <br />`case "OPT2": action to execute on match; break;` <br />`case "OPT3": action to execute on match; break;` <br />`default: action to execute on match; break;` <br /> `}`
If/Then (Ternary) | `(A < 1 ? "value if true" : "value if false")`
If/Then (Normal) | `if(thing to evaluate) {value if true} else {value if false}`
Ban User <br/><i>requires user's ID</i> | `msg.guild.members.ban(tempVars("user_id"))`<br/>`.then(user => console.log("Banned " + user.username + " from" + msg.guild.name))`<br/>`.catch(console.error);`
Unban User <br/><i>requires user's ID</i> | `msg.guild.members.unban(tempVars("user_id"))`<br/>`.then(user => console.log("Unbanned " + user.username + " from" + msg.guild.name))`<br/>`.catch(console.error);`
Find Emoji | `client.emojis.cache.find(c => c.name === "NameOfTheEmoji")`
Jump to a specific action #<br/>_in this example you will jump to action #22_ | `let jumpTo = 22`<br/>`const index = Math.max(jumpTo - 1, 0);`<br/>`cache.index = index - 1;`<br/>`this.callNextAction(cache)`
Show current date/time in timezone | `new Date().toLocaleString("en-US", { timeZone: "America/New_York" })`
Create server invite | `msg.channel.createInvite({ maxAge: 0 }).then(invite => msg.channel.send(invite.url))`
Create server invite (Variable) | `msg.guild.channels.cache.find(c => c.name === tempVars("channel_name")).createInvite({ maxAge: 0 }).then(invite => msg.channel.send(invite.url))` <br/>*can use "ID" instead of "Name"*
Add role to cmd author | `member.roles.add(tempVars("newroleid"));`
Stop the bot | `process.exit();`
Change nickname (command author) | `msg.member.setNickname(tempVars("new_nick"))`<br/>`.then(console.log)`<br/>`.catch(console.error);`
Get Variable value | `this.getVariable(1, "varname", cache);`
Store Variables via script | `this.storeValue(output, 1, "totalUsers", cache)` <br /> (*1 = temp, 2 = server, 3 = global*)
Set Bot Username via script | `this.getDBM().Bot.bot.user.setUsername('a very cool username')`
Set Bot Avatar via script | `this.getDBM().Bot.bot.user.setAvatar('image_link')`
Set Server Name via script | `msg.guild.setName('a very cool name')`
Set Server Icon via script | `msg.guild.setIcon('image_link')`