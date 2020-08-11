# Webhooks
Usage | Script
:- | :-
Create Webhook | `msg.channel.createWebHook('Webhook Name', { avatar: 'https://i.imgur.com/9kgJteG.png' })` <br/> The avatar is optional
Edit Webhook Name | `const hook = new DiscordJS.WebhookClient('webhook_id', 'webhook_token');`<br/>`hook.edit({ name: 'A very cool nickname' })`
Edit Webhook Avatar | `const hook = new DiscordJS.WebhookClient('webhook_id', 'webhook_token');`<br/>`hook.edit({ avatar: 'https://i.imgur.com/9kgJteG.png' })`
Edit Webhook Name & Avatar | `const hook = new DiscordJS.WebhookClient('webhook_id', 'webhook_token');`<br/>`hook.edit({ avatar: 'https://i.imgur.com/9kgJteG.png', name: 'a very cool name' })`
Send Message to Webhook | `const hook = new DiscordJS.WebhookClient('webhook_id', 'webhook_token');`<br/>`hook.send('a very cool message');`
Send Embed to Webhook | `const hook = new DiscordJS.WebhookClient('webhook_id', 'webhook_token');`<br/>`hook.send(tempVars("embed"));`


