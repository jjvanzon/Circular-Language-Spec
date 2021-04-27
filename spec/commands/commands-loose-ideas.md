Circular Language Spec | Commands
=================================

Loose Ideas
-----------

`[ Preliminary documentation ]`

__Contents__

- [From the Original Symbol Documentation](#from-the-original-symbol-documentation)
    - [Executions & Parameters](#executions--parameters)
        - [Execution Basics](#execution-basics)
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

#### Executions & Parameters

##### Execution Basics

`< 2021-04-20: Here the struggle might become visible of trying to this notation work for commands. >`

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

`<< rule rich >>`

(*Implicit* embedded command reference causes a separate implicit call.)

####### Brainstorm 6

`<< interpretation issues >>`

__*Commands can only be Called from another Command*__

*Commands can only be called directly from another command.*

< Because a call executes its target when its container square is executed. Actually, relate all restrictions to the fact that commands execute. >

< 2021-04-20: These issues seem to disappear with introducing the diamond for execution and having distinct call and reference lines: dashed vs. solid line styles. >

A command symbol might only have a call line if it’s directly inside another command. Usually the call line first exits the command that contains the call. In other words: a call line usually directly exits a square.

![](images/7.%20Commands%20Ideas.053.png)

Only when you call a nested command or an embedded command reference, the line doesn’t exit the command first:

*Call to nested command:*  
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

`<< implementations >>`

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
    - reference
    - call
    - definition
    - nested command
    - active nested command
    - inactive nested command
    - deeper nested command 
    - sub command 
    - ...

`<< special access >>`

- Nested command access

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
    - nested command
    - active nested command
    - inactive nested command
    - deeper nested command / sub command 
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

A command symbol might have one of four roles:

- definition
- call
- reference
- nested command

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

A call line makes the square a call. A reference line makes it a reference. No line at all indicates that it’s a command definition or a nested command. Lines can also be left out for abstraction reasons.

| ![](images/7.%20Commands%20Ideas.067.png) | ![](images/Symbol%20Language%20(2004).409b.png) | ![](images/7.%20Commands%20Ideas.068.png) | ![](images/7.%20Commands%20Ideas.069.png) <br> ![](images/7.%20Commands%20Ideas.070.png) | ![](images/7.%20Commands%20Ideas.071.png) |
|:----------:|:------:|:----:|:---------:|:------------------------------------------------------:|
| Definition | Nested command | Call | Reference | Illegal: a square can’t be both a call and a reference |

< Not true: a call might not directly exit a square if it calls a command reference embedded in the same command or a nested command of the command >

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
|        Reference to nested command        |           Call to nested command           |
|                                           |                                            |
| ![](images/7.%20Commands%20Ideas.074.png) | ![](images/7.%20Commands%20Ideas.076.png)  |
|          Reference to reference           |             Call to reference              |
|                                           | (A call to a reference calls the referenced command) |

`<< commands example diagrams >>`

|     |    |
|-----|----|
| ![](images/7.%20Commands%20Ideas.077.jpeg) | __Reference to sibling inactive nested command, in a square.__ <br> Only possible for static command members or exclusive establishment. | 
| ![](images/7.%20Commands%20Ideas.078.jpeg) | __Reference to sibling active nested command, in a square.__ <br> Only possible for static command members or exclusive establishment. | 
| ![](images/7.%20Commands%20Ideas.079.jpeg) | __Call to sibling inactive nested command, in a square.__ <br> This is like a jump to a nested command, that might otherwise not execute. <br> Only possible for static command members or exclusive establishment. |

`<< rule rich >>`

A diamond can be executing. Only during the execution of the diamond, lines between its non static children can be real. If the diamond isn’t executing, or it’s not a diamond, but a square, lines between the non static children are suggestive. Only lines between static members in such cases, can be real.