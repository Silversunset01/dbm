# Error: Unexpected Token
Unexpected Token has nothing to do with your bots token. It means you've got an unmatched bracket somewhere, or some character that javascript doesn't know what to do with.  

*  `Unexpected Token (` means you're missing `)`  
*  `Unexpected Token )` means you're missing `(`  
*  `Unexpected Token {` means you're missing `}`  
*  `Unexpected Token }` means you're missing `{`  
*  `Unexpected Token <` means you're missing `>`  
*  `Unexpected Token >` means you're missing `<`  

**Example:**
`${parseInt(tempVars("name")}` will throw an error: `Unexpected Token (` because you're missing a closing `)` after the variable. 