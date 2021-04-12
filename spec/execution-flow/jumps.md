Encircle Language Spec | Execution Flow
=======================================

Jumps
-----

`[ Preliminary documentation ]`

__Contents__

- [Concept](#concept)
- [Diagram](#diagram)
- [Normal Execution Order](#normal-execution-order)
    - [Concept](#concept-1)
    - [Diagram](#diagram-1)
- [Label & Goto](#label--goto)
    - [Concept](#concept-2)
    - [Diagram](#diagram-2)
- [Call & Return](#call--return)
    - [Concept](#concept-3)
    - [Diagram](#diagram-3)
- [Exit Command](#exit-command)
    - [Concept](#concept-4)
    - [Diagram](#diagram-4)

### Concept

Jumps are a form of control over *execution flow*. Execution flow is explained in the article *Execution Flow*.

A *jump* makes the program jump immediately to a different part of the program. However, sometimes a jump is placed inside a conditional execution statement, basing the jump on a decision after all.

The following forms of *jumps* are supported:

- Normal execution order
- Label, __Goto__
- __Call & Return__
- __Exit Command__
- __Exit Loop__
- __Continue__

Each form is explained in a separate article. 

The last two jumps are only used inside a loop, and might not be explained in this set of articles, but might be explained by the article *Jump-Related Loops*.

### Diagram

Jumps are a form of execution flow explained in the article *Jumps*. The articles that follow only explain their expression in a diagram.

The following forms of *jumps* are supported:

- Normal execution order
- Label, __Goto__
- __Call & Return__
- __Exit Command__
- __Exit Loop__
- __Continue__

Each form is explained in a separate article. 

The last two jumps are only used inside a loop, and might not be explained in this set of articles, but might be explained by the article *Jump-Related Loops in a Diagram*.

### Normal Execution Order

#### Concept

Normal execution order of a procedure means one command being followed up by the next.

But in Encircle, a command is basically just a collection of calls to other commands with no particular order.

If you don’t indicate the order in which to execute the commands, then they might execute in an arbitrary order. Sometimes this is acceptable from a functional point of view.

The order of a procedure can also be *automatically* determined by *input / output dependency*. A command, called inside a procedure, can take input, that is the output of another command. Then the other command needs to execute first, in order to pass its output on to the next command. This is called the *automatic execution order* principle, part of the flat & structured interchange principles. 

If commands should not be executed in an arbitrary order, and the input / output dependency does not determine the order either, then you can indicate the order of execution yourself. This is what we are usually talking about when we refer to *normal execution order*.

Normal execution order places one command call after another to form the order in which to execute the commands. One command actually *calls* the next one. However, it is a special call, because the call never returns to the caller, which it normally does when calling a command. The call to the next command is also called the __Command End__.

The first command to run is a command, that is no other commands’ next command, not even in the input, output dependency.  
Normal execution order is also indicated for calls to execution flow statements, like __If__ calls and __For__ calls.

Normal execution order is a form of execution flow. Following the *normal execution order* is considered following a consecution of jumps. *Jumps* are execution flow statements explained in the article *Jumps*. 

The hope that comes with automatic execution order determined by input / output dependency is to not have to define any normal execution order, because if parts of a procedure have no input / output dependency, then those parts can always execute in any arbitrary order.

Automatic execution order is not worked out in this article. It is might be worked out in the article *Automatic Execution Order*. Normal execution order is about indicating the order of execution yourself.

#### Diagram

If you do not indicate an order in which to execute the commands, then they may execute in an arbitrary order. Sometimes this is acceptable from a functional point of view. The diamonds representing the calls are simply placed inside the command definition as follows:

![](images/4.%20Jumps.001.png)

The order of execution of commands can also be determined by the input / output dependency of their parameters.

![](images/4.%20Jumps.002.png)

The output object of __A__ goes into __B__. The two output values of __B__ go into __C__ and __D__. Therefore __A__ executes first, then __B__, then __C__ and __D__ are executed in an arbitrary order.

This notation of parameter passings is described in the *Parameters* articles (may not be written yet)

When the order of the commands should not be arbitrary or determined by input / output direction, then the order is explicitly drawn out in the diagram. This is what we are usually talking about when we refer to *normal execution order*. One command actually *calls* the next, but the call never returns to the caller. This is displayed as follows:

![](images/4.%20Jumps.003.png)

The first command to run is a command, that is nobody’s next statement, not even in the input, output dependency. In the diagram above, that would be __A__. The commands are executed in the order __A__, __B__, __C__. The fact, that __B__ is followed up by __A__ is displayed as an active reference from __A__ to __B__. But the active reference never returns to __A__ again. This is displayed as the active reference from __A__ to __B__’s being stuck to the end of __A__, so that if you follow the line to __B__ back to __A__, it does not enter back into A again: it does not return back into __A__.

The diagram notation also looks like a call to the *end* of a command.  
The diamond stuck to the border of a call is actually called the __Command End__, and is an *actual* reference to the next command, but then called in a special way.

Normal execution order is also indicated for calls to execution flow statements, like __If__ calls and __For__ calls.

![](images/4.%20Jumps.004.png)

Normal execution order only puts command *calls* next to each other, not command *definitions*. The normal-execution-order ‘call’ (stuck to the side of the command) is always the *last* call of a sub-command. It moves execution on to the next step.

### Label & Goto

#### Concept

A __Goto__ statement is an execution flow statement, that immediately jumps to another part of the code.

In Encircle __Goto__ is an execution flow command that is passed a reference to the clause to go to. The reference to the clause to go to is called the __Target__ parameter.

A clause is a command definition embedded inside a command. The name of the clause is considered the *label* of the statement to jump to. In other computer programming languages the part of the code jumped to was marked with a label. In the new computer programming language, the next statement to jump to is encapsulated by a clause.

Just like in normal execution order a __Goto__ statement never returns to the code it was called from.

The implementation of the execution flow command __Goto__ must somehow first roll back part of the call stack, so that the call to the execution flow command does not return to where it was called from. Next the __Goto__ command uses a machine instruction to jump to the jump __Target__.

#### Diagram

Here is an example of a call to a __Goto__ command:

![](images/4.%20Jumps.005.png)

The public contents of the definition of the __Goto__ command look like this:

![](images/4.%20Jumps.006.png)

### Call & Return

#### Concept

Call and return was allready explained in the article *Command Call*.  
It is mentioned here for completeness, because it is considered a form of *jump*. All forms of jumps are covered by the article *Jumps*.

In other programming languages __Return__ can also mean to exit a command immediately and sometimes specifying a return value with that. This definition of __Return__ is not covered here. To exit a command immediately is covered in the article *Exit Command*.  
To specify a return value is covered by the article *Input, Output, Throughput*.

#### Diagram

Call and return is mentioned here for completeness sake, because it is considered a form of jump. But call and return was already explained in the article *Command Call in a Diagram*.

Here is what a call looks like in a diagram.

![](images/4.%20Jumps.007.png)

### Exit Command

#### Concept

__Exit Command__ is a *jump*. A jump is a type of execution flow statement, explained by the article *Jumps*.

__Exit Command__ immediately stops executing a command, leaving any output in any state it was in. Any order of commands, that would have followed, is omitted and the command ends right then and there. Execution returns to the command, that called the command that was just exited. __Return__ is a synonym for __Exit Command__.

The execution flow command __Exit Command__ takes a reference to the __Command End__ as a parameter. The __Command End__ is explained in the article *Normal Order*.

The implementation of the execution flow command __Exit Command__ might remove the command that is exited from the call stack, and immediately jumps to the command referred to by the __Command End__, that was passed to it.

#### Diagram

__Exit Command__ is defined in a command definition. It might transfer control to the command, that immediately follows after it. The __Exit Command__ command is passed the __Command End__ as an argument:

![](images/4.%20Jumps.008.png)

For information about the command end, see the article *Normal Execution Order* *in a Diagram*.

The normal execution order in the command *definition* is not yet pointing to the next step. It represents the normal execution order as it *might be* in a call to the command definition.

The __Exit Command__ looks as follows inside a command call: 

![](images/4.%20Jumps.009.png)
