# Storing Member Data (Numbers)
DBM uses a JSON object to store user data to the `players.json` file. By default, JSON objects are *always* stored as text values.  

This can cause issues with NUMERIC member data (things like wallet balances). In JavaScript, the `+` sign means "concatenate" if the variable is a text variable, and "add" if its a numeric variable. Since JSON is text by default DBM tends to concatenate values rather than add them.

**Symptom: 10 + 10 = 1010, but it should be 20**  

**Fix: convert the items to numeric and use "set value" instead of "add value"**  

**How to do this:**  
1. Store the members current data using `Store Member Data`  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/parseInt1.PNG)

2. Use `parseInt()` to convert the variable to numeric, and then use `Control Member Data` to **set value** the users data  
To ADD values: `parseInt(tempVars("oldBalance")) + parseInt(tempVars("amtToAdd"))`  
To SUBTRACT values: `parseInt(tempVars("oldBalance")) - parseInt(tempVars("amtToAdd"))`  
![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/parseInt2.PNG)

