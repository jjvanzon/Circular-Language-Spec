Circular Language Construct Drafts | From Spec
==============================================

Commands Construct Drafts
-------------------------

`[ Deprecated documentation ]`

__Contents__

- [Sub-Commands](#sub-commands)
- [Active and Inactive](#active-and-inactive)
- [Sub Command](#sub-command)
- [Nested Commands](#nested-commands)
- [Diamond Pointing to Another Diamond](#diamond-pointing-to-another-diamond)
- [No Diamond Shapes](#no-diamond-shapes)
    - [Commands Might Only Be Called from Another Command](#commands-might-only-be-called-from-another-command)
    - [Command Symbol Roles](#command-symbol-roles)
    - [Reference and Call Targets](#reference-and-call-targets)
- [Without Dashed Lines](#without-dashed-lines)
- [Loose Ideas](#loose-ideas)

### Sub-Commands

`<< terminology >>`  

Sub-commands `are` active commands `contained` inside a parent command. `You can` encounter them inside `any` command symbol: both active and inactive commands symbols `can` contain sub-commands. `The` sub-commands `are` *active* commands: command calls, active nested commands or active command references.

Below `is` a picture of two sub-commands inside an inactive command:

![](images/1.%20Commands%20Main%20Concepts.048.png)

`The` __Parent Command__ `is` an inactive command, because it `is` a square. In `the` diagram above, `the` __Parent Command__ `contains` two sub-commands. `The` sub-commands `are` displayed as diamond shapes. One of `the` sub-commands `is` a call, because it `has` a dashed line `going` outside `the` __Parent Command__, `tying the` sub-command to its command definition. `The` other sub-command `is` an *active nested command*, because it `might not` redirect its command definition.

Below `is` a picture of two sub-commands inside an active command:

![](images/1.%20Commands%20Main%20Concepts.049.png)

It `is the same` picture as `the` other diagram, `only now the` __Parent Command__ `is` an executable command symbol, `not` an inactive command.

### Active and Inactive

`<< terminology >>`  

A diamond executes, a square might not. A diamond is said to be active, while a square is inactive.

### Sub Command

`<< terminology >>`

A sub command is any command symbol inside another command symbol.

![](images/7.%20Commands%20Ideas.035.png)

But sometimes it may only be the diamonds that are referred to as sub commands. That’s because the execution of a command is made up of the execution of it’s contained diamonds combined.

![](images/7.%20Commands%20Ideas.036.png)

### Nested Commands

`<< nice formulation >>`  

Also executes, when its parent command executes,

`<< details >>`

but it doesn’t execute, unless you call it.

![](images/7.%20Commands%20Ideas.022.jpeg)

`<< terminology >>`

A nested command is usually not called a definition.

`<< details >>`

The nested command might be directly contained by a command. So this is not a nested command:

![](images/7.%20Commands%20Ideas.029.png)

### Diamond Pointing to Another Diamond

`<< interpretation issues >>`

When is a diamond executed multiple times?

A diamond pointing to another diamond: it may be a call to a call. both diamonds may represent the same call. They might never execute individually.

### No Diamond Shapes

2021-04-20: These idea seem from before the diamond shape was introduced. Other clues may have been hoped to disambiguate the different programming constructs. A newer idea may use diamond shapes along with squares, and may suggest a more specific use of solid lines and dashed lines.

These issues seem to disappear with introducing the diamond for execution and having distinct call and reference lines: dashed vs. solid line styles.

#### Commands Might Only Be Called from Another Command

*Commands can only be called directly from another command.*

< Because a call executes its target when its container square is executed. Actually, relate all restrictions to the fact that commands execute. >

A command symbol might only have a call line if it’s directly inside another command. Usually the call line first exits the command that contains the call. In other words: a call line usually directly exits a square.

![](images/7.%20Commands%20Ideas.053.png)

Only when you call a nested command or an embedded command reference, the line doesn’t exit the command first:

*Call to nested command:*  
![](images/7.%20Commands%20Ideas.054.jpeg)

*Call an internal command reference:*  
![](images/7.%20Commands%20Ideas.055.jpeg)

#### Command Symbol Roles

A call line makes the square a call. A reference line makes it a reference. No line at all indicates that it’s a command definition or a nested command. Lines can also be left out for abstraction reasons.

| ![](images/7.%20Commands%20Ideas.067.png) | ![](images/Symbol%20Language%20(2004).409b.png) | ![](images/7.%20Commands%20Ideas.068.png) | ![](images/7.%20Commands%20Ideas.069.png) <br> ![](images/7.%20Commands%20Ideas.070.png) | ![](images/7.%20Commands%20Ideas.071.png) |
|:----------:|:--------------:|:----:|:---------:|:---:|
| Definition | Nested command | Call | Reference | Illegal: a square can’t be both a call and a reference |

< Not true: a call might not directly exit a square if it calls a command reference embedded in the same command or a nested command of the command. >

Note here that the access symbol of a solid command reference line is also drawn solid.

#### Reference and Call Targets

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

### Without Dashed Lines

A command symbol can define its own command:

![](images/7.%20Commands%20Ideas.064.png)

But if it has a reference line it is regarded no more than a reference or call to a command. The target of the line is considered the command itself or the *definition* of the command.

*A is the reference, B is the definition:*  
![](images/7.%20Commands%20Ideas.065.jpeg)

*A is the command reference, B is the definition:*  
![](images/7.%20Commands%20Ideas.066.jpeg)

### Loose Ideas

`<< terminology >>`

It’s *commands* that are called. When you speak of calling an *object*, you’re talking about calling a command of an object (or a command of one of its sub objects).`

-----

`<< terminology >>`

Here I introduce basic terms in the area of executions and parameters. Here’s a quick reference list.

- Reference
- Call
- Definition
- Nested command
- Active
- Inactive
- Active nested command
- Inactive nested command
- Deeper nested command
- Sub command 
- Parameter
- Argument
- Executor
- Execution

-----

`<< terminology >>`

- Basic Terms
    - reference
    - call
    - definition
    - nested command
    - active nested command
    - inactive nested command
    - deeper nested command
    - sub command 
    - Definitions of the terms parameter and argument
    - < Which precisely? >
    - ...

-----

`<< terminology >>`

A command symbol might have one of four roles:

- definition
- call
- reference
- nested command

-----

`<< about other technology >>`

Differences with Com with returning object references.

-----

`<< interpretation >>`

- Executions & parameters: Inside directly accessible, outside only 'indirectly' accessible (if line set FOR you)

-----

`<< detail >>`

Alternative to command with return value: an object with a getter:  
A command might possibly not get its own symbol anyway. It might just be an object with an execution point.