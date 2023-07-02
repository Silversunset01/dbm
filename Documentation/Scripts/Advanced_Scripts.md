# Advanced Scripts
[Select item from list (no dups)](#select-items-from-list-no-dups-)  
[Select items from List (dups)](#select-items-from-list-dups-)  
[List All Bot Command Names](#list-all-of-the-bot-commands-names-)  
[List All Event Names](#list-all-of-the-bot-events-names-)  
[Display a missing variable with alt text](#display-a-missing-variable-with-alt-text)  

## Select items from List (no dups)
This script will select the specified number of items from a list (array), without any duplicates, and puts them into a new list. These items are usable in DBM by entering `${tempVars("newList")}`.

**TO USE**  
- Put this entire code block into a Run Script action, set the "Interpretation Style" to "Evaluate Text Directly", and leave the "Store in" option as "Nothing".
- Change the words "Your List Variable" to the variable name of the list you wish to use.  
- Change the value of `sel = 5` to however many items you want to select.

```
//count how many items are in the list  
var myList = tempVars("Your List Variable");  
var myListLen = myList.length;  
var sel = 5;  

//Select # random numbers from the total length of the list of items  
var arr = []  
var ckarr = []  
while(arr.length < sel){  
    var r = Math.floor(Math.random()*myListLen) + 1;  
    if(ckarr.indexOf(r) === -1) {  
        arr.push(myList.slice(r-1,r));  
        ckarr.push(r);  
    };  
}  
this.storeValue(arr, 1, "newList", cache);  
console.log("I have selected " + sel + " items from your list: " + arr);  
```  

## Select items from List (dups)
This script will select the specified number of items from a list (array), and may have duplicates, and puts them into a new list. These items are usable in DBM, by entering `${tempVars("newList")}`.

**TO USE**  
- Put this entire code block into a Run Script action, set the "Interpretation Style" to "Evaluate Text Directly", and leave the "Store in" option as "Nothing".
- Change the words "Your List Variable" to the variable name of the list you wish to use.  
- Change the value of `sel = 5` to however many items you want to select.

```  
// Count how many items are in the list  
var myList = tempVars("Your List Variable");  
var myListLen = myList.length;  
var sel = 5;  

// Select # random numbers from the total length of the list of items  
var arr = []  
while(arr.length < sel){  
    var r = Math.floor(Math.random()*myListLen) + 1;  
    arr.push(myList.slice(r-1,r));  
}  
this.storeValue(arr, 1, "newList", cache);  
console.log("I have selected " + sel + " items from your list: " + arr);  
```  

## List all of the bot commands (names)
This script will get all the names of your bot's commands and will store them onto a temp variable named `commands`.  

```  
const array = this.getDBM().Files.data.commands.filter((c) => c && c.name).map((c) => c.name);  
this.storeValue(array.join(', '), 1, 'commands', cache);  
```  

## List all of the bot events (names)
This script will get all the names of your bot's events and will store them onto a temp variable named `events`.  

```  
const array = this.getDBM().Files.data.events.filter((c) => c && c.name).map((c) => c.name);  
this.storeValue(array.join(', '), 1, 'events', cache);  
```  
