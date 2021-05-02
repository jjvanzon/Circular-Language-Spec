Circular Language Construct Drafts | From Spec
==============================================

Commands Construct Drafts
-------------------------

`[ Deprecated documentation ]`

__Contents__

- [Nested Commands](#nested-commands)
- [No Diamond Shapes](#no-diamond-shapes)
    - [Commands Might Only Be Called from Another Command](#commands-might-only-be-called-from-another-command)
    - [Command Symbol Roles](#command-symbol-roles)
    - [Reference and Call Targets](#reference-and-call-targets)
- [No Dashed Lines for Commands](#no-dashed-lines-for-commands)
- [Loose Ideas](#loose-ideas)

### Nested Commands

`<< nice formulation >>`  

A nested command also executes, when its parent command executes,

`<< details >>`

but it doesn’t execute, unless you call it.

![](images/7.%20Commands%20Ideas.022.jpeg)

`<< details >>`

The nested command might be directly contained by a command. So this is not a nested command:

![](images/7.%20Commands%20Ideas.029.png)

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

### No Dashed Lines for Commands

A command symbol can define its own command:

![](images/7.%20Commands%20Ideas.064.png)

But if it has a reference line it is regarded no more than a reference or call to a command. The target of the line is considered the command itself or the *definition* of the command.

*A is the reference, B is the definition:*  
![](images/7.%20Commands%20Ideas.065.jpeg)

*A is the command reference, B is the definition:*  
![](images/7.%20Commands%20Ideas.066.jpeg)

### Loose Ideas

`<< about other technology >>`

Differences with Com with returning object references.

-----

`<< interpretation >>`

- Executions & parameters: Inside directly accessible, outside only 'indirectly' accessible (if line set FOR you)

-----

`<< detail >>`

Alternative to command with return value: an object with a getter: A command might possibly not get its own symbol anyway. It might just be an object with an execution point.