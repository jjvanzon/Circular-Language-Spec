Encircle Language Spec | Execution Flow
=====================================

Loop-Related Jumps
------------------

`[ Preliminary documentation ]`

### Concept

Loop-related jumps are jumps used specifically inside a loop. Jumps are a form of control over *execution flow*. Loops are explained in the article *Loops*. Execution flow is explained in the article *Execution Flow*.

The following two forms of jump relate specifically to a loop:

- __Exit Loop__
- __Continue__

They each will be explained in their own article.

### Diagram

Loops-related jumps are a form of control over execution flow explained in the article *Loop-Related jumps*. The articles that follow only explain their expression in a diagram.

There are two forms of loop-related jump:

- __Exit Loop__
- __Continue__

Each form is explained in a separate article. See the articles *Exit Loop in a Diagram*, *Continue in a Diagram.*

### Continue

#### Concept

The __Continue__ statement is a loop-related jump. It is a jump that is only performed inside a loop.

__Continue__ skips the remainder of the loop procedure and immediately moves on to the next repetition of a loop.

A loop procedure is implemented as a reference to a command, passed as an argument to an execution flow command. So __Continue__ means no more, than to exit the command that is looped, so it is a synonym for __Exit Command__, but then used inside a loop.  
It will remove the command that is exited from the call stack, and immediately jumps to the command referred to by the __Command End__, that was passed to it.

#### Diagram

As explained in the article *Continue*, the __Continue__ command means no more than to exit the procedure that is looped.

So in the expression in a diagram, you see a loop, that has the command to loop associated to it. A continue statement looks the same as to exit a command:

![](images/5.%20Loop-Related%20Jumps.001.png)

### Exit Loop

#### Concept

The __Exit Loop__ statement is a loop-related jump. It is a jump that is only performed inside a loop.

__Exit Loop__ omits all repetitions, that would have followed and immediately ends the complete loop.

__Exit Loop__ is a jump to the __Command End__ of the loop command. The __Command End__ of a command is a reference to the next command to run, so the normal order that follows after the loop continues.

Do not confuse this with exiting the command that is *being* looped, because that causes the next repetition of the loop to run. That action is performed with the __Continue__ command. The __Exit Loop__ command ends the *whole loop*.

The implementation of the __Exit Loop__ command is a lot like the implementation of __Exit Command__, only the __Exit Loop__ command will delete the last *two* calls from the call stack, and immediately jumps to the command referred to by the __Command End__, that was passed to it.

#### Diagram

The __Exit Loop__ command is displayed inside the clause that is looped as a jump to the __Command End__ of the whole loop.

![](images/5.%20Loop-Related%20Jumps.002.png)

The text __Command End__ is not required in the diagram:

![](images/5.%20Loop-Related%20Jumps.003.png)

