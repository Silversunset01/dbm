# Variables

[DBM Tutorial - Obtaining Parameters >](https://www.youtube.com/watch?v=haAyykGaY_E)

There are a few ways to store and reuse information in DBM.

* **Temp variable** - exists only for the duration of the command. Once the command action list is over the variable is 'forgotten' by the bot. Note: these will be available in loops or when calling an event but you may have to type the variable manually, DBM doesn't pass temp variables between things even if they are available.
* **Server variable** - exists for a single server. The bot will 'remember' these variables between commands but only for the server they were created in.
* **Global variable** - exists for the bot regardless of server or command.

# Which variable type should I use? 
If you are unsure the variable type you should use please see the below chart:  

|     Variable Types    |   Same Server   | Different Server |
|:----------------------|:---------------:|:----------------:|
|   **Same Command**    |  Temp Variable  |   Temp Variable  |
| **Different Command** | Server Variable |  Global variable |

<table style="width:500px;">
<thead>
  <tr>
    <th style="background-color:black;color:white">Variable Types</th>
    <th>Same Server</th>
    <th>Different Server</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td style="font-weight: bold">Same Command</td>
    <td>Temp Variable</td>
    <td>Temp Variable</td>
  </tr>
  <tr>
    <td style="font-weight: bold">Different Command</td>
    <td>Server Variable</td>
    <td>Global variable</td>
  </tr>
</tbody>
</table>
