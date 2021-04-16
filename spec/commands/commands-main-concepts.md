Encircle Language Spec | Commands
=================================

Main Concepts
-------------

`[ Preliminary documentation ]`

__Contents__

- [Introduction](#introduction)
- [Diagram Elements](#diagram-elements)
- [Derived Constructs](#derived-constructs)
- [Command Definitions](#command-definitions)
- [Command Calls](#command-calls)
- [Command References](#command-references)
- [Code Blocks](#code-blocks)
    - [Code Blocks Details](#code-blocks-details)
- [Local Function](#local-function)
- [Clauses](#clauses)
- [Lambda Expression](#lambda-expression)
- [Parameters and Return Values Not Covered](#parameters-and-return-values-not-covered)
- [Implementation](#implementation)
- [Conclusion](#conclusion)
- [Details](#details)
    - [Command Definition Synonyms](#command-definition-synonyms)
    - [Definition Line Synonyms](#definition-line-synonyms)
    - [Executable Command Synonyms](#executable-command-synonyms)
    - [Command Call Synonyms](#command-call-synonyms)
    - [Command Reference Synonyms](#command-reference-synonyms)
- [`<< creation behavior of commands >>`](#-creation-behavior-of-commands-)
    - [Command Call Behavior](#command-call-behavior)
    - [Clause Creation Behavior](#clause-creation-behavior)
    - [Sub-Commands](#sub-commands)
    - [Reading & Writing Parameters](#reading--writing-parameters)
    - [Execute Once](#execute-once)
- [`<< details >>`](#-details-)
    - [Commands Edge Cases](#commands-edge-cases)
        - [Changing Inactive to Executable](#changing-inactive-to-executable)
            - [Diagram Notation](#diagram-notation)
    - [Sub-Commands in a Diagram](#sub-commands-in-a-diagram)
    - [Command References Inside Commands](#command-references-inside-commands)
    - [Executables & Executions](#executables--executions)
        - [Diagram Notation](#diagram-notation-1)
- [`<< explains other technology >>`](#-explains-other-technology-)
- [`<< pointers >>`](#-pointers-)
    - [Command Reference Pointer to Pointer Situations](#command-reference-pointer-to-pointer-situations)
- [`<< parameters >>`](#-parameters-)
- [`<< basic diagram elements >>`](#-basic-diagram-elements-)
    - [No Dashed Squares?](#no-dashed-squares)

### Introduction

Commands may be objects, that so happen to be *executable*. Commands could be actions, procedures and processes, that a computer might perform. They might be displayed in a diagram as squares and diamond shapes:

<img src="images/1.%20Commands%20Main%20Concepts.001.png" width="50" />
<img src="images/1.%20Commands%20Main%20Concepts.002.png" width="50" />

### Diagram Elements

The concept of commands may boil down to a limited set of characteristics.

A *diamond* in Encircle may express a command that might be __executable__.

<img src="images/1.%20Commands%20Main%20Concepts.002.png" width="50" />

An executable command might be carried out, while one that is not executable, might stay asleep.

A *square* in Encircle might symbolize that the command is __not executable__.

<img src="images/1.%20Commands%20Main%20Concepts.001.png" width="50" />

Containment is a way to express a relationship. One symbol might __contain__ another:

<img src="images/1.%20Commands%20Main%20Concepts.003.png" width="100" />

A *solid line* between symbols might mean that one command is a __reference__ to another:

<img src="images/1.%20Commands%20Main%20Concepts.004.png" width="100" />

A *dashed line* between command symbols might make one command a kind of copy of another:

<img src="images/1.%20Commands%20Main%20Concepts.005.png" width="80" />

It might also be said, that a command might be used as a __prototype__ for another command.

If a command might *only* be used as a prototype, it might be drawn with a *dashed border*:

<img src="images/1.%20Commands%20Main%20Concepts.006.png" width="80" />

(Using dashed shapes is still a bit of an open discussion.)

A command may have a *name*:

<img src="images/1.%20Commands%20Main%20Concepts.007.png" width="140" />

It might also be *nameless.*

<img src="images/1.%20Commands%20Main%20Concepts.001.png" width="50" />

Here is an attempt to summarize these traits that commands might have:

- __(not) executable__
- __(not) named__
- __containment__
- __references__
- __prototypes__ (or "definitions")
  
### Derived Constructs

Constructs that might be known from other programming languages, may have a reasonably unique expression using combinations of these more basic elements from Encircle mentioned above. Here follows an attempt to accompany this claim with some examples.

### Command Definitions

A command definition might describe the structure and behavior of another command.

It may look as follows in another programming language:

```c#
void MyDefinition()
{
}
```

Command definitions themselves might not necessarily execute. Just copies of it, more likely. Its *not executing* may be expressed with a square: 

<img src="images/1.%20Commands%20Main%20Concepts.008.png" width="50" />

If a command might only be used or usable as a definition, it might be drawn with a *dashed border*:

<img src="images/1.%20Commands%20Main%20Concepts.006.png" width="70" />

(Though dashed shape notation is still a bit of an open discussion.)

A definition might also have a *name*:

<img src="images/1.%20Commands%20Main%20Concepts.009.png" width="140" />

When used, a command definition may be pointed to by a *dashed line*:

<img src="images/1.%20Commands%20Main%20Concepts.010.png" width="210" />

That way another symbol might use `MyDefinition` as a *prototype*.

So a command definition might be symbolized by:

- square
- named
- dashed
- pointed to with dashed lines

because it may be:

- not executable (directly)
- named
- used as a prototype
 
### Command Calls

A command definition might be *called* multiple times.

In a different programming language a command call might look as follows:

```c#
MyCommand();
```

A command call may *execute*, so it might be symbolized with a diamond shape:

<img src="images/1.%20Commands%20Main%20Concepts.002.png" width="50" />

A call may point out a definition, so it might have a *dashed line* pointing away from it:

<img src="images/1.%20Commands%20Main%20Concepts.011.png" width="120" />

A call might be placed *inside* a parent command.

<img src="images/1.%20Commands%20Main%20Concepts.012.png" width="140" />

The call itself might remain *nameless*.

So a command call might be symbolized by:

- diamond
- nameless
- contained in a square
- dashed line pointing away from it

because it may be:

- executable
- nameless
- contained inside a definition
- uses another command as a definition
  
### Command References

A command could be *pointed to*.

This may look as follows in another programming language:

```c#
MyCommand
```

So without any decoration with brackets or what have you, it may represent a reference to a command.

A command reference may be a square, to indicate it might not *execute* directly.

<img src="images/1.%20Commands%20Main%20Concepts.008.png" width="50" />

A *solid line* can be used to point out a different command:

<img src="images/1.%20Commands%20Main%20Concepts.013.png" width="400" />

So a command reference might be symbolized by:

- square 
- solid line pointing to another command

because it is:

- not executable (directly)
- a reference

### Code Blocks

Some programming languages might allow code blocks within a command, to group statements together. This might scope variables, so variables inside the block might only be used within that block, for some added safety against programming errors, perhaps.

In another programming language, this might look as follows:

```c#
void MyDefinition()
{
    {
        ...
    }
}
```

The inner braces and its contents might be the code block.

In Encircle, a code block may be *embedded* inside another command:

<img src="images/1.%20Commands%20Main%20Concepts.014.png" width="100" />

The inner command (the code block) might be drawn as a *diamond*: it *executes* if the parent command executes.

A code block might be *nameless*. It might not have any *lines* going towards it or away from it.

A code block might also look like this:

<img src="images/1.%20Commands%20Main%20Concepts.015.png" width="100" />

The previous diagram might show a code block within a definition (a square). This diagram shows the code block while that command is executed.

So a code block might be symbolized by:

- a diamond
- inside another command
- nameless
- no lines pointing to or from it

because it is:

- executable
- contained by another command
- nameless
- not a reference
- not a definition

#### Code Blocks Details

Code blocks might be nested even further:

<img src="images/1.%20Commands%20Main%20Concepts.016.png" width="180" />

Because a code block does not point out a definition, its contents might be arbitrary / decided by its parent command, unlike calls, whose contents might comply with a  definition, that they may call.

Code blocks might freely be used for putting a frame around a piece of code inside a command. In that case that command might still do the same thing:

![](images/1.%20Commands%20Main%20Concepts.033.png)

![](images/1.%20Commands%20Main%20Concepts.034.png)

### Local Function

A local function might be known from other programming languages and may mean a command that is defined within another command.

In a different programming language this might look as follows:

```c#
void MyParentCommand()
{
    void MyLocalFunction()
    {
    }
}
```

In Encircle it might also be a command definition contained within another command definition.

<img src="images/1.%20Commands%20Main%20Concepts.017.png" width="100" />

When peeking at another programming language, a local function seems to be able to have a name.

<img src="images/1.%20Commands%20Main%20Concepts.018.png" width="160" />

It may also be *called* from within its parent command:

<img src="images/1.%20Commands%20Main%20Concepts.019.png" width="200" />

So a local function might be symbolized by:

- a square
- within a square
- with a name
- pointed to by dashed lines (possibly)

because it is:

- not executed directly
- contained in a definition
- has a name
- a prototype / might be called

### Clauses

Clauses might be found as elements of an `if` statement or for instance a `where` clause from querying languages.

This might look as follows in another language:

```c#
if { ... }
```

(This is pseudo code. A full `if` statement may have more parts.)

There might be a bit of an interpretation problem here. A clause in an `if` statement looks a bit like a *code block*. Maybe it could be interpreted as such.

<img src="images/1.%20Commands%20Main%20Concepts.020.png" width="100" />

It also may look a bit like a nameless local function that you might pass a reference to, to the `if` statement:

<img src="images/1.%20Commands%20Main%20Concepts.021.png" width="170" />

The following was another attempt to define what a clause might be in Encircle: *a command inside another command with no lines going to or from it*. That definition might not cover it. It might be just terminology quibbles. Later on it seemed to not matter much. Command-like constructs from other languages seem to be expressible within Encircle perhaps in a reasonable fashion.

So a clause might be expressed with:

- a square
- inside a diamond
- that might connect to another square
- with a solid line

because it is:

- not executable (directly)
- passed to another command or statement
- might be a command reference

### Lambda Expression

A lambda expression might be found in other programming languages as sort of a short notation for a function, embedded inside other statements.

In another programming language this might look as follows:

```c#
Where(x => x.IsChecked)
```

Minus the details:

```c#
Where(...)
```

So the `...` might be the lambda expression.

Honestly said, in Encircle there might not be a way to distinguish it from *clauses*.

<img src="images/1.%20Commands%20Main%20Concepts.022.png" width="100" />

Or:

<img src="images/1.%20Commands%20Main%20Concepts.023.png" width="160" />

### Parameters and Return Values Not Covered

Symbolizations for parameters and return values might be missing in much of these texts. Those are intended to be covered by another chapter: "Parameters".

### Implementation

The implementation of a command might be defined as the private contents of a command. Here is an attempt to demonstrate that visually:

<img src="images/1.%20Commands%20Main%20Concepts.024.png" width="300" />

The large square might have contents, drawn with thick lines, might represent the command’s *implementation*, because they might be private. The objects inside the large square that are drawn with thinner lines, might be the command’s parameters: its publics. (Notation for *parameters* might be involved in the picture above, but might remain unexplained until the chapter "Parameters".)

### Conclusion

Using the constructs for commands from Encircle, it may seem circumstantial whether a command symbol could be stereotyped as a block, clause, definition, call, etc. It seems to result from the way basic language elements from Encircle relate to each other. Still, it may be relevant to be aware how these symbols from Encircle can be combined to represent constructs from other languages.

### Details

#### Command Definition Synonyms

- prototype
- blue-print
- inactive command
- inactive command symbol
- square
- command definition
- definition

#### Definition Line Synonyms

- command definition line
- call line
- prototype line
- dashed line
- definition line

#### Executable Command Synonyms

- active command
- active command symbol
- diamond
- executable command
- executable command symbol

#### Command Call Synonyms

- execution

#### Command Reference Synonyms

- function pointer
- method reference
- delegate

### `<< creation behavior of commands >>`  

#### Command Call Behavior

`<< creation behavior of commands >>`  
At first a command call might be sort of asleep. That might be when there is a chance to set its parameters. After that the command call might be run.

`<< creation behavior of commands >>`  
If the parent command runs it might automatically executes the calls inside it.

#### Clause Creation Behavior

`<< creation behavior of commands >>`  
A clause `is always` created `as long as the` parent command `is` created. 

#### Sub-Commands

`<< details >>`  
`<< broader perspective >>`  
`<< already covered >>`  
> (in chapter "Introduction" and article "Creation Behavior of Commands")

`<< move >>`  
> (to article "Creation Behavior of Commands")

A parent command `automatically executes` its sub-commands. After a sub-command `completes, the` process `returns` to `the` parent command, which `might` then continue, `executing the` next sub-command.

Inside a command, `usually just` more commands `are` invoked.

There `are only a few` commands that `do` something other than execute other commands. Those `are special` commands, that `perform` a machine instruction: an operation that `is` executed by `the` CPU, `the` central processing unit of `the` computer.

On top of those `special` commands, a `few basic` commands exist, like __If__’s and __For__ loops, that control `the` flow of a program, making `the` next command to call dependent on a condition.

But `basically`, a command `just calls` more commands. Machine instructions, arithmetic operators, comparative and Boolean algebra, assignments, and execution control statements such as __If__ and __For__, `are` *`all` just commands*.

`<< broader perspective >>`
Apart from sub-commands, a command `can` also contain data.
(Inactive clauses and inactive command references for instance are also considered data, and `are` not sub-commands, because they `do not` execute.)

#### Reading & Writing Parameters

`<< creation behavior of commands >>`  
Before a command `is` run `you can mess about` with `the` parameters `all you want`.

During `the` execution of a command `you can not` read or write `anything`.

After a command `has` executed, `you can not` change `the` parameters, `just out of practical reasons`, because it `is more practical` for `the` parameters to `keep` visualizing `the` state they `were` in after `the` command `was` run.

- Before execution `you can` read and write.
- During execution `you can not` read or write.
- After execution `you can` only read.

#### Execute Once

`<< creation behavior of commands >>`  
`<< details >>`  
a command object might only execute *once*. A command object may represent a single execution. An execution might be created and dormant until it might be run. This might be a chance to set the input of the command. After a command was run, the execution might stay created while it may still be referenced, so output might be read, until `everybody` might be done with it. When the executable object might not be referenced anymore, it might be destroyed. A command object might not be executed twice: to run a command again, a new command object might be created, that may have the same *definition*. In an attempt to execute the same command symbol twice, what might happen instead, is that the old object may be released, and a new object could be created in its place. A reason why a command object might only be executed once, may be that this might give all the referrers a chance to read `the` execution’s output, `whenever` they want, `without` it `being` overwritten by new output. A command object `stays` created for `as long as` it `is being` referenced, so `everybody can` read `the` output of `the` command. `The` command object `might only` be `destroyed` when `nothing refers` to it `anymore`.

### `<< details >>`

`<< detail >>`  
Expected behavior might be that a command call might only run once.

`<< detail >>`  
When a call might be placed directly inside an *object,* it might* be a question what might actually happen to it. It may be an idea, that the command might only be run manually. Another idea might be, that those calls might run just after the object was created (perhaps a bit like constructors from object oriented programming).

`<< detail >>`  
A command reference may commonly be inactive. But a command reference might also be active.

`<< detail >>`  
`Both the` command reference and its target `can` be `either` active or inactive.

`<< detail >>`  
An *active* reference to an *inactive* command `might not` be executed. `The` `final` target of object redirections `is the` object itself, and when it `is` inactive, `the` command object `can not` be executed, `but only function` as a prototype.

`You can not` execute an *active* command object through an *inactive* command reference `either`. But an active reference to an inactive reference to an active command `*can*` be executed.

`<< detail >>`  
In Encircle command references and their target commands could in theory be either inactive or executable.

![](images/1.%20Commands%20Main%20Concepts.025.png)

It `might not matter` whether it `is` squares or diamonds, `because the only` difference between a square and a diamond, `is` that a square `can not` be executed and a diamond `*can*`.

`<< detail >>`  
`You can not` execute an active command object through an inactive command reference.

![](images/1.%20Commands%20Main%20Concepts.027.png)

`<< detail >>`  
But with an executable reference to an inactive reference to an executable command `you *can*` execute `the` command object `again`.

![](images/1.%20Commands%20Main%20Concepts.028.png)

`<< detail >>`  
A clause `might not` redirect its definition, because then `it might` be a command call.

`<< detail >>`  
A clause `might not` redirect its object, because then `it might` be a command reference.

`<< detail >>`  
A clause `is never` situated inside an object, or `it might` not be a clause.

`<< detail >>`  
Clauses `are` like command definitions, `therefore` they `can` have parameters `just like` command definitions.

`<< detail >>`  
Active clauses, command calls and active command references in parent commands `are always` private, because `you can not` reference a sub-command.

![](images/1.%20Commands%20Main%20Concepts.052.png)

But *inactive* clauses `*can*` be referenced and might be made public.

![](images/1.%20Commands%20Main%20Concepts.053.png)

If `you make` an inactive clause public, `you might` make it an __Object `Out`__ parameter: an object `produced or determined` by `the` command. It `might` be an __Object `Out`__ parameter, that `is` an executable object. That `might` work `just fine`.

`<< details >>`  
Only when an executable object `is actually` executed, it `is` called an execution. When an executable object `is` not executing yet, it `is still only` a *potential* execution.

`<< details >>`  
A command, that might be used as a definition, `is usually` not executable. Only `individual` calls to `the` command, that `use the` command as a definition, might be executable. If a command definition `is` executable `after all`, then it `is clearly` mentioned, that it `is` an *active* command definition, because it might be a special situation.

#### Commands Edge Cases

##### Changing Inactive to Executable

###### Diagram Notation

`<< details >>`  
When `you design` a command definition, `you` might want to do it using an active command object:

![](images/1.%20Commands%20Main%20Concepts.042.png)

and `test` it `once` by `running the` active command definition:

![](images/1.%20Commands%20Main%20Concepts.043.png)

After that `you can` change it to an inactive command definition and `give` it `the appropriate` default values.

![](images/1.%20Commands%20Main%20Concepts.044.png)

If `you decide` to change `the` inactive command definition back to an active command, then `you can not` run it again, because `the` command object `has` `already` run:

![](images/1.%20Commands%20Main%20Concepts.045.png)

`Others might` still have a reference to it `to be` able to read its output.

If `you` want to run `the` command definition again, `you might` make a call to it instead:

![](images/1.%20Commands%20Main%20Concepts.046.png)

If `you change` an inactive command definition to an executable command definition:

![](images/1.%20Commands%20Main%20Concepts.047.png)

then `you can all of a sudden` run it, which may overwrite `the` executable’s default output values.

#### Sub-Commands in a Diagram

`<< details >>`  
> (terminology quibbles)

Sub-commands `are` active commands `contained` inside a parent command. `You can` encounter them inside `any` command symbol: both active and inactive commands symbols `can` contain sub-commands. `The` sub-commands `are` *active* commands: command calls, active clauses or active command references.

Below `is` a picture of two sub-commands inside an inactive command:

![](images/1.%20Commands%20Main%20Concepts.048.png)

`The` __Parent Command__ `is` an inactive command, because it `is` a square. In `the` diagram above, `the` __Parent Command__ `contains` two sub-commands. `The` sub-commands `are` displayed as diamond shapes. One of `the` sub-commands `is` a call, because it `has` a dashed line `going` outside `the` __Parent Command__, `tying the` sub-command to its command definition. `The` other sub-command `is` an *active clause*, because it `might not` redirect its command definition.

Below `is` a picture of two sub-commands inside an active command:

![](images/1.%20Commands%20Main%20Concepts.049.png)

It `is the same` picture as `the` other diagram, `only now the` __Parent Command__ `is` an executable command symbol, `not` an inactive command.

#### Command References Inside Commands

`<< details >>`  
A command reference `is` considered data. A command reference in a parent command `is` considered data of `the` parent command, `even when` it `is` active, `in case of which` it `*is*` considered a sub-command `but a special` form of it. Even though it `executes`, it `is still` a reference to an executable object `*elsewhere*`. Only `the` *pointer* part `is the` data. Command references `are` *data* that can be *private* or *public*.

#### Executables & Executions

##### Diagram Notation

`<< details >>`
> (terminology quibbles)

An executable object `stands for` a potential execution:

![](images/1.%20Commands%20Main%20Concepts.050.png)

An executable object `never stands` for multiple executions, `just one` execution or `no` execution `at all`.

`<< commands compared to objects >>`  
`The same` command object `can` be displayed in `the` diagram multiple times. In that case, a symbol might be added to the diagram, that `the` multiple references to `the same` command object `might` converge to, so that a single symbol in `the` diagram `is` selected to represent `the` command object itself, while `the` other ones `are` just references.

![](images/1.%20Commands%20Main%20Concepts.051.png)

So it `is not so`, that each diamond in `the` diagram represents its own individual command execution. Each individual *command object* `represents` an individual command execution. Multiple symbols in `the` diagram `can` represent `the same` command object, but `might` converge into one symbol representing `the` object itself.

### `<< explains other technology >>`

`The handy thing` about command reference, `is` that it `makes you able to keep` the operation `to execute` variable. `The` target of `the` command reference `is` variable. When `you *call*` a command reference, then `the` target of `the` command reference `determines` which command `is` called. `So calling` a command reference `means` calling a variable command definition.

### `<< pointers >>`

#### Command Reference Pointer to Pointer Situations

`<< move >>`  
A command reference `can also` redirect to `yet` another command reference, `creating` multiple command object redirections. `The` target of `the` last command reference `determines the` definition of `the` first command reference.

### `<< parameters >>`  

`<< parameters >>`  
Whether a parameter of a command `can` be read or written `at all is` access-controlled. This access control `determines` whether a parameter `is` for instance input or output.

### `<< basic diagram elements >>`  

#### No Dashed Squares?

`<< basic diagram elements >>`  
When an *object* `is` drawn with a dashed line, then it `is only` used as a class:

![](images/1.%20Commands%20Main%20Concepts.054.png)

This notation `might *not*` be copied to `the` concept of commands. This `is` because a command’s definition `might usually` be a square and a square `might usually` be a command’s definition, so `using` dashed lines for command definitions, `might` create an `overload` of dashed squares. So command symbols, that `are only` used as a definition, `do not` get a dashed notation.