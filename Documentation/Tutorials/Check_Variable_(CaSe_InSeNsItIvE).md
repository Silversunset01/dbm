# Check variable (CaSe InSeNsItIvE)
When you use the `Check Variable` action DBM requires that it be an EXACT match, including case. That means
```TeXt LiKe ThIs```
is not the same as
```text like this```
or
```TEXT LIKE THIS```

The way to combat this is to convert your variable to the same case (either all upper-case or all lower-case) and compare that to your text.
**1. Store Command Params**  
    This is the variable you will be testing, however, the way you store it will depend on your command.  
    For this example, we will assume your variable is called `myInput`  
**2. Control Variable**  
    Enter the following text into the value field: `tempVars("myInput").toLowerCase()`  
    Then store this into a temporary variable. (For this example, we will use `myInputLowerCase`)
    You can also overwrite the original `myInput` variable with the lowercase value using this.
**3. Check Variable**  
    - Source Variable: Temporary Variable  
    - Variable name: `myInputLowerCase` (or `myInput` if it is overwritten)  
    - Comparison Type: Equals  
    - Value to compare to: "your text in all lower case with quotes around it"  
    - If True: continue  
    - iF False: end or skip, depending on your command