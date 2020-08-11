# Lists
Usage | Script
:- | :-
Create a list out of items that have data following them | `.array()}`
Count items in the specified array | `.array().length}` or `.size}`
Count items in the specified list <br/> **or** <br/> count the length of a string | `.length}`
Find position of item in a list <br/>_If the bot returns -1 that means the item is not on the list. 0 means its the first item, 1 is the second etc_ | `${tempVars("yourList").indexOf(tempVars("yourItemToFind"))}`
Remove item from list | `${tempVars("yourList").splice(# to remove, 1)}`
Return the last # of items in a list | `tempVars("your variable").slice(Math.max(tempVars("your variable").length - 5, 1))` <br/> *where 5 is the number of items to return*
Return item at [position] from [list] | `tempVars("list").slice(tempVars("pos_num") - 1, tempVars("pos_num"))`