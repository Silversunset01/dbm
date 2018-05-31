***Add these lines to dbm/tutorial.md***

## Best Practices

### Standards
Following these practices allows you to have the best ability in maintenance and adding in more revisions.

#### Commenting
The only way to add comments to DBM is by using console.log(), when logging don't forget to add in: Name of Module, purpose, description, and modifications. These allow you to have a glance at the command and exactly know how it works, without breaking it down to simplify. An example would be:  
`BakeCookies  
This allows the user to gain one cookie  
Whenever this module is invoked, the command author gains one cookie on MemberData(numCookies)  
Added a debounce  `

#### Naming Conventions
Please don't call your variables such as:  
* var  
* reeeee  
* test
* (nameofcommand)  
* potato, and other shit like that  
Whenever you name variables like that, it heavily decreases "code" readability  

#### Simplicity
Find the best way to achieve the purpose without having impertinent actions in your command. Being verbose(at some extent) also achieves this

#### Maintainance
There are a couple ways of achieving best maintainabilty if you follow the most basic code guidelines.

1. Invokes: Whenever you have a command that does two different functions that is dependant on the parameter or data, that command should only check for that and calls or invokes the appropriate command. Don't condense them into one command, whenever you have to make edits to that flow(the command the actions) conditionals such as "jump to action" will break it. Invoking a command means that if you need to change the function of the command, you would only need to change that flow and not the main command itself.  

2. As above, Naming Conventions  

> Notes: When not following these guidelines you might find at some point, making edits or checking how each works might be a pain, please follow these so that wouldn't exactly happen.  
> I am very hypocritcal to this whenever you check my commits in Github. I know what I am doing(even though I might forget)  
