# Math & Operations
Usage | Script
:- | :-
Force variable to be read as a number | `${parseInt(yourvariable)}`
Add two variables | `${parseInt(tempVars("var1")) + parseInt(tempVars("var2"))}`
Subtract two variables | `${parseInt(tempVars("var1")) - parseInt(tempVars("var2"))}`
Multiply two variables | `${parseInt(tempVars("var1")) * parseInt(tempVars("var2"))}`
Divide two variables | `${parseInt(tempVars("var1")) / parseInt(tempVars("var2"))}`
Round down | `${Math.floor(yourvariable)}`
Round to the nearest Integer | `${Math.round(yourvariable [, decimals])`
Translate (date) milliseconds to days | `${Math.floor((tempVars("uptime-ms") % 31536000) / 86400)}`
Translate (date) milliseconds to hours (up to 24) | `${Math.floor((tempVars("uptime-ms") % 86400) / 3600)} `
Translate (date) milliseconds to minutes (up to 60) | `${Math.floor((tempVars("uptime-ms") % 3600) / 60)}`
Translate (date) milliseconds to seconds (up to 60) | `${Math.round(tempVars("uptime-ms") % 60)}`
Translate (duration) milliseconds to a human readable format | `var duration = tempVars("time_var");` <br/> `var ms = parseInt((duration%1000)/100);` <br/> `var s = parseInt((duration/1000)%60);` <br/> `var m = parseInt((duration/(1000*60))%60);` <br/> `var h = parseInt((duration/(1000*60*60))%24);` <br/> `var timeoutput = h + "h:" + m + "m:" + s + "s:" + ms + "ms";`