# Adding a role on-join
Adding a role to members who join your server is quite simple.

1. **Create an event that is triggered on Member Join Server**

This event will detect every time someone joins your server, and when you enter a variable name in the box labeled `Temp Variable Name (stores member that joined):` it will store the member that joined. For this example, we will call the variable `new-member`

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/autorole1.PNG)

2. **Add the role to the member that joined**

Using the Add Member Role action, we can give a specified role to the member.

The `Source Role` field can be used to find a role via its role ID or name.
If you have a role object, you can its variable too.

Now we can use the found "Players" role and give it to the member stored in the `new-member` variable.

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/autorole2.PNG)

**That's it!**

Your new member now has a shiny new role.