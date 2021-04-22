Circular Language Broader View | From Spec
==========================================

Commands | Broader View
------------------------

`[ Preliminary documentation ]`

__Contents__

- [Sub-Commands](#sub-commands)
- [Execute Once](#execute-once)

### Sub-Commands

A parent command `automatically executes` its sub-commands. After a sub-command `completes, the` process `returns` to `the` parent command, which `might` then continue, `executing the` next sub-command.

Inside a command, `usually just` more commands `are` invoked.

There `are only a few` commands that `do` something other than execute other commands. Those `are special` commands, that `perform` a machine instruction: an operation that `is` executed by `the` CPU, `the` central processing unit of `the` computer.

On top of those `special` commands, a `few basic` commands exist, like __If__’s and __For__ loops, that control `the` flow of a program, making `the` next command to call dependent on a condition.

But `basically`, a command `just calls` more commands. Machine instructions, arithmetic operators, comparative and Boolean algebra, assignments, and execution control statements such as __If__ and __For__, `are` *`all` just commands*.

Apart from sub-commands, a command `can` also contain data.
(Inactive clauses and inactive command references for instance are also considered data, and `are` not sub-commands, because they `do not` execute.)


### Execute Once

`<< details >>`  
a command object might only execute *once*. A command object may represent a single execution. An execution might be created and dormant until it might be run. This might be a chance to set the input of the command. After a command was run, the execution might stay created while it may still be referenced, so output might be read, until `everybody` might be done with it. When the executable object might not be referenced anymore, it might be destroyed. A command object might not be executed twice: to run a command again, a new command object might be created, that may have the same *definition*. In an attempt to execute the same command symbol twice, what might happen instead, is that the old object may be released, and a new object could be created in its place. A reason why a command object might only be executed once, may be that this might give all the referrers a chance to read `the` execution’s output, `whenever` they want, `without` it `being` overwritten by new output. A command object `stays` created for `as long as` it `is being` referenced, so `everybody can` read `the` output of `the` command. `The` command object `might only` be `destroyed` when `nothing refers` to it `anymore`.