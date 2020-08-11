# Error: Cannot find module `discord.js`
1. Delete node_modules  
2. type `npm i discord.js@11.6.1` (this will reinstall the discord.js module)  

# Error: Cannot find module `./constants`
You need to reinstall your node modules from package.json  
## For Windows:
1. In CMD type `CD/your bot directory` (if you're not already in it)  
2. Enter the following exactly `rd /s /q node_modules`  
3. Reinstall modules with `npm i`  

## For Linux
1. From the terminal change directory to your bots folder  
2. type `rm -rf node_modules`  
3. Reinstall modules with `npm i`  

## To install specific modules
1. type `npm i <modulename> --save`  

