# Finding a user with some parts of their name
To make this, you'll require a simple Run Script action.<br/>
`var search = tempVars("parameters").toLowerCase()`<br/>`var member = msg.guild.members.find(member => member.name.toLowerCase().startsWith(search) || member.name.toLowerCase().endsWith(search) || member.name.toLowerCase().includes(search))`<br/>`this.storeValue(member, 1, "member", cache)`<br/>
_the `tempVars("parameters")` would be your input, and, to use the output, use `tempVars("member")`_