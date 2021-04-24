Circular Language Spec | Commands
=================================

Loose Ideas
-----------

`[ Preliminary documentation ]`

__Contents__

- [From the Original Symbol Documentation](#from-the-original-symbol-documentation)
    - [Introduction, Commands](#introduction-commands)
        - [Command Contents](#command-contents)
        - [Command Versus Type](#command-versus-type)
        - [Required and Optional Parameters](#required-and-optional-parameters)
    - [Executions & Parameters](#executions--parameters)
        - [Terms](#terms)
            - [Reference](#reference)
            - [Call](#call)
            - [Definition](#definition)
            - [Clause](#clause)
            - [Active and Inactive](#active-and-inactive)
            - [Active Clause](#active-clause)
            - [Inactive Clause](#inactive-clause)
            - [Sub Clause](#sub-clause)
            - [Sub Command](#sub-command)
            - [Executor and Execution](#executor-and-execution)
        - [Execution Basics](#execution-basics)
            - [Squares and Diamonds](#squares-and-diamonds)
            - [Diamonds Execute When Direct Parent Executes](#diamonds-execute-when-direct-parent-executes)
            - [Diamonds Can only be Directly Inside a Command Symbol, Diamonds Can’t be Directly Inside an Object Symbol](#diamonds-can-only-be-directly-inside-a-command-symbol-diamonds-cant-be-directly-inside-an-object-symbol)
            - [You Can Only Access Members of a Diamond](#you-can-only-access-members-of-a-diamond)
            - [You can Only Access Members of a Diamond, while the Diamond is executing](#you-can-only-access-members-of-a-diamond-while-the-diamond-is-executing)
            - [The Diamond Executor Can Access Members Only Just before and Just After the Execution](#the-diamond-executor-can-access-members-only-just-before-and-just-after-the-execution)
            - [Accessing a Diamond Member During a Call](#accessing-a-diamond-member-during-a-call)
            - [Passing an object reference to a command](#passing-an-object-reference-to-a-command)
            - [Command can set object reference itself too](#command-can-set-object-reference-itself-too)
            - [Clause Access](#clause-access)
            - [Passing a command reference](#passing-a-command-reference)
            - [The If example](#the-if-example)
            - [Brainstorm](#brainstorm)
        - [Argument Access](#argument-access)
            - [Prolog and Epilog](#prolog-and-epilog)
            - [Argument Assignment Requires Reading in Prolog!](#argument-assignment-requires-reading-in-prolog)
            - [Writing Arguments](#writing-arguments)
        - [Create Argument and Call Argument’s Members](#create-argument-and-call-arguments-members)
        - [Created Arguments](#created-arguments)
        - [Do It with a Parameter’s Members](#do-it-with-a-parameters-members)
        - [Brainstorm](#brainstorm-1)
            - [Summary of Old Subdivision](#summary-of-old-subdivision)
            - [New Subdivision](#new-subdivision)
            - [New Brainstorm Texts](#new-brainstorm-texts)
            - [Argument Access Summary](#argument-access-summary)
        - [Other](#other)
        - [Commands to Commands, Objects to Object](#commands-to-commands-objects-to-object)
        - [Brainstorm](#brainstorm-2)
    - [More Ideas](#more-ideas)
        - [Command Symbol Roles](#command-symbol-roles)
        - [Reference and Call Targets](#reference-and-call-targets)

### From the Original Symbol Documentation

#### Introduction, Commands

##### Command Contents

`<< details >>`  

Squares inside commands are non executing clauses or command references. Diamonds inside commands are executing clauses or command calls.

##### Command Versus Type

`<< commands compared to objects >>`

*Commands* differ from *types* in the following ways:

- They can execute
- A new command object is created *on each call* to the command and the command object is destroyed soon after the call.
- The public writable objects are written only right before the call.
- The public readable objects are read only right after the call.

##### Required and Optional Parameters

`<< optional / required >>`

As a command is like a type it may seem that you have full freedom regarding which objects you write and which you don’t. However, many parameters of commands are *required* parameters. This means that you *might* write something to it before the call. Optional parameters are ones that do not necessarily need to be written before the call. Required parameters are there to on one hand ensure a parameter holds a right value. That however, could have been done by the command’s initializing the value itself. The main point of required parameters is that a lot of times the function of a command just doesn’t make sense unless you write the parameters. The programmer is made extra aware of that by making the parameter required.

In diagram code, optional parameters are denoted by displaying the word __Optional__ near the optional parameter. The other parameters are required.

#### Executions & Parameters

`<< details >>`  

This section discusses all issues around executing commands and using parameters.

##### Terms

`<< terminology >>`

Here I introduce basic terms in the area of executions and parameters. Here’s a quick reference list.

- Reference
- Call
- Definition
- Clause
- Active
- Inactive
- Active clause
- Inactive clause
- Sub clause
- Sub command 
- Parameter
- Argument
- Executor
- Execution

###### Reference

`<< already covered >>`

The following are command references:

![](images/7.%20Commands%20Ideas.024.png)

It’s a square that is redirected. It’s always a *square* with a *reference line*. It is a command that redirects, but *might not* execute. It can point either to a square or a diamond.

###### Call

`<< already covered >>`

The following are calls:

![](images/7.%20Commands%20Ideas.025.png)

It’s a diamond that is redirected. It’s always a *diamond* with a *reference line*. It executes a command defined elsewhere. Therefore it is a call. It can point either to a square or a diamond.

###### Definition

`<< already covered >>`

A definition is a command symbol with no reference line at all.

![](images/7.%20Commands%20Ideas.026.png)

The reference line should not exist at all, not just not be shown. It’s a definition, because the contents of the command aren’t defined elsewhere, but defined in the symbol itself.

###### Clause

`<< already covered >>`

A command symbol inside another command symbol:

![](images/7.%20Commands%20Ideas.027.jpeg)

without a reference line is called a clause.

A clause is a definition contained in a command:

![](images/7.%20Commands%20Ideas.028.png)

`<< detail >>`  

This type of definition is usually not called a definition. The clause might be directly contained by a command. So this is not a clause:

![](images/7.%20Commands%20Ideas.029.png)

`<< already covered>>`  

The clause can be a diamond or a square. Its container can also be a diamond as well as a square. A clause might not have a reference line, or it might have been a reference or a call, not a clause.

###### Active and Inactive

`<< already covered>>`  

A diamond executes, a square might not. A diamond is said to be active, while a square is inactive.

###### Active Clause

`<< already covered>>`  

A clause that is a diamond, is called an active clause:

![](images/7.%20Commands%20Ideas.030.png)
![](images/7.%20Commands%20Ideas.031.png)

It’s called active, because it executes.

###### Inactive Clause

`<< already covered>>`  

An inactive clause is a clause that doesn’t execute. So it’s a clause that is a square:

![](images/7.%20Commands%20Ideas.032.png)
![](images/7.%20Commands%20Ideas.033.png)

It won’t execute unless you call it.

###### Sub Clause

`<< already covered>>`  

A sub clause is a clause inside a clause. So it’s a command symbol without a reference line in a command symbol without a reference line in a command symbol, for instance:

![](images/7.%20Commands%20Ideas.034.png)

It doesn’t matter whether any of the symbols is a square or a diamond.

###### Sub Command

`<< terminology >>`

A sub command is any command symbol inside another command symbol.

![](images/7.%20Commands%20Ideas.035.png)

But usually it’s only the diamonds that are referred to as sub commands. That’s because the execution of a command is made up of the execution of it’s contained diamonds combined.

![](images/7.%20Commands%20Ideas.036.png)

###### Executor and Execution

`<< terminology >>`

Any diamond symbol is called an executor, because it can execute. A single diamond can execute multiple times. An individual execution of a diamond is called an *execution*.

It’s allowed to call an executor an execution, but usually only while it’s executing.

##### Execution Basics

< Some things here may have a place in Execution Order >

`<< details >>`  

< Might this cover which situations only apply to commands compared to objects? >

This section covers some basic execution situations. Each situation has certain implications. Usually the implications are quite obvious, but perhaps noteworthy nevertheless.

`< 2021-04-20: Here the struggle might become visible of trying to this notation work for commands. >`

###### Squares and Diamonds

`<< nice formulation ? >>`

`<< rule rich ? >>`

![](images/7.%20Commands%20Ideas.037.jpeg)

A square doesn’t execute. Well, they only execute when you call it.

![](images/7.%20Commands%20Ideas.038.jpeg)

*A is a call to B.*

But then again: A is the one that’s executing, not B. So diamonds execute, and squares do not.

###### Diamonds Execute When Direct Parent Executes

`<< rule rich >>`

A diamond doesn’t execute automatically. It only executes when the parent symbol executes.

![](images/7.%20Commands%20Ideas.039.jpeg)

*A executes only as B executes.*

So diamonds inside squares don’t really execute.

![](images/7.%20Commands%20Ideas.040.jpeg)

But if you call B, then you get the following:

![](images/7.%20Commands%20Ideas.041.jpeg)

Actually, The letters distinguish the different symbols. If you only use letters to distinguish which command definition it’s about, you get the following:

![](images/7.%20Commands%20Ideas.042.jpeg)

So in that sense, diamond A might execute. But not the definition executes, only the call executes.

###### Diamonds Can only be Directly Inside a Command Symbol, Diamonds Can’t be Directly Inside an Object Symbol

`<< rule rich >>`

Because execution can only take place in a command, a diamond can’t be directly inside an object Symbol

![](images/7.%20Commands%20Ideas.043.jpeg)

###### You Can Only Access Members of a Diamond

`<< rule rich >>`

You can (usually) only access members of a diamond, because a square is never created, just like you can’t access members of a non created object.

![](images/7.%20Commands%20Ideas.044.jpeg)

![](images/7.%20Commands%20Ideas.045.jpeg)

###### You can Only Access Members of a Diamond, while the Diamond is executing

`<< rule rich ? >>`

`<< creation behavior of commands ? >>`

Because a diamond is only created when it’s executing, you can only access members when the diamond is in execution.

Some members of a command can be static. In that case the member belongs to the command definition. Those member are the same for any reference or call to a command. Static member of a command can be freely accessed through any square or diamond that represents it.

###### The Diamond Executor Can Access Members Only Just before and Just After the Execution

`<< creation behavior of commands ? >>`

If the diamond executor accesses something of a diamond, it’ll only access it just before and just after the call.

< Don’t know the notation, really >

In fact the diamond executor might only write members just before the call and might only read members just after the call.

< Don’t forget that you don’t need to read or write necessarily, you can also just call a member of the parameter instead of read or write it... explore that >

###### Accessing a Diamond Member During a Call

`<< rule rich >>`

So how might you access a diamond member *during* a call? Well, usually only commands called by the executing diamond can access the call parent.

![](images/7.%20Commands%20Ideas.046.jpeg)

Diamond A executes, then diamond B executes and accesses a member of diamond A. It’s not the command definition, the square, that accesses a member of diamond A, but it’s the specific call to the command that access diamond A. So usually you’ll only see child diamonds accessing parent diamonds, on top of the more common situation of write access before a call and read access after.

Multi-threading, which is basically multiple things running at the same time, may also make you able to access a diamond in execution, but this might not usually be a good idea. Restrictions might be imposed onto multi-threading to avoid such situations.

![](images/7.%20Commands%20Ideas.047.jpeg)

Two sibling commands are executing at the same time, in different threads, which makes it possible for one executing command to access the other. Thread control makes it possible to avoid such volatile situations.  
(the fact that the diamonds are drawn with thicker lines above, says that they are both in execution. If they wouldn’t be thicker drawn, then the diagram above doesn’t explicitly show that there is a multi-threaded situation. Regarding it single threadedly, the situation above is just the bigger diamond executing first, after which the smaller diamond uses its return value.)

< What happens when two threads try to initiate the same diamond or a thread tries to initiate a diamond that’s already executing. I want that one figured out. >

< Consider the example of diamond reference to diamond in the main argument reference example >

###### Passing an object reference to a command

`<< rule rich >>`

![](images/7.%20Commands%20Ideas.048.jpeg)

When you pass an object reference to a command, the command can access the object.  
In the situation above it seems the command could access the object anyway (because a command can access everything accessible to the object that contains it). It *can*, but in this case the *caller* decides which object to point to, not the called.

###### Command can set object reference itself too

`<< rule rich >>`

When the caller (the parent diamond) sets the line, then the caller decides which object the call might refer to.

So lines going out of a diamond aren’t necessarily lines set by the caller.  
Commands can’t set line going *into* the square themselves. Those are always set by the caller.

It’s important that the command itself sets lines, because the line targets of command members often serve as the output values of the command.

< I don’t know a notation to distinct sets by the caller and sets by the call. Well... in a more explicit notation you might see that the caller calls the set or the called calls the set. >

###### Clause Access

`<< rule rich >>`

`<< interpretation issues >>`

Clauses have special access privileges compared to delegated command symbols.

![](images/7.%20Commands%20Ideas.049.jpeg)

< Bad explanation following >  
A clause can freely access anything of its parent clause and the parent clause’s parent clause, etcetera. If going up the command ancestry a command symbol is encountered with a reference line, the clause can access this ancestor freely, but not any higher in the command ancestry.

In the picture above, the top two lines could have been set by A itself. The first resides in A’s parent clause. The second resides in the *execution* that parents A, so still accessible to A. The last line, crossed out, can’t be set by A itself, because it resides outside A’s containing call. It can be set only by a symbol higher than A’s containing call, for instance B.

Squares formally can’t have outward lines, except for static members. There are situations in which non static members of squares are shown to have outward lines, but those are discussed later.

###### Passing a command reference

`<< parameters >>`

When you pass a command reference to a child command:

![](images/7.%20Commands%20Ideas.050.jpeg)

The child can call the referenced command at will.

###### The If example

`<< execution flow >>`

An application of that is the If command.

![](images/7.%20Commands%20Ideas.051.jpeg)

Command A passes Clause A and Clause B to Command B, along with an object that serves as the condition. Depending on the state of the condition, Clause A is executed or Clause B. So Command B gets to decide which clause executes.

`<< interpretation issues >>`

The clauses can freely access anything of __Command A__, so __Command B__ is able to call things that can freely access __Command A__’s stuff.

###### Brainstorm

`<< rule rich >>`

####### Brainstorm 1

- Simple obvious issues regarding execution.
- For instance, diamond only inside a command symbol
- Stuff like that. Simple issues that you can easily understand.
- Diamond pointing to another diamond.
- Recursive calls... hmmm... advanced issue. You might not break your head over that. 
    - < Maar lijkt een Execution basics. Hmmm... de term Execution Basics is niet goed genoeg dan. De term basics is niet goed. Execution Facts... maybe not.>
- Wanneer wordt een diamond meerdere keren geexecute?

####### Brainstorm 2

`<< rule rich >>`

Diamond represents individual calls to a definition.  
In a recursive situation, though: < P >, one diamond can represent multiple calls < ? How to get that straight? >  
< NO IT CAN’T. >

####### Brainstorm 3

`<< interpretation issues >>`

A diamond pointing to another diamond: it’s a call to a call. both diamonds represent the same call. They might never execute individually.

####### Brainstorm 4

`<< circularity >>`

If eventually the original caller is called again, with one of its calls in progress... hmm... can you call upon a call on hold, because it is waiting for one of its calls to finish? Its public objects, maybe, but you can’t execute anything in it. 

![](images/7.%20Commands%20Ideas.052.png)

####### Brainstorm 5

`<< rule rich>>`

(*Implicit* embedded command reference causes a separate implicit call.)

####### Brainstorm 6

`<< interpretation issues >>`

__*Commands can only be Called from another Command*__

*Commands can only be called directly from another command.*

< Because a call executes its target when its container square is executed. Actually, relate all restrictions to the fact that commands execute. >

< 2021-04-20: These issues seem to disappear with introducing the diamond for execution and having distinct call and reference lines: dashed vs. solid line styles. >

A command symbol might only have a call line if it’s directly inside another command. Usually the call line first exits the command that contains the call. In other words: a call line usually directly exits a square.

![](images/7.%20Commands%20Ideas.053.png)

Only when you call a clause or an embedded command reference, the line doesn’t exit the command first:

*Call to clause:*  
![](images/7.%20Commands%20Ideas.054.jpeg)

*Call an internal command reference:*  
![](images/7.%20Commands%20Ideas.055.jpeg)

`<< creation behavior of commands >>`

Using arguments always requires assignment.

Just before execution you’ll write arguments. Just after execution, you’ll read arguments. Those are the main two occasions you’ll access arguments.

##### Argument Access

###### Prolog and Epilog

`<< creation behavior of commands >>`

Writing and reading arguments require things to be done just before and right after the execution. Things that might be done just before execution are called the *prolog* of the execution. Things that might be done just after the execution are called the *epilog*.

Writing arguments takes place in the prolog and reading arguments takes place in the epilog.

###### Argument Assignment Requires Reading in Prolog!

`<< rule rich >>`

Argument assignment takes place in the *prolog*. But *setting* the argument also requires *getting* the argument. However, getting the argument was said to take place in the *epilog*. For the purpose of *setting* the argument, however, *getting* happens in the *prolog*.

An assignment call:

![](images/7.%20Commands%20Ideas.056.jpeg)

*consults* the argument to *write*: *reads* the argument to *write*.

Assignment of arguments simply *might* take place in the prolog, even though they require reading the arguments.

Assignment commands are fundamental commands of the Symbol Language and behave much different from other commands.

###### Writing Arguments

`<< creation behavior of commands >>`

Writing an argument before execution means to set its state or line target.

`<< system interfaces >>`

An assignment as such, requires you to get a value from one place and set the argument to it. So writing an argument actually requires both a __Get__ and a __Set__. The fact that it’s the argument that’s __Set__ makes it writing *the argument*.

##### Create Argument and Call Argument’s Members

`<< system interfaces >>`

There may be more things you want to do with an argument before passing it to a command. You may want to create a brand new object as an argument and you may want to call some members of the argument first. You *can’t* do these operations directly on the argument. You might create a separate object, manipulate it and then pass it by reference

There’s a shorthand for creating a brand new object and passing it by reference. In text code this might look like this:

```vb
Command ( New Type )
```

It’s declared directly inside the command call. That is: unless the object is used elsewhere too. The above can also be notated as follows:

```vb
Object As Type       'Declaration
Object = New Type    'Creation
Command ( Object ) 'Pass to Command
```

But if __Object__ isn’t used anywhere else, you can just type: 

```vb
Command ( New Type )
```

That way, the object seems to be the argument itself, even though you’re actually passing an object by reference.

In diagram code, the declaration of the object, its creation and its being passed to the command, looks like this: 

![](images/7.%20Commands%20Ideas.057.jpeg)

`<< peels >>`

You can let the separate object seem to be the argument itself, by using a peel notation:

![](images/7.%20Commands%20Ideas.058.jpeg)

The creation might still be visible, but you’ve excluded the line, without loosing the information that it’s really an external object. 

Of course you might not show the implicit creation.

![](images/7.%20Commands%20Ideas.059.jpeg)

Then you just see that the object is created, and you might be satisfied knowing only *that* it is created, not where and when. This is just about exactly the effect of:

```vb
Command ( New Type )
```

##### Created Arguments

`<< implementations >>``

A command can decide if an argument is a created object or not. If it is a created object, then the object is created in the prolog, even before writing arguments. The argument object is created, then it is written, then the command executes.

Arguments as such are created objects directly contained by the command. They shouldn’t have lines. 

In the epilog, first arguments are read before the created arguments are destroyed. The command only destroys objects it directly contains.

##### Do It with a Parameter’s Members

`<< details >>`

<
*Other things done with parameters*  
or keeping a reference to a created parameter or __do the same with members of parameters__... Hmmm...

Except for passing command reference to a command.
\>

##### Brainstorm

###### Summary of Old Subdivision

`<< creation behavior of commands >>`

- Writing arguments before the call:
    - Assignment: lines or state
    - Creation
    - Possibly call members of an argument
- Reading parameters before the call:
    - Reading line targets (direct, final or intermediate)
    - Reading state
- Writing a parameter means setting a line or reading state from an object and writing it to a parameter
- Reading a parameter means writing it to another object

`<< rule rich >>`

- Execution basics: 
    - simple issues regarding execution
    - for instance, diamond only inside a command symbol
    - Stuff like that. Simple issues that you can easily understand.

`<< creation behavior of commands>>`

- Diamond member access:
    - The caller of a diamond accesses members just before the call and just after
    - The callees of a diamond can access the caller's members if given references to them

`<< terminology >>`

- The terms:
    - Reference
    - call
    - definition
    - clause
    - active clause
    - inactive clause
    - sub clause / sub command 
    - ...

`<< special access >>`

- Clause access

`<< explains other technology >>`

- Differences with Com with returning object references

`<< interpretation >>`

- Inside directly accessible, outside only 'indirectly' accessible (if line set FOR you)
- Seeming randomly referencing diamond members. 

`<< rule rich >>`

- Wanneer wordt een diamond meerdere keren geexecute?

`<< details >>`

- Diamond pointing to another diamond
- Line of connected diamonds change simultaneously

###### New Subdivision

`<< creation behavior of commands >>`

- Parameter Access
    - Writing parameters before execution
        - Assignment: lines or state
        - Creation
        - Possibly call members of an argument
    - Reading parameters after execution
        - Reading line targets (direct, final or intermediate)
        - Reading state
    - Access during execution
        - By owner
        - By child executions (~ is this the proper place for this?)
            - The callees of a diamond can access the caller's members if given references to them

`<< terminology >>`

- Basic Terms
    - Reference
    - call
    - definition
    - clause
    - active clause
    - inactive clause
    - sub clause / sub command 
    - Definitions of the terms parameter and argument
    - < Which precisely? >
    - ...

`<< rule rich >>`

- Execution Basics
    - Simple issues regarding execution < Which precisely? >
    - For instance, diamond only inside a command symbol
    - Stuff like that. Simple issues that you can easily understand.
    - Diamond pointing to another diamond

- Wanneer wordt een diamond meerdere keren geexecute?

?:

Line of connected diamonds change simultaneously

###### New Brainstorm Texts

The problems proposed in this text might have to do with:

`<< terminology >>`

- The terms prolog and epilog.
- The term executor and execution

`<< details >>`

- Paradox: Parameter assignments involve consults of parameters in prolog of command call, while consults are usually always in epilog.
- Diamond may only represent a single execution per definition call (not regarding unconditional jumps (? The latter is questionable.)

####### New

`<< creation behavior of commands >>`

- Prolog and epilog
- Parameter writes in prolog
- Parameter reads (/consults) in epilog 

- Paradox: Assignments of parameters suggests reading parameters. However, these assignments do take place in the prolog, even though they suggest reads. Assignments are different that way.

###### Argument Access Summary

`<< creation behavior of commands >>`

- Writing parameters before execution
    - Assignment: lines or state
    - Creation
    - Possibly call members of an argument
- Reading parameters after execution
    - Reading line targets (direct, final or intermediate)
    - Reading state

`<< details >>`

- Access during execution
    - By owner
    - By child executions (~ is this the proper place for this?)
        - The callees of a diamond can access the caller's members if given references to them

##### Other

`<< terminology >>`

A command symbol can have one of four roles: - definition, - clause, - call, - reference

-----

`<< creation behavior of commands >>`

2004,

Generating the stack operations preceding and concluding function calls is called prolog and epilog code in C

JJ

##### Commands to Commands, Objects to Object

`<< rule rich >>`

< 2008-10-12 I am not sure I should impose this rule or not >

Commands can be tied only to commands.

![](images/7.%20Commands%20Ideas.060.png)

Objects can be tied only to objects.

![](images/7.%20Commands%20Ideas.061.png)

Formally, there can be no lines connecting objects and commands:

![](images/7.%20Commands%20Ideas.062.jpeg)

`<< return values >>`

< Ignore this talk about implicit notations. >

However, the above *is* a valid notation. It actually denotes the object being a pointer to the *return value* of the command. It’s an *implicit* notation (covered later), that actually standard for something else:

![](images/7.%20Commands%20Ideas.063.jpeg)

`<< already covered >>`

So then object symbols point only to object symbols and command symbols only to command symbols.

However, the picture above is actually again an implicit notation for something else, but I won’t go into detail about that yet.

##### Brainstorm

`<< details >>`

A command might probably not get its own symbol anyway. It might just be an object with an execution point.

A command symbol can define its own command:

![](images/7.%20Commands%20Ideas.064.png)

But if it has a reference line it is regarded no more than a reference or call to a command. The target of the line is considered the command itself or the *definition* of the command.

*A is the reference, B is the definition:*  
![](images/7.%20Commands%20Ideas.065.jpeg)

*A is the command reference, B is the definition:*  
![](images/7.%20Commands%20Ideas.066.jpeg)

#### More Ideas

##### Command Symbol Roles

`<< construct drafts >>`

A call line makes the square a call. A reference line makes it a reference. No line at all indicates that it’s a command definition or a clause. Lines can also be left out for abstraction reasons.

| ![](images/7.%20Commands%20Ideas.067.png) | ![](images/Symbol%20Language%20(2004).409b.png) | ![](images/7.%20Commands%20Ideas.068.png) | ![](images/7.%20Commands%20Ideas.069.png) <br> ![](images/7.%20Commands%20Ideas.070.png) | ![](images/7.%20Commands%20Ideas.071.png) |
|:----------:|:------:|:----:|:---------:|:------------------------------------------------------:|
| Definition | Clause | Call | Reference | Illegal: a square can’t be both a call and a reference |

< Not true: a call might not directly exit a square if it calls a command reference embedded in the same command or a clause of the command >

Note here that the access symbol of a solid command reference line is also drawn solid.

< 2021-04-20: This seems from before the diamond shape was introduced. Other clues may have been hoped to disambiguate the different programming constructs. A newer idea may use diamond shapes along with squares, and may suggest a more specific use of solid lines and dashed lines. >

##### Reference and Call Targets

`<< construct drafts >>`

Here is a list of possible reference targets and call targets:

|                                           |                                            |
|:-----------------------------------------:|:------------------------------------------:|
| ![](images/7.%20Commands%20Ideas.072.png) | ![](images/7.%20Commands%20Ideas.075a.png) |
|          Reference to definition          |             Call to definition             |
|                                           |                                            |
| ![](images/7.%20Commands%20Ideas.073.png) | ![](images/7.%20Commands%20Ideas.075b.png) |
|            Reference to clause            |               Call to clause               |
|                                           |                                            |
| ![](images/7.%20Commands%20Ideas.074.png) | ![](images/7.%20Commands%20Ideas.076.png)  |
|          Reference to reference           |             Call to reference              |
|                                           | (A call to a reference calls the referenced command) |

`<< commands example diagrams >>`

|     |    |
|-----|----|
| ![](images/7.%20Commands%20Ideas.077.jpeg) | __Reference to sibling inactive clause, in a square.__ <br> Only possible for static command members or exclusive establishment. | 
| ![](images/7.%20Commands%20Ideas.078.jpeg) | __Reference to sibling active clause, in a square.__ <br> Only possible for static command members or exclusive establishment. | 
| ![](images/7.%20Commands%20Ideas.079.jpeg) | __Call to sibling inactive clause, in a square.__ <br> This is like a jump to a clause, that might otherwise not execute. <br> Only possible for static command members or exclusive establishment. |

`<< rule rich >>`

A diamond can be executing. Only during the execution of the diamond, lines between its non static children can be real. If the diamond isn’t executing, or it’s not a diamond, but a square, lines between the non static children are suggestive. Only lines between static members in such cases, can be real.