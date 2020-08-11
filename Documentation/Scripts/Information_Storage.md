# Information Storage
[Bot Info](#bot-info)  
[User Info](#user-info)  
[Server Info](#server-info)  

## Bot Info

| Usage | Script |
| :--- | :--- |
| Return Count of Members in all Bot Guilds | `${client.users.cache.size}` |
| Return Count of all Bot Guilds | `${client.guilds.cache.size}` |
| Return List of all Bot Guilds | `${client.guilds.cache.array()}` |
| Program memory usage \(in MB\) | `${Math.floor((process.memoryUsage().heapUsed / 1024)/1024)} MB` |
| Store the bot as a guild member (using the message sent) | `${msg.guild.me}`
| Store the client (using the message sent) | `${msg.guild.client}`
| Bot Ping | `${client.ws.ping}`
| Bot Rounded Ping | `${Math.floor(client.ws.ping)}` |
| Bots CPU | `${(process.cpuUsage().user / 1000000).toFixed(2)} Seconds`
| Bots Prefix | `${this.getDBM().Files.data.settings.tag}`
| Count of Commands in Bot | `${this.getDBM().Files.data.commands.length}`
| Count of Events in Bot | `${this.getDBM().Files.data.events.length}`
| Bot uptime<br/>_use tempVars("uptime-ms") to display this_ | `var uptime = process.uptime();`<br/>`var days = Math.floor((uptime % 31536000) / 86400);`<br/>`var hours = Math.floor((uptime % 86400) / 3600);`<br/>`var minutes = Math.floor((uptime % 3600) / 60);`<br/>`var seconds = Math.round(uptime % 60);`<br/>`var botuptime = (days > 0 ? days + " days, ":"") + (hours > 0 ? hours + " hours, ":"") + (minutes > 0 ? minutes + " minutes, ":"") + (seconds > 0 ? seconds + " seconds":"")`<br/>`this.storeValue(botuptime, 1, "uptime-ms", cache)`

## User Info

| Usage | Script |
| :--- | :--- |
|Author Username|`${msg.author.username}`
|Author Display Name (Nick)|`${member.displayName}`
|Author Created At| `${msg.author.createdAt}`
|Author Id|`${msg.author.id}`
|Author Tag|`${msg.author.tag}`
|Author Discriminator|`${msg.author.discriminator}`
|Author Avatar URL|`${msg.author.displayAvatarURL({ dynamic: true })}`
|Author Role List | `${member.roles.cache.array()}`
|Author Role List (truncated after 3 roles) <br/>*enter `${tempVars("role_list")}` into your send-message to view this output.*<br/>*output will display as `@role1,@role2,@role3 + # more roles!`* | `var roles = member.roles.cache.array();`<br/>`var len = roles.length;`<br/>`if (len > 3) {`<br/>`   var answer = roles.slice(0,3) + " + " + (len - 3) + " more!"`<br/>`} else {`<br/>`   var answer = roles`<br/>`};`<br/>`this.storeValue(answer, 1 ,"role_list", cache);`
|User (variable) Username|`${tempVars("user_object").user.username}`
|User (variable) Display Name (Nick)|`${tempVars("user_object").displayName}`
|User (variable) Id|`${tempVars("user_object").user.id}`
|User (variable) Tag|`${tempVars("user_object").user.tag}`
|User (variable) Discriminator|`${tempVars("user_object").user.discriminator}`
|User (variable) Avatar URL|`${tempVars("user_object").user.displayAvatarURL({ dynamic: true })}`

## Server Info

| Usage | Script |
| :--- | :--- |
| Return Server Name | `${msg.guild.name}` |
| Return Server Id | `${msg.guild.id}` |
| Return Server Icon URL | `${msg.guild.iconURL({ dynamic: true })}` |
| Return Server Region | `${msg.guild.region}` |
| Return Server Creation Date | `${msg.guild.createdAt}` |
| Return Server Verification Level | `${msg.guild.verificationLevel}` |
| Return Server Explicit Content Filter | `${msg.guild.explicitContentFilter}` |
| Return Server Owner Display Name | `${msg.guild.owner.displayName}` |
| Return Server Available Status | `${msg.guild.available}` |
| Return Server Member Count | `${msg.guild.memberCount}` |
| Return Server Emojis Count | `${msg.guild.emojis.cache.size}` |
| Return Server Count of Roles | `${msg.guild.roles.cache.size}` |
| Return Server Count of Channels | `${msg.guild.channels.cache.size}` |
| Return Server Count of Text Channels | `${msg.guild.channels.cache.find(c => c.type === 'text').length}` |
| Return Server Count of Voice Channels | `${msg.guild.channels.cache.find(c => c.type === 'voice').length}` |
| Store Count members in a role | `${tempVars("role").members.cache.size}`|
| Return List of Members in a Role | `tempVars("role").members.cache.map(m => m.user.tag)`
| Return Server Emojis List | `${msg.guild.emojis.cache.array()}` |
| Return # of Bot Accounts | `${msg.guild.members.cache.filter(m => m.user.bot).size}` |
| Return # of non-Bot Accounts | `${msg.guild.members.cache.filter(m => !m.user.bot).size}`
| Return Server Online members | `${msg.guild.members.cache.filter(m => m.user.presence.status === "online").size}` |
| Return Server Offine members | `${msg.guild.members.cache.filter(m => m.user.presence.status === "offline").size}` |
| Return Server Idle members | `${msg.guild.members.cache.filter(m => m.user.presence.status === "idle").size}` |
| Return Server DND members | `${msg.guild.members.cache.filter(m => m.user.presence.status === "dnd").size}` |
| Return Server AFK Channel | `${msg.guild.afkChannel}` |
| Return Server AFK Timeout \(in seconds\) | `${msg.guild.afkTimeout}` |