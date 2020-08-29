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

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-c3ow{border-color:inherit;text-align:center;vertical-align:top}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-c3ow">Variable Types</th>
    <th class="tg-c3ow">Same Server</th>
    <th class="tg-c3ow">Different Server</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-c3ow">Same Command</td>
    <td class="tg-c3ow">Temp Variable</td>
    <td class="tg-c3ow">Temp Variable</td>
  </tr>
  <tr>
    <td class="tg-c3ow">Different Command</td>
    <td class="tg-c3ow">Server Variable</td>
    <td class="tg-c3ow">Global variable</td>
  </tr>
</tbody>
</table>
