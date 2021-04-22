Circular Language Construct Drafts | From Spec
==============================================

Commands Construct Drafts
-------------------------

`[ Preliminary documentation ]`

- [Sub-Commands in a Diagram](#sub-commands-in-a-diagram)
- [Parent Controls Its Sub-Executions](#parent-controls-its-sub-executions)
    - [Sub-Commands Are Never Referenced](#sub-commands-are-never-referenced)
    - [Beware of Active Command References in Commands](#beware-of-active-command-references-in-commands)
    - [Sub-Commands Not Manually Started](#sub-commands-not-manually-started)
- [Loose Ideas](#loose-ideas)

### Sub-Commands in a Diagram

`<< terminology >>`  

Sub-commands `are` active commands `contained` inside a parent command. `You can` encounter them inside `any` command symbol: both active and inactive commands symbols `can` contain sub-commands. `The` sub-commands `are` *active* commands: command calls, active clauses or active command references.

Below `is` a picture of two sub-commands inside an inactive command:

![](images/1.%20Commands%20Main%20Concepts.048.png)

`The` __Parent Command__ `is` an inactive command, because it `is` a square. In `the` diagram above, `the` __Parent Command__ `contains` two sub-commands. `The` sub-commands `are` displayed as diamond shapes. One of `the` sub-commands `is` a call, because it `has` a dashed line `going` outside `the` __Parent Command__, `tying the` sub-command to its command definition. `The` other sub-command `is` an *active clause*, because it `might not` redirect its command definition.

Below `is` a picture of two sub-commands inside an active command:

![](images/1.%20Commands%20Main%20Concepts.049.png)

It `is the same` picture as `the` other diagram, `only now the` __Parent Command__ `is` an executable command symbol, `not` an inactive command.

### Parent Controls Its Sub-Executions

`<< rule rich >>`

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

Active clauses and command calls inside another command and are never referenced, because a command has to have full control over the execution of its sub-commands.

![](images/6.%20Comands%20Misc%20Issues.001.png)

If you could reference an active command inside a command, then the sub-command could be prematurely executed through that reference. Therefore sub-commands are never referenced.

It is *not* the rule, that command calls can *never* be referenced. It’s just that command calls *inside another command* can not be referenced. When a command call resides in an object, the command call *can* be referenced, to for instance allow a user to carry around a reference to an active command, executing on a site somewhere.

![](images/6.%20Comands%20Misc%20Issues.002.png)

So a command call inside an object can be referenced, but a command call inside another command can not be referenced.

Not being able to reference sub-commands might not mean, that you can use it as a class, because a class reference is also a reference. 

![](images/6.%20Comands%20Misc%20Issues.003.png)

This might also put the sub-command in danger of being prematurely executed, because you could establish an active reference to the class of another command object and execute it.

To not cause any confusion, sub-commands are made __Private__. 

![](images/6.%20Comands%20Misc%20Issues.004.png)

Do not change the rule to *sub-commands are always private*, because this might not fully solve the parent command’s control over its sub-commands’ execution. By just making them private, the parent command could still pass a reference to a sub-command.

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

If the external execution won’t finish, then the referring procedure is stuck.

If the external command object is an inactive command object, it might never execute, and the command might truly be stuck. A warning should be generated then.

![](images/6.%20Comands%20Misc%20Issues.009.png)

This also has consequences for setting parameters for the active command reference. If it is already executing or has already executed, then you can not overwrite the parameters. This may mean, that it might simply not be allowed to set parameters for an active command reference at all.

It is *not* the rule, to beware of any active command reference. It is the rule to just always beware of them in a *parent command*. An *object* can contain an active command reference, in order to for instance allow a user to carry around a reference to an active command, executing on a site somewhere.

![](images/6.%20Comands%20Misc%20Issues.010.png)

#### Sub-Commands Not Manually Started

This is a rule for enforcement of control of a parent command over the execution of its sub-commands.

Sub-commands are never manually started by a user. Then there is no way for a user to run the sub-command at any arbitrary moment, and the parent command might keep control over the execution of its sub-commands.

### Loose Ideas

`<< rule rich >>`  

Expected behavior might be that a command call might only run once.

-----

`<< rule rich >>`  

When a call might be placed directly inside an *object,* it might* be a question what might actually happen to it. It may be an idea, that the command might only be run manually. Another idea might be, that those calls might run just after the object was created (perhaps a bit like constructors from object oriented programming).

-----

`<< rule rich >>`  

A command reference may commonly be inactive. But a command reference might also be active.

-----

`<< rule rich >>`  

`Both the` command reference and its target `can` be `either` active or inactive.

-----

`<< rule rich >>`  

An *active* reference to an *inactive* command `might not` be executed. `The` `final` target of object redirections `is the` object itself, and when it `is` inactive, `the` command object `can not` be executed, `but only function` as a prototype.

`You can not` execute an *active* command object through an *inactive* command reference `either`. But an active reference to an inactive reference to an active command `*can*` be executed.

-----

`<< rule rich >>`  

In Circular command references and their target commands could in theory be either inactive or executable.

![](images/1.%20Commands%20Main%20Concepts.025.png)

It `might not matter` whether it `is` squares or diamonds, `because the only` difference between a square and a diamond, `is` that a square `can not` be executed and a diamond `*can*`.

-----

`<< rule rich >>`  

A clause `might not` redirect its definition, because then `it might` be a command call.

-----

`<< rule rich >>`  

A clause `might not` redirect its object, because then `it might` be a command reference.

-----

`<< rule rich >>`  

A clause `is never` situated inside an object, or `it might` not be a clause.

-----

`<< rule rich >>`  

Active clauses, command calls and active command references in parent commands `are always` private, because `you can not` reference a sub-command.

![](images/1.%20Commands%20Main%20Concepts.052.png)

But *inactive* clauses `*can*` be referenced and might be made public.

![](images/1.%20Commands%20Main%20Concepts.053.png)

-----

`<< rule rich >>`  

Only when an executable object `is actually` executed, it `is` called an execution. When an executable object `is` not executing yet, it `is still only` a *potential* execution.

-----

`<< rule rich >>`  

A command, that might be used as a definition, `is usually` not executable. Only `individual` calls to `the` command, that `use the` command as a definition, might be executable. If a command definition `is` executable `after all`, then it `is clearly` mentioned, that it `is` an *active* command definition, because it might be a special situation.

-----

`<< rule-rich >>`  

A command reference `is` considered data. A command reference in a parent command `is` considered data of `the` parent command, `even when` it `is` active, `in case of which` it `*is*` considered a sub-command `but a special` form of it. Even though it `executes`, it `is still` a reference to an executable object `*elsewhere*`. Only `the` *pointer* part `is the` data. Command references `are` *data* that can be *private* or *public*.

-----

`<< rule rich >>`

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

`<< rule rich >>`

Command Basics,  
2008-08-31

For instance: the rule ‘sub-commands are never referenced’, may be changed to being able to reference sub-commands after all, but never to be able to execute a sub-command through a reference, even if the reference is active. But this change of rules is just an example. It might prove not to be practical after all.  
\> Perhaps change that rule for real.

JJ

