Construct Drafts | From Spec | Commands Loose Ideas
===================================================

`[ Deprecated documentation ]`

__Contents__

- [Nested Commands](#nested-commands)
- [No Dashed Lines for Commands](#no-dashed-lines-for-commands)
- [Misc Ideas](#misc-ideas)

## Nested Commands

`<< nice formulation >>`  

A nested command also executes, when its parent command executes:

`<< details >>`

but it doesn’t execute, unless you call it.

![](images/7.%20Commands%20Ideas.022.jpeg)

`<< details >>`

The nested command might be directly contained by a command. So this is not a nested command:

![](images/7.%20Commands%20Ideas.029.png)

## No Dashed Lines for Commands

A command symbol can define its own command:

![](images/7.%20Commands%20Ideas.064.png)

But if it has a reference line it is regarded no more than a reference or call to a command. The target of the line is considered the command itself or the *definition* of the command.

*A is the reference, B is the definition:*  
![](images/7.%20Commands%20Ideas.065.jpeg)

*A is the command reference, B is the definition:*  
![](images/7.%20Commands%20Ideas.066.jpeg)

## Misc Ideas

`<< about other technology >>`

Differences with Com with returning object references.

-----

`<< interpretation >>`

- Executions & parameters: Inside directly accessible, outside only 'indirectly' accessible (if line set FOR you)

-----

`<< detail >>`

Alternative to command with return value: an object with a getter: A command might possibly not get its own symbol anyway. It might just be an object with an execution point.