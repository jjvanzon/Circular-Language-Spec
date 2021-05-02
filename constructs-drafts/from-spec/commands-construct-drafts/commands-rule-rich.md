Circular Language Construct Drafts | From Spec
==============================================

Commands Rule Rich
------------------

`[ Deprecated documentation ]`

__Contents__

- [Introduction](#introduction)
- [Parent Controls Its Sub-Executions](#parent-controls-its-sub-executions)
    - [Sub-Commands Are Never Referenced](#sub-commands-are-never-referenced)
    - [Sub-Commands Private?](#sub-commands-private)
    - [Beware of Active Command References in Commands](#beware-of-active-command-references-in-commands)
    - [Sub-Commands Not Manually Started](#sub-commands-not-manually-started)
- [Command Assignment Rule Rich](#command-assignment-rule-rich)
- [Executor & Execution](#executor--execution)
- [Diamonds Execute When Direct Parent Executes](#diamonds-execute-when-direct-parent-executes)
- [Diamonds Can only be Directly Inside a Command Symbol, Diamonds Can’t be Directly Inside an Object Symbol](#diamonds-can-only-be-directly-inside-a-command-symbol-diamonds-cant-be-directly-inside-an-object-symbol)
- [You Can Only Access Members of a Diamond](#you-can-only-access-members-of-a-diamond)
- [You Can Only Access Members of a Diamond, while the Diamond is executing](#you-can-only-access-members-of-a-diamond-while-the-diamond-is-executing)
- [Accessing a Diamond Member During a Call](#accessing-a-diamond-member-during-a-call)
- [Passing an Object Reference to a Command](#passing-an-object-reference-to-a-command)
- [Command Can Set Object Reference itself Too](#command-can-set-object-reference-itself-too)
- [Argument Assignment Requires Reading in Prolog!](#argument-assignment-requires-reading-in-prolog)
- [Commands to Commands, Objects to Object](#commands-to-commands-objects-to-object)
- [Pointing to Diamonds](#pointing-to-diamonds)
- [Forming New Subdivision](#forming-new-subdivision)
    - [Old Subdivision](#old-subdivision)
    - [New Subdivision](#new-subdivision)
- [Nested Commands Rule Rich](#nested-commands-rule-rich)
- [Loose Ideas](#loose-ideas)

### Introduction

A struggle to make it work seems noticeable here. To make the notation work for commands like for objects. Checking if commands can retain their integrity, when subjected to this diagram notation. What might be expressed with this diagram notation, would it be *valid* for commands? Can this diagram notation be *sufficient* for expressing different command situations that might be imagined?

The answer to these quesions seems to be 'yes'.

The Circular Language Spec itself might be more about *notation* and *meaning*, rather than rules and constraints. But texts about the struggle to make it work may still be retained here in this article inside *Construct Drafts*.

### Parent Controls Its Sub-Executions

A parent command needs full control over the execution of its sub-commands. The parent command makes the decision about the exact moment, that the sub-command runs.

To enforce this general rule, three rules are imposed to make sure a parent command never looses control over the execution of one of its sub-commands:

- Sub-commands are never referenced
- Beware of active command references in commands
- Sub-commands are never manually started

With these rules, there’s no way to point to sub-commands, and the point is made, that you might beware when you are using active command references inside commands. And there is no way for a user to start the sub-command at any arbitrary moment. There’s no way in, and you might be aware of the way out, so the sub-command is always an isolated command object, the execution of which is initiated by the parent command, or if it is an active command reference, you might be aware of giving up control. An external force can not execute the sub-command it before the parent command chooses to execute it, unless you use an active command reference.

Any command object, potentially executed within another command definition, needs to be protected against this risk. The rules to protect the system against this hazard could be changed in the future. But the *reason* for this protection might not change.

For instance: the rule ‘sub-commands are never referenced’, may be changed to being able to reference sub-commands after all, but never to be able to *execute* a sub-command through a reference, even if the reference is active. But this change of rules is just an example. It might prove not to be practical after all.

#### Sub-Commands Are Never Referenced

This is a rule for enforcement of control of a parent command over the execution of its sub-commands.

Active nested commands and command calls inside another command and are never referenced, because a command has to have full control over the execution of its sub-commands.

![](images/6.%20Comands%20Misc%20Issues.001.png)

But *inactive* nested commands might still be referenced and might be made public.

![](images/1.%20Commands%20Main%20Concepts.053.png)

If you could reference an active command inside a command, then the sub-command could be prematurely executed through that reference. Therefore sub-commands are never referenced.

It is *not* the rule, that command calls can *never* be referenced. It’s just that command calls *inside another command* can not be referenced. When a command call resides in an object, the command call *can* be referenced, to for instance allow a user to carry around a reference to an active command, executing on a site somewhere.

![](images/6.%20Comands%20Misc%20Issues.002.png)

So a command call inside an object can be referenced, but a command call inside another command can not be referenced.

Not being able to reference sub-commands might not mean, that you can use it as a class, because a class reference is also a reference. 

![](images/6.%20Comands%20Misc%20Issues.003.png)

This might also put the sub-command in danger of being prematurely executed, because you could establish an active reference to the class of another command object and execute it.

#### Sub-Commands Private?

To not cause any confusion, sub-commands might be made __Private__. 

![](images/6.%20Comands%20Misc%20Issues.004.png)

Active nested commands, command calls and active command references in parent commands may be private, because sub-command might not be referenced.

Perhaps do not change the rule *sub-commands are never referenced* to *sub-commands are always private*, because this might not fully solve the parent command’s control over its sub-commands’ execution. By just making them private, the parent command could still pass a reference to a sub-command.

![](images/6.%20Comands%20Misc%20Issues.005.png)

That might make the parent *give up control* over the execution of a sub-command. This is something, that might not be allowed. Now that you can *never reference a sub-command*, this control is restored.

![](images/6.%20Comands%20Misc%20Issues.006.png)

#### Beware of Active Command References in Commands

This is a rule for enforcement of control of a parent command over the execution of its sub-commands. It might not impose any restriction, but just advises you to beware of what you are doing, when you are using an active command reference inside a command.

When you are using an active command reference inside a command, then you are giving up the full control over this sub-command’s execution.

You might be aware, that when you use an active command reference, the active command reference may already have been executed.

![](images/6.%20Comands%20Misc%20Issues.007.png)

Or that you may be *waiting* on an external execution to finished.

![](images/6.%20Comands%20Misc%20Issues.008.png)

If the external execution won’t finish, then the referring command is stuck.

If the external command object is an inactive command object, it might never execute, and the command might truly be stuck. A warning should be generated then.

![](images/6.%20Comands%20Misc%20Issues.009.png)

This also has consequences for setting parameters for the active command reference. If it is already executing or has already executed, then you can not overwrite the parameters. This may mean, that it might simply not be allowed to set parameters for an active command reference at all.

It is *not* the rule, to beware of any active command reference. It is the rule to just always beware of them in a *parent command*. An *object* can contain an active command reference, in order to for instance allow a user to carry around a reference to an active command, executing on a site somewhere.

![](images/6.%20Comands%20Misc%20Issues.010.png)

#### Sub-Commands Not Manually Started

This is a rule for enforcement of control of a parent command over the execution of its sub-commands.

Sub-commands are never manually started by a user. Then there is no way for a user to run the sub-command at any arbitrary moment, and the parent command might keep control over the execution of its sub-commands.

### Command Assignment Rule Rich

You can only let two command symbols refer to the same object when they are command *definitions*. You can not assign a command object to a command call. This is due to the special object creation behavior of a call. Command calls can never *redirect* their object. They are always *their own* object, and they are only created, when they are running. Command definitions, however, are permanently created objects, and a command definition symbol can redirect its object target.

-----

Object assignment may only have the right effect between command definitions, as they make the command definitions the same command definition object.

-----

The target definition of one command reference or call is assigned as the target definition of another command reference or call. The reference to the original command definition is released. Only when the original command definition might not have any other references anymore, then the original object is deleted. But do not worry; as long as a command definition is part of a module, it means there still is a reference to it and it might not get deleted.

-----

You can only let two command symbols refer to the same target object when they are command *definitions*. You can not assign a command object to a command call. This is due to the special object creation behavior of a call. Command calls can never *redirect* their object. They are always *their own* object, and they are only created, when they are running. Command definitions, however, are permanently created objects, and a command definition symbol can redirect its object target.

### Executor & Execution

Any diamond symbol might be called an executor, since it can execute. A single diamond might execute multiple times. An individual execution of a diamond might be called an *execution*.

It might be ok to call an executor an execution, but perhaps only while it’s executing.

### Diamonds Execute When Direct Parent Executes

A diamond doesn’t execute automatically. It only executes when the parent symbol executes.

![](images/7.%20Commands%20Ideas.039.jpeg)

*A executes only as B executes.*

So diamonds inside squares don’t really execute.

![](images/7.%20Commands%20Ideas.040.jpeg)

But if you call B, then you get the following:

![](images/7.%20Commands%20Ideas.041.jpeg)

Actually, The letters distinguish the different symbols. If you only use letters to distinguish which command definition it’s about, you get the following:

![](images/7.%20Commands%20Ideas.042.jpeg)

So in that sense, diamond A might execute. But not the definition executes, only the call executes.

### Diamonds Can only be Directly Inside a Command Symbol, Diamonds Can’t be Directly Inside an Object Symbol

Because execution can only take place in a command, a diamond can’t be directly inside an object Symbol

![](images/7.%20Commands%20Ideas.043.jpeg)

### You Can Only Access Members of a Diamond

You can (usually) only access members of a diamond, because a square is never created, just like you can’t access members of a non created object.

![](images/7.%20Commands%20Ideas.044.jpeg)

![](images/7.%20Commands%20Ideas.045.jpeg)

### You Can Only Access Members of a Diamond, while the Diamond is executing

Because a diamond is only created when it’s executing, you can only access members when the diamond is in execution.

However, *static* members of a command can be freely accessed through any square or diamond that represents it, even when it is not executing.

(Some members of a command can be static. In that case the member belongs to the command definition. Those member are the same for any reference or call to a command.)

### Accessing a Diamond Member During a Call

So how might you access a diamond member *during* a call? Well, usually only commands called by the executing diamond can access the call parent.

![](images/7.%20Commands%20Ideas.046.jpeg)

Diamond A executes, then diamond B executes and accesses a member of diamond A. It’s not the command definition, the square, that accesses a member of diamond A, but it’s the specific call to the command that access diamond A. So usually you’ll only see child diamonds accessing parent diamonds, on top of the more common situation of write access before a call and read access after.

Multi-threading, which is basically multiple things running at the same time, may also make you able to access a diamond in execution, but this might not usually be a good idea. Restrictions might be imposed onto multi-threading to avoid such situations.

![](images/7.%20Commands%20Ideas.047.jpeg)

Two sibling commands are executing at the same time, in different threads, which makes it possible for one executing command to access the other. Thread control makes it possible to avoid such volatile situations.  
(the fact that the diamonds are drawn with thicker lines above, says that they are both in execution. If they wouldn’t be thicker drawn, then the diagram above doesn’t explicitly show that there is a multi-threaded situation. Regarding it single threadedly, the situation above is just the bigger diamond executing first, after which the smaller diamond uses its return value.)

< What happens when two threads try to initiate the same diamond or a thread tries to initiate a diamond that’s already executing? I might want that one figured out. >

< Consider the example of diamond reference to diamond in the main argument reference example. >

### Passing an Object Reference to a Command

![](images/7.%20Commands%20Ideas.048.jpeg)

When you pass an object reference to a command, the command can access the object.  
In the situation above it seems the command could access the object anyway (because a command can access everything accessible to the object that contains it). It *can*, but in this case the *caller* decides which object to point to, not the called.

### Command Can Set Object Reference itself Too

When the caller (the parent diamond) sets the line, then the caller decides which object the call might refer to.

So lines going out of a diamond aren’t necessarily lines set by the caller.  
Commands can’t set line going *into* the square themselves. Those are always set by the caller.

It’s important that the command itself sets lines, because the line targets of command members often serve as the output values of the command.

< I don’t know a notation to distinct sets by the caller and sets by the call. Well... in a more explicit notation you might see that the caller calls the set or the called calls the set. >

### Argument Assignment Requires Reading in Prolog!

Argument assignment takes place in the *prolog*. But *setting* the argument also requires *getting* the argument. However, getting the argument was said to take place in the *epilog*. For the purpose of *setting* the argument, however, *getting* happens in the *prolog*.

An assignment call:

![](images/7.%20Commands%20Ideas.056.jpeg)

*consults* the argument to *write*: *reads* the argument to *write*.

Assignment of arguments simply *might* take place in the prolog, even though they require reading the arguments.

Assignment commands are fundamental commands of the Symbol Language and behave much different from other commands.

### Commands to Commands, Objects to Object

< 2008-10-12 I am not sure I should impose this rule or not >

Commands can be tied only to commands.

![](images/7.%20Commands%20Ideas.060.png)

Objects can be tied only to objects.

![](images/7.%20Commands%20Ideas.061.png)

Formally, there can be no lines connecting objects and commands:

![](images/7.%20Commands%20Ideas.062.jpeg)

So then object symbols point only to object symbols and command symbols only to command symbols.

### Pointing to Diamonds

`<< interpretation issues >>`

When is a diamond executed multiple times?

A diamond pointing to another diamond: it may be a call to a call. both diamonds may represent the same call. They might never execute individually.

### Forming New Subdivision

These seem fragments of an attempt to re-subdivide topics formerly inside the original Symbol documentation from 2004.

#### Old Subdivision

...

- Execution basics: 
    - simple issues regarding execution
    - for instance, diamond only inside a command symbol
    - Stuff like that. Simple issues that you can easily understand.

-----

- Wanneer wordt een diamond meerdere keren geexecute?

#### New Subdivision

...

- Execution Basics
    - Simple issues regarding execution < Which precisely? >
    - For instance, diamond only inside a command symbol
    - Stuff like that. Simple issues that you can easily understand.
    - Diamond pointing to another diamond

- Wanneer wordt een diamond meerdere keren geexecute?

?:

Line of connected diamonds change simultaneously

### Nested Commands Rule Rich

A nested command might not redirect its definition, because then it might be a command call.

A nested command might not redirect its object, because then it might be a command reference.

A nested command `is never` situated inside an object, or it might not be a nested command.

### Loose Ideas

Expected behavior might be that a command call might only run once.

-----

When a call might be placed directly inside an *object,* it might* be a question what might actually happen to it. It may be an idea, that the command might only be run manually. Another idea might be, that those calls might run just after the object was created (perhaps a bit like constructors from object oriented programming).

-----

A command reference may commonly be inactive. But a command reference might also be active.

-----

`Both the` command reference and its target `can` be `either` active or inactive.

-----

An *active* reference to an *inactive* command `might not` be executed. `The` `final` target of object redirections `is the` object itself, and when it `is` inactive, `the` command object `can not` be executed, `but only function` as a prototype.

`You can not` execute an *active* command object through an *inactive* command reference `either`. But an active reference to an inactive reference to an active command `*can*` be executed.

-----

In Circular command references and their target commands could in theory be either inactive or executable.

![](images/1.%20Commands%20Main%20Concepts.025.png)

It `might not matter` whether it `is` squares or diamonds, `because the only` difference between a square and a diamond, `is` that a square `can not` be executed and a diamond `*can*`.

-----

Only when an executable object `is actually` executed, it `is` called an execution. When an executable object `is` not executing yet, it `is still only` a *potential* execution.

-----

A command, that might be used as a definition, `is usually` not executable. Only `individual` calls to `the` command, that `use the` command as a definition, might be executable. If a command definition `is` executable `after all`, then it `is clearly` mentioned, that it `is` an *active* command definition, because it might be a special situation.

-----

A command reference `is` considered data. A command reference in a parent command `is` considered data of `the` parent command, `even when` it `is` active, `in case of which` it `*is*` considered a sub-command `but a special` form of it. Even though it `executes`, it `is still` a reference to an executable object `*elsewhere*`. Only `the` *pointer* part `is the` data. Command references `are` *data* that can be *private* or *public*.

-----

Command Basics,

The following Basic Command articles do not have a diagram expression article:

- Execute Once
- Resolution When Not Allowed For Commands
- Parent Controls Its Sub-Executions
- Sub-Commands Not Manually Started
- No Overhead of Command Creation
- No Circular Command Creation

JJ

-----

Command Basics,  
2008-08-31

For instance: the rule ‘sub-commands are never referenced’, may be changed to being able to reference sub-commands after all, but never to be able to execute a sub-command through a reference, even if the reference is active. But this change of rules is just an example. It might prove not to be practical after all.  
\> Perhaps change that rule for real.

JJ

-----

When a command is called, the contained command *references* are *not* called.

![](images/7.%20Commands%20Ideas.018.jpeg)

When __A__ is called, __B__ and __D__ are called, but not __C__.

-----

(*Implicit* embedded command reference causes a separate implicit call.)

-----

A diamond can be executing. Only during the execution of the diamond, lines between its non static children can be real. If the diamond isn’t executing, or it’s not a diamond, but a square, lines between the non static children are suggestive. Only lines between static members in such cases, can be real.

-----

- Diamond may only represent a single execution per definition call.

-----

What might these imply? More brain teasers.

- Diamond pointing to another diamond.
- Line inside connected diamonds changing simultaneously.
- Paradox: Parameter assignments involve consults of parameters in prolog of command call, while consults are usually always in epilog.
- Access during execution
    - By owner
    - By child executions (~ is this the proper place for this?)
        - The callees of a diamond can access the caller's members if given references to them
