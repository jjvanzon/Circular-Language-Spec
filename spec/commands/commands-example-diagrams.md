﻿Commands | Example Diagrams
===========================

[back](./)

`[ Preliminary documentation ]`

__Contents__

- [Introduction](#introduction)
- [Command Calls in a Command Definition](#command-calls-in-a-command-definition)
- [Command Calls in a Command Call](#command-calls-in-a-command-call)
- [Command Calls in a Command Reference](#command-calls-in-a-command-reference)
- [Parameters in a Command Definition](#parameters-in-a-command-definition)
- [Parameters in a Command Call](#parameters-in-a-command-call)
- [Parameters in a Command Reference](#parameters-in-a-command-reference)
- [Local variables in a Command Definition](#local-variables-in-a-command-definition)
- [Local Variables in a Command Call](#local-variables-in-a-command-call)
- [Local variables in a Command Reference](#local-variables-in-a-command-reference)
- [Command References in a Command Definition](#command-references-in-a-command-definition)
- [Command References in a Command Call](#command-references-in-a-command-call)
- [Command References in a Command Reference](#command-references-in-a-command-reference)
- [Nested Commands in Nested Commands](#nested-commands-in-nested-commands)
- [Inactive Nested Commands in a Command Definition](#inactive-nested-commands-in-a-command-definition)
- [Inactive Nested Commands in a Command Call](#inactive-nested-commands-in-a-command-call)
- [Inactive Nested Commands in a Command Reference](#inactive-nested-commands-in-a-command-reference)
- [Active Nested Commands in a Command Definition](#active-nested-commands-in-a-command-definition)
- [Active Nested Commands in a Command Call](#active-nested-commands-in-a-command-call)
- [Active Nested Commands in a Command Reference](#active-nested-commands-in-a-command-reference)
- [Command Calls in an Inactive Nested Command](#command-calls-in-an-inactive-nested-command)
- [Command Calls in an Active Nested Command](#command-calls-in-an-active-nested-command)
- [Parameters in an Inactive Nested Command](#parameters-in-an-inactive-nested-command)
- [Parameters in an Active Nested Command](#parameters-in-an-active-nested-command)
- [Local Variables in an Inactive Nested Command](#local-variables-in-an-inactive-nested-command)
- [Local variables in an Active Nested Command](#local-variables-in-an-active-nested-command)
- [Command References in an Inactive Nested Command](#command-references-in-an-inactive-nested-command)
- [Command References in an Active Nested Command](#command-references-in-an-active-nested-command)
- [Reference to Sibling Inactive Nested Command](#reference-to-sibling-inactive-nested-command)
- [Reference to Sibling Active Nested Command](#reference-to-sibling-active-nested-command)
- [Call to Sibling Inactive Nested Command](#call-to-sibling-inactive-nested-command)

## Introduction

This article tries to systematically demonstrate different situations of commands.

Relationships between the following concepts may be demonstrated. It is containment relationships between these constructs, that might be explored. This may enrich an impression of commands in Circular.

| | | |
|--------------------|-|------------------------------------------------------------------------------|
| __Command definition__ | <img src="images/command-definition.png" width="100" /> | Does not execute directly but may get called. |
| __Command call__ | <img src="images/command-call.png" width="100" /> | Executes a command definition it points out. |
| __Command reference__ | <img src="images/command-reference.png" width="120" /> | Pointer to another command. |
| __Active nested command__ | <img src="images/active-nested-command.png" width="80" /> | Command defined inside another command, that may execute. |
| __Inactive nested command__ | <img src="images/inactive-nested-command.png" width="80" /> | Command defined inside another command, that might not be executed directly. |
| __Parameter__ | <img src="images/parameter.png" width="100" /> | Instruction passed to a command, that makes it behave differently. |
| __Local variable__ | <img src="images/local-variable.png" width="100" /> | Helper variables inside a command, invisible from the outside. |

## Command Calls in a Command Definition

![](images/5.%20Commands%20Example%20Diagrams.001.png)

The large square is the parent command definition. The diamonds inside the parent command are two command calls. The diamonds are connected to squares with dashed lines. This makes those squares the command calls’ command definitions.

## Command Calls in a Command Call

![](images/5.%20Commands%20Example%20Diagrams.002.png)

The bigger diamond is a command call, because it is tied to its definition, the larger square, with a dashed line, a class line. The smaller diamonds inside the larger diamonds are command calls inside a command call. The smaller diamonds also point out their definitions, the smaller squares, with a dashed line, a class line.

## Command Calls in a Command Reference

![](images/5.%20Commands%20Example%20Diagrams.003.png)

The square on the left is a command reference, because it points out its target definition, the square on the right, with a solid line, an object line. The command reference contains two command calls, displayed as diamonds. Those diamonds are calls, because they point out their definitions, the smaller squares at the bottom, with class lines, dashed lines. The square on the right could also have displayed the same calls, because both larger squares represent the same command object, that have the same contents.

The command reference and its target could also be replaced with a diamond arbitrarily, which make the command reference or target command executable.

## Parameters in a Command Definition

The diagram below displays an inactive command definition with parameters:

![](images/5.%20Commands%20Example%20Diagrams.004.png)

The square is a command definition. The circles inside of it are the parameters. The rest of what’s visible in the diagram are the parameter passings. Parameter passings are explained in the *parameter* articles. The parameter passings are the lines connected to the circles, that are marked with an access mark.

## Parameters in a Command Call

![](images/5.%20Commands%20Example%20Diagrams.005.png)

The diamond shape is a command call. What makes it a command call, is that it is tied to its command definition, the square, with a class line, the dashed line. The circles inside the diamond are the parameters. The parameters are tied to objects on the outside with parameter passings. The parameter passings are the lines connecting the smaller circles inside the diamond, the parameters, to the larger circles outside the diamond. Parameter passings are explained later in the *parameter* articles.

## Parameters in a Command Reference

![](images/5.%20Commands%20Example%20Diagrams.006.png)

The larger square on the left is a command reference. It is tied to its reference target, the square on the right, with an object line, which is a solid line. The circles inside the square on the left are the parameters of the command reference. The lines tied to those are the parameter passing types. The parameter passings are the lines connected to the circles, that are marked with an access mark. The square on the right could have had the same contents as the square on the left, because both command reference and command definition represent the same command definition.

Either of the squares could have been replaced by a diamond, making the command symbol executable, rather than dormant.

## Local variables in a Command Definition

![](images/5.%20Commands%20Example%20Diagrams.007.png)

The square is a command definition. The circles inside of it are local variables. In diagram above the fact that they are private is displayed with the object line and the cross it ends with indicating, that you can not reference these objects from the outside.

The following picture is another possible expression of the variables:

![](images/5.%20Commands%20Example%20Diagrams.008.png)

Because public object, parameters, always come with an indication of the parameter passing, you may not need to express the objects’ being private, because it might be obvious: if they do not have a parameter passing, then they are private.

## Local Variables in a Command Call

![](images/5.%20Commands%20Example%20Diagrams.009.png)

The diamond is a command call. Its definition is indicated with the dashed line connecting it to the square, which is the definition. The circles inside the diamond are the local variables of the command call. The fact, that they are private is displayed with the object line and the cross it ends with indicating, that you can not reference these objects from the outside.

Another possible expression of the local variables is the following:

![](images/5.%20Commands%20Example%20Diagrams.010.png)

Because public object, parameters, always come with an indication of the parameter passing, you may not need to express the objects’ being private, because it might be obvious: if they do not have a parameter passing, then they are private.

## Local variables in a Command Reference

![](images/5.%20Commands%20Example%20Diagrams.011.png)

The square on the left is a command reference. Its target definition is indicated with a solid line, which is an object, pointing at the square on the right, which is the target definition. The circles inside the square on the left are the local variables of the command call. The fact, that they are private is displayed with the object line and the cross it ends with indicating, that you can not reference these objects from the outside.

Another possible expression of the local variables is the following:

![](images/5.%20Commands%20Example%20Diagrams.012.png)

Because public object, parameters, always come with an indication of the parameter passing, you may not need to express the objects’ being private, because it might be obvious: if they do not have a parameter passing, then they are private.

Either of the square could have been replaced by a diamond, making the command symbol executable, rather than dormant.

## Command References in a Command Definition

![](images/5.%20Commands%20Example%20Diagrams.013.png)

The larger square is a command definition. The smaller square inside them are command references in a command definition. They are actually *public* command references. This makes the command references *parameters* of the command definition. The command references have object lines, solid ones, going outside, ending at an access mark. Those object lines are indications of parameter passing, indicating that the command references are so called Reference parameters. Parameter passings are explained in the *parameter* articles.

## Command References in a Command Call

![](images/5.%20Commands%20Example%20Diagrams.014.png)

The diamond is a command call. The command call’s definition is indicated with the dashed line, pointing to the square on the right, which is the command definition. The smaller squares inside the call are command references in a command call. They are actually *public* command references. This makes the command references *parameters* of the command call. The command references have object lines, solid ones, going outside, ending at the targets of the command references.

## Command References in a Command Reference

![](images/5.%20Commands%20Example%20Diagrams.015.png)

The larger square on the left is a command reference. The target of the command reference is the square on the right, a command definition. The larger square on the left, contains again two command references, smaller squares, that are connected to their reference targets on the outside of the larger command reference.

Most of the squares could have been replaced by diamond shapes, making the command symbol executable, rather than dormant. But the smaller squares inside the larger square can not be replaced by diamonds, because a command can not contain active command references, for reasons explained by the article *Parent Controls Its Sub-Executions*.

## Nested Commands in Nested Commands

Because nested commands are always part of a parent command, the parent command is displayed in the pictures below as the outer square. Inside the square is a nested command, and inside that symbol are two nested commands in a nested command. Inactive nested commands are squares. Active nested commands are diamonds.

Inactive nested commands in an inactive nested command in a command definition:

![](images/5.%20Commands%20Example%20Diagrams.016.png)

Active nested commands in an inactive nested command in a command definition:

![](images/5.%20Commands%20Example%20Diagrams.017.png)

Inactive nested commands in an active nested command in a command definition:

![](images/5.%20Commands%20Example%20Diagrams.018.png)

Active nested commands in an active nested command in a command definition:

![](images/5.%20Commands%20Example%20Diagrams.019.png)

## Inactive Nested Commands in a Command Definition

![](images/5.%20Commands%20Example%20Diagrams.020.png)

The larger square is a command definition. The smaller squares inside the larger square are inactive nested commands inside a command definition. Squares inside a square, that do not redirect, are inactive nested commands.

## Inactive Nested Commands in a Command Call

![](images/5.%20Commands%20Example%20Diagrams.021.png)

The diamond shape is a command call. The command definition of the command call is pointed out by the dashed line, pointing at the square on the right, which is the command definition. The diamond contains two squares, that do not redirect. Those are the inactive nested commands inside the command call. They are nested commands, because they are situated inside a command symbol and they do not redirect their target.

## Inactive Nested Commands in a Command Reference

![](images/5.%20Commands%20Example%20Diagrams.022.png)

The large square on the left is a command reference. It is pointing out its target command definition with an object line, the solid line, targeting the square on the right, which is the command definition. The command reference on the left contains two inactive nested commands, smaller squares, that do not redirect their target. The target definition on the right also shows the smaller squares inside of it. Both command reference and target definition both represent the same command object, so their contents are also the same, so they both show inactive nested commands.

Either of the larger squares could have been replaced by a diamond, making the command symbol executable, rather than dormant.

## Active Nested Commands in a Command Definition

![](images/5.%20Commands%20Example%20Diagrams.023.png)

The square is a command definition. The diamond shapes squares inside the square are active nested commands inside a command definition. Diamonds inside a square, that do not redirect, are active nested commands.

## Active Nested Commands in a Command Call

![](images/5.%20Commands%20Example%20Diagrams.024.png)

The diamond shape is a command call. The command definition of the command call is pointed out by the dashed line, pointing at the square, which is the command definition. The diamond contains two diamond shapes, that do not redirect. Those are the active nested commands inside the command call. They are nested commands, because they are situated inside a command symbol and they do not redirect their target.

## Active Nested Commands in a Command Reference

![](images/5.%20Commands%20Example%20Diagrams.025.png)

The large square on the left is a command reference. It is pointing out its target command definition with an object line, the solid line, targeting the square on the right, which is the command definition. The command reference on the left contains two active nested commands, diamonds, that do not redirect their target. The target definition on the right also shows the diamonds inside of it. Both command reference and target definition both represent the same command object, so their contents are also the same, so they both show active nested commands.

Either of the squares could have been replaced by a diamond, making the command symbol executable, rather than dormant.

## Command Calls in an Inactive Nested Command

![](images/5.%20Commands%20Example%20Diagrams.026.png)

The large square is the command definition the nested command is in. The square inside of it, is the inactive nested command. It contains two diamonds, which are the command calls inside the inactive nested command. The diamonds redirect their command definition with a class line, a dashed line, connected to the squares on the right, which are the command definitions, that are called.

## Command Calls in an Active Nested Command

![](images/5.%20Commands%20Example%20Diagrams.027.png)

The large square is the command definition the nested command is in. The diamond inside of it, is the active nested command. It contains two diamonds, which are the command calls inside the active nested command. The small diamonds redirect their command definition with a class line, a dashed line, connected to the squares on the right, which are the command definitions, that are called.

## Parameters in an Inactive Nested Command

![](images/5.%20Commands%20Example%20Diagrams.028.png)

The large square is a command definition the inactive nested command is in. The square inside the square is the inactive nested command. The inactive nested command contains three circles, which are the parameters in the nested command. The lines connected to the circles, which are also dissected by an access mark, are the parameter passings. Parameter passings are explained in the *parameter* articles.

## Parameters in an Active Nested Command

![](images/5.%20Commands%20Example%20Diagrams.029.png)

The large square is a command definition the inactive nested command is in. The diamond inside the square is the active nested command. The diamond contains three circles, which are the parameters in the nested command. The circles inside the diamond are connected to the circles outside the diamond with parameter passings. Parameter passings are explained in the *Parameters* articles.

## Local Variables in an Inactive Nested Command

![](images/5.%20Commands%20Example%20Diagrams.030.png)

The large square is a command definition, the nested command is in. The square inside the larger square is the inactive nested command. It contains two circles, which are the local variables of the inactive nested command. The lines that go outside, that end at a cross are the indications that the objects are private. They indicate you can not reference the circles from the outside. 

Another possible expression of the local variables is the following:

![](images/5.%20Commands%20Example%20Diagrams.031.png)

Because public object, parameters, always come with an indication of the parameter passing, you may not need to express the objects’ being private, because it might be obvious: if they do not have a parameter passing, then they are private.

## Local variables in an Active Nested Command

![](images/5.%20Commands%20Example%20Diagrams.032.png)

The large square is a command definition, the nested command is in. The diamond inside the square is the active nested command. It contains two circles, which are the local variables of the active nested command. The lines that go outside, that end at a cross are the indications that the objects are private. They indicate you can not reference the circles from the outside.

Another possible expression of the local variables is the following:

![](images/5.%20Commands%20Example%20Diagrams.033.png)

Because public object, parameters, always come with an indication of the parameter passing, you may not need to express the objects’ being private, because it might be obvious: if they do not have a parameter passing, then they are private.

## Command References in an Inactive Nested Command

![](images/5.%20Commands%20Example%20Diagrams.034.png)

The large square is a command definition, the inactive nested command is in. The square inside the large square is the nested command. The inactive nested command contains two squares, which are the command references. They are actually *public* command references. This makes the command references parameters of the inactive nested command. The command references have object lines, solid ones, going outside, ending at an access mark. Those object lines are indications of parameter passing, indicating that the command references are so called Reference parameters. Parameter passings are explained in the *Parameters* articles. The parameters are not filled in, because an inactive nested command is a dormant command definition. Only in a call to the dormant command definitions, the parameters are filled in.

## Command References in an Active Nested Command

![](images/5.%20Commands%20Example%20Diagrams.035.png)

The large square is the command definition, that the active nested command is in. The diamond is the active nested command. The smaller squares inside the diamond are command references in an active nested command. They are actually *public* command references. This makes the command references parameters of the active nested command. The command references have object lines, solid ones, going outside, ending at the targets of the command references.

## Reference to Sibling Inactive Nested Command

![](images/7.%20Commands%20Ideas.077.jpeg)

## Reference to Sibling Active Nested Command

![](images/7.%20Commands%20Ideas.078.jpeg)

## Call to Sibling Inactive Nested Command

![](images/7.%20Commands%20Ideas.079.jpeg)

This might be like a jump to a nested command, that might otherwise not execute.