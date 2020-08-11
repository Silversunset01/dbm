# Check variable (CaSe InSeNsItIvE)
When you use the `Check Variable` action DBM requires that it be an EXACT match, including case. That means
```TeXt LiKe ThIs```
is not the same as
```text like this```
or
```TEXT LIKE THIS```

The way to combat this is to convert your variable to the same case (either all upper-case or all lower-case) and compare that to your text. You will need to use `Run Script` for this to work.  
**1. Store Command params**  
    - this is the variable you will be testing, however, you store it will depend on your command.  
    - For this example, we will assume your variable is called `myInput`  
**2. Run Script**  
    - enter the following script into the box `tempVars("myInput").toLowerCase();`  
    - in the Store-in box underneath, store this as a new temporary variable called `myInputLowerCase`  
**3. Check Variable**  
    - Source Variable: Temporary Variable  
    - Variable name: `myInputLowerCase`  
    - Comparison Type: equals  
    - Value to compare to: "your text in all lower case with quotes around it"  
    - If True: continue  
    - iF False: end or skip, depending on your command 