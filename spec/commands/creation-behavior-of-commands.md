Encircle Language Spec | Commands
=================================

Creation Behavior
-----------------

`[ Preliminary documentation ]`

__Contents__

- [Creation Behavior of Calls](#creation-behavior-of-calls)
  - [Calls In A Parent Command](#calls-in-a-parent-command)
  - [Original Problem & Solution](#original-problem--solution)
  - [Problems Solved By Delayed Creation](#problems-solved-by-delayed-creation)
  - [Delayed Creation Of Private Contents Only Counts For Command Calls](#delayed-creation-of-private-contents-only-counts-for-command-calls)
  - [Compared To CPU-Like Call](#compared-to-cpu-like-call)
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
- [Comparison to CPU-Like Call Instantiation](#comparison-to-cpu-like-call-instantiation)
  - [What happens in other programming languages?](#what-happens-in-other-programming-languages)
  - [Why does that not work for my own system?](#why-does-that-not-work-for-my-own-system)
  - [Data](#data)
  - [Pointers to this data](#pointers-to-this-data)
  - [Sub-commands](#sub-commands)
  - [Parameters of these sub-commands](#parameters-of-these-sub-commands)
  - [Assignment of data to the sub-commands’ parameters](#assignment-of-data-to-the-sub-commands-parameters)
  - [Reason to always create and assign sub-commands…](#reason-to-always-create-and-assign-sub-commands)
  - [How can a parameter passing assignment be stored](#how-can-a-parameter-passing-assignment-be-stored)
  - [More Brainstorming](#more-brainstorming)
  - [Former Text](#former-text)

### Creation Behavior of Calls

A call can be present inside an object or inside another command. When a call is created, it is not immediately run, so that you get a chance to set its parameters. Before a command call is run, the command call’s public contents are there: its parameters. Those parameters are copied out of the call’s definition. The private contents are not there yet. A command’s private contents include private objects, clauses and command calls. The private contents will be copied out of the command defininition, only just before the command call runs. The public contents of a command call are added when the command object is created. The private contents of a command call are only added when its about to run. So the general rule is: creation of private contents of a command call is delayed until just before a command call is run.

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
When a sub-command would only be created just before it is run, there is a problem: if a sub-command is created only just before it is run, when can a parent command fill in the parameters of the *not yet created* sub-command? Parameter passings could not reference the sub-command’s parameters. That’s why before running the parent command, the sub-commands need to be created.  
But when creating the sub-command even before it is  run, there is another problem: if sub-commands need to be created when their parent is created, the sub-commands of sub-commands would also need to be created, and their sub-commands and so on. So the whole call structure would have to be created before the parent command could even run. This could even have resulted in circularities, that would make the system hang.

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

But if a command object does not have a definition, then it defines its own definition. For command objects that define their own definition, private contents have to be created all the time, because nothing else defines its private contents but the object itself. This counts for command definitions. This also counts for *active* command definitions, which are executable object that define their own definition. But it also counts for clauses. See the article *Creation Behavior of Clauses*.

#### Compared To CPU-Like Call

There was a lot of brainstorming about how this relates to the way it goes in other programming languages, which have a command call creation scheme totally compliant to the CPU’s way of handling command calls, which is not in the spirit of *commands as an object*. But that brainstorming was postponed, because it did not have anything to do with a goal, but more with optimization of Encircle. The contemplations are still there in the article *Comparison to CPU-Like Call Instantiation*, as an unfinished brainstorm, that may be later worked out, to better take advantage of CPU power.

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

But if a command object does not have a definition, then it defines its own definition. For command objects that define their own definition, private contents *are* created all the time, because nothing else defines its private contents but the object itself.

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

Special creation behavior does *not* count for inactive command objects inside a parent command, that have a class redirection to a command definition. This looks like the inactive form of a command call, but this kind of object does not have special creation behavior like that. It is an uncommon situation. But an inactive command inside a parent command with a class reference to a definition *can* be referenced, unlike its active form. Therefore, it can also be *class* referenced by a call. In that case its privates and publics had better be there more permanently, or the *call* to it can not instantiate private contents at all.

Creating its private contents, does not create a recursive creation or anything: the inactive call’s own private calls do not create *their* private contents, so there is no recursion there.

#### Diagram

The article *Creation Behavior of ‘Inactive Calls’* already explained this behavior conceptually. The current article further clarifies the idea using diagrams.

Command calls inside a parent command have special creation behavior:

![](images/3.%20Creation%20Behavior%20Of%20Commands.018.png)

Their publics are created as soon as the parent command is created

![](images/3.%20Creation%20Behavior%20Of%20Commands.019.png)

but their privates are only created when the command call is about to be run.

![](images/3.%20Creation%20Behavior%20Of%20Commands.020.png)

Special creation behavior does *not* count for inactive command objects inside a parent command, that have a class redirection to a command definition.

![](images/3.%20Creation%20Behavior%20Of%20Commands.021.png)

This looks like the inactive form of a command call, but this kind of object does not have special creation behavior like that. It is an uncommon situation. But an inactive command inside a parent command with a class reference to a definition *can* be referenced

![](images/3.%20Creation%20Behavior%20Of%20Commands.022.png)

Unlike its active form, which can not be referenced.

![](images/3.%20Creation%20Behavior%20Of%20Commands.023.png)

Therefore, it can also be *class* referenced by a call.

![](images/3.%20Creation%20Behavior%20Of%20Commands.024.png)

In that case its privates and publics had better be there more permanently, or the *call* to it can not instantiate private contents at all.

![](images/3.%20Creation%20Behavior%20Of%20Commands.025.png)

Creating its private contents, does not create a recursive creation or anything: the inactive call’s own private calls do not create *their* private contents, so there is no recursion there.

![](images/3.%20Creation%20Behavior%20Of%20Commands.026.png)

### No Overhead of Command Creation

One of the reasons why private contents of a call are only created just before the call is run, is because this prevents overhead of creation. If you would have to create the whole call structure when the great grandparent of commands is created, then this is not only a lot of work in one blow, but also, a lot of command call objects are created, that never get to run in the first place, because it only runs under certain conditions. Delayed creation of the private contents of a command call prevents this overhead of procedure creation and creates a neat and steady rate of procedure creation.

### No Circular Command Creation

Another reason why private contents of a call are only created just before the call is run, is because this prevents circular creation of commands. Some command may call another command and that command may call the first one again. Command calls are usually private, so if you would create all possible command calls, you end up creating an endless recurrence of command creations, while in reality, the recurrence will be broken by some conditional execution of one of the command calls. Creating private contents of command calls prevents this circular creation and only creates a command object when it will actually run.

#### Diagram

The concept of No Circular Command Creation has already been explained in the article *No Circular Command Creation*. The current article shows what circular creation could look like

![](images/3.%20Creation%20Behavior%20Of%20Commands.027.png)

### No Private Contents in a Call in a Definition

A definition is always dormant, and never runs. So also the *calls* inside a definition will never run. Therefore, the private contents of calls inside a definition are *never* created. A call in a definition never shows the call’s private contents. The call at most shows its parameters, so the public contents of the command call. Only the *definition* of the called command will show private contents. So you have to hop to the definition of a call to see the private contents of the command.

Not creating a call’s private contents before it even runs, takes away discussion about when to display and when not to display a command’s private contents.

Bear in mind, that when an executable object does not redirect its definition, it has to define its own private contents, because nothing else defines its private contents but he himself. But *calls inside* such a definition, only have their *public* contents are created again.

#### Diagram

This section repeats the story, but now demonstrates the concept using diagrams.

A definition is always dormant, and never runs. So also the *calls* inside a definition will never run.

![](images/3.%20Creation%20Behavior%20Of%20Commands.028.png)

Therefore, the private contents of calls inside a definition are *never* created.

![](images/3.%20Creation%20Behavior%20Of%20Commands.029.png)

A call in a definition never shows the call’s private contents. The call at most shows its parameters, so the public contents of the command call.

![](images/3.%20Creation%20Behavior%20Of%20Commands.030.png)

Only the *definition* of the called command will show private contents.

![](images/3.%20Creation%20Behavior%20Of%20Commands.031.png)

So you have to hop to the definition of a call to see the private contents of the command.

Not creating a call’s private contents before it even runs, takes away discussion about when to display and when not to display a command’s private contents.

Bear in mind, that when an executable object does not redirect its definition, it has to define its own private contents, because nothing else defines its private contents but he himself.

![](images/3.%20Creation%20Behavior%20Of%20Commands.032.png)

But *calls inside* such a definition, only have their *public* contents are created again.

![](images/3.%20Creation%20Behavior%20Of%20Commands.033.png)

### A Call in a Call Shows Privates When Running

A call inside another call only contains its private content when it is actually running. If a call is not running, then you would have to hop to the definition of a call to see the private contents of the command.

Not creating a call’s private contents before it even runs, takes away discussion about when to display and when not to display a command’s private contents.

#### Diagram

A call inside another call only contains its private content when it is actually running. 

If a call is not running:

![](images/3.%20Creation%20Behavior%20Of%20Commands.034.png)

Then you would have to hop to the definition of a call to see the private contents of the command.

When a call is running, you do see its private contents:

![](images/3.%20Creation%20Behavior%20Of%20Commands.035.png)

Not creating a call’s private contents before it even runs, takes away discussion about when to display and when not to display a command’s private contents.

### Active Command in Inactive Command

A clause in a clause only ever runs when its top parent command is an active command object. If the top parent command is an inactive command object, for instance a command definition, then even an *active* clause in it is dormant.

An executable command inside a command definition can not be run, because its parent is dormant, and an executable sub-command can not be referenced from elsewhere either.

#### Diagram

A clause in a clause only ever runs when its top parent command is an active command object. If the top parent command is an inactive command object, for instance a command definition, then even an *active* clause in it is dormant.

![](images/3.%20Creation%20Behavior%20Of%20Commands.036.png)

The clause will only ever run in a *call* to the definition, but then it is a copy of the definition’s clause:

![](images/3.%20Creation%20Behavior%20Of%20Commands.037.png)

An executable command inside a command definition can not be run, because its parent is dormant, and an executable sub-command can not be referenced from elsewhere either.

### Comparison to CPU-Like Call Instantiation

There was a lot of brainstorming about how Encircle’s call instantiation compares to call instantiation in other programming languages, which are totally compliant to the CPU’s way of handling command calls, but is not in the spirit of *commands as an object*. But that brainstorming was postponed, because it did not have anything to do with a goal of a workable type of call instantiation, but more with optimization of Encircle. The contemplations are still there in this article, as an unfinished brainstorm, that may be later worked out, to better take advantage of CPU power.

Perhaps creation behavior is just the most important issue of Command is an Object. It really belongs to the introduction of commands, that explains how a command is an executable object. Closely related to it, is the special creation behavior of executable objects. You have to well understand the creation behavior to implement a command as an object.

There was a brainstorm about the problems, that come with creating a sub-call object just before it executes. This brainstorm in further down below in the section *Former Text*.  
But the idea will now be further worked out by making a comparison between other programming languages and how it will be solved in the new programming language.

#### What happens in other programming languages?

In other programming languages, when a call is executed, calls to sub-commands are not copied to the call instance.

In other programming languages, it is always the command definition itself that is running. But because each time it is running it is operating on different data, you can consider it a separate command object every times it runs.

From a single-threaded point of view, the same command does not run at the same time, so if a command runs multiple times, it is always first running one one piece of data and only after that running on another piece of data.

In a multi-threaded situation a command could run twice at the same time.  
A thread, however, `has its own stack and also its own instruction pointer, as well as its own registers.

In a time-sliced threading situation, whenever the CPU switches from one thread to another, the data the command operates on is changed and the command will pick it up where it left off in that thread’s previous time slice.

In multi-threaded situations with two CPU’s or two CPU cores things still go ok, because each thread has its own instruction pointer and a different call stack. It is no problem to reuse the same code. The code does not specify which specific data it is operating on, so the code is just instruction data, that is reused.

The only thing a call-instance consists of in other programming languages is either different data on the call stack, or a different call stack altoghether (different thread).

The parameters and local variables *do* need to be instantiated on the stack in other programming languages. But sub-command calls, parameter assignments, and all that, do not need to be copied to the call-instance, because it is always just the definition that is running.

What the CPU does, is get new instructions from the spot pointed out by the instruction pointer. The instruction may refer to data with a pointer address. This pointer address is always fixed in the code, but it is related to a base address. This base address is stored as the *data segment* in the DS register of the CPU, to make hard-coded pointer addresses work by always relating it to this base address. A thread has an instruction pointer location, a stack, and its own CPU register values. Therefore each thread at one given time operates on its own piece of data. There are CPU registers that store an instruction pointer (IP CPU-register), a memory base address (DS CPU-register), a code base address (CS CPU-register) and a stack base address (SS CPU-register). 

The same code, with fixed pointers has to be executed on different data all the time, so that must mean a data switch. Each object has its own data segment. To operate on that data, the DS register needs to be set. That means, that on each call to an object’s method, the original DS register is put onto the stack to remember it, and the DS register is replaced to point to the object from which to call a method. Inside the method of the object called, other objects may be created. This changes nothing about the DS register. The object pointers are put onto the stack, instructions can operate on a fixed spot in the stack, instead of a fixed spot in the data segment. But inside the method of the object called, objects are created, but also objects are called. As soon as another object’s method is called, the original value in the DS register is put on the stack, and the DS register is set to point to the object to call. After the object call is done, the DS register is restored to its original value, by popping the original value off the stack again. That’s probably the way it works in object oriented systems.

#### Why does that not work for my own system?

The CPU is quite straightforward in a way. It executes and executes doing exactly what it is lead to do by its instruction pointer that only goes forward, and it only skips to another spot, when it encounters a jump instruction and the data then determines whether it will jump at all. A CPU is really quite straightforward and just does what we tell it to do. As a normal program runs, you do not *see* debug information. When a program runs normally, you do not see what method it is in and of what object, and even the CPU does not see what method it is in and of what object. When you debug, though, you want to see the exact code line of what exact method and of what object, you can even see (from an alternated call stack) what commands were called before and of what object.

In my own computer language, when you pause on a running command, you see the procedure call stack as the hierarchy upward. This call stack was not built up as the command was running. You can zoom in on any piece ‘call stack’, that is not even running, but might be running in the future.

Now, the data, assigned to a call’s parameters… where does it come from in CPU-like, procedural and object oriented programming languages? Where does it come from in my own system? 

There is:

- data
- pointers to this data
- sub-commands
- parameters of these sub-commands
- and the assignment of data to the sub-commands’ parameters

funny enough, that is all a command call consists of. Do remember that machine instructions, arithmetic operators, comparative and boolean algebra and execution control statements such as If and For, are all just command calls.

#### Data

In a CPU-like programming language, the data is already there as created objects somewhere in memory. That’s the same in my own language.

#### Pointers to this data

Pointers to the data, that was already there, are on the call stack in a CPU-like language. In my own language the pointers to this other data are inside the call object. So from that perspective, the call object constitutes, what is otherwise a chunk of the stack, that belongs to a particular procedure call.

#### Sub-commands

Now, the sub-commands in a CPU-like language are there as CALL instructions. CALL instructions are in the command definition. In my own language sub-commands are there as sub-command references, with a *definition* assigned to them, but no object  yet. The sub-command *object* is only created just before a sub-command will be run.

I still do not have a clear view on why in CPU-like languages it is CALL instructions in the definition, and in my own language it is sub-command references inside a call object.  
< ... >

< It’s just that, in CPU-like languages the instructions run and the data to operate are such separated things. The registers and the stack hold the data, and the instructions hold the code. In my own language, the data to operate on is not on *the stack*, but *inside* the procedure to execute. So the procedure call (instruction) *contains* the data to operate on. No. I still don’t get it>

#### Parameters of these sub-commands

In CPU-like languages this means, that space is created on the stack for these parameters just before the sub-command is executed. Actually this happens in one blow with assigning data to the parameters.  
In my own language, the pointer parameters are created as pointers, the value parameters are created as pointers and simple created objects (data). This all done, just before the sub-command is executed.

#### Assignment of data to the sub-commands’ parameters

In CPU-like languages this means, that parameter space on the stack is assigned values. Actually, this happens in one blow ith creating the space on the stack. This all just before the sub-command executes. In my own language, this means, that the pointer parameters are set to point to objects and the value parameters, that are created simple objects, are now assigned values. This also happens, just before the sub-command executes.

< There is a difference between when the assignment is executed, and where the assignment call is. The assignment call in CPU-like languages are PUSH instructions in the command definition. Only when executing the parameter assignment / push instruction, the parameters are actually created. The assignment call in my own language is a special assignment command call, displayed as a parameter passing. The assignment command call must already link to parameter references of sub-commands, therefore the sub-commands must already be created, but not yet initialized. Only when the sub-command is about to be run, the parameter assignment is actually executed. >

#### Reason to always create and assign sub-commands…

For visibility...

When navigating through the call symbols in a diagram, you want to see call objects as created objects anyway, but this is just visualization of what *might* happen. Huh?

When you debug calls, then you want to see all the sub-command objects created, even though nothing needs to be assigned to the parameters. The parameter passings are visible anyway, because those are actually assignment commands *displayed as* parameter passing.

You have:

- data
- pointers to this data
- sub-commands
- parameters of these sub-commands
- and the assignment of data to the sub-commands’ parameters

The sub-commands have to be created and their parameter sub-objects need to be in there, but can be Nothing. The parameter assignments are (really) special sub-commands, that are displayed with a parameter passing notation, but that does not require the parameters to be created.

#### How can a parameter passing assignment be stored

A parameter passing assignment could only be stored by the parent command-call if the sub-commands are created (but not initialized; parameter references are there, but not filled in yet).

#### More Brainstorming

< A problem is, that in my own computer language, the command definition is not assembly code. It is objects of Encircle. >

In CPU-like languages the sub-command-calls are in the machine instructions.
In my own computer language sub-commands-calls are in an objects somewhere.
The command definition object has the sub-commands, but they are not lined up like machine instructions. Each command call is tied to the next with a pointer to another command object.  
It is very hard to make the command definition use the data in the command CALL, because that is what has to be done, to do it in the more CPU-like fashion.

In CPU-like fashion you have a split up between the data context, and the code context.  
In my own language you really see both data and code together.  
To let a definition run multiple times at the same time, with a different data context, just looks wrong in a diagram.  
But can you let a definition run multiple times at the same time, with a different data context, and in the diagram let it SEEM the CALL is running?  
The definition is an object now. Let's not change THAT.  
I'm having trouble in my head now, because up until now, the diagram was a clear representation of what was actually going on.

\-----

Isn't it jut solved if you just accept, to create a call object as a replica of a definition, even though, then you are copying 'code' as well as data.  
And just when running the parent command, you create all the sub-commands,
and their parameters, but leave them unfilled in and create the parent command's parameter assignments. Then you have everything instantiated, that you need, and you can just start at sub-command 1, run the input parameters assignments, and run it, run the output parameter assignments (even when they immediately assign something to parameters of another command), and then continue with sub-command 2.
That would just solve the problem.

Just leave that CPU comparison stuff in another article.  
Just confess in that article, that it is just a brainstorm,  
the goal of the brainstorm and that it is still not solved,  
and then leave it unfinished indefinitely.

#### Former Text

*{ Most of this is brainstorming. The more true conclusions are there under ‘What happens in current programming languages?’. }*

The problem is:  
Parameter assignment calls have to point to parameters. How can you point to a parameter, if the call is not created yet?

You have to add to the command call article, that in a definition, the calls have to be created, because a definition has to specify what will become input and output for the command call. Or perhaps add that to sub-commands articles.

I am still totally confused about the creation behavior of calls.  
It looks like a call object has to be created as soon as its parent call is created, because input and output references have to be defined?  
No. Input and output references are not defined. Input and output references are actually assignments, that only look like references. Yeah, but the assignments reference the parameters.

Perhaps you have to separate the creation behavior from the explanations of the general terms.

\-----

Eventually it’s all call structure, for which definitions are just blue prints.

It looks like after a call’s created, based on the definition, input is set, it starts executing. First the first sub-command is created, based on its definition, input is set, based on the parent command’s definition, and it starts executing.

The assignment commands of parameter assignments are special. They do not count as the sub-commands of a command.

So what’s complicated about this? Well… the fact that when you process a sub-command, to set its input, the parent command’s definition must be consulted.

So what if after you created the parent command, based on the definition, you set input and then, before executing, the sub-commands are all created, and their input set, but not their sub-commands.  
Only when you are about to *execute* a sub-command, its own sub-commands are created. But before that the parameters had already been assigned…

But crap. That works for reference parameters, but not for value parameters. You have to set value input right before you execute.

Create the parent command, based on the definition  
Set input of parent command  
Create all sub-commands,  
input, output assignments taken over from parent command  
set input of first sub-command  
execute first sub-command  
get output from first sub-command

So just before executing a parent command, you don’t only see the parent command’s input, but you also create all sub-commands, but leave their sub-objects empty. And then you copy the parameter assignments from the parent command definition.  
Then you have the material ready to start executing the sub-commands one by one. The parameter assignments are executed appropriately before and after a sub-command executes.

So the connection between a sub-command parameter and something out of the parent command is not part of the parent command’s definition, but the assignment call that makes the connection between a sub-command parameter and something of the parent command is part of the parent command’s definition. The assignment call is only executed as the parent command executes.

So it’s all about getting the material ready for a parent command to execute. The creation behavior of a call is indeed still to be worked out.

\> I do not think it is mandatory to immediately create sub-command-calls and their parameters for a call-instance

