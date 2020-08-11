# Error: Search bar doesnt work 
## Reinstall Mods
DBM Beta allows you to search for actions,  but sometimes mods make this break. to fix it:  
1. Close Discord Bot Maker  
2. Open your Steam Library and find Discord Bot Maker on the Software tab  
3. Right-click it → Properties → Local Files → Browse Local Files  
4. Delete the actions folder  
5. Go back to the Properties (Local Files) tab, and press Verify Integrity of Application Files  
6. After the verification is finished and the missing files are reacquired, go back to the DBM folder, refresh it, and copy the actions folder  
7. Open your project folder and delete the actions folder, and paste the one you copied from the DBM folder  

That should have fixed it.
By doing this, your mods will be deleted. So, if you want, you can install them again. Follow the installation guide at https://github.com/dbm-network/mods/tree/beta#installing-mods

## Delete your DBM Cache
For Windows 10:  
1. Exit Discord Bot Maker  
2. Browse to %localappdata%  
3. Delete DBM, DBM2, and any other DBM folders  
4. Start Discord Bot Maker  
5. Search should work  
