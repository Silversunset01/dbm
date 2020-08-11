# Error: Uncaught, unspecific "error" event.
This error appears in your console because your hosting service or discord has a few internet problems. That's normal! Problem: It crashes your bot.  
To solve this you can add this easy code into a "Bot Initialization" event. Make sure to put it into a "Run Script" action:  
```js
client.on('error', (error) => {
  if (error.message == 'Unexpected server response: 520') {
    console.error('Cant connect to Discords API, Retrying...')
  } else if (error.message == 'read ECONNRESET') {
    console.error('Connection Reset! Reconnecting...')
  } else {
    console.error(error)
  }
})
```