Circular Language Construct Drafts | From Spec
==============================================

Nested Commands Rule Rich
-------------------------

`[ Deprecated documentation ]`

__Contents__

- [Introduction](#introduction)
- [Nested Command](#nested-command)
- [Access from Nested Commands](#access-from-nested-commands)
- [Access from Nested Commands](#access-from-nested-commands-1)
- [Nested Command](#nested-command-1)
- [Active Nested Command](#active-nested-command)
- [Inactive Nested Command](#inactive-nested-command)
- [Deeper Nested Command](#deeper-nested-command)
- [The If Example](#the-if-example)
- [Active Nested Commands Compared to Objects](#active-nested-commands-compared-to-objects)
- [Loose Ideas](#loose-ideas)

### Introduction

`<< already covered >>`

Nested commands may be:

- Code blocks
- Clauses
- Local functions
- Lambda expressions

The definition of *nested command* may be: *a command inside another command with no lines going to or from it*.

### Nested Command

`<< already covered >>`

A diamond without a line:

![](images/7.%20Commands%20Ideas.019.jpeg)

`<< nice formulation >>`  

Also executes, when its parent command executes,

`<< details >>`  

but it doesn’t delegate to another command, like a call might:

![](images/7.%20Commands%20Ideas.020.jpeg)

`<< formulation >>`  

It is an undelegated part of a command, that might be called a *code block*.

`<< synonyms >>`  

Because a diamond might not be a call, it is also called an *execution* or an *execution point*.

`<< already covered >>`  

An undelegated square inside a command is also considered a nested command that may be a clause, local function or lambda expression.

![](images/7.%20Commands%20Ideas.021.jpeg)

`<< nice formulation >>`

but it doesn’t execute, unless you call it.

![](images/7.%20Commands%20Ideas.022.jpeg)

### Access from Nested Commands

`<< special access >>`

Nested commands may have special access privileges compared to delegated command symbols.

![](images/7.%20Commands%20Ideas.049.jpeg)

< Bad explanation following >  
Nested commands may freely access anything of its parent block and the parent block’s parent block, etcetera. If going up the command ancestry a command symbol is encountered with a reference line, the nested command can access this ancestor freely, but not any higher in the command ancestry.

In the picture above, the top two lines could have been set by A itself. The first resides in A’s parent nested command. The second resides in the *execution* that parents A, so still accessible to A. The last line, crossed out, can’t be set by A itself, because it resides outside A’s containing call. It can be set only by a symbol higher than A’s containing call, for instance B.

### Access from Nested Commands

`<< special access >>`

< Nice sentence:  
A command makes all direct children accessible to all blocks.  
Only is that true? >

In a diagram nested commands might be squares contained in other squares that have no lines. Beware that a diagram may not be showing the line, even when it exist.

![](images/0.%20Special%20Access.016.png)

Nested commands have access to the contents of all their ancestor blocks and the command definition they’re in. This means that a nested command can directly access its containing definition’s members:

![](images/0.%20Special%20Access.017.png)

and all its encapsulating nested commands:

![](images/0.%20Special%20Access.018.png)

But a nested command might not have access to a nested command that doesn’t encapsulate it.

![](images/0.%20Special%20Access.019.png)

So its like the borders of nested commands can be ignored in outward access.

### Nested Command

`<< terminology >>`

A nested command is usually not called a definition.

`<< details >>`

The nested command might be directly contained by a command. So this is not a nested command:

![](images/7.%20Commands%20Ideas.029.png)

`<< nice formulation >>`

The nested command can be a diamond or a square. Its container can also be a diamond as well as a square. A nested command might not have a reference line, or it might have been a reference or a call, not a nested command.

### Active Nested Command

`<< nice formulation >>`

A nested command that is a diamond, is called an active nested command:

![](images/7.%20Commands%20Ideas.030.png)
![](images/7.%20Commands%20Ideas.031.png)

It’s called active, because it executes.

### Inactive Nested Command

`<< nice formulation >>`

An inactive nested command is a nested command that doesn’t execute. So it’s a nested command that is a square:

![](images/7.%20Commands%20Ideas.032.png)
![](images/7.%20Commands%20Ideas.033.png)

It won’t execute unless it is called.

### Deeper Nested Command

`<< details >>`  

A deeper nested command is a nested command inside a nested command. So it’s a command symbol without a reference line in a command symbol without a reference line in a command symbol, for instance:

![](images/7.%20Commands%20Ideas.034.png)

It doesn’t matter whether any of the symbols is a square or a diamond.

### The If Example

`<< execution flow >>`

An application of that is the If command.

![](images/7.%20Commands%20Ideas.051.jpeg)

Command A passes Nested Command A and Nested Command B to Command B, along with an object that serves as the condition. Depending on the state of the condition, Nested Command A is executed or Nested Command B. So Command B gets to decide which nested command executes.

The nested commands can freely access anything of __Command A__, so __Command B__ is able to call things that can freely access __Command A__’s stuff.

### Active Nested Commands Compared to Objects

`<< commands compared to objects. >>`

An active nested command `is analogous` to an object that `might not` have a class. A *call* `is more` like an object that *`might`* have a class.

### Loose Ideas

`<< details >>`

A nested command `might not` redirect its definition, because then `it might` be a command call.

-----

`<< details >>`

A nested command `might not` redirect its object, because then `it might` be a command reference.

-----

`<< details >>`

A nested command `is never` situated inside an object, or `it might` not be a nested command.

-----

`<< rule rich >>`

Active nested commands, command calls and active command references in parent commands `are always` private, because `you can not` reference a sub-command.

![](images/1.%20Commands%20Main%20Concepts.052.png)

But *inactive* nested commands `*can*` be referenced and might be made public.

![](images/1.%20Commands%20Main%20Concepts.053.png)

-----

`<< rule rich >>`

*Active* nested commands, command calls and active command references in parent commands `are always` private, because `you can not` reference a sub-command.