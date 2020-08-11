# Adding a role on-join
Adding a role to users who join your server is quite simple.

1. **Create an event that is triggered ON MEMBER JOIN**

This event will detect every time someone joins your server, and when you enter a variable name in the box labeled `Temp Variable Name (stores member that joined):` it will store the user that joined. For this example, we will call the variable `new-user`

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/autorole1.PNG)

2. **Find the role you want to apply to users**

To apply a role you must first obtain the role object. Do this with a Find Role action. You can search by Role ID, Role Name, or Role Color (name or ID are the best options for this as they are the least likely to duplicate).

Give this role a variable name that you can easily identify later. Here we will search for the role called `Players` and store it as the variable name `default-role`

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/autorole2.PNG)

3. **Add the role to the member that joined**

You have stored both the member object for the user that joined (variable `new-user`) and the role object for your default role (variable `default-role`). Now you will select an Add Member Role action, and apply the role you stored to the member you stored.

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/autorole3.PNG)

**That's it!**

Your new user now has a shiny new role.
