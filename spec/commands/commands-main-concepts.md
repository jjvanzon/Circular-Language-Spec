Circular Language Spec | Commands
=================================

Main Concepts
-------------

`[ Preliminary documentation ]`

__Contents__

- [Introduction](#introduction)
- [Diagram Elements](#diagram-elements)
    - [Squares May Not Execute](#squares-may-not-execute)
- [Derived Constructs](#derived-constructs)
- [Command Definitions](#command-definitions)
- [Command Calls](#command-calls)
    - [How Calls May Work](#how-calls-may-work)
- [Command References](#command-references)
    - [How Command References May Work](#how-command-references-may-work)
- [Code Blocks](#code-blocks)
    - [Code Blocks Details](#code-blocks-details)
- [Local Function](#local-function)
- [Clauses](#clauses)
- [Lambda Expression](#lambda-expression)
- [Nested Commands](#nested-commands)
- [Parameters and Return Values Not Covered](#parameters-and-return-values-not-covered)
- [Implementation](#implementation)
- [Conclusion](#conclusion)
- [Synonyms](#synonyms)
    - [Command Definition Synonyms](#command-definition-synonyms)
    - [Definition Line Synonyms](#definition-line-synonyms)
    - [Executable Command Synonyms](#executable-command-synonyms)
    - [Command Call Synonyms](#command-call-synonyms)
    - [Command Reference Synonyms](#command-reference-synonyms)

### Introduction

Commands may be objects, that so happen to be *executable*. Commands could be actions, procedures and processes, that a computer might perform. They might be displayed in a diagram as squares and diamond shapes:

<img src="images/1.%20Commands%20Main%20Concepts.001.png" width="50" /> <img src="images/1.%20Commands%20Main%20Concepts.002.png" width="50" />

They may represent elements of the command structure. The square may be a general symbol for a command. The diamond may have a special meaning.

Relations between commands might be expressed by *containment*:

![](images/7.%20Commands%20Ideas.010.jpeg)

And by connecting them with *lines:*

![](images/7.%20Commands%20Ideas.011.jpeg)

There can be solid, dashed or dotted lines between command symbols. Names might be displayed with commands as well.

### Diagram Elements

Command concepts may be expressed by a limited set of characteristics.

A *diamond* in Circular may express a command that may be __executable__.

<img src="images/1.%20Commands%20Main%20Concepts.002.png" width="50" />

The side effect of a diamond might be that it *executes*. An *executable* command might be carried out, while one that is *not executable*, might stay asleep.

A *square* in Circular might symbolize that the command is __not executable__.

<img src="images/1.%20Commands%20Main%20Concepts.001.png" width="50" />

Relations betwen commands may be expressed by *containment*. One symbol might __contain__ another:

<img src="images/1.%20Commands%20Main%20Concepts.003.png" width="100" />

A *solid line* between symbols might mean that one command is a __reference__ to another:

<img src="images/1.%20Commands%20Main%20Concepts.004.png" width="100" />

Two symbols connected with a line, might be considered the same command.

A *dashed line* between command symbols might make one command a kind of copy of another:

<img src="images/1.%20Commands%20Main%20Concepts.005.png" width="80" />

It might also be said, that a command might be used as a __prototype__ for another command.

If a command might be used as a prototype, it might be drawn with a *dashed border*:

<img src="images/1.%20Commands%20Main%20Concepts.006.png" width="80" />

(Using dashed shapes is still a bit of an open discussion.)

A command may have a *name*:

<img src="images/1.%20Commands%20Main%20Concepts.007.png" width="140" />

It might also be *nameless.*

<img src="images/1.%20Commands%20Main%20Concepts.001.png" width="50" />

Here is an attempt to summarize these traits that commands might have:

- __(not) executable__
- __containment__
- __references__
- __prototypes__ (or "definitions")
- __(not) named__

#### Squares May Not Execute

![](images/7.%20Commands%20Ideas.037.jpeg)

A square might not execute. Well, they may only execute when called. __A__ may call __B__:

![](images/7.%20Commands%20Ideas.038.jpeg)

 But then again: __A__ may be the one that’s executing, not __B__. So diamonds may execute, and squares may not.

### Derived Constructs

Constructs that might be known from other programming languages, may have a reasonably unique expression using combinations of these more basic elements from Circular. Here follows an attempt to accompany this claim with some examples.

### Command Definitions

A command definition might describe the structure and behavior of another command.

It may look as follows in another programming language:

```c#
void MyDefinition()
{
}
```

Command definitions themselves might not necessarily execute. Just copies of it, more likely. Its *not executing* may be expressed with a square: 

<img src="images/1.%20Commands%20Main%20Concepts.008.png" width="50" />

If a command might used as a definition, it might be drawn with a *dashed border*:

<img src="images/1.%20Commands%20Main%20Concepts.006.png" width="70" />

(Though dashed shape notation is still a bit of an open discussion.)

A definition might also have a *name*:

<img src="images/1.%20Commands%20Main%20Concepts.009.png" width="140" />

When used, a command definition may be pointed to by a *dashed line*:

<img src="images/1.%20Commands%20Main%20Concepts.010.png" width="210" />

That way another symbol might use `MyDefinition` as a *prototype*.

So a command definition might be symbolized by:

- square
- named
- dashed
- pointed to with dashed lines

because it may be:

- not executable (directly)
- named
- used as a prototype
 
### Command Calls

A command definition might be *called* multiple times.

In a different programming language a command call may look as follows:

```c#
MyCommand();
```

A command call may *execute*, so it might be symbolized with a diamond shape:

<img src="images/1.%20Commands%20Main%20Concepts.002.png" width="50" />

A call may point out a definition, which might give it a *dashed line* pointing away from it:

<img src="images/1.%20Commands%20Main%20Concepts.011.png" width="120" />

A call might be placed *inside* a parent command.

<img src="images/1.%20Commands%20Main%20Concepts.012.png" width="140" />

The call itself might remain *nameless*.

So a command call might be symbolized by:

- diamond
- nameless
- contained in a square
- dashed line pointing away from it

because it may be:

- executable
- nameless
- contained inside a definition
- uses another command as a definition

#### How Calls May Work

To make one command call another command, a diamond might be put in the calling command and it may be connected to the command to call.

![](images/7.%20Commands%20Ideas.014.jpeg)

It could be said that __A__ calls __B__, or __B__ is called from __A__.

__C__ is now sort of part of command __A__ and it might execute when __A__ executes. It’s like the code of __B__ is inserted right into command __A__.

When one square is called, its contained squares may be called too.

![](images/7.%20Commands%20Ideas.015.jpeg)

When __A__ may be called, __B__ may be called. When __B__ would be called, __C__, __D__ and __E__ might be called too.

### Command References

A command could be *pointed to*.

This may look as follows in another programming language:

```c#
MyCommand
```

So without decoration with brackets or what have you, it may represent a reference to a command.

A command reference may be a square, to indicate it might not *execute* directly.

<img src="images/1.%20Commands%20Main%20Concepts.008.png" width="50" />

A *solid line* can be used to point out a different command:

<img src="images/1.%20Commands%20Main%20Concepts.013.png" width="400" />

So a command reference might be symbolized by:

- square 
- solid line pointing to another command

because it is:

- not executable (directly)
- a reference

#### How Command References May Work

A square connected to another command may be a mere *reference* to a command.

![](images/7.%20Commands%20Ideas.013.png)

A call to any square that represents the same command might be a call to the same command. A reference to either of the command references, is a reference to the same command.

Therefore, when a command reference might be called, it is like the referenced command is called:

![](images/7.%20Commands%20Ideas.017.jpeg)

When __A__ calls __B__, it’s actually calling __C__.

Command references may be a way to leave the command to call undetermined, variable, to be determined later.

### Code Blocks

Some programming languages might allow code blocks within a command, to group statements together. This might scope variables, so variables inside the block might only be used within that block, for some added safety against programming errors, perhaps.

In another programming language, this might look as follows:

```c#
void MyDefinition()
{
    {
        ...
    }
}
```

The inner braces and its contents might be the code block.

In Circular, a code block may be *embedded* inside another command:

<img src="images/1.%20Commands%20Main%20Concepts.014.png" width="100" />

The inner command (the code block) might be drawn as a *diamond*: it *executes* if the parent command executes.

A code block might be *nameless*. It might not have any *lines* going towards it or away from it.

A code block might also look like this:

<img src="images/1.%20Commands%20Main%20Concepts.015a.png" width="100" />

The previous diagram might show a code block within a definition (a square). This diagram shows the code block while that command is executed.

So a code block might be symbolized by:

- a diamond
- inside another command
- nameless
- no lines pointing to or from it

because it is:

- executable
- contained by another command
- nameless
- not a reference
- not a definition

#### Code Blocks Details

Code blocks might be nested even further:

<img src="images/1.%20Commands%20Main%20Concepts.016.png" width="180" />

Because a code block does not point out a definition, its contents might be arbitrary / decided by its parent command, unlike calls, whose contents might comply with a  definition, that they may call.

Code blocks might freely be used for putting a frame around a piece of code inside a command. In that case that command might still do the same thing:

![](images/1.%20Commands%20Main%20Concepts.033.png)

![](images/1.%20Commands%20Main%20Concepts.034.png)

### Local Function

A local function might be known from other programming languages and may mean a command that is defined within another command.

In a different programming language this might look as follows:

```c#
void MyParentCommand()
{
    void MyLocalFunction()
    {
    }
}
```

In Circular it might also be a command definition contained within another command definition.

<img src="images/1.%20Commands%20Main%20Concepts.017.png" width="100" />

When peeking at another programming language, a local function seems to be able to have a name.

<img src="images/1.%20Commands%20Main%20Concepts.018.png" width="160" />

It may also be *called* from within its parent command:

<img src="images/1.%20Commands%20Main%20Concepts.019.png" width="200" />

So a local function might be symbolized by:

- a square
- within a square
- with a name
- pointed to by dashed lines (possibly)

because it is:

- not executed directly
- contained in a definition
- has a name
- a prototype / might be called

### Clauses

Clauses might be found as elements of an `if` statement or for instance a `where` clause from querying languages.

This might look as follows in another language:

```c#
if { ... }
```

(This is pseudo code. A full `if` statement may have more parts.)

There might be a bit of an interpretation problem here. A clause in an `if` statement looks a bit like a *code block*. Maybe it could be interpreted as such.

<img src="images/1.%20Commands%20Main%20Concepts.020.png" width="100" />

It also may look a bit like a nameless local function that you might pass a reference to, to the `if` statement:

<img src="images/1.%20Commands%20Main%20Concepts.021.png" width="170" />

The exact interpretation might not matter too much. Clauses seem adequately expressible in Circular.

So a clause might be expressed with:

- a square
- inside a diamond
- that might connect to another square
- with a solid line

because it is:

- not executable (directly)
- passed to another command or statement
- might be a command reference

### Lambda Expression

A lambda expression might be found in other programming languages as sort of a short notation for a function, embedded inside other statements.

In another programming language this might look as follows:

```c#
Where(x => x.IsChecked)
```

Minus the details:

```c#
Where(...)
```

So the `...` might be the lambda expression.

Honestly said, in Circular there might not be a way to distinguish it from *clauses*.

<img src="images/1.%20Commands%20Main%20Concepts.022.png" width="100" />

Or:

<img src="images/1.%20Commands%20Main%20Concepts.023.png" width="160" />

### Nested Commands

A nested command may be a command inside another command with no lines going to or from it.

They may look like this:

<img src="images/7.%20Commands%20Ideas.021.jpeg" width="90" />
<img src="images/7.%20Commands%20Ideas.019.jpeg" width="80" />
<img src="images/1.%20Commands%20Main%20Concepts.015a.png" width="60" />
<img src="images/1.%20Commands%20Main%20Concepts.015b.png" width="60" />

They may coincide with the terms:

- Code blocks
- Clauses
- Local functions
- Lambda expressions

Those may all be examples of *nested commands*. Sometimes however, it might be easier to use a single name for these phenomena.

A distinction between *active* nested commands and *inactive* nested commands might be relevant sometimes. Code blocks might be *active* nested commands. A local function may be an *inactive* nested command for instance.

### Parameters and Return Values Not Covered

Symbolizations for parameters and return values might be missing in much of these texts. Those are intended to be covered by another chapter: "Parameters".

### Implementation

The implementation of a command might be defined as the private contents of a command. Here is an attempt to demonstrate that visually:

<img src="images/1.%20Commands%20Main%20Concepts.024.png" width="300" />

The large square might have contents, drawn with thick lines, might represent the command’s *implementation*, because they might be private. The objects inside the large square that are drawn with thinner lines, might be the command’s parameters: its publics. (Notation for *parameters* might be involved in the picture above, but might remain unexplained until the chapter "Parameters".)

### Conclusion

Using the constructs for commands from Circular, it may seem circumstantial whether a command symbol could be stereotyped as a block, clause, definition, call, etc. It seems to result from the way basic language elements from Circular relate to each other. Still, it may be relevant to be aware how these symbols from Circular can be combined to represent constructs from other languages.

### Synonyms

These terms may possibly be used interchangeably depending on context.

#### Command Definition Synonyms

- prototype
- blue-print
- inactive command
- inactive command symbol
- square
- command definition
- definition

#### Definition Line Synonyms

- command definition line
- call line
- prototype line
- dashed line
- definition line

#### Executable Command Synonyms

- active command
- active command symbol
- diamond
- executable command
- executable command symbol

#### Command Call Synonyms

- execution

#### Command Reference Synonyms

- function pointer
- method reference
- delegate