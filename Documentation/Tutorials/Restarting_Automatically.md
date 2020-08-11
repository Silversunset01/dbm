# Restarting Automatically
[Linux](#linux) | [Windows](#windows) | [Forever.js](#forever.js) | [Nodemon](#nodemon)

## Linux

* Go into your bot folder with: `cd BotFolderLocation`
* Use `nano start.sh` to create a file called `start.sh` and start editing.
* Paste the code below :

```bash
# /bin/sh
while true
do
echo Starting Bot
node bot.js
echo Restarting Bot in 5 Seconds...
sleep 5
done
```

* Press CTRL+C then Y and ENTER to save the start.sh file.
* Use `chmod 777 start.sh` to give the file executable permission.
* Done! Now you can start your bot by executing that file with: `./start.sh`

**Tutorial Video** _\(Click on image to watch it\)_

[![](https://asciinema.org/a/Gjc27yyaid3LxAIDlc8AqM4Z3.png)](https://asciinema.org/a/Gjc27yyaid3LxAIDlc8AqM4Z3)

## Windows


* Create a file with `.bat` extension.
* Paste the code below and save it.

```
@echo off
echo Starting...
:main
node bot.js
echo Restarting Bot...
goto main
```

* Done! Now you can run your bot just executing that file.

[**Tutorial Video **_\(Click to watch it\)_](https://youtu.be/1ZDE3z_Fsi4)

## Forever.js

You can install a script called **Forever.js** that will automatically restart your bot if it crashes.

* `npm install --no-optional -g forever`
* If you're on Linux (ignore if you're on Windows): `chmod -R a+rwx <bot folder>`- Give the bot folder permission to be read/write and executable
* `cd <bot folder>` - Change to the bots directory
* `forever start bot.js` - Start the bot program using "Forever" \(this will keep the bot running and restart it if it crashes\)

## Nodemon

`node bot.js` will have to be restarted every time you make changes. You can use Nodemon to do this automatically  

1. Install nodemon with `npm i -g nodemon`
2. Open project directory
3. Click into the address bar
4. At the beginning type "cmd" and hit enter (this will open a cmd prompt in this folder)
5. Type `nodemon --inspect --watch actions --watch data/commands.json --watch data/events.json --watch node_modules --watch js --watch data/settings.json bot.js`