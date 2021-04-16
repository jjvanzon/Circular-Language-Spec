Encircle Language Broader View | From Spec
==========================================

Commands Compared to Objects
----------------------------

`[ Preliminary documentation ]`

__Contents__

- [Introduction](#introduction)
- [Commands Anywhere](#commands-anywhere)
- [Exchangeability Between Commands & Objects](#exchangeability-between-commands--objects)
- [Executables & Executions](#executables--executions)
- [Command Definition Compared to Objects](#command-definition-compared-to-objects)
- [Command Definition Analogy to Classes](#command-definition-analogy-to-classes)
- [Command Call Compared to Objects](#command-call-compared-to-objects)
- [Command Call Compared to Objects](#command-call-compared-to-objects-1)
- [Command Reference Compared to Objects](#command-reference-compared-to-objects)
- [Active Clause Compared to Objects](#active-clause-compared-to-objects)
- [Reading & Writing Parameters](#reading--writing-parameters)
- [Resolution When `Not Allowed` For Commands](#resolution-when-not-allowed-for-commands)

### Introduction

Notation for commands may differ from that of objects, mainly by usage of different shapes. The similarity in notations may lead to questions like: "Are commands just like objects? In what way might they be different?" This article tries to explore ways commands may compare to objects. Command creation behavior might not be covered, but be a separate topic altogether. 

### Commands Anywhere

Commands might be executable objects that may move around more freely. `You` might start thinking of an executable object `more like` an object, that `just so happens to be` executable. `You might see` an execution `much, much more like` an executable object that `can` be situated `anywhere` and referenced from `anywhere`. 

`You` might put `the` executable object inside another object:

![](images/1.%20Commands%20Main%20Concepts.035.png)

`You` might reference an executable object:

![](images/1.%20Commands%20Main%20Concepts.036.png)

`Yes, you` might put an executable object inside a command definition:

![](images/1.%20Commands%20Main%20Concepts.037.png)

`But you` might `also` put an executable object inside a class:

![](images/1.%20Commands%20Main%20Concepts.038.png)

`You` might run an execution inside an object, sort of like having an execution run inside a specific folder:

![](images/1.%20Commands%20Main%20Concepts.039.png)

`You` might `also` run `the` execution inside `your` 'user object' and sort of take it along with `you`, wherever `you` go into `the` digital world.

`You` might also run an execution globally on a site:

![](images/1.%20Commands%20Main%20Concepts.040.png)

Executions might also be placed in a list. `You` might run `each` item in `the` list individually.

![](images/1.%20Commands%20Main%20Concepts.041.png)

### Exchangeability Between Commands & Objects

In some programming languages, commands might not be exchangeable with objects, but be totally separate constructs. But in Encircle, commands could be seen as objects, that just happen to be executable.

Using some programming languages a process might be implemented as a procedure. Sometimes a procedure might become more complex. It might be an option to then rewrite a procedure to an object, whose purpose could be to execute that procedure. This object may then hide complexity of the input and output better, and might better hides the complexity of the procedure itself. An object in some programming languages might offer a way to split up a procedure into separate steps, without seeing that on the outside. Turning a procedure into an object may make linking to it more flexible. For instance you might plug a new process into an already existing system, that was not aware of this procedure. That might not be easily possible, unless you turn a procedure into an object.

In Encircle though, procedures might be considered an object as is, without rewriting anything. The only difference might be that this object has the special property, that it might be *executable*.

In the Encircle notation, a command could have complexity hiding and linking possibilities, just like a 'normal' object. A command might for instance also *inherit* a base procedure from another command, just to name something.

A command could be structured similarly as an object. Perhaps that takes away the argument that using just procedures might be a less structured way of programming than using objects. A command might already be an object, that represents a process. It may looks like a command, but might have the capabilities of an object.

In that philosophy, commands might be *executable objects*.

### Executables & Executions

An executable object might stands for a potential execution:

![](images/1.%20Commands%20Main%20Concepts.050.png)

An executable object might not stands for multiple executions, `just one` execution or `no` execution `at all`.

`The same` command object might be displayed in `the` diagram multiple times. In that case, a symbol might be added to the diagram, that `the` multiple references to `the same` command object `might` converge to, so that a single symbol in `the` diagram `is` selected to represent `the` command object itself, while `the` other ones `are` just references.

![](images/1.%20Commands%20Main%20Concepts.051.png)

So it `is not so`, that each diamond in `the` diagram represents its own individual command execution. Each individual *command object* `represents` an individual command execution. Multiple symbols in `the` diagram `can` represent `the same` command object, but `might` converge into one symbol representing `the` object itself.

### Command Definition Compared to Objects

Command definitions may be similar to *object classes*. A command object might have a similar structure as its definition, but not necessarily the same data. Values might change for each individual command object. *Which* objects are referenced might also be different for each individual command object. But initially the command object might be an exact replica of the definition. The definition’s attribute values and object references might only function as a default.

### Command Definition Analogy to Classes

`<< already covered >>`

Commands with `the same` definition `contain the same` list of attributes, related items and related lists.

There `is` a `complete` analogy between a command’s definition and `the` class of an object.

`Anything` that `applies` to classes, also `applies` to command definitions.

### Command Call Compared to Objects

A command call might be like an instantiation of a command definition. A command call might be an individual object with something similar to a class reference to another command. There might be an analogy between calls to a definition and objects of a class, with an addition, that a call might be *executable*.

A command call might select its command definition with a *class* redirection, because the definition might be like the command call’s *prototype*, and the call may always be its own individual object for which the command definition may be the prototype.

### Command Call Compared to Objects

Initially, a call might be sort of a copy of its definition. Data of the command definition might just be default values. Data of a call object might be changed before it might run and change while it runs. What data of a command might be changed or not, might be something to cover elsewhere.

Because `the` definition `is the` prototype of `the` call, and `not the same` object as `the` call, a dashed class line `needs to` be used to point out `the` definition of a call.

### Command Reference Compared to Objects

A command reference might be achieved with *object* redirection.

A command reference `represents the same` object as `the` object `pointed to`. `So the` command reference’s contents `are the exact same` objects as that of `the` command object it `points to`.

### Active Clause Compared to Objects

< May change terminology. >

An active clause `is analogous` to an object that `might not` have a class. A *call* `is more` like an object that *`might`* have a class.

### Reading & Writing Parameters

A command definition’s parameter values `are` public, `so` if `you can` reach `the` definition, `you can basically` change its parameter values, and `mess about` with them `all you want`. This might `be` access controlled, but how this `should` be done `is not yet determined`.

### Resolution When `Not Allowed` For Commands

When `the` command concept `imposes a rule`, that `might not apply` to normal objects, then `you might` seem `to be` able to `break that rule`. To `keep direct` conversion between an object and a command `possible without any loss` of structure, it seems to be `allowed to break any of the extra rules imposed` by commands. But in that case `the` command `might always` get `the next best` alternative behavior and a warning `might` be generated. This might keep conversion between objects and commands possible `without any loss of` structure.