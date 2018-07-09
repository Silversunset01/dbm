# Frequently Asked Questions

# Running the bot
## Can I run two bots at the same time? 
Sort of. You cannot run two bots in DBM at the same time, but you can run a second instance of your bot via command prompt. [Click Here](https://silversunset.net/dbm/tutorials#running-your-bot-247-running-your-bot-with-cmd) for instructions.

## Why does my bot keep shutting off? 
When you close DBM your bot will shut down. If you want your bot to run always you'll need to keep DBM running, run the bot via command prompt (which you must also keep on and running), or host it externally on a VPS (virtual private server). 
You can run `!info vps` in the discord server for some VPS options, and some hosting tutorials can be found [here](https://silversunset.net/dbm/tutorials#running-your-bot-247). 

# Roles
## Can I make rainbow roles? 
No. This is API abuse and is not allowed by the Discord API. [More information on rate limits can be found here](https://discordapp.com/developers/docs/topics/rate-limits). More specifically because of [this](https://discordapp.com/developers/docs/legal) from the Discord TOS:
```
2.7 Rate Limits. You will not attempt to exceed or circumvent limitations on access to and use of the SDK or API, exceed or circumvent any limitation on the API calls you may make, or otherwise use the SDK or API in a manner that exceeds reasonable request volume, or constitutes excessive or abusive usage (“Rate Limits”). If Discord, in its sole discretion, determines that you have attempted to exceed or circumvent Rate Limits, or other controls that limit use of the SDK or API, then your ability to use the SDK or API may be temporarily suspended or permanently blocked.
```

# Miscellanous
## Are there any tutorials for DBM? 
Yes, SRD made some youtube videos [you can watch here](https://www.youtube.com/playlist?list=PLkfg3Bt9RE055BeP8DeDZSUCYxeSLnobe). Additionally there are some [included in this guide](https://silversunset.net/dbm/tutorials).

## There are things I want to do but I do not have actions for them. 
You can use the run-script action to create your own custom actions using javascript & Discord.js. Or you can download mods which are user-created actions that are available for use. You can type `!info mods` in the discord server or visit https://dbm-mods.xyz/

## Why won't anyone help me make a kick / ban / dm all command?
Inviting your bot to a server and then using it to kick, ban, or DM all users is abuse of your bot (and probably the Discord API rules) that we will not assist with. 

## My bot isn't doing what I expect.
You may have created a command that it can't interperate, or there is a corrupted file in the folder. 

**The first thing you should do is check your bots log** (under the PROJECT menu, choose OPEN BOT LOG) and see what sort of errors it gives you. Often times the error will tell you exactly what the problem is. Some errors can be found [here](https://silversunset.net/dbm/troubleshooting) with their resolutions. 

If the bot is still not working as expected after you've checked the log and attempted to troubleshot, you can ask in the `support` channel of the main DBM guild (or the DBM-Mods guild if your error relates to a mod). 

**In order to get a good answer from the helpers in discord** you should provide the following information:

* What is your command. **example:** `My command is !ping`
* What is your command supposed to do. **example:** `It is supposed to tell me the ping of the bot in milliseconds`
* What is it *actually* doing. **example:** `Instead, it is saying "false"`
* What does your bots log show. **example:** `I checked my bot log and it says "client is not defined"`
