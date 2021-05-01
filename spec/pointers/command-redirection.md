Circular Language Spec | Pointers
=================================

Command Redirection
-------------------

`[ Preliminary documentation ]`

__Contents__

- [Inactive Command Object Redirection](#inactive-command-object-redirection)
- [Inactive Command Class Redirection](#inactive-command-class-redirection)
    - [Diagram](#diagram)
- [Executable Command Class Redirection in a Diagram](#executable-command-class-redirection-in-a-diagram)
    - [Concept](#concept)
    - [Diagram](#diagram-1)
- [Executable Command Object Redirection](#executable-command-object-redirection)
    - [Diagram](#diagram-2)
- [Target Command Object](#target-command-object)
    - [Diagram](#diagram-3)
- [Target Command Definition](#target-command-definition)
    - [Diagram](#diagram-4)
- [Recursion](#recursion)
    - [Concept](#concept-1)
    - [Diagram](#diagram-5)
- [Loose Ideas about Command Redirection](#loose-ideas-about-command-redirection)
    - [Ideas (about Target Command Object)](#ideas-about-target-command-object)
        - [Execution Trace](#execution-trace)
        - [Tracing Command Aspects](#tracing-command-aspects)
            - [Redirecting to an Execution](#redirecting-to-an-execution)
    - [Ideas (about Target Command Definition)](#ideas-about-target-command-definition)
        - [Definition Trace](#definition-trace)
        - [Execution-Definition Trace](#execution-definition-trace)
- [Loose Ideas about Recursion](#loose-ideas-about-recursion)

### Inactive Command Object Redirection

An inactive command object redirection makes an inactive command symbol a command reference.

An inactive command reference can point to another inactive command as well as to an active command object.

The picture below displays an inactive command, that redirects its definition to another inactive command.

![](images/4.%20Command%20Redirection.001.png)

Inactive command symbol __A__ is a square because it is an *inactive* command. Inactive command symbol __A__ redirects to the inactive command symbol __B__. Symbol __B__ is also a square because it is also an *inactive* command. The redirection from command __A__ to command __B__ is displayed as a solid line, which is an object line. The direction of the line is indicated by a line dissector, close to symbol __B__.

Symbol __B__ could also be replaced by a diamond, because inactive pointers to active commands are allowed.

![](images/4.%20Command%20Redirection.002.png)

### Inactive Command Class Redirection

Inactive command class redirection is less common than inactive command object redirection. Inactive command *object* redirection is a reference to a command definition. Inactive command *class* redirection creates a new command definition for which another command is the prototype. 

Inactive command *class* redirection makes a command definition take over all aspects of another command definition, but creates a *new* command definition object, for which the other command definition is the prototype. The new command definition can only redefine the other definition’s *default values*. That’s all that is additionally possible, compared to inactive command *object* redirection.

Inactive command class redirection is analogous to having a class redirect its class, making one object the prototype for another prototype.

An inactive command class redirection can also point to an active command, making an *executable* command object the prototype for the new command definition. That is even less common, but possible all the same.

Do remember, that the new prototype can *not* be executed by pointing to it with an active command reference, because the new prototype is a new *inactive* command object, and an inactive command object can not be executed.

#### Diagram

![](images/4.%20Command%20Redirection.003.png)

Inactive command symbol __A__ is a square because it is an *inactive* command. Inactive command symbol __A__ redirects its class to the inactive command symbol __B__. Symbol __B__ is also a square because it is also an *inactive* command. The redirection from command __A__ to command __B__ is displayed as a dashed line, which is a class line. The direction of the line is indicated by a line dissector, close to symbol __B__.

Symbol __B__ could also be replaced by a diamond, making an *executable* command the prototype for a new command object. That is less common, but possible all the same.

![](images/4.%20Command%20Redirection.004.png)

### Executable Command Class Redirection in a Diagram

#### Concept

If an executable command redirects its class, then it is a command call. The class redirection points to the command definition of the command call.

If an executable command *might not have* a class redirection, then it defines its own contents. An object redirection automatically also redirects the class aspect of a symbol. So then it also might not define its own contents. If an executable command, that might not redirect its class or object resides inside another command, then it is called an *active nested command*. If the executable command without redirections resides inside an object, then it is simply an executable command with no definition, that can be manually run by a user.

You could let an executable command redirect its definition to another executable command, but this is far less common. But an active command *can* function as the prototype for another executable command.

#### Diagram

Executable command class redirection is explained in the article *Executable Command Class Redirection*. The current article demonstrates the concept in a diagram.

The picture below displays a command call, redirecting its definition to an inactive command.

![](images/4.%20Command%20Redirection.005.png)

Active command symbol __A__ is a diamond shape, because it is an *active* command. Active command symbol __A__ redirects its definition to the inactive command symbol __B__. Symbol __B__ is a square because it is an *inactive* command. The redirection from command __A__ to command __B__ is displayed as a dashed line, which is a class line. This makes symbol __A__ a command call, for which command __B__ functions as a definition.

You could let an executable command redirect its definition to another executable command, but this is far less common:

![](images/4.%20Command%20Redirection.006.png)

### Executable Command Object Redirection

An executable command, that redirects to another executable command, is a reference to a command that could run, or could be running. Say you run the command on a site and you want to navigate away from the site, but keep a reference to it in your user object, that points to a process running on a site somewhere, and take along the reference anywhere you go on the internet.

Executable command object redirection is less common than inactive command object redirection.

You can also object redirect an executable command to an inactive command. If the final target of the object redirections is an inactive command, then you can not run that inexecutable command object through an active reference to it. It is kind of pointless to point to an inactive command object through an executable command reference, so it is very uncommon.

#### Diagram

The concept of execution object redirection is explained in the article *Execution Object Redirection*. The current article explains its expression in a diagram.

![](images/4.%20Command%20Redirection.007.png)

Active command symbol __A__ is a diamond shape, because it is an *active* command. Active command symbol __A__ redirects its object to the active command symbol __B__. The redirection from command __A__ to command __B__ is displayed as a solid line, which is an object line. This makes symbol __A__ a reference to an execution running elsewhere.

You can also have an active reference to an inactive command:

![](images/4.%20Command%20Redirection.008.png)

But this situation is very uncommon. You can not run command __B__ through symbol __A__, because an inactive command object can never be run.

### Target Command Object

A command reference can point to another command reference, which points to another command reference and so on. The first command found in this redirection, that might not refer to another command again, is called the *target command object*. Even though any of the command *references* can be used like it is the command object itself, the *target command object* is considered the real command object and not just a reference to it.

The term target command is also used to denote the direct reference target, not necessarily the final target. What kind of target is denoted, might be clear from the context.

#### Diagram

The target command object is the last point in a string of object redirections of command symbols.

![](images/4.%20Command%20Redirection.009.png)

Symbol __A__ is an active command reference to symbol __B__. Symbol __B__ is an inactive command reference to symbol __C__. Symbol __C__ is the target command object of both symbols __A__ and __B__. Symbol __C__ represents the command object itself.

### Target Command Definition

A target command definition is completely analogous to a *target class*.

A target command definition is found by following the redirections, that lead to a symbol’s command definition.

When you want to find the definition of a command, and the command is actually a command reference, you first need to follow all object reference redirections, to find the target command object. When you found the target command object, you can find the target command definition, by following one class redirection. Do not follow more than one class redirection, because if a definition points out a definition again, then the second definition is *another* command object, that the first definition is just *based* on. If the definition is a command reference itself, you might follow all object redirections to find the target *definition* object. Then you have found the target command definition. That’s where redirection following ends. If the definition object has a definition itself, you might be tempted to follow the definition object’s class redirections as well, to find the final target definition, but you should not do that. If a definition object has a definition itself, then the definition object is only based on another definition, but it *is* an object of its own. An object redirection is just a much tighter bond like that, than a class redirection.

#### Diagram

To find the target definition, you first follow *all* the object redirections, then *one* class redirection, then *all* the object redirections and there it ends.

![](images/4.%20Command%20Redirection.010.png)

It might not matter if whether it is a diamond, that can be executed, or a square, that can not be executed.

If the definition has a definition as well, this might not redirect the original command object’s definition, because the second definition is *another* definition object, that the first definition is just *based* on. An object redirection is just a much tighter bond, than a class redirection.

![](images/4.%20Command%20Redirection.011.png)

The target definition of the first object reference is the symbol __Command Definition__, not the symbol __Command definition’s command definition__. The same counts for the diagram below.

![](images/4.%20Command%20Redirection.012.png)

### Recursion

#### Concept

Recursion in commands happens when a command contains a call to the same command definition again.

It can also occur when one command calls another command and the other command potentially calls the first command again.

In fact, in any string of commands, that somewhere along the line calls the first command again, all the commands in the string are called recursive.

The *point* of recursive execution is that it is not endlessly recursive after all. At some point, a potential execution should not be executed, in order to exit the seemingly endless recursion.

The problem with endless recursion is solved, by the fact, that private contents of an executable object are only created just before it is actually going to execute.

When a command definition contains a call to the same command definition, then the call might not contain any private content yet, because it is not executing yet.

When a command call contains a call to the same command definition, then the call also might not contain any private content yet, before it executes.

Only when the call actually executes, you can see private contents inside the recursive call. So only when recursive calls are actually busy executing, this recursive repetition is present in the system.

So only creating private content just before a command actually executes solves the problem of endless recursion.

#### Diagram

Recursion in commands happens when a command contains a call to the same command definition again.

![](images/4.%20Command%20Redirection.013.png)

The recursion is usually conditional, for instance by putting a break on it using an __If__ statement:

![](images/4.%20Command%20Redirection.014.png)

Recursion can also occur when one command calls another command and the other command potentially calls the first command again.

![](images/4.%20Command%20Redirection.015.png)

The problem with endless recursion is solved, by the fact, that private contents of an executable object are only created just before it is actually going to execute.

When a command definition contains a call to the same command definition, then the call might not contain any private content yet, because it is not executing.

![](images/4.%20Command%20Redirection.014.png)

The call in the __then__ clause might not execute, so shows no private contents. Might the __then__ clause be executing, then the diagram might look like this:

![](images/4.%20Command%20Redirection.016.png)

But that never happens, because an inactive command object never executes.

When a command call contains a call to the same command definition, then the call also might not contain any private content yet, before it executes.

![](images/4.%20Command%20Redirection.017.png)

The call on the left contains a call to the same definition, but it shows no private content, because it is not running yet.

The picture below displays a call to a *conditionally* recursive command:

![](images/4.%20Command%20Redirection.018.png)

Only when the __then__ clause in the call on the left is actually executed, the call’s private contents are created *and* visible in the diagram.

![](images/4.%20Command%20Redirection.019.png)

So only when recursive calls are actually busy executing, you this recursive repetition is visible in the system.

Here is a diagram of a call to a command that delegates to another command, that delegates to the first command again. The two command definitions are on the right, the calls are on the left:

![](images/4.%20Command%20Redirection.020.png)

The call on the right might be executing, but its call inside the __then__ clause is not executing yet. Only when the __then__ clause is executed, the private contents of the diamond inside the __then__ clause are created *and* visible in the diagram.

![](images/4.%20Command%20Redirection.021.png)

Yes, there are a lot of class lines, but each separate call has a separate class line to the right definition. If there is a recursive command running, then each execution of the same command has a separate execution symbol, because there might be an execution contained in an execution, contained in an execution, etcetera.

### Loose Ideas about Command Redirection

#### Ideas (about Target Command Object)

(Out of the original Symbol documentation)

##### Execution Trace

To find the execution you do the following.

![](images/4.%20Command%20Redirection.022.jpeg)

What you do is that you follow reference lines until you encounter a symbol without a reference line. The last symbol in the trace to be a *diamond* is the target execution.

Tracing the execution target only seems to be relevant when the source symbol is a diamond. It usually is. Usually you’ll only do this trace for a diamond. However, the target execution is also relevant for a square, because if a square’s redirection has a diamond in it, any call to the square is a call to the same execution.

##### Tracing Command Aspects

Even though there are only *two* line types for command symbols, there are *three* aspects of a command symbol to trace:

- Execution
- Definition
- Interface

A definition is a lot like the type of the command, while an execution is an instance of the command.

###### Redirecting to an Execution

A lot of times you might redirect an execution, but you won’t redirect *to* an execution.

![](images/4.%20Command%20Redirection.023.jpeg)

By redirecting to an execution, it is possible for multiple symbols to represent the same single execution.

![](images/4.%20Command%20Redirection.024.jpeg)

Also note that when redirecting to an execution, the definition is always the same execution.

#### Ideas (about Target Command Definition)

(Out of the original Symbol documentation)

##### Definition Trace

The definition trace is quite easy: follow reference lines until you bump into a symbol without a reference line. That symbol’s the definition

![](images/4.%20Command%20Redirection.025.jpeg)

##### Execution-Definition Trace

Just as with the object-type trace, the execution trace requires you to find the definition anyway, so when you need both, the execution trace might suffice. It’s called a *execution-definition trace* when you use an execution trace to find both execution and definition.


### Loose Ideas about Recursion

(Out of the original Symbol documentation)

- Recursive calls... hmm... advanced issue. Hoef je je klomp niet over te breken.

    - Maar lijkt een Execution basics. Hmm… de term Execution Basics is niet goed genoeg dan. De term basics is niet goed. Execution Facts... nah.

