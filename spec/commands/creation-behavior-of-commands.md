Encircle Language Spec | Commands
=================================

Creation Behavior of Commands
-----------------------------

`[ Preliminary documentation ]`

__Contents__

- [Creation Behavior of Calls](#creation-behavior-of-calls)
  - [Calls In A Parent Command](#calls-in-a-parent-command)
  - [Original Problem & Solution](#original-problem--solution)
  - [Problems Solved By Delayed Creation](#problems-solved-by-delayed-creation)
  - [Delayed Creation Of Private Contents Only Counts For Command Calls](#delayed-creation-of-private-contents-only-counts-for-command-calls)
  - [Diagram Notation](#diagram-notation)
- [Creation Behavior of Clauses](#creation-behavior-of-clauses)
  - [Diagram](#diagram)
- [Creation Behavior of ‘Inactive Calls’](#creation-behavior-of-inactive-calls)
  - [Diagram](#diagram-1)
- [No Overhead of Command Creation](#no-overhead-of-command-creation)
- [No Circular Command Creation](#no-circular-command-creation)
  - [Diagram](#diagram-2)
- [No Private Contents in a Call in a Definition](#no-private-contents-in-a-call-in-a-definition)
  - [Diagram](#diagram-3)
- [A Call in a Call Shows Privates When Running](#a-call-in-a-call-shows-privates-when-running)
  - [Diagram](#diagram-4)
- [Active Command in Inactive Command](#active-command-in-inactive-command)
  - [Diagram](#diagram-5)
- [Loose Ideas](#loose-ideas)
  - [From "Commands Main Concepts"](#from-commands-main-concepts)
    - [Command Call Behavior](#command-call-behavior)
    - [Clause Creation Behavior](#clause-creation-behavior)
    - [Sub-Commands](#sub-commands)
    - [Reading & Writing Parameters](#reading--writing-parameters)
    - [Execute Once](#execute-once)

### Creation Behavior of Calls

A call can be present inside an object or inside another command. When a call is created, it is not immediately run, so that you get a chance to set its parameters. Before a command call is run, the command call’s public contents are there: its parameters. Those parameters are copied out of the call’s definition. The private contents are not there yet. A command’s private contents include private objects, clauses and command calls. The private contents might be copied out of the command definition, only just before the command call runs. The public contents of a command call are added when the command object is created. The private contents of a command call are only added when its about to run. So the general rule is: creation of private contents of a command call is delayed until just before a command call is run.

The reasons for the delay of creation of private contents are explained later. First, the steps of a command call’s creation are laid out one by one.

Before a command is running, it is in the current state:

- Command is created
- Parameters / public contents are present
- Private contents are *not* created  
  (private objects, clauses and command calls)
- __Reference__ and __Object Out__ parameters are already assigned
- __Value__ parameter assignments refer to their sources and targets

Right before a command executes:

- __Value In__ parameter assignments are executed
- Private contents are created  
  (private objects, clauses and command calls)  
  (copied out of the command’s definition)
- *Sub*-commands’ parameters / public contents are created  
  (copied out of the sub-command’s definition)
- Mind, that the sub-command’s private contents are not created, which disincludes its private objects, command calls and clauses.
- *Sub*-commands’ __Reference__ and __Object Out__ parameters are assigned  
(targets copied from the parent command’s definition)
- Sub-commands’ __Value__ parameter assignments refer to their sources and targets  
(copied out of the parent command’s definition)

Then the command runs, which means it runs all its sub-commands one by one, following the same procedure of call creation.

After a command call has finished:

- __Value Out__ parameter assignments are executed
- Private contents are released  
  (private objects, clauses and command calls)

#### Calls In A Parent Command

A parent command, that executes, automatically executes its sub-command-calls one by one. This means, that when a parent command is about to run, the sub-command-calls are created with *public* contents only. A sub-command-call’s *private* contents are created just before a sub-command-call is run. After a sub-command-call has run, the private contents are released, but its public contents remain. Sub-command-calls are the parent command’s private contents, so after the parent command is done, the sub-command-calls with their public contents are released. Because the parent command has a sole reference to its sub-command-call, releasing the sub-command-call means, that the sub-command-call is destroyed. But the parameter objects of the sub-command could still keep existing if they are still referenced in other places.

#### Original Problem & Solution

This was the original problem:  
When a sub-command might only be created just before it is run, there is a problem: if a sub-command is created only just before it is run, when can a parent command fill in the parameters of the *not yet created* sub-command? Parameter passings could not reference the sub-command’s parameters. That’s why before running the parent command, the sub-commands need to be created.  
But when creating the sub-command even before it is  run, there is another problem: if sub-commands need to be created when their parent is created, the sub-commands of sub-commands might also need to be created, and their sub-commands and so on. So the whole call structure might be created before the parent command could even run. This could even have resulted in circularities, that might make the system hang.

The solution was, to create a call before it is run, but only the public contents, so that a parent can set the parameters. But the private contents are only created just before the command is run, which creates its sub-commands, but again only its parameters. This prevents recursive creation of the call structure, and gives command creation a neat and steady pulse. So this all makes it doable. Otherwise there could have been an endless recursive creation procedure, before any command could ever run.

#### Problems Solved By Delayed Creation

The creation behavior of command calls also solves *when* and *when not* to display a command’s private contents.

The problems solved by delayed creation of a command’s private contents are covered in separate articles:

- *No Overhead of Command Creation*
- *No Circular Command Creation*
- *No Private Contents in Calls in Definitions*
- *Calls in Calls Show Privates When Running*

#### Delayed Creation Of Private Contents Only Counts For Command Calls

Delayed creation of private contents only counts for command calls. Command calls redirect their definition.

But if a command object might not have a definition, then it defines its own definition. For command objects that define their own definition, private contents might be created all the time, because nothing else defines its private contents but the object itself. This counts for command definitions. This also counts for *active* command definitions, which are executable object that define their own definition. But it also counts for clauses. See the article *Creation Behavior of Clauses*.

#### Diagram Notation

The creation behavior of calls was already explained in the article *Creation Behavior Of Calls*. The current article demonstrates the concept in a diagram.

The steps of creation of a call are clarified with diagrams.

Before a command is running, it is in the current state:

- Command is created

    ![](images/3.%20Creation%20Behavior%20Of%20Commands.001.png)

- Parameters / public contents are present 

    ![](images/3.%20Creation%20Behavior%20Of%20Commands.002.png)

- Private contents are *not* created  
  (private objects, clauses and command calls)
  
    ![](images/3.%20Creation%20Behavior%20Of%20Commands.003.png)

- __Reference__ and __Object Out__ parameters are already assigned
  
    ![](images/3.%20Creation%20Behavior%20Of%20Commands.004.png)

- __Value__ parameter assignments refer to their sources and targets
  
    ![](images/3.%20Creation%20Behavior%20Of%20Commands.005.png)

Right before a command executes:

- __Value In__ parameter assignments are executed
  
    ![](images/3.%20Creation%20Behavior%20Of%20Commands.006.png)

- Private contents are created  
  (private objects, clauses and command calls)  
  (copied from the command’s definition)  
  (The definition of the parent command is not shown in the diagram.)

    ![](images/3.%20Creation%20Behavior%20Of%20Commands.007.png)

- *Sub*-commands’ parameters / public contents are created  
  (copied from the sub-command’s definition)  
  (The contents of the definition of the sub-command are not shown in the diagram.)

    ![](images/3.%20Creation%20Behavior%20Of%20Commands.008.png)

- Mind, that the sub-command’s private contents are not created, which includes its private objects, command calls and clauses.

    ![](images/3.%20Creation%20Behavior%20Of%20Commands.009.png)

- *Sub*-commands’ __Reference__ and __Object Out__ parameters are assigned  
  (targets copied from the parent command’s definition)  
  (The definition of the parent command is not shown in the diagram.)

    ![](images/3.%20Creation%20Behavior%20Of%20Commands.010.png)

- Sub-commands’ __Value__ parameter assignments refer to their sources and targets  
  (copied from the parent command’s definition)

    ![](images/3.%20Creation%20Behavior%20Of%20Commands.011.png)

- Then the command runs:

    ![](images/3.%20Creation%20Behavior%20Of%20Commands.012.png)

  which means it runs all its sub-commands one by one, following the same procedure. The sub-command’s public content needed to be created in order to instantiate the parameter passings, part of the parent command.

- After a command has finished:

    ![](images/3.%20Creation%20Behavior%20Of%20Commands.013.png)

- __Value Out__ parameter assignments are executed
  
    ![](images/3.%20Creation%20Behavior%20Of%20Commands.014.png)

- Private contents are released  
  (private objects, clauses and command calls)

    ![](images/3.%20Creation%20Behavior%20Of%20Commands.015.png)

### Creation Behavior of Clauses

The section *Creation Behavior of Calls* talked about delaying the creation of a call’s private contents, until the command is about to be run, while the public contents of a command call are there straight away, as soon as the command call is created.

But if a command object might not have a definition, then it defines its own definition. For command objects that define their own definition, private contents *are* created all the time, because nothing else defines its private contents but the object itself.

This also counts for clauses.

Clauses are like command definitions inside another command. 

Even when a clause is an execution, it is also a command definition. Command definitions are created permanently, so clauses are created permanently too, as well as clauses inside other clauses. Active clauses have added behavior compared to other sub-commands (command calls). They are like command definitions inside another command. An active clause’s private data is already created. Even when the clause structure inside a command is very deep, the *whole* depth of the clause structure is recursively created when the parent command is created. The clause structure can not have circularities and is always a limited tree structure, so that the process of creating the whole clause structure can never hang or anything like that.

Other active sub-commands (for instance command calls) behave differently. A command calls’ *private* data is not created until the command is actually run.

Clauses being permanently created as long as the parent command is created even counts for clauses inside a command call. Right before a call is executed, its private contents are created, including the whole depth of its clauses. In theory the definition of the clause could be pointing to the clauses inside the command call’s definition. The private contents of the clause could be created only just before the clause is run. But this is not done. As soon as a clause in a command call is copied from the definition, the clause has no connection anymore to the clause in the definition. Therefore, it needs to define its own private contents.

Note, that though everything of the clauses is created, parameters of an active clause are only *assigned* right before the clause is run.

#### Diagram

Just like other commands, that do not have a definition, a clause’s contents are created all the time, including its private contents.

Clauses being permanently created as long as the parent command is created even counts for clauses inside a command call. Right before a call is executed, its private contents are created, including the whole depth of its clauses.

![](images/3.%20Creation%20Behavior%20Of%20Commands.016.png)

In theory the definition of the clause could be pointing to the clause inside the command call’s definition. The private contents of the clause could be created only just before the clause is run. But this is not done. As soon as a clause in a command call is copied from the definition, the clause has no connection anymore to the clause in the definition. Therefore, it needs to define its own private contents.

Even when the clause structure inside a command is very deep, the *whole* depth of the clause structure is recursively created when the parent command is created.

![](images/3.%20Creation%20Behavior%20Of%20Commands.017.png)

The sub-call inside the big call and inside the big definition only have the public parameter created, not their private contents as neither of them is running. But the clause, with all its contents, are created inside the big call all anyway.

### Creation Behavior of ‘Inactive Calls’

Command calls inside a parent command have special creation behavior: their publics are created as soon as the parent command is created, but their privates are only created when the command call is about to be run.

There is also the *inactive* form of a command call inside a parent command.

Special creation behavior might *not* count for inactive command objects inside a parent command, that have a class redirection to a command definition. This looks like the inactive form of a command call, but this kind of object might not have special creation behavior like that. It is an uncommon situation. But an inactive command inside a parent command with a class reference to a definition *can* be referenced, unlike its active form. Therefore, it can also be *class* referenced by a call. In that case its privates and publics had better be there more permanently, or the *call* to it can not instantiate private contents at all.

Creating its private contents, might not create a recursive creation or anything: the inactive call’s own private calls do not create *their* private contents, so there is no recursion there.

#### Diagram

The article *Creation Behavior of ‘Inactive Calls’* already explained this behavior conceptually. The current article further clarifies the idea using diagrams.

Command calls inside a parent command have special creation behavior:

![](images/3.%20Creation%20Behavior%20Of%20Commands.018.png)

Their publics are created as soon as the parent command is created

![](images/3.%20Creation%20Behavior%20Of%20Commands.019.png)

but their privates are only created when the command call is about to be run.

![](images/3.%20Creation%20Behavior%20Of%20Commands.020.png)

Special creation behavior might *not* count for inactive command objects inside a parent command, that have a class redirection to a command definition.

![](images/3.%20Creation%20Behavior%20Of%20Commands.021.png)

This looks like the inactive form of a command call, but this kind of object might not have special creation behavior like that. It is an uncommon situation. But an inactive command inside a parent command with a class reference to a definition *can* be referenced

![](images/3.%20Creation%20Behavior%20Of%20Commands.022.png)

Unlike its active form, which can not be referenced.

![](images/3.%20Creation%20Behavior%20Of%20Commands.023.png)

Therefore, it can also be *class* referenced by a call.

![](images/3.%20Creation%20Behavior%20Of%20Commands.024.png)

In that case its privates and publics had better be there more permanently, or the *call* to it can not instantiate private contents at all.

![](images/3.%20Creation%20Behavior%20Of%20Commands.025.png)

Creating its private contents, might not create a recursive creation or anything: the inactive call’s own private calls do not create *their* private contents, so there is no recursion there.

![](images/3.%20Creation%20Behavior%20Of%20Commands.026.png)

### No Overhead of Command Creation

One of the reasons why private contents of a call are only created just before the call is run, is because this prevents overhead of creation. If you might create the whole call structure when the great grandparent of commands is created, then this is not only a lot of work in one blow, but also, a lot of command call objects are created, that never get to run in the first place, because it only runs under certain conditions. Delayed creation of the private contents of a command call prevents this overhead of procedure creation and creates a neat and steady rate of procedure creation.

### No Circular Command Creation

Another reason why private contents of a call are only created just before the call is run, is because this prevents circular creation of commands. Some command may call another command and that command may call the first one again. Command calls are usually private, so if you might create all possible command calls, you end up creating an endless recurrence of command creations, while in reality, the recurrence might be broken by some conditional execution of one of the command calls. Creating private contents of command calls prevents this circular creation and only creates a command object when it might actually run.

#### Diagram

The concept of No Circular Command Creation has already been explained in the article *No Circular Command Creation*. The current article shows what circular creation could look like

![](images/3.%20Creation%20Behavior%20Of%20Commands.027.png)

### No Private Contents in a Call in a Definition

A definition is always dormant, and never runs. So also the *calls* inside a definition might never run. Therefore, the private contents of calls inside a definition are *never* created. A call in a definition never shows the call’s private contents. The call at most shows its parameters, so the public contents of the command call. Only the *definition* of the called command might show private contents. So you might hop to the definition of a call to see the private contents of the command.

Not creating a call’s private contents before it even runs, takes away discussion about when to display and when not to display a command’s private contents.

Bear in mind, that when an executable object might not redirect its definition, it has to define its own private contents, because nothing else defines its private contents but he himself. But *calls inside* such a definition, only have their *public* contents are created again.

#### Diagram

This section repeats the story, but now demonstrates the concept using diagrams.

A definition is always dormant, and never runs. So also the *calls* inside a definition might never run.

![](images/3.%20Creation%20Behavior%20Of%20Commands.028.png)

Therefore, the private contents of calls inside a definition are *never* created.

![](images/3.%20Creation%20Behavior%20Of%20Commands.029.png)

A call in a definition never shows the call’s private contents. The call at most shows its parameters, so the public contents of the command call.

![](images/3.%20Creation%20Behavior%20Of%20Commands.030.png)

Only the *definition* of the called command might show private contents.

![](images/3.%20Creation%20Behavior%20Of%20Commands.031.png)

So you might hop to the definition of a call to see the private contents of the command.

Not creating a call’s private contents before it even runs, takes away discussion about when to display and when not to display a command’s private contents.

Bear in mind, that when an executable object might not redirect its definition, it has to define its own private contents, because nothing else defines its private contents but he himself.

![](images/3.%20Creation%20Behavior%20Of%20Commands.032.png)

But *calls inside* such a definition, only have their *public* contents are created again.

![](images/3.%20Creation%20Behavior%20Of%20Commands.033.png)

### A Call in a Call Shows Privates When Running

A call inside another call only contains its private content when it is actually running. If a call is not running, then you might hop to the definition of a call to see the private contents of the command.

Not creating a call’s private contents before it even runs, takes away discussion about when to display and when not to display a command’s private contents.

#### Diagram

A call inside another call only contains its private content when it is actually running. 

If a call is not running:

![](images/3.%20Creation%20Behavior%20Of%20Commands.034.png)

Then you might hop to the definition of a call to see the private contents of the command.

When a call is running, you do see its private contents:

![](images/3.%20Creation%20Behavior%20Of%20Commands.035.png)

Not creating a call’s private contents before it even runs, takes away discussion about when to display and when not to display a command’s private contents.

### Active Command in Inactive Command

A clause in a clause only ever runs when its top parent command is an active command object. If the top parent command is an inactive command object, for instance a command definition, then even an *active* clause in it is dormant.

An executable command inside a command definition can not be run, because its parent is dormant, and an executable sub-command can not be referenced from elsewhere either.

#### Diagram

A clause in a clause only ever runs when its top parent command is an active command object. If the top parent command is an inactive command object, for instance a command definition, then even an *active* clause in it is dormant.

![](images/3.%20Creation%20Behavior%20Of%20Commands.036.png)

The clause might only ever run in a *call* to the definition, but then it is a copy of the definition’s clause:

![](images/3.%20Creation%20Behavior%20Of%20Commands.037.png)

An executable command inside a command definition can not be run, because its parent is dormant, and an executable sub-command can not be referenced from elsewhere either.

### Loose Ideas

#### From "Commands Main Concepts"

*These texts might have been part of Commands Main Concepts once but might be integrated here into Creation Behavior of Commands instead.*

##### Command Call Behavior

At first a command call might be sort of asleep. That might be when there is a chance to set its parameters. After that the command call might be run.

If the parent command runs it might automatically executes the calls inside it.

##### Clause Creation Behavior

A clause `is always` created `as long as the` parent command `is` created. 

##### Sub-Commands

`<< details >>`  
`<< broader perspective >>`  

A parent command `automatically executes` its sub-commands. After a sub-command `completes, the` process `returns` to `the` parent command, which `might` then continue, `executing the` next sub-command.

Inside a command, `usually just` more commands `are` invoked.

There `are only a few` commands that `do` something other than execute other commands. Those `are special` commands, that `perform` a machine instruction: an operation that `is` executed by `the` CPU, `the` central processing unit of `the` computer.

On top of those `special` commands, a `few basic` commands exist, like __If__’s and __For__ loops, that control `the` flow of a program, making `the` next command to call dependent on a condition.

But `basically`, a command `just calls` more commands. Machine instructions, arithmetic operators, comparative and Boolean algebra, assignments, and execution control statements such as __If__ and __For__, `are` *`all` just commands*.

`<< broader perspective >>`
Apart from sub-commands, a command `can` also contain data.
(Inactive clauses and inactive command references for instance are also considered data, and `are` not sub-commands, because they `do not` execute.)

##### Reading & Writing Parameters

Before a command `is` run `you can mess about` with `the` parameters `all you want`.

During `the` execution of a command `you can not` read or write `anything`.

After a command `has` executed, `you can not` change `the` parameters, `just out of practical reasons`, because it `is more practical` for `the` parameters to `keep` visualizing `the` state they `were` in after `the` command `was` run.

- Before execution `you can` read and write.
- During execution `you can not` read or write.
- After execution `you can` only read.

##### Execute Once

`<< details >>`  
a command object might only execute *once*. A command object may represent a single execution. An execution might be created and dormant until it might be run. This might be a chance to set the input of the command. After a command was run, the execution might stay created while it may still be referenced, so output might be read, until `everybody` might be done with it. When the executable object might not be referenced anymore, it might be destroyed. A command object might not be executed twice: to run a command again, a new command object might be created, that may have the same *definition*. In an attempt to execute the same command symbol twice, what might happen instead, is that the old object may be released, and a new object could be created in its place. A reason why a command object might only be executed once, may be that this might give all the referrers a chance to read `the` execution’s output, `whenever` they want, `without` it `being` overwritten by new output. A command object `stays` created for `as long as` it `is being` referenced, so `everybody can` read `the` output of `the` command. `The` command object `might only` be `destroyed` when `nothing refers` to it `anymore`.