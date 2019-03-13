# Discord (Not DBM Specific)
These are tutorials that are not necessary specific to DBM, but rather are more geared towards "how discord works" or other things that can be done outside DBM.

## Display Twitch notifications with IFTTT
### Creating the Webhook/Trigger
1. Register on IFTTT
	* Go to https://ifttt.com/ and create an account (if you don't already have one)
2. Make a Discord Webhook
	* Find the Discord channel in which you would like to send Tweets.
	* In the settings for that channel, find the Webhooks option and create a new webhook.
		* **Note: This URL should be kept _private_. It allows anyone to write messages to that specific channel using that specific URL.** Keep it safe!
	* Name the webhook however you like and feel free to change the generic profile picture.
	* Copy the URL somewhere and keep it handy for the next step.
3. Create a new IFTTT applet/recipe
	1. Go [here](https://ifttt.com/create) to create a new "Applet"
	2. Click the big blue "[+] This" and choose "Twitch" (use the search bar to find it quickly)
	3. Connect your account if necessary.
	4. Choose "New stream started by you" (it should be the 2nd option from the left)
	5. Click the big blue "[+] That" and choose "Webhooks"
	6. Choose "Make a web request" (it should be the only option)
	7. Fill in the following details:
		> **URL:** _[your URL from "part 2" above]_  
		> **Method:** POST  
		> **Content type:** `application/json`  
		> **Body:** _[see the snippet below]_  
	8. Click "Create Action"
	
### Formatting the **Snippet**
The following template shows a basic snippet 
```json
{
  "content": "{{ChannelName}} went live on Twitch",
  "embeds": [{
    "title": "{{ChannelUrl}}",
    "url": "{{ChannelUrl}}",
    "color": 6570404,
    "footer": {
      "text": "{{CreatedAt}}"
    },
    "image": {
      "url": "{{StreamPreview}}"
    },
    "author": {
      "name": "{{ChannelName}} is now streaming"
    },
    "fields": [
      {
        "name": "Playing",
        "value": "{{Game}}",
        "inline": true
      },
      {
        "name": "Started at (streamer timezone)",
        "value": "{{CreatedAt}}",
        "inline": true
      }
    ]
  }]
}
```

If you'd like to customize the message text -- "<user> has gone live on Twitch!" -- change the **content attribute:**
```json
  "content": "{{ChannelName}} has gone live on Twitch!",
```
