# Store Command Parameters

You can store parameters entered into a command using the "Store command parameters" action. This will assume your parameters are using the default `space` \(`\s+`\) as a separator.

![](https://raw.githubusercontent.com/Silversunset01/dbm/master/screenshots/storeparams.png)

* Parameter Number:
  * This tells the bot which word to start on. Using 1 would mean "the first word after the command"; 2 would mean "the second word after the command" and so on.
  * DBM defines a "word" as a complete string of characters between your parameter separator
    * ex: If your separator is a space, a "world" would be anything between spaces - `this is four words`
    * ex: if your separator is a comma, a "word" would be anything between commas - `this is, two things`

* Source Info:
  * **One Parameter** - creates a parameter using a single word, beginning at the \# given in the "parameter number" field.
    * ex: `!prune 50 100` - using "One Parameter" and "1" your parameter would be `50`
    * ex: `!prune 50 100` - using "One Parameter" and "2" your parameter would return `100`
  * **Multiple Parameters** - creates a parameter using multiple words separated by the character indicated in the bot settings(default space), beginning from the number you specify in "Parameter Number" and going to the end of the command input
    * ex: `!ban @Silversunset You are breaking the rules` - using "Multiple Parameters" and "2" your parameter would be `You are breaking the rules`
    * ex: `!ban @Silversunset You are breaking the rules` - using "Multiple Parameters" and "3" your parameter would be `are breaking the rules`
  * **Mentioned Member** - stores the `@username` from a command as a parameter
  * **Mentioned Role** - stores the `@role` from a command as a parameter
  * **Mentioned Channel** - stores the `#channel` from a command as a parameter