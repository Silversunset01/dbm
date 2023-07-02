# Information Storage
[Bot Info](#bot-info)  
[User Info](#user-info)  
[Server Info](#server-info)  

## Bot Info

| Usage | Script |
| :--- | :--- |
| Count of Members in all Bot Guilds | `${client.users.cache.size}` |
| Count of all Bot Guilds | `${client.guilds.cache.size}` |
| List of all Bot Guilds | `${Array.from(client.guilds.cache)}` |
| Program memory usage \(in MB\) | `${Math.floor((process.memoryUsage().heapUsed / 1024)/1024)} MB` |
| Store the bot as a guild member (using the message sent) | `${msg.guild.me}`
| Store the bot as a user | `${this.getDBM().Bot.bot.user}`
| Store the client (using the message sent) | `${msg.guild.client}`
| Bot Ping | `${client.ws.ping}`
| Bot Rounded Ping | `${Math.floor(client.ws.ping)}` |
| Bots CPU | `${(process.cpuUsage().user / 1000000).toFixed(2)} Seconds`
| Bots Prefix | `${this.getDBM().Files.data.settings.tag}`
| Count of Commands in Bot | `${this.getDBM().Files.data.commands.length}`
| Count of Events in Bot | `${this.getDBM().Files.data.events.length}`
| Bot uptime<br/>_use tempVars("uptime-ms") to display this_ | `var uptime = process.uptime();`<br/>`var days = Math.floor((uptime % 31536000) / 86400);`<br/>`var hours = Math.floor((uptime % 86400) / 3600);`<br/>`var minutes = Math.floor((uptime % 3600) / 60);`<br/>`var seconds = Math.round(uptime % 60);`<br/>`var botuptime = (days > 0 ? days + " days, ":"") + (hours > 0 ? hours + " hours, ":"") + (minutes > 0 ? minutes + " minutes, ":"") + (seconds > 0 ? seconds + " seconds":"")`<br/>`this.storeValue(botuptime, 1, "uptime-ms", cache)`

## User Info

**Note:** Since the pomelo username update, user discriminator numbers have been replaced with "0" for users with the new username system. Currently, in discord.js v13 (the version that DBM currently uses), there is no way to get a user's display name

*Author = User | (you can also use `user` in most cases, instead of `msg.author`)* 

| Usage | Script |
| :--- | :--- |
|Author Username|`${msg.author.username}`
|Author Display Name (Nick)|`${member.displayName}`
|Author Created At| `${msg.author.createdAt}`
|Author ID|`${msg.author.id}`
|Author Tag|`${msg.author.tag}`
|Author Discriminator|`${msg.author.discriminator}`
|Author Avatar URL|`${msg.author.displayAvatarURL({ dynamic: true })}`
|Author Role List | `${Array.from(member.roles.cache)}`
|Author Role List (truncated after 3 roles) <br/>*enter `${tempVars("role_list")}` into your send-message to view this output.*<br/>*output will display as `@role1,@role2,@role3 + # more roles!`* | `var roles = Array.from(member.roles.cache);`<br/>`var len = roles.length;`<br/>`if (len > 3) {`<br/>`   var answer = roles.slice(0,3) + " + " + (len - 3) + " more!"`<br/>`} else {`<br/>`   var answer = roles`<br/>`};`<br/>`this.storeValue(answer, 1 ,"role_list", cache);`
|Get User (object) from Member object | `tempVars("member_object").user`
|User (variable) Username|`${tempVars("user_object").username}`
|Member (variable) Display Name (Nick)|`${tempVars("member_object").displayName}`
|User (variable) Id|`${tempVars("user_object").id}`
|User (variable) Tag|`${tempVars("user_object").tag}`
|User (variable) Discriminator|`${tempVars("user_object").discriminator}`
|User (variable) Avatar URL|`${tempVars("user_object").displayAvatarURL({ dynamic: true })}`
|User (variable) Banner URL|`${tempVars("user_object").bannerURL({ dynamic: true })}`
|User (variable) Accent Color|`${tempVars("user_object").accentColor`
|User (variable) Accent Color (in hex)|`${tempVars("user_object").hexAccentColor`

## Server Info

| Usage | Script |
| :--- | :--- |
| Server Name | `${msg.guild.name}` |
| Server ID | `${msg.guild.id}` |
| Server Icon URL | `${msg.guild.iconURL({ dynamic: true })}` |
| Server Splash URL | `${msg.guild.splashURL({ dynamic: true })}` | 
| Server Banner URL | `${msg.guild.bannerURL({ dynamic: true })}` |
| Server Vanity Invite | `${msg.guild.bannerURL({ dynamic: true })}` |
| Server Creation Date | `${msg.guild.createdAt}` |
| Server Verification Level | `${msg.guild.verificationLevel}` |
| Server Explicit Content Filter | `${msg.guild.explicitContentFilter}` |
| Server Owner ID | `${msg.guild.ownerId}` |
| Server Available Status | `${msg.guild.available}` |
| Server Member Count | `${msg.guild.memberCount}` |
| Server Emojis Count | `${msg.guild.emojis.cache.size}` |
| Server Rules Channel | `${msg.guild.rulesChannel}` |
| Server Public Updates Channel | `${msg.guild.publicUpdatesChannel}` |
| Server Count of Roles | `${msg.guild.roles.cache.size}` |
| Server Count of Channels | `${msg.guild.channels.cache.size}` |
| Server Count of Text Channels | `${msg.guild.channels.cache.filter(c => c.type === 'GUILD_TEXT').size}` |
| Server Count of Voice Channels | `${msg.guild.channels.cache.filter(c => c.type === 'GUILD_VOICE').size}` |
| Store Count members in a role | `${tempVars("role").members.cache.size}`|
| List of Members in a Role | `tempVars("role").members.map(m => m.user.tag)`
| Server Emojis List | `${Array.from(msg.guild.emojis.cache)}` |
| # of Bot Accounts | `${msg.guild.members.cache.filter(m => m.user.bot).size}` |
| # of non-Bot Accounts | `${msg.guild.members.cache.filter(m => !m.user.bot).size}`
| Server Online members | `${msg.guild.members.cache.filter(m => m.presence.status === "online").size}` |
| Server Offine members | `${msg.guild.members.cache.filter(m => m.presence.status === "offline").size}` |
| Server Idle members | `${msg.guild.members.cache.filter(m => m.presence.status === "idle").size}` |
| Server DND members | `${msg.guild.members.cache.filter(m => m.presence.status === "dnd").size}` |
| Server AFK Channel | `${msg.guild.afkChannel}` |
| Server AFK Timeout \(in seconds\) | `${msg.guild.afkTimeout}` |
