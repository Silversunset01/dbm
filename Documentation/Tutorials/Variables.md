# Variables

[DBM Tutorial - Obtaining Parameters >](https://www.youtube.com/watch?v=haAyykGaY_E)

There are a few ways to store and reuse information in DBM.

* **Temp variable** - exists only for the duration of the command. Once the command action list is over the variable is 'forgotten' by the bot. Note: these will be available in loops or when calling an event but you may have to type the variable manually, DBM doesn't pass temp variables between things even if they are available.
* **Server variable** - exists for a single server. The bot will 'remember' these variables between commands but only for the server they were created in.
* **Global variable** - exists for the bot regardless of server or command.

# Which variable type should I use? 
If you are unsure the variable type you should use please see the below chart:  

<table style="width:500px;">
<thead>
  <tr>
    <th style="background-color:black;color:white;text-align:center;">Variable Types</th>
    <th style="text-align:center;">Same Server</th>
    <th style="text-align:center;">Different Server</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td style="font-weight: bold;text-align:left;">Same Command</td>
    <td style="color:green;">Temp Variable</td>
    <td style="color:green;">Temp Variable</td>
  </tr>
  <tr>
    <td style="font-weight: bold;text-align:left;">Different Command</td>
    <td style="color:blue;">Server Variable</td>
    <td style="color:purple;">Global variable</td>
  </tr>
</tbody>
</table>
