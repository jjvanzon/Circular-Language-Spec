﻿Commands | Creation Behavior of Commands
========================================

[back](./)

`[ Preliminary documentation ]`

__Contents__

- [Introduction](#introduction)
- [Creation Behavior of Calls](#creation-behavior-of-calls)
  - [Calls In A Parent Command](#calls-in-a-parent-command)
  - [Original Problem & Solution](#original-problem--solution)
  - [Problems Solved By Delayed Creation](#problems-solved-by-delayed-creation)
  - [Delayed Creation Of Private Contents Only Counts For Command Calls](#delayed-creation-of-private-contents-only-counts-for-command-calls)
  - [Are Parameter Connections Actually Assignments?](#are-parameter-connections-actually-assignments)
- [Creation Behavior of Nested Commands](#creation-behavior-of-nested-commands)
- [Creation Behavior of ‘Inactive Calls’](#creation-behavior-of-inactive-calls)
- [No Overhead of Command Creation](#no-overhead-of-command-creation)
- [No Circular Command Creation](#no-circular-command-creation)
- [No Private Contents in a Call in a Definition](#no-private-contents-in-a-call-in-a-definition)
- [A Call in a Call Shows Private Contents When Running](#a-call-in-a-call-shows-private-contents-when-running)
- [Active Command in Inactive Command](#active-command-in-inactive-command)

## Introduction

Notation for commands may differ from that of objects, mainly by usage of different shapes. The similarity in notations may lead to questions like: "Are commands just like objects? In what way might they be different?"

This article tries to explore one way commands may be different from objects, suggesting they might have special *creation behavior*, that normal objects might not.

## Creation Behavior of Calls

A call can be present inside an object or inside another command. When a call is created, at first it might be sort of asleep. That might be when there is a chance to set its parameters. Before a command call is run, the command call’s public contents are there: its parameters. Those parameters are copied out of the call’s definition. The private contents are not there yet. A command’s private contents include private objects, nested commands and command calls. The private contents might be shown as a copy out of the command definition, only just before the command call runs. The public contents of a command call are added when the command object is created. The private contents of a command call are only added when its about to run. So the general rule seems to be: creation of private contents of a command call is delayed until just before a command call is run.

The reasons for the delay of creation of private contents are explained later. First, the steps of a command call’s creation are laid out one by one.

- Before a command is running, it is in the current state:

    - Command is created

      <img src="images/3.%20Creation%20Behavior%20Of%20Commands.001.png" width="300" />

    - Parameters / public contents are present

      <img src="images/3.%20Creation%20Behavior%20Of%20Commands.002.png" width="300" />

    - Private contents are *not* created  
      (private objects, nested commands and command calls)

      <img src="images/3.%20Creation%20Behavior%20Of%20Commands.003.png" width="300" />

    - __Reference__ and __Object Out__ parameters are already assigned

      <img src="images/3.%20Creation%20Behavior%20Of%20Commands.004.png" width="300" />

    - __Value__ parameter assignments refer to their sources and targets

      <img src="images/3.%20Creation%20Behavior%20Of%20Commands.005.png" width="300" />

- Right before a command executes:

    - __Value In__ parameter assignments are executed

      <img src="images/3.%20Creation%20Behavior%20Of%20Commands.006.png" width="300" />

    - Private contents are created  
      (private objects, nested commands and command calls)  
      (shown as a copy from the command’s definition)
      (The definition of the parent command is not shown in the diagram.)

      <img src="images/3.%20Creation%20Behavior%20Of%20Commands.007.png" width="300" />

    - *Sub*-commands’ parameters / public contents are created  
      (shown as a copy from the sub-command’s definition)  
      (The contents of the definition of the sub-command are not shown in the diagram.)

      <img src="images/3.%20Creation%20Behavior%20Of%20Commands.008.png" width="300" />

    - Mind, that the sub-command’s private contents are not created, which disincludes its private objects, command calls and nested commands.

      <img src="images/3.%20Creation%20Behavior%20Of%20Commands.009.png" width="300" />

    - *Sub*-commands’ __Reference__ and __Object Out__ parameters are assigned  
      (targets copied from the parent command’s definition)  
      (The definition of the parent command is not shown in the diagram.)

      <img src="images/3.%20Creation%20Behavior%20Of%20Commands.010.png" width="300" />

    - Sub-commands’ __Value__ parameter assignments refer to their sources and targets  
      (copied from the parent command’s definition)

      <img src="images/3.%20Creation%20Behavior%20Of%20Commands.011.png" width="300" />

- After that the command call might be run:

  <img src="images/3.%20Creation%20Behavior%20Of%20Commands.012.png" width="300" />

  If the parent command runs, it might automatically execute all the sub-commands inside it one by one, following the same procedure of call creation.  
  The sub-command’s public content needed to be created in order to instantiate the parameter passings, part of the parent command.

- After a command call has finished:

  <img src="images/3.%20Creation%20Behavior%20Of%20Commands.013.png" width="300" />

    - __Value Out__ parameter assignments are executed

      <img src="images/3.%20Creation%20Behavior%20Of%20Commands.014.png" width="300" />

    - Private contents are released  
      (private objects, nested commands and command calls)

      <img src="images/3.%20Creation%20Behavior%20Of%20Commands.015.png" width="300" />

### Calls In A Parent Command

A parent command, that executes, automatically executes its sub-command-calls one by one. This means, that when a parent command is about to run, the sub-command-calls are created with *public* contents only. A sub-command-call’s *private* contents are created just before a sub-command-call is run. After a sub-command-call has run, the private contents are released, but its public contents remain. Sub-command-calls are the parent command’s private contents, so after the parent command is done, the sub-command-calls with their public contents are released. Because the parent command has a sole reference to its sub-command-call, releasing the sub-command-call means, that the sub-command-call is destroyed. But the parameter objects of the sub-command could still keep existing if they are still referenced in other places.

### Original Problem & Solution

This was the original problem:  
When a sub-command might only be created just before it is run, there is a problem: if a sub-command is created only just before it is run, when can a parent command fill in the parameters of the *not yet created* sub-command? Parameter passings could not reference the sub-command’s parameters. That’s why before running the parent command, the sub-commands need to be created.  
But when creating the sub-command even before it is  run, there is another problem: if sub-commands need to be created when their parent is created, the sub-commands of sub-commands might also need to be created, and their sub-commands and so on. So the whole call structure might be created before the parent command could even run. This could even have resulted in circularities, that might make the system hang.

The solution was, to create a call before it is run, but only the public contents, so that a parent can set the parameters. But the private contents are only created just before the command is run, which creates its sub-commands, but again only its parameters. This prevents recursive creation of the call structure, and gives command creation a neat and steady pulse. So this all makes it doable. Otherwise there could have been an endless recursive creation procedure, before any command could ever run.

### Problems Solved By Delayed Creation

The creation behavior of command calls also solves *when* and *when not* to display a command’s private contents.

The problems solved by delayed creation of a command’s private contents are covered in separate articles:

- *No Overhead of Command Creation*
- *No Circular Command Creation*
- *No Private Contents in Calls in Definitions*
- *Calls in Calls Show Private Contents When Running*

### Delayed Creation Of Private Contents Only Counts For Command Calls

Delayed creation of private contents only counts for command calls. Command calls redirect their definition.

But if a command object might not have a definition, then it defines its own definition. For command objects that define their own definition, private contents might be created all the time, because nothing else defines its private contents but the object itself. This counts for command definitions. This also counts for *active* command definitions, which are executable object that define their own definition. But it also counts for nested commands. See the section *Creation Behavior of Nested commands*.

### Are Parameter Connections Actually Assignments?

It may be a bit of an open end whether the lines connected to parameters are connections, or that they are cloaked assignment calls. Or perhaps that connections for parameters might simply behave a bit like assignment calls. It might also be that value connections with direction might be interpreted as assignment calls altogether. Perhaps at some point in the creation process they show as assignments and other times as connections. There might not be any right answers, it is just a set of options that might be chosen or not.

## Creation Behavior of Nested Commands

The section *Creation Behavior of Calls* talked about delaying the creation of a call’s private contents, until the command is about to be run, while the public contents of a command call are there straight away, as soon as the command call is created.

But if a command object might not have a definition, then it defines its own definition. For command objects that define their own definition, private contents *are* created all the time, because nothing else defines its private contents but the object itself.

This also counts for nested commands.

Nested commands are like command definitions inside another command. 

A nested command might always be created as long as the parent command is created. 

Even when a nested command is an execution, it is also like a command definition. Command definitions might be created permanently, so nested commands might be created permanently too, as well as nested commands inside other nested commands. Active nested commands have added behavior compared to other sub-commands (command calls). They are like command definitions inside another command. An active nested command’s private data is already created. Even when the nested command structure inside a command is very deep, the *whole* depth of the nested command structure is recursively created when the parent command is created. The nested command structure can not have circularities and is always a limited tree structure, so that the process of creating the whole nested command structure can never hang or anything like that.

Other active sub-commands (for instance command calls) behave differently. A command calls’ *private* data is not created until the command is actually run.

Just like other commands, that do not have a definition, a nested command’s contents are created all the time, including its private contents.

Nested commands being permanently created as long as the parent command is created even counts for nested commands inside a command call. Right before a call is executed, its private contents are created, including the whole depth of its nested commands.

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.016.png" width="300" />

In theory the definition of the nested command could be pointing to the nested commands inside the command call’s definition. The private contents of the nested command could be created only just before the nested command is run. But this is not done. As soon as a nested command in a command call is copied from the definition, the nested command has no connection anymore to the nested command in the definition. Therefore, it needs to define its own private contents.

Note, that though everything of the nested commands is created, parameters of an active nested command are only *assigned* right before the nested command is run.

Even when the nested command structure inside a command is very deep, the *whole* depth of the nested command structure is recursively created when the parent command is created.

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.017.png" width="400" />

The sub-call inside the big call and inside the big definition only have the public parameter created, not their private contents as neither of them is running. But the nested command, with all its contents, are created inside the big call all anyway.

## Creation Behavior of ‘Inactive Calls’

Command calls inside a parent command have special creation behavior:

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.018.png" width="200" />

Their publics are created as soon as the parent command is created

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.019.png" width="200" />

but their private contents are only created when the command call is about to be run.

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.020.png" width="200" />

There is also the *inactive* form of a command call inside a parent command.

Special creation behavior might *not* count for inactive command objects inside a parent command, that have a class redirection to a command definition.

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.021.png" width="200" />

This looks like the inactive form of a command call, but this kind of object might not have special creation behavior like that. It is an uncommon situation. But an inactive command inside a parent command with a class reference to a definition *can* be referenced

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.022.png" width="300" />

Unlike its active form, which can not be referenced.

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.023.png" width="300" />

Therefore, it can also be *class* referenced by a call. In that case its private and public contents had better be there more permanently, or the *call* to it can not instantiate private contents at all.

Creating its private contents, might not create a recursive creation or anything: the inactive call’s own private calls do not create *their* private contents, so there is no recursion there.

Therefore, it can also be *class* referenced by a call.

![](images/3.%20Creation%20Behavior%20Of%20Commands.024.png)

In that case its private and public contents had better be there more permanently, or the *call* to it can not instantiate private contents at all.

![](images/3.%20Creation%20Behavior%20Of%20Commands.025.png)

Creating its private contents, might not create a recursive creation or anything: the inactive call’s own private calls do not create *their* private contents, so there is no recursion there.

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.026.png" width="300" />

## No Overhead of Command Creation

One of the reasons why private contents of a call are only created just before the call is run, is because this prevents overhead of creation. If you might create the whole call structure when the great grandparent of commands is created, then this is not only a lot of work in one blow, but also, a lot of command call objects are created, that never get to run in the first place, because it only runs under certain conditions. Delayed creation of the private contents of a command call prevents this overhead of command creation and creates a neat and steady rate of command creation.

## No Circular Command Creation

Another reason why private contents of a call are only created just before the call is run, is because this prevents circular creation of commands. Some command may call another command and that command may call the first one again. Command calls are usually private, so if you might create all possible command calls, you end up creating an endless recurrence of command creations

![](images/3.%20Creation%20Behavior%20Of%20Commands.027.png)

while in reality, the recurrence might be broken by some conditional execution of one of the command calls. Creating private contents of command calls prevents this circular creation and only creates a command object when it might actually run.

## No Private Contents in a Call in a Definition

A definition is always dormant, and never runs. So also the *calls* inside a definition might never run.

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.028.png" width="200" />

Therefore, the private contents of calls inside a definition are *never* created.

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.029.png" width="200" />

A call in a definition never shows the call’s private contents. The call at most shows its parameters, so the public contents of the command call.

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.030.png" width="200" />

Only the *definition* of the called command might show private contents.

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.031.png" width="200" />

So you might hop to the definition of a call to see the private contents of the command.

Not creating a call’s private contents before it even runs, takes away discussion about when to display and when not to display a command’s private contents.

Bear in mind, that when an executable object might not redirect its definition, it has to define its own private contents, because nothing else defines its private contents but he himself.

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.032.png" width="200" />

But *calls inside* such a definition, only have their *public* contents are created again.

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.033.png" width="360" />

## A Call in a Call Shows Private Contents When Running

A call inside another call only contains its private content when it is actually running.

If a call is not running:

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.034.png" width="200" />

Then you might hop to the definition of a call to see the private contents of the command.

When a call is running, you do see its private contents:

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.035.png" width="200" />

Not creating a call’s private contents before it even runs, takes away discussion about when to display and when not to display a command’s private contents.

## Active Command in Inactive Command

A nested command in a nested command only ever runs when its top parent command is an active command object. If the top parent command is an inactive command object, for instance a command definition, then even an *active* nested command in it is dormant.

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.036.png" width="300" />

The nested command might only ever run in a *call* to the definition, but then it is a copy of the definition’s nested command:

<img src="images/3.%20Creation%20Behavior%20Of%20Commands.037.png" width="380" />

An executable command inside a command definition can not be run, because its parent is dormant, and an executable sub-command can not be referenced from elsewhere either.