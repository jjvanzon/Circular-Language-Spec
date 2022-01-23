Construct Drafts | Implementations | System Interfaces Implementation
=====================================================================

`[ Out of Scope ]`

## System Commands Implementation

There is a paradox.

A *command* is a special object, that can execute, but an object has system *commands*. So here I want to replace a command by an object, but an object *might* have system commands in order to function.

The paradox is only there for *fundamental* system commands, that the system can not do without, and might be implemented in the code base. The code base is the minimal needs, that need to be programmed in another programming language, required to be able to fully reprogram that code base using the new programming language itself. Commands were not to be implemented in the code base, but as an *aspect*, programmed within Circular itself. How can fundamental system commands be present in the lowest layer of the code base, when commands is an aspect, that is programmed using Circular itself? Well… the answer is simple: fundamental system commands are exceptional, and might be present in the code base even though later, the principle of commands might be reprogrammed as an aspect. That aspect might also encompass reimplementing the fundamental system commands, so they behave the same as other commands.

*Object* do not have fundamental system commands. Only object *references*, symbols, have fundamental system commands.

The fundamental system commands are only a limited set, so you only might consider a few of them. See the *System Interfaces* articles for all fundamental system objects, that need to be implemented in the code base. They also discuss the fundamental system commands. Those are the system commands we are talking about here.

It is not so much about system commands, that are added by aspects, but about the fundamental system commands. System commands, added by aspects, can build on top of the fundamental layer of the engine of Circular.

It is really not that much of a problem. Just *some* commands need to be present in the code base, just like *some* objects need to be present in the code base.

## Obsolete Members: Initialize Item & Terminate Item

In experiment 2.0, a related list also had the extension commands __Initialize Item__ and __Terminate Item__. In experiment 3.0, __Initialize Item__ might be replaced by __Add  .  Post-Extend__ and __Terminate Item__ is replaced by __Remove  .  Pre-Extend__.