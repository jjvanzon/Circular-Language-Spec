Construct Drafts | From Spec | Commands Terminology
===================================================

`[ Deprecated documentation ]`

__Contents__

- [Introduction](#introduction)
- [Sub-Commands Terminology (1)](#sub-commands-terminology-1)
- [Sub Command Terminology (2)](#sub-command-terminology-2)
- [Active and Inactive Terminology](#active-and-inactive-terminology)
- [Nested Commands Terminology](#nested-commands-terminology)
- [Loose Ideas about Terminology](#loose-ideas-about-terminology)
- [Synonyms](#synonyms)
    - [Command Definition Synonyms](#command-definition-synonyms)
    - [Definition Line Synonyms](#definition-line-synonyms)
    - [Executable Command Synonyms](#executable-command-synonyms)
    - [Command Call Synonyms](#command-call-synonyms)
    - [Command Reference Synonyms](#command-reference-synonyms)

## Introduction

The Circular Language Spec itself might be more about *notation* and *meaning*, rather than specific terminology. Therefor, terminology quibbles in the area of commands, might be moved here instead.

## Sub-Commands Terminology (1)

Sub-commands `are` active commands `contained` inside a parent command. `You can` encounter them inside `any` command symbol: both active and inactive commands symbols `can` contain sub-commands. `The` sub-commands `are` *active* commands: command calls, active nested commands or active command references.

Below `is` a picture of two sub-commands inside an inactive command:

![](images/1.%20Commands%20Main%20Concepts.048.png)

`The` __Parent Command__ `is` an inactive command, because it `is` a square. In `the` diagram above, `the` __Parent Command__ `contains` two sub-commands. `The` sub-commands `are` displayed as diamond shapes. One of `the` sub-commands `is` a call, because it `has` a dashed line `going` outside `the` __Parent Command__, `tying the` sub-command to its command definition. `The` other sub-command `is` an *active nested command*, because it `might not` redirect its command definition.

Below `is` a picture of two sub-commands inside an active command:

![](images/1.%20Commands%20Main%20Concepts.049.png)

It `is the same` picture as `the` other diagram, `only now the` __Parent Command__ `is` an executable command symbol, `not` an inactive command.

## Sub Command Terminology (2)

A sub command is any command symbol inside another command symbol.

![](images/7.%20Commands%20Ideas.035.png)

But sometimes it may only be the diamonds that are referred to as sub commands. That’s because the execution of a command is made up of the execution of it’s contained diamonds combined.

![](images/7.%20Commands%20Ideas.036.png)

## Active and Inactive Terminology

A diamond executes, a square might not. A diamond is said to be active, while a square is inactive.

## Nested Commands Terminology

A nested command is usually not called a definition.

## Loose Ideas about Terminology

It’s *commands* that are called. When you speak of calling an *object*, you’re talking about calling a command of an object (or a command of one of its sub objects).`

-----

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

A command symbol might have one of four roles:

- definition
- call
- reference
- nested command

-----

The terms executor and execution.


## Synonyms

The following terms may possibly be used interchangeably depending on context.

### Command Definition Synonyms

- prototype
- blue-print
- inactive command
- inactive command symbol
- square
- definition

### Definition Line Synonyms

- command definition line
- call line
- prototype line
- dashed line

### Executable Command Synonyms

- active command
- active command symbol
- diamond
- executable command symbol
- execution
- execution point

### Command Call Synonyms

- execution

### Command Reference Synonyms

- function pointer
- method reference
- delegate

[back](../../)