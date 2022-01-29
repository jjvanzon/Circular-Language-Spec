Construct Drafts | From Spec | No Diamond Shapes
================================================

`[ Deprecated documentation ]`

__Contents__

- [Introduction](#introduction)
- [Commands Might Only Be Called from Another Command](#commands-might-only-be-called-from-another-command)
- [Command Symbol Roles](#command-symbol-roles)
- [Reference and Call Targets](#reference-and-call-targets)

## Introduction

These ideas seem from before the diamond shape was introduced. Other clues may have been hoped to disambiguate the different programming constructs. A newer idea may use diamond shapes along with squares, and may suggest a more specific use of solid lines and dashed lines.

These issues seem to disappear with introducing the diamond for execution and having distinct call and reference lines: dashed vs. solid line styles.

## Commands Might Only Be Called from Another Command

*Commands can only be called directly from another command.*

< Because a call executes its target when its container square is executed. Actually, relate all restrictions to the fact that commands execute. >

A command symbol might only have a call line if it’s directly inside another command. Usually the call line first exits the command that contains the call. In other words: a call line usually directly exits a square.

![](images/7.%20Commands%20Ideas.053.png)

Only when you call a nested command or an embedded command reference, the line doesn’t exit the command first:

*Call to nested command:*  
![](images/7.%20Commands%20Ideas.054.jpeg)

*Call an internal command reference:*  
![](images/7.%20Commands%20Ideas.055.jpeg)

## Command Symbol Roles

A call line makes the square a call. A reference line makes it a reference. No line at all indicates that it’s a command definition or a nested command. Lines can also be left out for abstraction reasons.

| ![](images/7.%20Commands%20Ideas.067.png) | ![](images/Symbol%20Language%20(2004).409b.png) | ![](images/7.%20Commands%20Ideas.068.png) | ![](images/7.%20Commands%20Ideas.069.png) <br> ![](images/7.%20Commands%20Ideas.070.png) | ![](images/7.%20Commands%20Ideas.071.png) |
|:----------:|:--------------:|:----:|:---------:|:---:|
| Definition | Nested command | Call | Reference | Illegal: a square can’t be both a call and a reference |

< Not true: a call might not directly exit a square if it calls a command reference embedded in the same command or a nested command of the command. >

Note here that the access symbol of a solid command reference line is also drawn solid.

## Reference and Call Targets

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
