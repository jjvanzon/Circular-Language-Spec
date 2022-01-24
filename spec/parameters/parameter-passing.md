Parameters | Parameter Passing
==============================

`[ Draft ]`

[back](./)

__Contents__

- [In & Out](#in--out)
- [By Value](#by-value)
- [By Reference](#by-reference)
- [Value In](#value-in)
- [Value In in a Diagram](#value-in-in-a-diagram)
- [Value Out](#value-out)
- [Value Out in a Diagram](#value-out-in-a-diagram)
- [Value Thru](#value-thru)
- [Value Thru in a Diagram](#value-thru-in-a-diagram)
- [Reference In](#reference-in)
- [Reference Out](#reference-out)
- [Reference Out in a Diagram](#reference-out-in-a-diagram)
- [Reference Thru](#reference-thru)
- [Reference Thru in a Diagram](#reference-thru-in-a-diagram)
- [Object Out](#object-out)
    - [Command Out](#command-out)
    - [New Command Out](#new-command-out)
    - [New Object Out](#new-object-out)
    - [Existing Command Out](#existing-command-out)
    - [Existing Object](#existing-object)
- [Object Out in a Diagram](#object-out-in-a-diagram)
- [Structs Parameter Passing](#structs-parameter-passing)
- [Ambiguity of Input / Output for Reference Parameters](#ambiguity-of-input--output-for-reference-parameters)
- [Longer Names](#longer-names)
- [Three Parameter Passing Elements](#three-parameter-passing-elements)
- [Parameters of Calls Directly Tied Together](#parameters-of-calls-directly-tied-together)
- [Strict About Parameter Passing](#strict-about-parameter-passing)
- [The Class of a Parameter](#the-class-of-a-parameter)
- [Type Arguments](#type-arguments)
- [Sub-Commands Are Never Output Objects](#sub-commands-are-never-output-objects)
- [In, Out & Thru Parameters](#in-out--thru-parameters)
- [Downput](#downput)
- [Incidental Parameter Passing](#incidental-parameter-passing)
- [Indirect Value Transmission](#indirect-value-transmission)
- [Wrong Approach to the Terms In, Out and Thru](#wrong-approach-to-the-terms-in-out-and-thru)
    - [In, Out & Thru](#in-out--thru)
    - [Terms for Reading](#terms-for-reading)
    - [Consider New In & New Out](#consider-new-in--new-out)
    - [More](#more)
- [Brainstorm 2008-09-27](#brainstorm-2008-09-27)
- [Brainstorm 2008-09-26](#brainstorm-2008-09-26)
- [Loose Ideas](#loose-ideas)
- [From the Original Symbol Documentation from 2004](#from-the-original-symbol-documentation-from-2004)
    - [Command Parameters](#command-parameters)
        - [Input, Output and Throughput Parameters](#input-output-and-throughput-parameters)
    - [Executions & Parameters](#executions--parameters)
        - [Argument Access](#argument-access)
            - [Input, Output and Throughput](#input-output-and-throughput)
                - [Output by Reference](#output-by-reference)
                - [Write, Read ≠ Input, Output](#write-read--input-output)
                - [Reference Arguments](#reference-arguments)
            - [Using Arguments](#using-arguments)
            - [Accessing Arguments During Execution](#accessing-arguments-during-execution)
        - [Implicit Notations](#implicit-notations)
            - [Previous Texts](#previous-texts)
                - [A](#a)
        - [Argument Reference](#argument-reference)
            - [Summary](#summary)
        - [In, Out and Thru Argument Notation](#in-out-and-thru-argument-notation)
            - [Execution Order in Text Code](#execution-order-in-text-code)
        - [Implicit Notations](#implicit-notations-1)
            - [Previous Texts](#previous-texts-1)
                - [B](#b)
                - [C](#c)
            - [Brainstorm Items](#brainstorm-items)
                - [1](#1)
                - [2](#2)
                - [3](#3)
        - [Forming New Subdivision](#forming-new-subdivision)
            - [Old Subdivision](#old-subdivision)
            - [New Subdivision](#new-subdivision)
            - [New Main Subdivision](#new-main-subdivision)
        - [Brainstorm](#brainstorm)
            - [New Brainstorm Texts](#new-brainstorm-texts)
                - [New](#new)
                - [Old](#old)
            - [Argument Access Summary](#argument-access-summary)
                - [In, Out and Thru](#in-out-and-thru)
        - [Brainstorm](#brainstorm-1)
            - [Other](#other)
    - [Misc Loose Ideas](#misc-loose-ideas)

## In & Out

These articles may talk about *input* and *output* parameters.

Input seems what's *read*. Output seems what's *written*. But perhaps also in the context of the containment struct`ure: input seems *read* on the *inside*. Output seems *written* on the *inside*. But *read* on the *outside*! So the terms *input and output* do not seem to map neatly to *reading and writing*, but seem quite dependent on context in a containment structure: inside or outside.

Another thing slightly open to interpretation might be, that reading/writing parameters may involve the direct value or object reference of a parameter, not so much the things deeper in the containment structure.

## By Value

A parameter is __By Value__, if you can only publicly read or write the value of the object.

Passing a parameter by value means, that the input or output is *copied* to or from the parameter object.

The diagram below may represent a __By Value__ parameter tied to the value source or target:

![](images/Input%20Output%20Parameter%20Passings.001.png)

The diamond is the command. The circle inside it is the parameter. The circle outside the command is the value source or target. And the wavy line may indicate value transmission between the parameter and the other object.

It may actually be a value assignment, that performs a yield over of value. Here is a diagram showing such a value assignment:

![](images/Input%20Output%20Parameter%20Passings.002.png)

Parameters passed by value might be useful for smaller amounts of data. The data might be changed inside the command, but that might not affect the original object.  
For an object, that only stores one value and that’s it, it may be ok to just copy the value.

## By Reference

Next to passing a parameter by *value*, you can also pass a parameter *by reference*. For instance: instead of copying a value to an input parameter, a command might be passed reference to an object outside the command.

If you want to pass more complex objects to a command, this might be done by reference instead of by value, but then changes to the parameter might affect the original objects.

__Reference__ parameter:

![](images/Input%20Output%20Parameter%20Passings.005.png)

## Value In

A __Value In__ parameter passes a value from an object to the parameter of a command. A __Value In__ parameter is an object inside the command call, that can be written before the command is invoked, by assigning to it a value of an object outside the command call.

The command can manipulate the __Value In__ parameter without affecting the original object.

## Value In in a Diagram

A diagram of an executable command with a __Value In__ parameter:

![](images/Input%20Output%20Parameter%20Passings.006.png)

Here is a diagram of an unfilled-in __Value In__ parameter of an executable command:

![](images/Input%20Output%20Parameter%20Passings.007.png)

`<< parameter passing >>`

A command definition or other inactive command displays __Value In__ parameters the exact same way. The __Value In__ parameter of a command definition is usually not filled in:

![](images/Input%20Output%20Parameter%20Passings.010.png)

But the __Value In__ parameter of an inactive command could be filled in just as well:

![](images/Input%20Output%20Parameter%20Passings.011.png)

`<< interpretation >>`

The fact, that it is an inactive command, means that it might not run, but for the rest it is the same as any other command object, so it basically has the same possibilities.

## Value Out

A __Value Out__ parameter is a value produced by a command, that can be yielded over to another object after the command is done. A __Value Out__ parameter is an object inside the command call, that is written to by the command or by one of its sub-commands. After execution of the command the value of the output parameter can be copied, by assigning the value to another object.

## Value Out in a Diagram

A diagram of an executable command with a __Value Out__ parameter looks as follows:

![](images/Input%20Output%20Parameter%20Passings.014.png)

The following diagram shows the __Value Out__ parameter with an assignment target indicated to which the output value might be transferred:

![](images/Input%20Output%20Parameter%20Passings.015.png)

`<< parameter passing >>`

A command definition or other inactive command displays __Value Out__ parameters the exact same way. The __Value Out__ parameter of a command definition might look like this:

![](images/Input%20Output%20Parameter%20Passings.018.png)

The __Value Out__ parameter of an inactive command can also be read and written to a target object, like this:

![](images/Input%20Output%20Parameter%20Passings.019.png)

`<< interpretation >>`

The fact, that it is an inactive command, means that it might not run, but for the rest it is the same as any other command object, so it basically has the same possibilities, even reading and writing its parameters.

## Value Thru

Throughput by value is when a by value parameter is first written to, then changed by the command, and then the value of the parameter is read from again, and assigned to the original object.  
A __Value Thru__ parameter is an object inside the command call, that can be written before the command is invoked, by assigning to it a value of an object outside the command call. It is used but also written to by the command or one of its sub-commands. After execution of the command the value of the throughput parameter can be copied, by assigning the its to another object.

`<< details >>`

In theory the value could first come from one object, and after the call be written to another object. But that’s not regularly what a __Value Thru__ parameter is used for. The value might first be copied from one object and assigned to the parameter, and afterwards the value of the parameter is copied to the original object again.

## Value Thru in a Diagram

A diagram of an executable command with a __Value Thru__ parameter:

![](images/Input%20Output%20Parameter%20Passings.022.png)

Here is a diagram of an unfilled-in __Value Thru__ parameter of an executable command:

![](images/Input%20Output%20Parameter%20Passings.023.png)

A command definition or other inactive command displays __Value Thru__ parameters similarly. The __Value Thru__ parameter of a command definition is usually not filled in:

![](images/Input%20Output%20Parameter%20Passings.026.png)

But the __Value Thru__ parameter of an inactive command could be filled in just as well:

![](images/Input%20Output%20Parameter%20Passings.027.png)

`<< interpretation >>`

The fact, that it is an inactive command, means that it might not run, but for the rest it is the same as any other command object, so it basically has the same possibilities.

## Reference In

A __Reference In__ parameter might be used to assign a reference to a complex object as the input of the command. Because a __Reference In__ parameter is input, the called command can only *read* out of the object, that it was given a reference to.

A diagram of an executable command with a __Reference In__ parameter may look as follows:

![](images/Input%20Output%20Parameter%20Passings.030.png)

When a __Reference In__ parameter might not have a reference target filled in yet, then the diagram may look as follows:

![](images/Input%20Output%20Parameter%20Passings.031.png)

An inactive command displays __Reference In__ parameters similarly.

`<< interpretation >>`

The fact, that it is an inactive command, means, that it might not run, but for the rest it behaves the same way as any other command object, so it basically has the same possibilities as an active command.

`<< parameter passing >>`

The reference target of a __Reference In__ parameter of an inactive command definition might not be filled in.

![](images/Input%20Output%20Parameter%20Passings.032.png)

Here is a picture in which a command definition’s __Reference In__ parameter might have its reference target filled in:

![](images/Input%20Output%20Parameter%20Passings.033.png)

`<< interpretation >>`

Do note, that the expression of read-write direction is not a connector, like for __Value__ parameters. It is an abstract expression of value direction. You can not connect anything to it. The reference target connector, however, *is* a connector.

## Reference Out

The distinction between __Reference In__ and __Reference Out__ might be about whether values are read or written to the object passed to the sub-command.

When a command is passed a reference to an object, and the command writes to the parameter, it might be called a __Reference Out__ parameter. Because a __Reference Out__ parameter is output, the called command might only *write* to the object, that it was given a reference to. A __Reference Out__ parameter can be used to assign a reference to a complex object to which a command writes output.


## Reference Out in a Diagram

A diagram of an executable command with a __Reference In__ parameter may look as follows:

![](images/Input%20Output%20Parameter%20Passings.034.png)

The access mark on the left is a connector, to which the reference target of the __Reference Out__ parameter can be attached. Here an attempt to depict a diagram in which a reference target may be attached to the __Reference Out__ parameter.

![](images/Input%20Output%20Parameter%20Passings.035.png)

The fact that the reference goes outwards, might not make it an Out parameter. That just makes it a __Reference__ parameter. The fact, that the command only *writes* to the parameter may make make it an __Out__ parameter, so the term __Out__ is about value direction, not reference direction.

An inactive command may display __Reference Out__ parameters in a similar way.

`<< interpretation >>`

The fact, that it is an inactive command, means, that it might not run, but for the rest it behaves the same way as any other command object, so it basically has the same possibilities as an active command.

`<< parameter passing >>`

The reference target of a __Reference Out__ parameter of an inactive command definition might usually not be filled in:

![](images/Input%20Output%20Parameter%20Passings.036.png)

Here is a picture in which a command definition’s __Reference Out__ parameter might have its reference target filled in:

![](images/Input%20Output%20Parameter%20Passings.037.png)

`<< interpretation >>`

Note, that the indication of read-write direction is an abstract expression of the value direction inside the command. You can not connect anything to it.

## Reference Thru

Next to __Reference In__ and __Reference Out__, there might also be __Reference Thru__, which may means, that the command both reads and writes to the object passed to it. A __Reference Thru__ parameter might be a pointer to something outside the command. The object pointed to may be both read from and written to.

`<< interpretation >>`

A __Reference Thru__ parameter can be used to assign a reference to a complex object, from which input is read and output is written to. 

## Reference Thru in a Diagram

A diagram of an executable command with a __Reference Thru__ parameter may look as follows:

![](images/Input%20Output%20Parameter%20Passings.038.png)

When a __Reference Thru__ parameter might not have a reference target filled in yet, then the diagram might look as follows:

![](images/Input%20Output%20Parameter%20Passings.039.png)

An inactive command may display __Reference Thru__ parameters similarly.

`<< interpretation >>`

The fact, that it is an inactive command, means, that it might not run, but for the rest it behaves the same way as any other command object, so it basically has the same possibilities as an active command.

`<< parameter passing >>`

The reference target of a __Reference Thru__ parameter of an inactive command definition might not be filled in:

![](images/Input%20Output%20Parameter%20Passings.040.png)

Here is a picture in which a command definition’s __Reference Thru__ parameter might have its reference target filled in:

![](images/Input%20Output%20Parameter%20Passings.041.png)

`<< interpretation >>`

Do note, that the expression of read-write direction is not a connector. It is an abstract expression of value direction. You can not connect anything to it. The reference target connector, however, *is* a connector.

## Object Out

`<< parameter passing >>`

An __Object Out__ parameter might be an object, that resides inside the command. The __Object Out__ parameter may be a new object, or redirect to an existing object. Anyway, the *command* might determine which object may be output. The produced object can be referenced from outside the command.

`<< rule rich >>`

Unlike parameters passed __By Reference__, an __Object Out__ parameter is *referred to*. This is an exclusive aspect of the __Object Out__ parameter passing.

`<< parameter passing >>`

So this is a __Reference Inward__ parameter, as opposed to a __Reference Outward__ parameter. The reference direction goes the other way around.

`<< already covered >>`

Instead of a parent passing an object to the command, it is like the *command* passes a reference back to container of the command.

`<< parameter passing >>`

The command writes to the output object.

`<< rule rich >>`

Unlike __Reference__ and __Value__ parameters, there is no distinction between __In, Out__ and __Thru__ for __Reference Inward__ parameters. The reason __Reference Inward__ parameters do not have three variations, is that the command’s reading and writing values to the object is irrelevant to the *parameter passing*. To the outside, it might not matter whether the parameter is read from or written to or both. All that matters, is that an object is produced. __Reference Inward, Value In__ and __Reference Inward, Value Thru__ are not relevant. The __Reference Inward__ parameter *can* be *read from* by the sub-command, but that it’s just not relevant to *parameter passing* between a command and its container. Because __Reference Inward, Value Out__ is only relevant for reading values from an output object, it is shortened to __Object Out__. 

An __Object Out__ should really only be accessed *after* the command has run.

### Command Out

An __Object Out__ parameter can be a regular object, but it can also be a command. In that case it might be a command *produced* by another command. The parent command can return a new command or the parent command can return a reference to an existing command.

### New Command Out

When an __Object Out__ parameter is actually a new command, then the new command is either a pre-configured instance of another command, or it can be a brand new, generated command, any part of which is constructed by its parent command, based on a set of variables.

### New Object Out

An __Object Out__ parameter might be typed a __New Object Out__ parameter, if it might be a brand new object that might be returned.

### Existing Command Out

An __Object Out__ parameter can also be an existing command. In that case the __Object Out__ parameter object-redirects to another command again, so the parent command basically picked out a command for you, instead of actually producing a new one.

`<< different section ? >>`

In Circular, multiple return values is accomplished by having multiple __Object Out__ parameters. So you do not need __Reference Out__ parameters for that purpose anymore.

### Existing Object

An __Object Out__ can be typed more specifically as __Existing Object Out__ if it might not be a new object that is returned, but one that already existed.

## Object Out in a Diagram

A diagram of an executable command with an __Object Out__ parameter may look as follows:

![](images/Input%20Output%20Parameter%20Passings.042.png)

The outer end of the line is an connection point to which you can connect an object to refer to the __Object Out__ parameter:

![](images/Input%20Output%20Parameter%20Passings.043.png)

An inactive command might display __Object Out__ parameters in a similar way.

`<< interpretation >>`

The fact, that it is an inactive command, means, that it might not run, but for the rest it behaves the same way as any other command object, so it basically has the same possibilities as an active command.

`<< parameter passing >>`

The object referring to the __Object Out__ parameter of an inactive command definition might not be filled in:

![](images/Input%20Output%20Parameter%20Passings.044.png)

Here is a picture in which a command definition’s __Object Out__ parameter might have a referrer:

![](images/Input%20Output%20Parameter%20Passings.045.png)

## Structs Parameter Passing

A construct that other languages might call __structs__, are a value type that might have multiple distict fields / values.

This type of construct's value might be transferred with a cloning depth of 2. The idea that the object itself + its values are transferred as a whole in case of value assignment, and by extension also __By Value__ parameter passing of a __struct__.

It may happen automatically for __struct__ types. A clone notation where the cloning depth of __2__ might be visually expressed, might also be suggested. This clone notation may be found in a separate document.

No definite choice might be necessary about which notation to pick. It might depend on the particular application that may be developed that perhaps would use this Circular notation.

## Ambiguity of Input / Output for Reference Parameters

`<< move ? >>`

`<< ambiguity of input / output for reference parameters >>`

When a command call has an outward reference to an object, this might make the object a parameter. It seems an *input* parameter, since the line might be set from the outside. But it seems ambiguous whether it is input, because values might still be read or written. It being an outward reference, *might not* determine yet whether it is input, output or throughput. The *in* and *out* in this case refer to whether *values* are written or read to the object reference. A reference parameter is always sort of like input, though: the parent command passes the object to the sub-command, so the parent inputs something into the sub command.

-----

`<< ambiguity of input / output for reference parameters >>`

In a sense, a __Reference *Out*__ parameter is actually *through*put.  
When output is *alteration* of an *existing* object, it could be considered throughput, even though there is only *written* to the object, and nothing is *read* from the object, it is still an object passed *through* the command. In yet another sense, a __Reference Out__ parameter is input, because you are passing an object *into* a command.

-----

`<< ambiguity of input / output for reference parameters >>`

The reason why it is important to keep understanding the three aspects of parameter passing, is that __Reference__ parameters, even though they can be __In, Out__ or __Thru__, are always *input* in a way, because it is a reference passed from the parent command to the sub-command.

## Longer Names

A By Reference parameter can also be called __Reference Outward, Value In__ and __Reference Outward, Value Out__ But those names may be quite long.

The long names of parameters passed __By Reference__ were:

- __Reference Outward, Value Inward__
- __Reference Outward, Value Outward__
- __Reference Outward, Value Thru__

The long name of value __Object Out__ might be:

- __Reference Inward, Value Out__

Long names for the different parameter passing types might be:

- __Value In__
- __Value Out__
- __Value Thru__
- __Reference Outward, Value In__
- __Reference Outward, Value Out__
- __Reference Outward, Value Thru__
- __Reference Inward, Value Out__
- ~~__Reference Inward, Value In__~~ 
- ~~__Reference Inward, Value Thru__~~ 

But these two might not be relevant:

- __Reference Inward, Value In__
- __Reference Inward, Value Thru__

## Three Parameter Passing Elements

`<< interpretation >>`

__By Value__, __Reference Outward__ and __Reference Inward__ might be the different reference situations a parameter can have. But this may not tell us whether a parameter is input, output or throughput. What might determine, whether it is in, out or thru may be whether values are written to the parameter or read from the parameter.

`<< rule rich >>`

Perhaps because a reference *inward* only is about an *output* object.

It might be relevant to observe that there might be three elements to parameter passing:

- Values read or written
- Parameter is a reference outward
- Parameter is referenced from the outside

To understand how the different parameter passings came about, it is important to keep those three aspects in mind.

`<< parameter passing >>`

Here is a list of the parameter passings, with their short names, and their diagram expression:

- __Value In__

    - ![](images/Input%20Output%20Parameter%20Passings.046.png)

- __Value Out__

    - ![](images/Input%20Output%20Parameter%20Passings.047.png)

- __Value Thru__

    - ![](images/Input%20Output%20Parameter%20Passings.048.png)

- __Reference In__

    - ![](images/Input%20Output%20Parameter%20Passings.049.png)

- __Reference Out__

    - ![](images/Input%20Output%20Parameter%20Passings.050.png)

- __Reference Thru__

    - ![](images/Input%20Output%20Parameter%20Passings.051.png)

- __Object Out__

    - ![](images/Input%20Output%20Parameter%20Passings.052.png)

`<< interpretation >>`

__Value In__ and __Value Out__ means reading and writing done by de caller. __Reference In__ and __Reference Out__ means reading and writing done by the called command. In both cases __In__ might mean, that the called command *uses* something, and __Out__ means, that the called command returns something.

## Parameters of Calls Directly Tied Together

In other programming languages, sub-commands might not directly read or write to each other’s parameters. Parameters might only be read or written by the parent command.

However, in Circular, parameters of commands might be tied together directly.

One type of parameter passing might only be tied to a parameter with a specific other parameter passing.

__Value In__ parameters and __Value Out__ parameters may be tied together:

![](images/Input%20Output%20Parameter%20Passings.053.png)

Only __Object Out__ and __Reference__ parameters might be tied together:

![](images/Input%20Output%20Parameter%20Passings.054.png)

Tying parameters may express a dependency. No direct reference to the parameter objects may be required inside the parent command in this notation.

`<< rule rich >>`

A __Value Thru__ parameter can not be tied to another parameter:

![](images/Input%20Output%20Parameter%20Passings.055.png)

This is because it creates a circularity in which one parameter writes its values to the other, and the other parameter writes its value to the first parameter. It is just an unlogical circular situation.

## Strict About Parameter Passing

`<< implementation >>`

I really want the programming environment, to not so easily accept, that a parameter is typed throughput, when it is only read from. Because otherwise you rely too much on courtesy of the programmer, to make the whole system function correctly.

You could define a parameter as throughput, but actually only read from it. In that case the parameter is implicitly degraded to an input parameter. The implicit parameter type counts. The implicit parameter passing is dependant on the way it is declared and the way it is used. A throughput parameter is not only declared as such, but also always used as such. 

## The Class of a Parameter

The class of a parameter is usually set by the command, that holds the parameter. In that case, you can only assign objects or values of objects to it, that have the same class as the parameter indicates.

It is also possible, that a parameter might not have a class. In that case any object or any object’s value can be passed to the command.

## Type Arguments

When the class of a parameter might be determined from the outside, then it is special. It may be a __Class Reference__ parameter. In that case you might not use it as a normal __Reference__ parameter. In some other programming languages thes might be called *type arguments*.

## Sub-Commands Are Never Output Objects

`<< rule rich >>`

Sub-commands, so active command objects inside another command, are never referenced so sub-commands can never output objects.

The rule is explained in the article *Sub-Commands are Never Referenced*, as part of the set of rules that protect a parent command’s control over the execution of its sub-commands.

This rule also implies, that sub-commands (active commands inside another command) can not be output objects. If the rules that protect the parent’s control over its sub-command’s execution change, then the rule sub-commands are never output objects might not apply anymore.

A parameter, that is a command reference, can be run, but it can never point to an active command inside another command, so that never lets any parent command loose control over any sub-command’s execution.

## In, Out & Thru Parameters

Parameters can function as input, output and throughput. Input, output and throughput may be parameter passing types. They might be shortened to __In, Out__ and __Thru__.

`<< interpretation >>`

When a command’s parameter is __In__, it means that the command reads from the parameter. When a command’s parameter is __Out__, it means that the command writes to the parameter. When a command’s parameter is Thru, it means, that the command reads and writes the parameter. Throughput functions as both input and output at the same time.

`<< creation behavior of commands >>`

Before execution you can read and write. > 2008-09-24 from the outside  
During execution you can not read or write. > 2008-09-24 from the outside  
After execution you can only read. > 2008-09-24 from the outside

## Downput

`<< terminology >>`

Next to the terms input, output and throughput, the term downput might be introduced. Downput is intermediate data as a helper of a process, that might eventually produce output. Temporary variables, local variables. They are all downput. Actually, in the command-call structure, a command in which output data is disposed, this output has become downput.

Downput data is private data of the command.

The term downput might be a good term, because it is only passed *down* into sub-commands. And may be dropped after the parent command is done (dropped *down*). It is ‘put down’ / rejected after the execution. Or put down / to put something down, that you had in your hand.

When a command disposes objects after it is done, then those objects might be called *downput*. Downput may have been input for sub-commands, or it could have been output of sub-commands. To the parent command, though, it might be *downput*. Downput parameters might not be further considered here, because they might not have anything to do with parameter *passing*.

## Incidental Parameter Passing

`<< rule rich >>`

One time a command runs, something may only be read. Another time it may be read and written to. This changes the implicit position of the object in relation to to the command for each call to the command. You could stereotype it an input parameter as __Not Input__ and an output as __Not Output__ and a thru parameter as __Only Input__ or __Only Output__ or __Not Thruput__. But it might not replace the parameter’s __In, Out__ or __Thru__ properties, because they belong to the command definition.

The object command’s on the other end of the relationship, also get additional typing based on the incidental parameter passing, but the passing names are not even determined yet.

< 2021-05-03: This may be like 'connector' vs 'connection'. >

## Indirect Value Transmission

`<< input output >>`

Used in abstract notations, explained later, a value line might not necessarily mean yielding over the value of one object on one end of the line to the other object on the other end of the line. It may be yielding over values between sub-objects. So it’s not synonym to a value assignment in that case.  
But usually value direction means assigning the value of one object to another.

- \> Indirect value direction may be called data direction, and might be given a double wavy line as a symbol. It can indicate addition, removal, creation, annulment and value transfers of the direct object or its sub objects.

For __Reference__ parameters it might not need to be the value of the object itself, that is read or written.

It can also be a *sub-object* of the parameter, that is read or written. Even though the parameter itself is not read or written, but only its sub-object, the parameter *itself* is considered input or output, even though only the values of its *sub-*objects are used. 

Sometimes the command itself might not read or write from a parameter, but the parameter is passed down to a sub-command, that reads or writes from the object. This yields over the in-out-thru properties of the parameter. This might give the parameter an indication of value direction, but this is an abstract notation of what is going on. The assignments are done by a sub-command.

Next to values being read or written, an abstract indication of value direction is also used to indicate addition, removal, creation and annulment of objects. These actions might all be considered *writing* or *output*.  
In the definition of the command, you might see the individual additions, removals, creations and annulments as calls to system commands (see the *System Interfaces* documentation section).  
But the __Reference__ *parameter* might get an *abstract* value direction indication, that says the reference parameter is output.

All in all, non-value transmissions may apply to __By Reference__ parameters only.

So for reference parameters, the in-out-thru direction might be an abstract indication of what is going on. It can mean a lot of different things.

The exact objects and manipulations a command might executes on a reference parameter might be indicated by its command IO, might be covered in a topic *Command IO*.

## Wrong Approach to the Terms In, Out and Thru

*2008-09-29*

### In, Out & Thru

`<< terminology >>`

`<< in / out vs. read / write confusion >>`

The terms I might like to see back in access control literals are the terms __In, Out__ and __Thru__.

After a lot of brainstorm I figured, that whether something is __In__ or __Out__ depends on whether something is being *written* from the *outside* or on the *inside*. When something is set on both the outside and the inside, then it is called __Thru__. From which direction something is *read* is not relevant for the terms __In, Out__ and __Thru__.

When you write one aspect on the outside, it might not mean that the same aspect is supposed to be read on the inside. You may write one aspect on the outside and read another aspect on the inside. For instance, if you write the object from the outside, you may only read its value from the inside. Earlier, this might produce the following literal:

- __Object Set Public, Value Set Private__

But the terms __Set Public__ and __Set Private__ can be replaced now by the terms __In__ and __Out__:

- __Object In Value Out__

It looks a lot clearer that way.

If the *same* system aspect is written from both the inside as well the outside, then the term __Thru__ might be used, for instance:

- __Object In Value Thru__

The keyword __Thru__ can only be used, when it is the same aspect, that is set from both the inside and the outside. When different aspects are written on the inside and the outside, you might not see the word __Thru__ in the access control literal. For instance, when a parameter is:

- __Object In Value Out__

it can be called a __Thru__ parameter, but you might not use the term __Thru__ in the access control literal, because you can only use the term __Thru__ in a literal when the *same aspect* is set on both the inside and the outside.

The use of the keyword __Thru__ may also become scarce, if you insist to keep the access control elements in chronological order:

- __Object In, Value In, Value Get Private, Value Out__

Even though __Value__ is __Thru__, the __Value Get Private__ is put in between the __Value In__ and __Value Out__, because of the chronological order of access control elements. It is not clear yet what I want to do with this in the future. Perhaps a rule, that makes the literal:

- __Object In, Value Thru, Value Get Private__

But I am not sure yet.

### Terms for Reading

`<< terminology >>`

`<< in / out vs. read / write confusion >>`

Reading stuff might not seem to have anything to do with the terms __In, Out__ and __Thru__. __In, Out__ and __Thru__ only determine the write-direction.

Reading stuff seems to matter less. Reading might not be seen as parameter passing. It might be only about: who writes it and from which direction. Reading has less impact than writing.

`<< input output >>`

But its impact may become important later, when perhaps using it in more advanced techniques for for instance concurrency resolution.

`<< terminology >>`

`<< in / out vs. read / write confusion >>`

What I see now, is that if I find simpler terms for reading, I might probably be totally happy with my parameter access control literals. Since there is such beautiful names for writing from either inside or outside (__In, Out__ and __Thru__) can I come up with beautiful names for reading too? If I can find a replacement for the terms __Get Private__ and __Get Public__, then I might probably be completely satisfied with how the parameter access control literals look.

Next to an easier expression of __Get Private__ and __Get Public__, you may also want to invent keywords to express that something is publicly written and privately read, or the other way around. So when __Value__ is set on the outside and read on the inside, you get an easier expression for it, than saying __Value In, Value Get Private__. Do note, that when you set a value on the outside, it might not imply, that you also *read* the value on the inside.

< 2021-05-03: It may seem to matter less, the precise words. It might be more about the diagram notation and how it might map to perhaps more familiar concepts from programming. Even automatically determining in, out and thru might not be dependent on what names things are given. >

### Consider New In & New Out

`<< parameter passing >>`

2008-09-29

However, __New In__ might mean creation from the outside and __New Out__ might mean creation on the inside... so ... it’s not just the inside then... how might that relate to the rest of the ideas about __In, Out__ and __Thru__?

JJ

### More

`<< parameter passing >>`

If an aspect is both __In__ and __Out__ and the two access control elements are right next to each other, it can be replaced by a single access control element __Thru__:

- __Object Thru__
    - __New Thru__
    - __Annul Thru__
- __Value Thru__
- __Class Thru__

## Brainstorm 2008-09-27

`<< input output >>`

I think the terms input and output should not be about whether something is written from the outside and whether something is written from the inside. That’s what I did earlier. I think the term input should mean: everything that is read on the inside of a command, and the term output should mean: everything that is written on the inside of a command.  
So it is about what happens on the inside. Whether something is written or read from the outside might not be the issue.

Anyway, input and output are too complicated to just wrap up the old parameter passing type stories, which depend on those terms.  
Advanced Command Topics might also do a lot with input and output. Actually, most of it is about the complexity of input and output. I should really save it for another project. One of the objectives of the project Work Out Advanced Command Topics should be to determine the exact definition of input and output and the exact definition of input and output parameters.  
I should shove it over to that project.  
I should register in the project description that determining the exact definition of input and output is one of the objectives.

The current project might wrap up everything else about parameters.  
I might clean up the objectives of the current project and create a new plan for it.  
Then I can work my way up to an end point. And in the next project I might just calmly look at the exact complexity of input and output.

## Brainstorm 2008-09-26

`<< input output >>`

<

2021-05-04:

- The following brainstorm may be about labeling things In and Out. A quest for simpler names might be observed.
- Perhaps a more relevant issue might be the elements: different ways that objects might be accessed like Public Get Value or Private Set Object. Perhaps not so much what to name it, but rather what elements there are and what the notation might be. 
- Also edge cases might be given more attention than might be  necessary.
- Another thing that emerges in the brainstorm might be: wanting a grip on what input and output precisely mean and how to define it precisely. That might be more for the Input / Output chapter in Construct Drafts.

My mistake may once have been to think: "These terms In and Out must be simple to define." and then might have gotten stuck on that for a while.

\>

The problem with defining what is input and what is output, is:

- Is input what is written from the outside, or is input what is read from the inside.
- Is output what is read from the outside, or what is written on the inside?

You might think: both; something that is written from the outside is read on the inside and something that is written on the inside, is read from the outside.

But one prime example might overthrow that: An object can be written, so passed to a command, and the value of the object might be read. So Object Set Public, Value Get Private. So then you do not set the object, to read it on the inside, but the object is set, to read the value on the inside, so when an aspect, such as Object or Value, is In, it might not mean that it is both written from the outside and read on the inside.

But in the car on my way home from work I realized, that I have been forgetting about half the gets. When an object is written from the outside of the command, of which the __Value__ is read on the inside, the __Object__ is read as well, because might read the object, before you can retrieve the value of the object. So the object is read for access. Not for copy / assignment.

Perhaps you need to consider reading an object for access too. I already wrote something about that in the old Symbol documentation: different forms of getting, that also might be separately access controlled.  
It makes a difference when something gettable for access compared to gettable for copying. It might make a difference for outcome dependency. For instance: when you can get something for accessing but can’t get something for copying, then the object can be accessed inside the command, but it can not be passed further down into sub-commands.  
This has implications for automatic determination of in out and thru and also for compared IO and automatic execution order.

Perhaps I need to consider Command IO a little to come up with a more exact definition of input and output. But I think I am getting there now.

Outside the command, something is only written to the command, to be read from the inside of the command, even when it is not reading for assignment, but reading for access.

So the thing is: you don’t always read something only to write it to something else. You also can read something for access: read something for redirection to something else.  
So that suggestion I made earlier was wrong.

So it seems, that after all input is: written from the outside, read on the inside. And input is: written on the inside, read from the outside. reading can also mean reading for access, not reading for assignment.

But there is one thing wrong here:

- incidentally something that is written from the outside, is not read on the inside
- and incidentally something that is written on the inside, is not read from the outside.
- Incidentally something is not written from the outside at all, but read on the inside all that same, but then a default value is read or an error or something missing is caught. 
- Incidentally something was not written on the inside, but read from the outside all the same, but then a default value is read of an error or missing of something is caught

That has to get a name: so it is a missing read or write of input or a missing read or write of output.

But still:

- input means writing on the outside, reading on the inside.
- Reading can also be reading for access. Not necessarily reading for assignment
- Reading for access and reading for assignment need to be separately access controlled and it might change parameter passing.
- Incidentally a read or write of input or output is missing. That might be given a term.
- When a read or write is done on the outside, the a write or read might be executed on the inside, even though scarcely or incidentally not.  
If you don’t read input, then you can not call it input: an error or warning is generated.

-----

- __In For Access__
- __In For Copy__
- __Value In For Redirection__ > not possible
- __Value In For Copy__
    - \> is just __Value In__
- __Object In For Redirection__
- __Object In For Copy__
- __Class In For Access__
    - \> How can you access a class? Don’t you only access an object? Yeah, I think you do. So the separation between 'for access' and 'for copy' may only count for Object access.

So:

__Object Set Public, Value Get Private__  
\=  
__Object Set Public, Object Get Private For Redirection, Value Get Private__

Hmmm... if you get the value of an object, might that mean you first follow redirection? I guess you do..  
The last bit of the access control literal specifies, you can only follow redirection of the object to get the value or otherwise it might be Data Get Private.

But the access literal above further simplified  
= Object In For Redirection, Value Get Private.

Now I am confused again: you may set and get the object, but you only GET the value. Weren't I supposed to call something input, when it is set from the outside and read from the inside.

The thing is: I am not reading what’s set on the outside: I am reading from what’s inside what’s set on the outside.

So you are going further down the structure when you read the value of the object passed to the command.

So Value In means you write the value from the outside, not the object, and you read the value on the inside. Value Out means the other way around.

Actually, it could be: Value Set Public, Object Get Private For Copy.  
Value is Set, but not read. Well.. it has to be read by a sub-command then...

I am still confused. I have brainstorming to do.

But it’s no use writing something, if you don’t read it at some point.  
Sub-commands yield over in, out properties to their parent commands. 

You write the value... it needs to be written at some point.

When you write the value from the outside, and you can only access the object on the inside, you might pass the object to a sub-command, that might write the value. But can you really know? Maybe not, but it should be read somewhere on the inside.

Look, there is a whole object theory behind the in out and thru. And it should be covered by advanced command topics, to the extent, that you can automatically determine execution outcome dependency, execution order and possible resolve concurrency.  
But writing means you’re going to read it, and when you read it, is has to have been read.

Oh, yeah? What if you write the value of the object some place, and the object is passed to the command, and the command reads its value. In that case the value is only written to the object *somewhere* on the outside, and read only *somewhere* on the inside.

Is there really a point to talking about input and output at this stage?  
Isn’t input and output much more complicated than expected.  
The general meaning is understandable, but what it means on an object oriented level could be very complex. I really think it is something for Advanced Command topics.

I can talk about Reference In, but when you assign the object to a parameter, and the value is supposed to be accessible, it doesn’t mean, that you might read the value directly in the command. You may very well read it somewhere in a deep sub-command.

This whole theory about how something becomes input or output might just be saved for Advanced command topics. And things like Reference In and all that, are just not as simple as suggested.

Perhaps a simpler conclusion, for now:  
the rules I suggested above are still true: when you set input, it is meant to be read somewhere, but WHERE you actually read it is more complicated.  
But when you SET something of a parameter, than you are sure it is input or output.  
Where you then GET it, is not clear. It could be far away on a higher level, or far a way on a deeper level. That’s why SETTING allows you to say something about something’s being input or output. But can the ability to set a parameter on either inside or outside exclusively tell you it is input or output?  
What use might access control over getting have?  
I think being able to allow a Set from the outside, and then still being able to disallow getting on the inside might be unuseful: it has to be gotten at some point, if only for redirection.  
So those allowances should go hand in hand: if you can write it from the outside, you can read if from the inside. If you can write it on the inside, you can read it from the outside.  
but WHERE it is then read could be somewhere totally else than directly outside or directly inside. MIGHT THAT count for SETTING too?

## Loose Ideas

`<< parameter passing >>`

Parameters,  
2008-08

The command definition can also contain a set of related objects. Those are the parameters of the command. They are just input, output, throughput or downput. This input, output, throughput and downput is passed on to the sub-commands, that are given outward references to these items.

JJ

-----

Parameter passing,  
2008-09-05

`<< terminology >>`

If a command parameter is typed with in, out, or though,  
then an object command can also be given a title depending  
on whether it might be input, output, throughput, etcetera.

input is not an object that something is done to. It can be considered an object doing something to another object. So it is clearly an actor.

`<< thruput parameters | affected used and transformed >>`

It matters whether the object is used (read), affected (written), or produced. This alters the object’s position in relation to to the command.

JJ

-----

Parameters,   
2008-06

`<< input output >>`

Always something is the input and something is the output: at least one thing is used, and at least one thing is affected. But the affected thing can also be a new thing.  
One thing is executed on another. So its data executed on data.

JJ

-----

Access Controling System Aspects,  
2008-09-21

`<< broader view >>`

When you access control the system aspects of a parameter, might this have implications for access control of the object’s command?

When you show a command inside an object, how might you see, that the command outputs the object or if the command uses the object?

JJ

-----

`<< get purposes >>`

2008-09-26

Adapt the access control of system aspects in the parameter articles to Object Get for access and for copy...

JJ

-----

Parameters,  
2008-09-11

`<< construct drafts >>`

Value In parameter used for selection  
Value In parameter used for persistance

JJ

-----

`<< details >>`

When a command is called, objects are filled into the parameters of the command. A command might use objects to do its work. The objects filled in as parameters are also called arguments.

As commands call each other, every time different data is passed along to the different commands, that are called.

-----

`<< details >>`

ByRefs have pros and cons in different situations.

-----

`<< parameter passing >>`

The objects inside a command can be regarded:

- Input parameters
- Output parameters
- Throughput parameters
- Return values
- Local variables

-----

`<< parameter passing >>`

The input parameters of a command are its writable objects. The output values are its readable objects. Objects that are read-write are like in-out or thru parameters.

-----

`<< return values >>`

One readable object can be chosen to be the return value, which promotes it to being the main output parameter. This might not give it extra capabilities, only an extra notation in certain places. The return value might be denoted in a diagram by putting the term __Return__ near one of the parameters.

< Don’t forget that you don’t need to read or write necessarily, you can also just call a member of the parameter instead of read or write it... explore that >

-----

`<< command in >>`

Passing a command reference,

When you pass a command reference to a child command:

![](images/7.%20Commands%20Ideas.050.jpeg)

The child can call the referenced command at will.

## From the Original Symbol Documentation from 2004

### Command Parameters

`<< already covered >>`

`<< perhaps usable >>`

Commands can have *parameters*: instructions passed along with the command that make the command behave differently. The __Button . Set Text__ command, for instance, has a __Text__ parameter, which indicates what the new text of the button might be.

Text is an *idea*. It is an *object*. It is *objects* that serve as parameters.

![](images/Input%20Output%20Parameter%20Passings.059.jpeg)

The command can do whatever it wants with the parameters passed to it. All it really can do with it is again pass the parameter to another command *or* call commands of the parameter.

*Pass the Text parameter on to the next command (Format Text):*  
![](images/Input%20Output%20Parameter%20Passings.060.jpeg)

*Call the a command of the Text parameter:*  
![](images/Input%20Output%20Parameter%20Passings.061.jpeg)

The terms *parameter* and *argument* are often intermixed. For now you can assume that a parameter is a setting of a command and an argument is the value that it holds. That’s not the entire truth, though, but I’ll save the exact meaning for later.

#### Input, Output and Throughput Parameters

`<< nice formulation >>`

Parameters are commonly input (instructions) for a command. Parameters can also be output (returned results). They make a command return something to the caller. One of the output parameters can be appointed to be *the* return value, which makes it sort of like the main output parameter. Some parameters can be input, and then output again. Then the command uses the parameter, transforms it and gives it back in the transformed state. These parameters are called throughput parameters, or in-out parameters. There are also objects in a command that are only used locally. Those are not usually called parameters, but sooner called *local objects*.

### Executions & Parameters

#### Argument Access

##### Input, Output and Throughput

###### Output by Reference

`<< in / out vs. read / write confusion >>`

< 2008-10-06 Move to Input Output >

The command output method above is hardly used ever used. That’s because you can’t really tell if the target object might keep existing, unless you’ve defined the object yourself. Therefore, using output other than state output is usually done by passing a reference to an existing object to the command.

This, however requires you to *write* the line of an argument.

![](images/Input%20Output%20Parameter%20Passings.062.jpeg)

Nothing is *read* in the epilog in this case. Even though the argument functions as *output*, it’s still a *write* argument.

Any line going out of a diamond is set just before the diamond executes.

###### Write, Read ≠ Input, Output

`<< in / out vs. read / write confusion >>`

As such, *read and write arguments* is not analogous to *input and output arguments*. A write argument can easily serve as an output argument.

< 2021-05-02: It might be about context: reading from the inside, writing on the outside versus writing on the outside, reading on the inside. It seems about reading/writing in the context of containment structure. >

###### Reference Arguments

`<< details >>`

Reference arguments can serve as input, output and throughput. State arguments can serve as input, output and throughput too. 

`<< rule rich >>`

You’ll hardly use a line target as output information. You’ll probably use an argument’s line target only to pass an object by reference.

Even though an argument’s line is hardly ever read, an argument’s state *is* commonly read.

##### Using Arguments

`<< parameter passing >>`

You’ll mainly use arguments by reading and writing their state or to pass objects by reference.

##### Accessing Arguments During Execution

`<< creation behavior of commands >>`

Apart from writing in the prolog and reading in the epilog, there’s a third period in which you can access an argument: during execution. You can only access the arguments of a diamond *in execution*. The caller of the diamond is frozen, till the execution completes, so the caller doesn’t have any chance of accessing the arguments during execution. However, everything inside the executor is in motion. The executor itself can freely access its arguments, of course, but also anything it calls, could access its arguments, if given a reference. But, as I said, the *caller* of an execution can’t access the arguments during execution.

`<< details >>`

The diagrammatic effect of this is the following. A member can be accessed by the diamond that contains it, and by all its sub diamonds:

![](images/Input%20Output%20Parameter%20Passings.063.png)

I said, that commands called by a command can access its arguments. That suggests that the command that accesses the member can be somewhere else than inside the member’s diamond:

![](images/Input%20Output%20Parameter%20Passings.064.png)

Note, however, that it’s not the definition that’s accessing member __m__. It’s the call that’s accessing member __m__, and the call is contained inside the diamond that contains member __m__.

More rules on that are covered in the *Execution Basics* section.

#### Implicit Notations

`<< parameters of calls directly tied together >>`

`<< implicit calls >>`

< you can call an implicit call a parameter reference too. Mention it so you show that there’s a big difference between parameter reference and argument reference >

- Implicit call and Explicit call
- Implicit return value reference
- Implicit argument assignment

##### Previous Texts

###### A

####### Referencing Square Members: Implicit Call

`<< rule rich >>`

It is really only allowed to reference members of diamonds:

![](images/Input%20Output%20Parameter%20Passings.065.jpeg)

When you do reference a square’s member:

![](images/Input%20Output%20Parameter%20Passings.066.jpeg)

You’re actually seeing only part of the diagram. The reference to a square member actually creates a sibling diamond which is a call to the square:

![](images/Input%20Output%20Parameter%20Passings.065.jpeg)

The diamond missing when referencing the square member is called the implicit call to the square.

Even though the Symbol code *really* *defines* a reference to a square member, when the code is executed, it’s treated as having an extra diamond. Allowing referencing a square member can simplify the notation in many cases, that’s why it’s allowed.

The implied diamond always becomes the sibling of the reference to a member. In a more encapsulative situation, this:

![](images/Input%20Output%20Parameter%20Passings.067.jpeg)

Is the implicit notation of this:

![](images/Input%20Output%20Parameter%20Passings.068.jpeg)

The reference to a square member implicitly creates a call to the square right next to it.

Whenever you reference a square member, an implicit call is made.

![](images/Input%20Output%20Parameter%20Passings.069.jpeg)  
\=  
![](images/Input%20Output%20Parameter%20Passings.070.jpeg)

< Add some access symbols >

If you want to access members of a command using only one call, you might explicitly notate the diamond that is the call.

![](images/Input%20Output%20Parameter%20Passings.071.jpeg)

< Add some access symbols >

But the accesses can only only take place just before the call and just after.

But as I said: child diamonds can access their parent diamond’s members if the parent diamonds allows it.

![](images/Input%20Output%20Parameter%20Passings.072.jpeg)

####### An Object symbol as a Pointer to a Command Symbol: Implicit Return Value Reference.

`<< return values >>`

You can also let an object symbol point to a command symbol.

![](images/Input%20Output%20Parameter%20Passings.073.jpeg)

In that case you’re actually implicitly referencing the return value.

![](images/Input%20Output%20Parameter%20Passings.074.jpeg)

####### Implicit Call and Implicit Return Value Reference

`<< implicit calls >>`

`<< rule rich >>`

If an object symbol is a reference to a square, it’s both an implicit call and an implicit return value reference.

![](images/Input%20Output%20Parameter%20Passings.075.jpeg)

![](images/Input%20Output%20Parameter%20Passings.076.jpeg)

![](images/Input%20Output%20Parameter%20Passings.077.jpeg)

in the second picture you see the explicit call. The third picture adds the explicit return value reference. You don’t first do the explicit call and then the explicit return value reference. That order is totally arbitrary, you can also see it like this:

![](images/Input%20Output%20Parameter%20Passings.075.jpeg)

![](images/Input%20Output%20Parameter%20Passings.078.jpeg)

![](images/Input%20Output%20Parameter%20Passings.077.jpeg)

####### Reference to Other Out Parameters

`<< return values >>`

An object reference to a command can only be a reference to the command’s return value. If you want to reference other out parameters, you might reference them explicitly.

![](images/Input%20Output%20Parameter%20Passings.079.jpeg)

(o = out, r = return)

__a__ can only be a reference to __r__, the return value. __b__ is a reference to __o__, another out parameter.

#### Argument Reference

`<< interpretation >>`

There are three ways to use arguments: state read, state write and passing by reference:

| ![](images/Input%20Output%20Parameter%20Passings.080.png) | ![](images/Input%20Output%20Parameter%20Passings.081.png) | ![](images/Input%20Output%20Parameter%20Passings.082.png)|
|:------------:|:-------------:|:-------------------:|
| *State read* | *State write* | *Pass by reference* |

There seems to be one more: *argument reference*.

*Argument reference:*  

![](images/Input%20Output%20Parameter%20Passings.083.png)

`<< interpretation >>`

`<< rule rich >>`

<  
If it is interpreted as an implicit assignment call, things seem to fall in to place. And then the following ideas might not be needed.  
\>

This is however not possible, because the argument destroys after execution, so you can’t reference it after execution, because then there is nothing left to reference anymore. Argument reference is useless.

Argument reference is actually a fictive concept.

![](images/Input%20Output%20Parameter%20Passings.083.png)

It is actually an implicit notation for a *reference argument*:

![](images/Input%20Output%20Parameter%20Passings.082.png)

There’s more to getting the explicit notation of argument reference than just inversion of direction. Consider this diagram:

![](images/Input%20Output%20Parameter%20Passings.084.png)

This diagram has two argument references in it. If you might simply invert the direction you’d get the following:

![](images/Input%20Output%20Parameter%20Passings.085.png)

*(Note that the last access symbol didn’t change, because that line isn’t an argument reference)*

It still has a argument reference in it. 

The explicit notation that solves this is the following:

![](images/Input%20Output%20Parameter%20Passings.086.png)

The child diamond is inserted as a substitute for the higher diamond it refers to. This offers a solution because the parent of the child diamond might exist when the child exists. {This might be an issue for multiple execution of a diamond. It also raises the question what happens when you consult something of the diamond on the right. Is the bigger diamond executed first? What?} That’s rule two for getting to the explicit notation of parameter reference.

< I have doubts about this third rule. I think this case might be illegal. I need to find the rule on what makes it illegal and how you see the illegality of it in the implicit notation >

There’s one more problem. The explicit notation introduced so fat has a flaw: the object has two line targets! If a situation as such occurs, the directions of all flawed non-argument references are inverted:

![](images/Input%20Output%20Parameter%20Passings.087.png)

Which gives is rule three of the explicit notation of argument reference.

If a reference argument targets the argument of a parent diamond, it is not considered an argument reference.

![](images/Input%20Output%20Parameter%20Passings.088.png)

Argument reference is only the case where you *enter* a diamond.

##### Summary

So the implicit argument reference notation:

![](images/Input%20Output%20Parameter%20Passings.089.png)

Has the following explicit notation: < I know it is wrong, I should investigate later >

![](images/Input%20Output%20Parameter%20Passings.090.png)

Rule 1:

A argument reference (a line entering a diamond) is an implicit notation of the reverse direction (a reference parameter).

Rule 2:

If the line both enters and exists a diamond, then the inversion of direction doesn’t solve it. < > In that case, a child diamond is created in the diamond that holds the argument reference. The diamond references the diamond that held the argument reference target. The new child diamond is used instead. < >

Rule 3:

< ... >

You go from implicit to explicit notation in the following steps:

![](images/Input%20Output%20Parameter%20Passings.084.png)

Reverse direction of argument references

![](images/Input%20Output%20Parameter%20Passings.085.png)

Create child diamonds where the inversion doesn’t work

![](images/Input%20Output%20Parameter%20Passings.086.png)

Invert the direction of other lines that became faulty

![](images/Input%20Output%20Parameter%20Passings.090.png)

#### In, Out and Thru Argument Notation

`<< interpretation >>`

`<< rule rich >>`

< The out parameter access symbol isn’t required, so the notation of it *suggests* that it’s an in parameter reference. >

Argument reference notation (an implicit one):

![](images/Input%20Output%20Parameter%20Passings.091.png)

is saying that the actual reference argument:

![](images/Input%20Output%20Parameter%20Passings.092.png)

Is used as out and *not* as in.

![](images/Input%20Output%20Parameter%20Passings.093.png)

The explicit notation:

![](images/Input%20Output%20Parameter%20Passings.092.png)

can be in, thru or out. But the access symbol is usually not notated in case of outward direction:

![](images/Input%20Output%20Parameter%20Passings.094.png)

Therefore this outward notation with an access symbol suggests that it’s an in argument.

![](images/Input%20Output%20Parameter%20Passings.095.png)

Thru can be notated as:

![](images/Input%20Output%20Parameter%20Passings.096.png)

Which is not a real bidirection, because the line can’t *really* go inward anyway. It’s an implicit notation.

As such, there are six explicit argument purposes:

| ![](images/Input%20Output%20Parameter%20Passings.097.png) | ![](images/Input%20Output%20Parameter%20Passings.098.png) | ![](images/Input%20Output%20Parameter%20Passings.099.png) |
|:--------------:|:---------------:|:----------------:|
|   *State in*   |   *State out*   |   *State thru*   |
| ![](images/Input%20Output%20Parameter%20Passings.100.png) | ![](images/Input%20Output%20Parameter%20Passings.101.png) | ![](images/Input%20Output%20Parameter%20Passings.102.png) |
| *Reference in* | *Reference out* | *Reference thru* |

##### Execution Order in Text Code

`<< text code >>`

The resulting sequence of code lines corresponds to the execution order required for dependency. As you change the diagram, the order of the text code can change. You can freely move around text lines of sibling symbols.  
< The resulting sequence of code lines and the execution order within code lines. >

< Don’t cover exact text code here >

#### Implicit Notations

##### Previous Texts

###### B

####### Implicit Calls

`<< implicit calls >>`

< 2008-10-08 The texts that follow use an old notation for calls: a definition is a square without a reference line, a call is a square with a reference line. >  

< Maybe diagrams can be more basic, expressing solely a concept >  

< Reference a command parameter from an object. >  

To explain this concept I use an example where one command, called __Get__, returns an object that is then passed to another command, called __Set__. This requires two calls: first a call to __Get__ and then to __Set__.

######## Explicit Calls

`<< implicit calls >>`

The steps of this process can be described as follows:

```
Get
Set . In = Get . Out
Set
```

The out parameter of __Get__ is called __Out__ and the in parameter of __Set__ is called __In__. In diagram code, that is:

*Explicit calls:*

![](images/Input%20Output%20Parameter%20Passings.103.png)

Only the blue parts are shown in the piece of text code. You can see that __Get__ is called and __Set__ is called. Both __Get__ and __Set__ have a parameter. The parameters are shown in the definition, but also in the call. In the call, the parameters are actually created and the parameters in the calls are worked with. The __Out__ of __Get__ and the __In__ of __Set__ are tied together with an object line. You can’t explicitly see the order in which __Get__ and __Set__ are called, but because the __Set__ call references a parameter in the __Get__ call, __Set__ is dependent of __Get__, therefore __Get__ is called first.

######## Implicit Calls

`<< implicit calls >>`

In text code you can write the two calls in a single code line:

```
Set ( In = Get . Out )
```

__Get . Out__ is assigned to the parameter of __Set__. You’re referencing a parameter of __Get__ without displaying the call. To read the __Out__ parameter of __Get__ requires a call and this call is implicitly made. In the text code line above you don’t see that __Get__ is called. __Get . Out__ is simply referenced. You can apply the same to diagram code:

*Implicit call:*

![](images/Input%20Output%20Parameter%20Passings.104.png)

*Note that the Exit Most Borders rule determines the direction.*

You can see that the __Out__ parameter of the __Get__ command *definition* is referenced. This implicitly causes a call to __Get__. In *explicit calls* you reference the parameters of the command *call*, not the command *definition*.

######## Implicit Return Value Reference

`<< implicit calls >>`

__Out__ is __Get__’s return value. Therefore, the identifier __Get__ symbolizes the return value. __In__ is a parameter of __Set__ and you don’t necessarily need to mention its name in the parameter list. This all makes the text code:

```
Set ( Get )
```

__Get__’s symbolizing its return value can also be applied to diagram code:

*Implicit return value reference, implicit call:*

![](images/Input%20Output%20Parameter%20Passings.105.png)

The line to __Get__ is not really a line from an object to a command. The return value of __Get__ is implicitly referenced.

The diagram above looks far simpler than the first diagram. So might the text code. In reality multiple steps are taken: • Call __Get__ • Read __Get . Out__ • Write __Set . In__, • Call __Set__.

In the diagram above, the return value is implicitly referenced by pointing to the command definition. You can also implicitly reference the return value by pointing to a command call square. That way, the call is explicit, but the return value reference is implicit.

*Explicit call, implicit return value reference:*

![](images/Input%20Output%20Parameter%20Passings.106.png)

######## Multiple Out Parameters

######### Implicit Return Value Reference

`<< return values >>`

`<< implicit calls >>`

Implicit return value reference is only a way to reference the *return value*, not to the other out parameters. The other out parameters might be explicitly referenced. 

*Implicit return value reference, explicit out parameter reference:*

![](images/Input%20Output%20Parameter%20Passings.107.png)

######### Implicit Calls

`<< implicit calls >>`

When you reference output parameters of a command multiple times, each reference causes its own call to be made. 

*Two references to a parameter of the definition: two implicit calls:*

![](images/Input%20Output%20Parameter%20Passings.108.png)

If the diagram above is an abstract view on the system, there might only be made a single call, but officially the diagram above is showing *two* implicit calls. The meaning of the diagram above is:

< P: same system as above, now physically showing the two calls >

If you want to reference multiple output parameters of a single call, you might explicitly display the call and reference the objects that are inside the call symbol. By referencing the parameters of the call, you only use one call.

![](images/Input%20Output%20Parameter%20Passings.109.png)

< Call in blue >

###### C

####### ? Referencing a Command Member

`<< details >>`

< 2008-10-08 Most of what is said in this section no longer applies, because a more explicit notation is desired, to make things less ambiguous, and some remarks have already been thought through and work differently. >

`<< ? >>`

Referencing a diamond’s members is like reading a command member.

![](images/Input%20Output%20Parameter%20Passings.110.jpeg)

`<< implicit calls >>`

< 20040418: this is interesting. It has to do with implicit call and I might explore in which situation this is useful. I think that when you call a member of the top circle, then the diamond executes. It’s like calling member of the bottom circle... >

It always happens just after the diamond executes.

`<< creation behavior of commands >>`

`<< interpretation >>`

< The parameter objects destroy right after the call. If you use the top circle like above, every consult of the top circle might result in executing the diamond again. To persist the information contained in the argument, without having to call the command again, you might do a State Copy. Another way of using output parameters is to give the execution a reference to an external symbol. Anyway: if you want return information to persist after the call, it has to be stored in external symbol: store the returned state to an object that the caller contains, or pass a reference to the caller’s object to the called command >

`<< interpretation >>`

< That’s true what I just said, but there’s nothing wrong with linking directly to the parameter and executing the command on each consult. There’s nothing wrong with that. The link might be something like consulting a property command in VB, a Get, which returns a reference to an object. Every time you consult the property, the command is launched again. That’s normal. >

< 2021-05-04: That last interpretation may be different if you might regard each diagram its own execution. Or when you might see the parameter line as a cloaked assignment call.  >

`<< details >>`

< Might denote that the notation above is not an output situation. It’s an implicit call situation >

##### Brainstorm Items

###### 1

`<< implicit calls >>`

Oh, die assignments lijken afzonderlijke referenties, waardoor je implicit calls krijgt? Of is dat alleen bij referenties naar inhoud van squares?

Oh, nee! Hè! Ik heb ergens in dit hoofdstuk iets staan over een diamond die execute telkens als je een object met een line naar een parameter beraadslaagt. Hoe zit DAT dan?

Dat is verkeerd  
\>

###### 2

`<< implicit calls >>`

*Nice wording:*  
A reference to something inside a square causes an implicit call to the square, because the command is required to execute in order to reference something inside of it.

###### 3

`<< implicit calls >>`

Implicit calls when referencing square contents (and their explicit diagram representations)

#### Forming New Subdivision

These seem fragments of an attempt to re-subdivide topics formerly inside the original Symbol documentation from 2004.

##### Old Subdivision

`<< implicit calls >>`

- Implicit call and Explicit call
- Implicit return value reference

`<< parameter passing >>`

- Out, In and Thru parameter usage
    - Cover command reference too
    - `<< execution flow >>`
    - If example

`<< implicit calls >>`

- Initiation of execution:
    - Containment in other diamond
    - Consult of a parameter.

##### New Subdivision

- `<< parameter passing >>`
- Out, In and Thru
    - Using reference parameters for in, out and thru (hard to control whether it’s in out or thru: you just use the object)
    - Using State as In, Out and Thru
    - Using a parameter’s line targets as Out
        - `<< about other technology >>`
        - Comparison with Com regarding returning object references.
            - Persisting object reference (harder, is hardly done anyway. Or is it? Consider passing the returned object to another command)
            - Using the command parameter as object reference directly
    - `<< parameter passing >>`
    - Command reference too
    - `<< execution flow >>`
    - If example

- Execution Order
    - `<< interpretation >>`
    - Seeming randomly referencing diamond members.
    - `<< ? >>`
    - Initiation of execution:
        - Containment in other diamond
        - Consult of a parameter.
    - `<< sequence order >>`
    - Manual execution order

`<< implicit calls >>`

- Implicit Notations
    - Implicit call and Explicit call
    - Implicit return value reference

##### New Main Subdivision

`<< parameter passing >>`

- Out, In and Thru

`<< ? >>`

- Execution Basics

`<< ? >>`

- Execution Order

`<< implicit calls >>`

- Implicit Notations

#### Brainstorm

##### New Brainstorm Texts

###### New

`<< creation behavior of commands >>`

- < > The assignment destination consult is not seen as a consult. < > Consult of a parameter as assignment destination might not require execution of the parameter holder.
- Executor represents one execution per call on definition.
    - Implicit calls are not made for diamond contents reference < >

###### Old

`<< creation behavior of commands >>`

`<< interpretation of parameter connections >>`

< 2008-10-08 This talks about parameter passing, a notation for value assignment and about implicit call. Those three might be spread over multiple documentation sections. But do the cross out here. >

![](images/Input%20Output%20Parameter%20Passings.111.jpeg)

In implicit argument assignment, there is no way to express state assignment.

![](images/Input%20Output%20Parameter%20Passings.112.jpeg)

If it were to become a connection between symbols, like implicit line assignments, it might definitely not behave the same as a line.

*Implicit assignments:*

![](images/Input%20Output%20Parameter%20Passings.113.jpeg)

De assignment calls gedragen zich niet normaal, want consult van de argumenten van __A__ veroorzaken geen executie. Een soort passieve parameter consult vind plaats door de assignment calls, in het proloog van __A__. Bedenk wel: het zijn systeem commands: niet normaal.

![](images/Input%20Output%20Parameter%20Passings.113.jpeg)![](images/Input%20Output%20Parameter%20Passings.114.jpeg)

De calls naar system commands gedragen zich anders dan gewone calls. Ze vinden namelijk hier plaats in het proloog van de executie. Je ziet dit wèl in de text code, maar hoe zie je in diagram code of een systeem commando apart wordt aangeroepen of in de context van een andere functie aanroep?  
Hypothese: als je bij systeem commando aanroep een parameter betrekt in een diepere executie, dan zit het in het proloog of epiloog. Zit de parameter in de huidige of hogere executie, of is er helemaal geen parameter bij betrokken, dan wordt de systeem commando call normaal uitgevoerd. En veroorzaakt geen executie van de sub executor.

Niet het een executor, anders verwar je het met een aparte executie! Een system commando triggert geen executor:

![](images/Input%20Output%20Parameter%20Passings.115.jpeg)

\* dit zou A triggeren als het niet een line van een system commando call was.

Assignment commands = system commands, eerste argument is het __This__ argument.

![](images/Input%20Output%20Parameter%20Passings.116.jpeg)

\* 2 consults, 1 execution. 1 executor zou er eigenlijk moeten zijn om 1 keer uitgevoerd te worden per ... definitie aanroep (afgezien van jumps) (? Hoe zit het daar dan precies mee)

Dus implicit call moet niet bestaan bij het referen naar diamond members. Dus dan heb je ook niet het probleem dat *assignment calls* speciaal geplaatst moeten worden in het proloog en epiloog: consult van diamond members vind *altijd* plaats in proloog of epiloog!  
Oh jawel! Consult vind gewoonlijk altijd plaats in epiloog, maar bij assignment van argumenten consulteerd __*system commando*__ de argument in *proloog*.

![](images/Input%20Output%20Parameter%20Passings.117.jpeg)

![](images/Input%20Output%20Parameter%20Passings.118.jpeg)

##### Argument Access Summary

###### In, Out and Thru

- `<< parameter passing >>`
- Using reference parameters for in, out and thru (hard to control whether it’s in out or thru: you just use the object)
- Using State as In, Out and Thru
- Using a parameter’s line targets as Out
    - `<< other technology >>`
    - Comparison with Com regarding returning object references.
        - Persisting object reference (harder, is hardly done anyway. Or is it? Consider passing the returned object to another command)
        - Using the command parameter as object reference directly
- `<< parameter passing >>`
- Command reference too
- `<< execution flow >>`
- If example

#### Brainstorm

##### Other

__*Different Wording, Not important, though*__

`<< creation behavior of commands >>`

`<< nice wording >>`

In an explicit call you always see the the call displayed as a separate diamond. If the call is made, the call is like a created object. After the call it is destroyed. When the call is created, you can reference its contents from anywhere without causing another call.

### Misc Loose Ideas

`<< parameter passing >>`

There are three types of parameters: in, out and thru. In parameters go in, out parameters go out and thru parameters come in and go out.

-----

`<< rule rich >>`  

`<< interpretation issues >>`

When pass an input parameter by value, it is guaranteed, that the operations inside the command might not affect the original object. < 2021-05-03: in VB.NET's ByVal parameter passing for reference types, the situation seem slightly more nuanced than that. >

-----

`<< details >>`

In parameter passing __By Value__, the parameter object and the object, that is passed the value to or from, are not referring to each other at all.

-----

`<< about other technology >>`

In some programming languages one use of *by reference* was to be able to pass large objects to a command. Another use was to be able to let the command have multiple return values, because in other programming languages a command might only have one return value.

`<< details >>`

A __Value In__ parameter works best simple objects, that stores a single value,
