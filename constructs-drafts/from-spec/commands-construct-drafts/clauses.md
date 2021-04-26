Circular Language Construct Drafts | From Spec
==============================================

Clauses
-------

`[ Deprecated documentation ]`

__Contents__

- [Introduction](#introduction)
- [Command Clause](#command-clause)
- [Access from Code Blocks, Clauses & Local Functions](#access-from-code-blocks-clauses--local-functions)
- [Access from Code Blocks, Clauses & Local Functions](#access-from-code-blocks-clauses--local-functions-1)
- [Access from Code Blocks, Clauses & Local Functions](#access-from-code-blocks-clauses--local-functions-2)
- [Clause](#clause)
- [Active Clause](#active-clause)
- [Inactive Clause](#inactive-clause)
- [Sub Clause](#sub-clause)
- [The If Example](#the-if-example)
- [Active Clause Compared to Objects](#active-clause-compared-to-objects)
- [Loose Ideas](#loose-ideas)

### Introduction

A deprecated meaning of 'clause'. In earlier texts the term 'clause' was defined a bit differently. 

The alternative interpretation of the word clause may have been: *a command inside another command with no lines going to or from it*.

'Clause' in more common IT terminology may mean: a piece of code inside another statement.

A mapping between that alternative interpretation and perhaps more common IT terminology might be:

| Alternative term | More Common IT terminology |
|------------------|----------------------------|
| Active clause    | Code block                 |
| Inactive clause  | Local function or clause   |

### Command Clause

`<< already covered >>`

A diamond without a line:

![](images/7.%20Commands%20Ideas.019.jpeg)

`<< nice formulation >>`  

Also executes, when its parent command executes,

`<< details >>`  

but it doesn’t delegate to another command, like a call might:

![](images/7.%20Commands%20Ideas.020.jpeg)

`<< terminology >>`  

It is an undelegated part of a command, called a *clause*.

`<< synonyms >>`  

Because a diamond might not be a call, it is also called an *execution* or an *execution point*.

`<< terminology >>`  

An undelegated square inside a command is also considered a clause.

![](images/7.%20Commands%20Ideas.021.jpeg)

but it doesn’t execute, unless you call it.

![](images/7.%20Commands%20Ideas.022.jpeg)

`<< synonyms >>`  

A lineless diamond is also called an *active clause*, while a lineless square is also called an *inactive clause*.

### Access from Code Blocks, Clauses & Local Functions 

Squares formally can’t have outward lines, except for static members. There are situations in which non static members of squares are shown to have outward lines, but those are discussed later.

### Access from Code Blocks, Clauses & Local Functions 

Code blocks, clauses and local functions may have special access privileges compared to delegated command symbols.

![](images/7.%20Commands%20Ideas.049.jpeg)

< Bad explanation following >  
A code blocks, clauses or local functions may freely access anything of its parent block and the parent block’s parent block, etcetera. If going up the command ancestry a command symbol is encountered with a reference line, the code blocks, clauses or local functions can access this ancestor freely, but not any higher in the command ancestry.

In the picture above, the top two lines could have been set by A itself. The first resides in A’s parent code block. The second resides in the *execution* that parents A, so still accessible to A. The last line, crossed out, can’t be set by A itself, because it resides outside A’s containing call. It can be set only by a symbol higher than A’s containing call, for instance B.

### Access from Code Blocks, Clauses & Local Functions 

< Nice sentence:  
A procedure makes all direct children accessible to all blocks.  
Only is that true? >

Code blocks, clauses and local functions are embedded procedures. In a diagram these are squares contained in other squares that have no lines. Beware that a diagram may not be showing the line, even when it exist.

![](images/0.%20Special%20Access.016.png)

Code blocks, clauses and local functions have access to the contents of all their descendant blocks and the procedure definition they’re in. This means that a code blocks, clauses or local functions can directly access its containing definition’s members:

![](images/0.%20Special%20Access.017.png)

and all its encapsulating code blocks, clauses and local functions:

![](images/0.%20Special%20Access.018.png)

But a blocks might not have access to a block that doesn’t encapsulate it.

![](images/0.%20Special%20Access.019.png)

So its like the borders of clauses can be ignored in outward access.

### Clause

`<< terminology >>`

A command symbol inside another command symbol:

![](images/7.%20Commands%20Ideas.027.jpeg)

without a reference line is called a clause.

A clause is a definition contained in a command:

![](images/7.%20Commands%20Ideas.028.png)

`<< detail >>`

This type of definition is usually not called a definition. The clause might be directly contained by a command. So this is not a clause:

![](images/7.%20Commands%20Ideas.029.png)

`<< terminology >>`

The clause can be a diamond or a square. Its container can also be a diamond as well as a square. A clause might not have a reference line, or it might have been a reference or a call, not a clause.

### Active Clause

`<< terminology >>`

A clause that is a diamond, is called an active clause:

![](images/7.%20Commands%20Ideas.030.png)
![](images/7.%20Commands%20Ideas.031.png)

It’s called active, because it executes.

### Inactive Clause

`<< terminology >>`

An inactive clause is a clause that doesn’t execute. So it’s a clause that is a square:

![](images/7.%20Commands%20Ideas.032.png)
![](images/7.%20Commands%20Ideas.033.png)

It won’t execute unless you call it.

### Sub Clause

`<< terminology >>`  

A sub clause is a clause inside a clause. So it’s a command symbol without a reference line in a command symbol without a reference line in a command symbol, for instance:

![](images/7.%20Commands%20Ideas.034.png)

It doesn’t matter whether any of the symbols is a square or a diamond.

### The If Example

An application of that is the If command.

![](images/7.%20Commands%20Ideas.051.jpeg)

Command A passes Clause A and Clause B to Command B, along with an object that serves as the condition. Depending on the state of the condition, Clause A is executed or Clause B. So Command B gets to decide which clause executes.

The clauses can freely access anything of __Command A__, so __Command B__ is able to call things that can freely access __Command A__’s stuff.

### Active Clause Compared to Objects

< May change terminology. >

An active clause `is analogous` to an object that `might not` have a class. A *call* `is more` like an object that *`might`* have a class.

### Loose Ideas

A clause `might not` redirect its definition, because then `it might` be a command call.

-----

A clause `might not` redirect its object, because then `it might` be a command reference.

-----

A clause `is never` situated inside an object, or `it might` not be a clause.

-----

Active clauses, command calls and active command references in parent commands `are always` private, because `you can not` reference a sub-command.

![](images/1.%20Commands%20Main%20Concepts.052.png)

But *inactive* clauses `*can*` be referenced and might be made public.

![](images/1.%20Commands%20Main%20Concepts.053.png)

-----

*Active* clauses, command calls and active command references in parent commands `are always` private, because `you can not` reference a sub-command.