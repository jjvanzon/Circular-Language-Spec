Circle Language Construct Drafts | Input Output
===============================================

Parameter Passing
-----------------

These sections were set aside in the project *Work Out Parameter Articles*.

The sections each cover an obsolete parameter passing type.

The terminology of these parameter passings types are still used elsewhere in the documentation, so I wanted to wrap these terms up into articles.

But these articles talk too much about input and output. The terms input and output are harder to define. The *Advanced Command Topics* are for a big part about input and output. So these sections are yielded over to the *Advanced Command Topics*, so they can be approached in there.

Much of the text may not be true anymore.

### By Value

A parameter is __By Value__, if you can only publicly read or write the value of the object or clone the values of an object up until a certain depth. 

Passing a parameter by value means, that the input or output is *copied* to or from the parameter object.

Parameters passed by value are really only useful for smaller amounts of data. The data might be changed inside the command, but that will not affect the original object.  
For an object, that only stores one value and that’s it, it is easy to just copy the value. More complex objects passed by value will be cloned up until a certain cloning depth.

When pass an input parameter by value, it is guaranteed, that the operations inside the command will not affect the original object.

For that reason, when a value parameter is cloned up until a certain depth, no references to original objects will be taken over by the clone. __By Value__ clones never have references to existing objects, but always contain entirely new objects or object references that are __Nothing__.

A single-value transfer is actually the equivalent of a cloning operation with a depth of __1__.

If you want to pass more complex objects to a command, you do it by reference, but then changes to the parameter will affect the original objects.

In parameter passing by value, the parameter object and the object, that is passed the value to or from, are not referring to each other at all.

-----

Relations between objects,  
Value parameters,  
2008-09-09

Value parameters do not have the interchangeability between command parameters and object commands, because they are not a relationship.

JJ

### By Value in a Diagram

The diagram below represents a __By Value__ parameter tied to the value source or target:

![](images/Input%20Output%20Parameter%20Passings.001.png)

The diamond is the command. The circle inside it is the parameter. The circle outside the command is the value source or target. And the wavy line indicates value transmission between the parameter and the other object.

It is actually a value assignment, that performs a yield over of value.  
Here is a diagram showing such a value assignment:

![](images/Input%20Output%20Parameter%20Passings.002.png)

A value assignment *does* have an invisible reference to the parameter, but you won’t see it in the diagram, because an assignment is something so basic, that the notation of it is kept very basic.

The complicated notation:

![](images/Input%20Output%20Parameter%20Passings.003.png)

(the arrows are pointing to the references invisible earlier)

But this still does not tie the source and target symbols directly together.

The notation of a __By Value__ cloning operation looks as follows:

![](images/Input%20Output%20Parameter%20Passings.004.png)

The number __2__ stands for the cloning depth.
A single-value transfer will be the same as a cloning depth of __1__, but the number __1__ will not be shown then.

### By Reference

Next to passing a parameter by *value*, you can also pass a parameter by reference. For instance: instead of copying a value to an input parameter, you give the command a reference to an object outside the command.

__Reference__ parameter:

![](images/Input%20Output%20Parameter%20Passings.005.png)

Therefore it can also be called __Reference Outward, Value In__ and __Reference Outward, Value Out__ But those names are too long. The distinction between __Reference In__ and __Reference Out__ is about whether values are read or written to the object passed to the sub-command.

In earlier programming languages one use of by reference was to be able to pass large objects to a procedure. Another use was to be able to let the procedure have multiple return values, because in other programming languages a procedure can really only have one return value. In the new computer language, multiple return values is accomplished by having multiple __Object Out__ parameters. So you do not need __Reference Out__ parameters for that purpose anymore.

When a command call has an outward reference to an object, this *does* make the object a parameter, but this *does not* determine yet whether it is input, output or throughput. The *in* and *out* in this case refer to whether *values* are written or read to the object reference. A reference parameter is always sort of like input, though: the parent command passes the object to the sub-command, so the parent inputs something into the sub command.

### Value In

A __Value In__ parameter passes a value from an object to the parameter of a command. A __Value In__ parameter is an object inside the command call, that can be written before the command is invoked, by assigning to it a value of an object outside the command call.

The command can manipulate the __Value In__ parameter without affecting the original object.

A __Value In__ parameter works best simple objects, that stores a single value, but can also work for more complex objects, that will then be cloned up until a certain depth.

### Value In in a Diagram

A diagram of an executable command with a __Value In__ parameter:

![](images/Input%20Output%20Parameter%20Passings.006.png)

Here is a diagram of an unfilled-in __Value In__ parameter of an executable command:

![](images/Input%20Output%20Parameter%20Passings.007.png)

A __Value In__ parameter can also have an indication of a cloning depth, which is displayed as follows:

![](images/Input%20Output%20Parameter%20Passings.008.png)

Or for an unfilled-in __Value In__ parameter:

![](images/Input%20Output%20Parameter%20Passings.009.png)

The pictures above display a cloning depth of __2__, but any cloning depth can be used.

A command definition or other inactive command displays __Value In__ parameters the exact same way. The __Value In__ parameter of a command definition is usually not filled in:

![](images/Input%20Output%20Parameter%20Passings.010.png)

But the __Value In__ parameter of an inactive command could be filled in just as well:

![](images/Input%20Output%20Parameter%20Passings.011.png)

The fact, that it is an inactive command, means that it will not run, but for the rest it is the same as any other command object, so it basically has the same possibilities.

Here is the expression of cloning depth for __Value In__ parameters of inactive commands, which is the same notation as for active commands:

![](images/Input%20Output%20Parameter%20Passings.012.png)

![](images/Input%20Output%20Parameter%20Passings.013.png)

### Value Out

A __Value Out__ parameter is a value produced by a command, that can be yielded over to another object after the command is done. A __Value Out__ parameter is an object inside the command call, that is written to by the command or by one of its sub-commands. After execution of the command the value of the output parameter can be copied, by assigning the value to another object.

As said in the article __By Value__, the parameter is either a copy of a single value, or a clone up to a certain depth.

### Value Out in a Diagram

A diagram of an executable command with a __Value Out__ parameter looks as follows:

![](images/Input%20Output%20Parameter%20Passings.014.png)

The following diagram shows the __Value Out__ parameter with an assignment target indicated to which the output value will be transferred:

![](images/Input%20Output%20Parameter%20Passings.015.png)

A __Value Out__ parameter can also have an indication of a cloning depth, which is displayed as follows:

![](images/Input%20Output%20Parameter%20Passings.016.png)

Or with the target of the output filled in:

![](images/Input%20Output%20Parameter%20Passings.017.png)

The pictures above display a cloning depth of __2__, but any cloning depth can be used.

A command definition or other inactive command displays __Value Out__ parameters the exact same way. The __Value Out__ parameter of a command definition will look like this:

![](images/Input%20Output%20Parameter%20Passings.018.png)

The __Value Out__ parameter of an inactive command can also be read and written to a target object, like this:

![](images/Input%20Output%20Parameter%20Passings.019.png)

The fact, that it is an inactive command, means that it will not run, but for the rest it is the same as any other command object, so it basically has the same possibilities, even reading and writing its parameters.

Here is the expression of cloning depth for __Value Out__ parameters of inactive commands, which is the same notation as for active commands:

![](images/Input%20Output%20Parameter%20Passings.020.png)

![](images/Input%20Output%20Parameter%20Passings.021.png)

### Value Thru

Throughput by value is when a by value parameter is first written to, then changed by the command, and then the value of the parameter is read from again, and assigned to the original object.  
A __Value Thru__ parameter is an object inside the command call, that can be written before the command is invoked, by assigning to it a value of an object outside the command call. It is used but also written to by the command or one of its sub-commands. After execution of the command the value of the throughput parameter can be copied, by assigning the its to another object.

As said in the article __By Value__, the parameter is either a copy of a single value, or a clone to a certain depth.

In theory the value could first come from one object, and after the call be written to another object. But that’s not regularly what a __Value Thru__ parameter is used for. The value will first be copied from one object and assigned to the parameter, and afterwards the value of the parameter is copied to the original object again.

### Value Thru in a Diagram

A diagram of an executable command with a __Value Thru__ parameter:

![](images/Input%20Output%20Parameter%20Passings.022.png)

Here is a diagram of an unfilled-in __Value Thru__ parameter of an executable command:

![](images/Input%20Output%20Parameter%20Passings.023.png)

A __Value Thru__ parameter can also have an indication of a cloning depth, which is displayed as follows:

![](images/Input%20Output%20Parameter%20Passings.024.png)

Or for an unfilled-in __Value Thru__ parameter:

![](images/Input%20Output%20Parameter%20Passings.025.png)

The pictures above display a cloning depth of __2__, but any cloning depth can be used.

A command definition or other inactive command displays __Value Thru__ parameters the exact same way. The __Value Thru__ parameter of a command definition is usually not filled in:

![](images/Input%20Output%20Parameter%20Passings.026.png)

But the __Value Thru__ parameter of an inactive command could be filled in just as well:

![](images/Input%20Output%20Parameter%20Passings.027.png)

The fact, that it is an inactive command, means that it will not run, but for the rest it is the same as any other command object, so it basically has the same possibilities.

Here is the expression of cloning depth for __Value Thru__ parameters of inactive commands, which is the same notation as for active commands:

![](images/Input%20Output%20Parameter%20Passings.028.png)

![](images/Input%20Output%20Parameter%20Passings.029.png)

### Reference In

A __Reference In__ parameter can be used to assign a reference to a complex object as the input of the command. Because a __Reference In__ parameter is input, the called command can only *read* out of the object, that it was given a reference to.

### Reference In in a Diagram

A diagram of an executable command with a __Reference In__ parameter looks as follows:

![](images/Input%20Output%20Parameter%20Passings.030.png)

When a __Reference In__ parameter does not have a reference target filled in yet, then the diagram looks as follows:

![](images/Input%20Output%20Parameter%20Passings.031.png)

An inactive command displays __Reference In__ parameters the exact same way. The fact, that it is an inactive command, means, that it will not run, but for the rest it behaves the same way as any other command object, so it basically has the same possibilities as an active command. The reference target of a __Reference In__ parameter of an inactive command definition is usually not filled in.

![](images/Input%20Output%20Parameter%20Passings.032.png)

Here is a picture in which a command definition’s __Reference In__ parameter does have its reference target filled in:

![](images/Input%20Output%20Parameter%20Passings.033.png)

Do note, that the expression of read-write direction is not a connector point, like for __Value__ parameters. It is an abstract expression of value direction. You can not connect anything to it. The reference target connector, however, *is* a connector point.

### Reference Out

When a command is passed a reference to an object, and the command writes to the parameter, it is called a __Reference Out__ parameter. Because a __Reference Out__ parameter is output, the called command can only *write* to the object, that it was given a reference to. A __Reference Out__ parameter can be used to assign a reference to a complex object to which a command writes output.

In a sense, a __Reference *Out*__ parameter is actually *through*put.  
When output is *alteration* of an *existing* object, it could be considered throughput, even though there is only *written* to the object, and nothing is *read* from the object, it is still an object passed *through* the command. In yet another sense, a __Reference Out__ parameter is input, because you are passing an object *into* a command.

### Reference Out in a Diagram

A diagram of an executable command with a __Reference In__ parameter looks as follows:

![](images/Input%20Output%20Parameter%20Passings.034.png)

The access mark on the left is a connector point, to which the reference target of the __Reference Out__ parameter can be attached. Here is a diagram in which a reference target is attached to the __Reference Out__ parameter.

![](images/Input%20Output%20Parameter%20Passings.035.png)

The fact that the reference goes outwards, does not make it an Out parameter. That just makes it a __Reference__ parameter. The fact, that the command only *writes* to the parameter makes it an Out parameter, so the term __Out__ is about value direction, not reference direction.

An inactive command displays __Reference Out__ parameters the exact same way. The fact, that it is an inactive command, means, that it will not run, but for the rest it behaves the same way as any other command object, so it basically has the same possibilities as an active command. The reference target of a __Reference Out__ parameter of an inactive command definition is usually not filled in:

![](images/Input%20Output%20Parameter%20Passings.036.png)

Here is a picture in which a command definition’s __Reference Out__ parameter does have its reference target filled in:

![](images/Input%20Output%20Parameter%20Passings.037.png)

Note, that the indication of read-write direction is an abstract expression of the value direction inside the command. You can not connect anything to it.

### Reference Thru

Next to __Reference In__ and __Reference Out__, there is also __Reference Thru__, which means, that the command both reads and writes to the object passed to it. A __Reference Thru__ parameter is a pointer to something outside the command. The object pointed to both read from and written to. A __Reference Thru__ parameter can be used to assign a reference to a complex object, from which input is read and output is written to. 

### Reference Thru in a Diagram

A diagram of an executable command with a __Reference Thru__ parameter looks as follows:

![](images/Input%20Output%20Parameter%20Passings.038.png)

When a __Reference Thru__ parameter does not have a reference target filled in yet, then the diagram looks as follows:

![](images/Input%20Output%20Parameter%20Passings.039.png)

An inactive command displays __Reference Thru__ parameters the exact same way. The fact, that it is an inactive command, means, that it will not run, but for the rest it behaves the same way as any other command object, so it basically has the same possibilities as an active command. The reference target of a __Reference Thru__ parameter of an inactive command definition is usually not filled in.

![](images/Input%20Output%20Parameter%20Passings.040.png)

Here is a picture in which a command definition’s __Reference Thru__ parameter does have its reference target filled in:

![](images/Input%20Output%20Parameter%20Passings.041.png)

Do note, that the expression of read-write direction is not a connector point. It is an abstract expression of value direction. You can not connect anything to it. The reference target connector, however, *is* a connector point.

### Object Out

An __Object Out__ parameter is an object, that resides inside the command. The __Object Out__ parameter may be a new object, or redirect to an existing object. Anyway, the *command* determines which object will be output. The produced object can be referenced from outside the command.

Unlike parameters passed __By Reference__, an __Object Out__ parameter is *referred to*. This is an exclusive aspect of the __Object Out__ parameter passing.

The long names of parameters passed __By Reference__ were:

- __Reference Outward, Value Inward__
- __Reference Outward, Value Outward__
- __Reference Outward, Value Thru__

The long name of value __Object Out__ is:

- __Reference Inward, Value Out__

So this is a __Reference Inward__ parameter, as opposed to a __Reference Outward__ parameter. The reference direction goes the other way around. Instead of a parent passing an object to the command, it is like the *command* passes a reference back to container of the command.

The command writes to the output object. Unlike __Reference__ and __Value__ parameters, there is no distinction between __In, Out__ and __Thru__ for __Reference Inward__ parameters. The reason __Reference Inward__ parameters do not have three variations, is that the command’s reading and writing values to the object is irrelevant to the *parameter passing*. To the outside, it does not matter whether the parameter is read from or written to or both. All that matters, is that an object is produced. __Reference Inward, Value In__ and __Reference Inward, Value Thru__ are not relevant. The __Reference Inward__ parameter *can* be *read from* by the sub-command, but that it’s just not relevant to *parameter passing* between a command and its container. Because __Reference Inward, Value Out__ is only relevant for reading values from an output object, it is shortened to __Object Out__. 

An __Object Out__ should really only be accessed *after* the command has run.

< An __Object Out__ parameter can be a regular object, but it can also be a command object. In that case it is a command *produced* by another command. The parent command can return a new command or the parent command can return a reference to an existing command. >

#### New command ( / new object )

When an __Object Out__ parameter is actually a new command, then the new command is either a pre-configured instance of another command, or it can be a brand new, generated command, any part of which is constructed by its parent command, based on a set of variables.

#### Existing command ( / existing object )

An __Object Out__ parameter can also be an existing command. In that case the Object Out parameter object-redirects to another command again, so the parent command basically picked out a command for you, instead of actually producing a new one.

### Object Out in a Diagram

A diagram of an executable command with an __Object Out__ parameter looks as follows:

![](images/Input%20Output%20Parameter%20Passings.042.png)

The outer end of the line is an connection point to which you can connect an object to refer to the __Object Out__ parameter:

![](images/Input%20Output%20Parameter%20Passings.043.png)

An inactive command displays __Object Out__ parameters the exact same way. The fact, that it is an inactive command, means, that it will not run, but for the rest it behaves the same way as any other command object, so it basically has the same possibilities as an active command. The object referring to the __Object Out__ parameter of an inactive command definition is usually not filled in.

![](images/Input%20Output%20Parameter%20Passings.044.png)

Here is a picture in which a command definition’s __Object Out__ parameter does have a referrer:

![](images/Input%20Output%20Parameter%20Passings.045.png)

### Three Parameter Passing Elements

__By Value, Reference Outward__ and __Reference Inward__ are the different reference situations a parameter can have. But this tells us nothing about whether a parameter is input, output or throughput. What determines, whether it is in, out or thru is whether values are written to the parameter or read from the parameter.

So the long names of the different parameter passing types are:

- __Value In__
- __Value Out__
- __Value Thru__
- __Reference Outward, Value In__
- __Reference Outward, Value Out__
- __Reference Outward, Value Thru__
- __Reference Inward, Value Out__
- ~~__Reference Inward, Value In__~~ 
- ~~__Reference Inward, Value Thru__~~ 

__Reference Inward, Value In__ and __Reference Inward, Value Thru__ are not relevant, because an reference *inward* only is about an *output* object.

It is important to keep understanding that there are three elements to parameter passing:

- Values read or written
- Parameter is a reference outward
- Parameter is referenced from the outside

To understand how the different parameter passings came about, it is important to keep those three aspects in mind.

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

The reason why it is important to keep understanding the three aspects of parameter passing, is that __Reference__ parameters, even though they can be __In, Out__ or __Thru__, are always *input* in a way, because it is a reference passed from the parent command to the sub-command.

__Value In__ and __Value Out__ means reading and writing done by de caller. __Reference In__ and __Reference Out__ means reading and writing done by the called command. In both cases __In__ does mean, that the called command *uses* something, and __Out__ means, that the called command returns something.

### Parameters of calls directly tied together

In other programming languages, sub-commands do not directly read or write to each other’s parameters. Parameters are only read or written by the parent command.

However, in the new computer language, parameters of commands can be tied together directly.

One parameter type can only be tied to a parameter with specific other parameter type.

__Value In__ parameters and __Value Out__ parameters can only be tied together:

![](images/Input%20Output%20Parameter%20Passings.053.png)

Only __Object Out__ and __Reference__ parameters can be tied together:

![](images/Input%20Output%20Parameter%20Passings.054.png)

Tying parameters together directly states a direct dependency. No direct reference to the parameter objects are required inside the parent command.

A __Value Thru__ parameter can not be tied to another parameter:

![](images/Input%20Output%20Parameter%20Passings.055.png)

This is because it creates a circularity in which one parameter writes its values to the other, and the other parameter writes its value to the first parameter. It is just an unlogical circular situation.

When directly tying together value parameters, cloning depth can be intermixed:

![](images/Input%20Output%20Parameter%20Passings.056.png)

![](images/Input%20Output%20Parameter%20Passings.057.png)

Effectively, it will be the lowest cloning depth that will be transferred to the input parameter on the right. When the __Value In__ and __Value Out__ parameters have the same cloning depth, it is drawn out as follows:

![](images/Input%20Output%20Parameter%20Passings.058.png)

### Strict about parameter passing

I really want the programming environment, to not so easily accept, that a parameter is typed throughput, when it is only read from. Because otherwise you rely too much on courtesy of the programmer, to make the whole system function correctly.

You could define a parameter as throughput, but actually only read from it. In that case the parameter is implicitly degraded to an input parameter. The implicit parameter type counts. The implicit parameter passing is dependant on the way it is declared and the way it is used. A throughput parameter is not only declared as such, but also always used as such. 

### The class of a parameter

The class of a parameter is usually set by the command, that holds the parameter. In that case, you can only assign objects or values of objects to it, that have the same class as the parameter indicates.

It is also possible, that a parameter does not have a class. In that case any object or any object’s value can be passed to the command.

When the class of a parameter is determined from the outside, then it is special. It is a __Class Reference__ parameter. In that case you may not be able to also use it as a normal __Reference__ parameter. < I don’t know yet. >

### Sub-commands are never output objects

Sub-commands, so active command objects inside another command, are never referenced so sub-commands can never output objects.

The rule is explained in the article *Sub-Commands are Never Referenced*, as part of the set of rules that protect a parent command’s control over the execution of its sub-commands.

This rule also implies, that sub-commands (active commands inside another command) can not be output objects. If the rules that protect the parent’s control over its sub-command’s execution change, then the rule sub-commands are never output objects might not apply anymore.

A parameter, that is a command reference, can be run, but it can never point to an active command inside another command, so that never lets any parent command loose control over any sub-command’s execution.

### In, Out & Thru Parameters

Parameters can function as input, output and throughput. Input, output and throughput are parameter passing types. They are shortened to __In, Out__ and __Thru__.

When a command’s parameter is __In__, it means that the command reads from the parameter. When a command’s parameter is __Out__, it means that the command writes to the parameter. When a command’s parameter is Thru, it means, that the command reads and writes the parameter. Throughput functions as both input and output at the same time.

Before execution you can read and write. > 2008-09-24 from the outside  
During execution you can not read or write. > 2008-09-24 from the outside  
After execution you can only read. > 2008-09-24 from the outside

### Downput

Next to the terms input, output and throughput, the term downput will be introduced. Downput is intermediate data as a helper of a process, that will eventually produce output. Temporary variables, local variables. They are all downput. Actually, in the command-call structure, a command in which output data is disposed, this output has become downput.

Downput data is private data of the command.

The term downput is a good term, because it is only passed *down* into sub-commands. And it is dropped after the parent command is done (dropped *down*). It is ‘put down’ / rejected after the execution. Or put down / to put something down, that you had in your hand.

When a command disposes objects after it is done, then those objects are called *downput*. Downput may have been input for sub-commands, or it could have been output of sub-commands. To the parent command, though, it is *downput*. Downput parameters will not be further considered here, because they do not have anything to do with parameter *passing*.

### Incidental parameter passing

One time a command runs, something may only be read. Another time it may be read and written to. This changes the implicit position of the object in relation to to the command for each call to the command. You could stereotype it an input parameter as __Not Input__ and an output as __Not Output__ and a thru parameter as __Only Input__ or __Only Output__ or __Not Thruput__. But it does not replace the parameter’s __In, Out__ or __Thru__ properties, because they belong to the command definition.

The object command’s on the other end of the relationship, also get additional typing based on the incidental parameter passing, but the passing names are not even determined yet.

### Indirect Value Transmission

Used in abstract notations, explained later, a value line does not necessarily mean yielding over the value of one object on one end of the line to the other object on the other end of the line. It may be yielding over values between sub-objects. So it’s not synonym to a value assignment in that case.  
But usually value direction means assigning the value of one object to another.

- \> Indirect value direction may be called data direction, and will be given a double wavy line as a symbol. It can indicate addition, removal, creation, annulment and value transfers of the direct object or its sub objects.

For __Reference__ parameters it does not need to be the value of the object itself, that is read or written.

It can also be a *sub-object* of the parameter, that is read or written. Even though the parameter itself is not read or written, but only its sub-object, the parameter *itself* is considered input or output, even though only the values of its *sub-*objects are used. 

Sometimes the command itself does not read or write from a parameter, but the parameter is passed down to a sub-command, that reads or writes from the object. This yields over the in-out-thru properties of the parameter. This does give the parameter an indication of value direction, but this is an abstract notation of what is going on. The assignments are done by a sub-command.

Next to values being read or written, an abstract indication of value direction is also used to indicate addition, removal, creation and annulment of objects. These actions are all considered *writing* or *output*.  
In the definition of the command, you will see the individual additions, removals, creations and annulments as calls to system commands (see the *System Objects* documentation section).  
But the __Reference__ *parameter* will get an *abstract* value direction indication, that says the reference parameter is output.

All in all, non-value transmissions apply to __By Reference__ parameters only.

So for reference parameters, the in-out-thru direction will be an abstract indication of what is going on. It can mean a lot of different things. The exact objects and manipulations a command executes on a reference parameter are indicated by its command IO, covered in the article *Command IO* (possibly still part of the article *Automatic Execution Order*).

### Wrong approach to the terms In, Out and Thru

*2008-09-29*

#### In, Out & Thru

The terms I would like to see back in access control literals are the terms __In, Out__ and __Thru__.

After a lot of brainstorm I figured, that whether something is __In__ or __Out__ depends on whether something is being *written* from the *outside* or on the *inside*. When something is set on both the outside and the inside, then it is called __Thru__. From which direction something is *read* is not relevant for the terms __In, Out__ and __Thru__.

When you write one aspect on the outside, it does not mean that the same aspect is supposed to be read on the inside. You may write one aspect on the outside and read another aspect on the inside. For instance, if you write the object from the outside, you may only read its value from the inside. Earlier, this would produce the following literal:

- __Object Set Public, Value Set Private__

But the terms __Set Public__ and __Set Private__ can be replaced now by the terms __In__ and __Out__:

- __Object In Value Out__

It looks a lot clearer that way.

If the *same* system aspect is written from both the inside as well the outside, then the term __Thru__ will be used, for instance:

- __Object In Value Thru__

The keyword __Thru__ can only be used, when it is the same aspect, that is set from both the inside and the outside. When different aspects are written on the inside and the outside, you will not see the word __Thru__ in the access control literal. For instance, when a parameter is:

- __Object In Value Out__

it can be called a __Thru__ parameter, but you will not use the term __Thru__ in the access control literal, because you can only use the term __Thru__ in a literal when the *same aspect* is set on both the inside and the outside.

The use of the keyword __Thru__ may also become scarce, if you insist to keep the access control elements in chronological order:

- __Object In, Value In, Value Get Private, Value Out__

Even though __Value__ is __Thru__, the __Value Get Private__ is put in between the __Value In__ and __Value Out__, because of the chronological order of access control elements. It is not clear yet what I want to do with this in the future. Perhaps a rule, that makes the literal:

- __Object In, Value Thru, Value Get Private__

But I am not sure yet.

#### Terms for reading

Reading stuff does not seem to have anything to do with the terms __In, Out__ and __Thru__. __In, Out__ and __Thru__ only determine the write-direction.

Reading stuff seems to matter less. Reading might not be seen as parameter passing. It might be only about: who writes it and from which direction. Reading has less impact than writing. But its impact may become important later, when using it in more advanced techniques for for instance concurrency resolution.

What I see now, is that if I find simpler terms for reading, I will probably be totally happy with my parameter access control literals. Since there is such beautiful names for writing from either inside or outside (__In, Out__ and __Thru__) can I come up with beautiful names for reading too? If I can find a replacement for the terms __Get Private__ and __Get Public__, then I will probably be completely satisfied with how the parameter access control literals look.

Next to an easier expression of __Get Private__ and __Get Public__, you may also want to invent keywords to express that something is publicly written and privately read, or the other way around. So when __Value__ is set on the outside and read on the inside, you get an easier expression for it, than saying __Value In, Value Get Private__. Do note, that when you set a value on the outside, it does not imply, that you also *read* the value on the inside.

#### Consider New In & New Out

2008-09-29

However, __New In__ does mean creation from the outside and __New Out__ does mean creation on the inside... so ... it’s not just the inside then... how does that relate to the rest of the ideas about __In, Out__ and __Thru__?

JJ

#### More

If an aspect is both __In__ and __Out__ and the two access control elements are right next to each other, it can be replaced by a single access control element __Thru__:

- __Object Thru__
    - __New Thru__
    - __Annul Thru__
- __Value Thru__
- __Class Thru__

### Brainstorm 2008-09-27

I think the terms input and output should not be about whether something is written from the outside and whether something is written from the inside. That’s what I did earlier. I think the term input should mean: everything that is read on the inside of a command, and the term output should mean: everything that is written on the inside of a command.  
So it is about what happens on the inside. Whether something is written or read from the outside is not the issue.

Anyway, input and output are too complicated to just wrap up the old parameter passing type stories, which depend on those terms.  
Advanced Command Topics will also do a lot with input and output. Actually, most of it is about the complexity of input and output. I should really save it for another project. One of the objectives of the project Work Out Advanced Command Topics should be to determine the exact definition of input and output and the exact definition of input and output parameters.  
I should shove it over to that project.  
I should register in the project description that determining the exact definition of input and output is one of the objectives.

The current project will wrap up everything else about parameters.  
I have to clean up the objectives of the current project and create a new plan for it.  
Then I can work my way up to an end point. And in the next project I can just calmly look at the exact complexity of input and output.

### Brainstorm 2008-09-26

The problem with defining what is input and what is output, is:

- Is input what is written from the outside, or is input what is read from the inside.
- Is output what is read from the outside, or what is written on the inside?

You might think: both; something that is written from the outside is read on the inside and something that is written on the inside, is read from the outside.

But one prime example would overthrow that: An object can be written, so passed to a command, and the value of the object might be read. So Object Set Public, Value Get Private. So then you do not set the object, to read it on the inside, but the object is set, to read the value on the inside, so when an aspect, such as Object or Value, is In, it does not mean that it is both written from the outside and read on the inside.

But in the car on my way home from work I realized, that I have been forgetting about half the gets. When an object is written from the outside of the command, of which the __Value__ is read on the inside, the __Object__ is read as well, because you need to read the object, before you can retrieve the value of the object. So the object is read for access. Not for copy / assignment.

Perhaps you need to consider reading an object for access too. I already wrote something about that in the old Symbol documentation: different forms of getting, that also might be separately access controlled.  
It makes a difference when something gettable for access compared to gettable for copying. It would make a difference for outcome dependency. For instance: when you can get something for accessing but can’t get something for copying, then the object can be accessed inside the command, but it can not be passed further down into sub-commands.  
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
- Reading for access and reading for assignment need to be separately access controlled and it will change parameter passing.
- Incidentally a read or write of input or output is missing. That will be given a term.
- When a read or write is done on the outside, the a write or read must be executed on the inside, even though scarcely or incidentally not.  
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
    - \> How can you access a class? Don’t you only access an object? Yeah, I think you do. So the separation between for access and for copy only counts for Object access.

So:

__Object Set Public, Value Get Private__  
\=  
__Object Set Public, Object Get Private For Redirection, Value Get Private__

Hmmm... if you get the value of an object, does that mean you first follow redirection? I guess you do..  
The last bit of the access control literal specifies, you can only follow redirection of the object to get the value or otherwise it would be Data Get Private.

But the access literal above further simplified  
= Object In For Redirection, Value Get Private.

Now I am confused again: you may set and get the object, but you only GET the value. Were’s I supposed to call something input, when it is set from the outside and read from the inside.

The thing is: I am not reading what’s set on the outside: I am reading from what’s inside what’s set on the outside.

So you are going further down the structure when you read the value of the object passed to the command.

So Value In means you write the value from the outside, not the object, and you read the value on the inside. Value Out means the other way around.

Actually, it could be: Value Set Public, Object Get Private For Copy.  
Value is Set, but not read. Well.. it has to  be read by a sub-command then...

I am still confused. I have brainstorming to do.

But it’s no use writing something, if you don’t read it at some point.  
Sub-commands yield over in, out properties to their parent commands. 

You write the value... it needs to be written at some point.

When you write the value from the outside, and you can only access the object on the inside, you have to pass the object to a sub-command, that does write the value. But can you really know? Maybe not, but it should be read somewhere on the inside.

Look, there is a whole object theory behind the in out and thru. And it should be covered by advanced command topics, to the extent, that you can automatically determine execution outcome dependency, execution order and possible resolve concurrency.  
But writing means you’re going to read it, and when you read it, is has to have been read.

Oh, yeah? What if you write the value of the object some place, and the object is passed to the command, and the command reads its value. In that case the value is only written to the object *somewhere* on the outside, and read only *somewhere* on the inside.

Is there really a point to talking about input and output at this stage?  
Isn’t input and output much more complicated than expected.  
The general meaning is understandable, but what it means on an object oriented level could be very complex. I really think it is something for Advanced Command topics.

I can talk about Reference In, but when you assign the object to a parameter, and the value is supposed to be accessible, it doesn’t mean, that you will read the value directly in the command. You may very well read it somewhere in a deep sub-command.

This whole theory about how something becomes input or output should just be saved for Advanced command topics. And things like Reference In and all that, are just not as simple as suggested.

Perhaps a simpler conclusion, for now:  
the rules I suggested above are still true: when you set input, it is meant to be read somewhere, but WHERE you actually read it is more complicated.  
But when you SET something of a parameter, than you are sure it is input or output.  
Where you then GET it, is not clear. It could be far away on a higher level, or far a way on a deeper level. That’s why SETTING allows you to say something about something’s being input or output. But can the ability to set a parameter on either inside or outside exclusively tell you it is input or output?  
What use does access control over getting have?  
I think being able to allow a Set from the outside, and then still being able to disallow getting on the inside is stupid: it has to be gotten at some point, if only for redirection.  
So those allowances should go hand in hand: if you can write it from the outside, you can read if from the inside. If you can write it on the inside, you can read it from the outside.  
but WHERE it is then read could be somewhere totally else than directly outside or directly inside. DOES THAT count for SETTING too?

### More Ideas

Parameters,  
2008-08

The command definition can also contain a set of related objects. Those are the parameters of the command. They are just input, output, throughput or downput. This input, output, throughput and downput is passed on to the sub-commands, that are given outward references to these items.

JJ

-----

Parameter passings,  
2008-09-05

If a command parameter is typed with in, out, or though,  
then an object command can also be given a title depending  
on whether it will be input, output, throughput, etcetera.

input is not an object that something is done to. It can be considered an object doing something to another object. So it is clearly an actor.

It matters whether the object is used (read), affected (written), or produced. This alters the object’s position in relation to to the command.

JJ

-----

Parameters,   
2008-06

Always something is the input and something is the output: at least one thing is used, and at least one thing is affected. But the affected thing can also be a new thing  
One thing is executed on another. So its data executed on data.

JJ

-----

Access Controling System Aspects,  
2008-09-21

When you access control the system aspects of a parameter, does this have implications for acces control of the object’s command?

When you show a command inside an object, how will you see, that the command outputs the object or if the command uses the object?

JJ

-----

2008-09-26

Adapt the access control of system aspects
in the parameter articles to Object Get for access and for copy...

JJ

-----

Parameters,  
2008-09-11

Value In parameter used for selection  
Value In parameter used for persistance

JJ

-----

When a command is called, objects are filled into the parameters of the command. A command will use objects to do its work. The objects filled in as parameters are also called arguments.

As commands call each other, every time different data is passed along to the different commands, that are called.

-----

Actually, the method will only become part of the classes that it directly uses. When the method uses submembers of the classes, the method does not become part of the classes of the submembers.

-----

Byrefs have pros and cons in different situations.

# From the original Symbol documentation

## Procedure Parameters

Procedures can have *parameters*: instructions passed along with the procedure that make the procedure behave differently. The __Button . Set Text__ procedure, for instance, has a __Text__ parameter, which indicates what the new text of the button will be.

Text is an *idea*. It is an *object*. It is *objects* that serve as parameters.

![](images/Input%20Output%20Parameter%20Passings.059.jpeg)

The procedure can do whatever it wants with the parameters passed to it. All it really can do with it is again pass the parameter to another procedure *or* call procedures of the parameter.

*Pass the Text parameter on to the next procedure (Format Text):*  
![](images/Input%20Output%20Parameter%20Passings.060.jpeg)

*Call the a procedure of the Text parameter:*  
![](images/Input%20Output%20Parameter%20Passings.061.jpeg)

The terms *parameter* and *argument* are often intermixed. For now you can assume that a parameter is a setting of a procedure and an argument is the value that it holds. That’s not the entire truth, though, but I’ll save the exact meaning for later.

### Input, Output and Throughput Parameters

Parameters are commonly input (instructions) for a procedure. Parameters can also be output (returned results). They make a procedure return something to the caller. One of the output parameters can be appointed to be *the* return value, which makes it sort of like the main output parameter. Some parameters can be input, and then output again. Then the procedure uses the parameter, transforms it and gives it back in the transformed state. These parameters are called throughput parameters, or in-out parameters. There are also objects in a procedure that are only used locally. Those are not usually called parameters, but sooner called *local objects*.

## Get and Set are Inseparable

A state write is always paired with a state read and a state read is always paired with a state write.

When you read a state, the state is meant to be assigned to another object. And from the other perspective, there’s no point in reading the state if you’re not going to assign the state to another object.

## Executions & Parameters

### Argument Access

#### Input, Output and Throughput

##### Output by Reference

< 2008-10-06 Move to Input Output >

The procedure output method above is hardly used ever used. That’s because you can’t really tell if the target object will keep existing, unless you’ve defined the object yourself. Therefore, using output other than state output is usually done by passing a reference to an existing object to the procedure.

This, however requires you to *write* the line of an argument.

![](images/Input%20Output%20Parameter%20Passings.062.jpeg)

Nothing is *read* in the epilog in this case. Even though the argument functions as *output*, it’s still a *write* argument.

Any line going out of a diamond is set just before the diamond executes.

##### Write, Read ≠ Input, Output

As such, *read and write arguments* is not analogous to *input and output arguments*. A write argument can easily serve as an output argument.

##### Reference Arguments

Reference arguments can serve as input, output and throughput. State arguments can serve as input, output and throughput too. 

You’ll hardly use a line target as output information. You’ll probably use an argument’s line target only to pass an object by reference.

Even though an argument’s line is hardly ever read, an argument’s state *is* commonly read.

#### Using Arguments

You’ll mainly use arguments by reading and writing their state or to pass objects by reference.

#### Accessing Arguments During Execution

Apart from writing in the prolog and reading in the epilog, there’s a third period in which you can access an argument: during execution. You can only access the arguments of a diamond *in execution*. The caller of the diamond is frozen, till the execution completes, so the caller doesn’t have any chance of accessing the arguments during execution. However, everything inside the executor is in motion. The executor itself can freely access its arguments, of course, but also anything it calls, could access its arguments, if given a reference. But, as I said, the *caller* of an execution can’t access the arguments during execution.

The diagrammatic effect of this is the following. A member can be accessed by the diamond that contains it, and by all its sub diamonds:

![](images/Input%20Output%20Parameter%20Passings.063.png)

I said, that procedures called by a procedure can access its arguments. That suggests that the procedure that accesses the member can be somewhere else than inside the member’s diamond:

![](images/Input%20Output%20Parameter%20Passings.064.png)

Note, however, that it’s not the definition that’s accessing member __m__. It’s the call that’s accessing member __m__, and the call is contained inside the diamond that contains member __m__.

More rules on that are covered in the *Execution Basics* section.

### Implicit Notations

< you can call an implicit call a parameter reference too. Mention it so you show that there’s a big difference between parameter reference and argument reference >

- Implicit call and Explicit call
- Implicit return value reference
- Implicit argument assignment

#### Previous Texts

##### A

###### Referencing Square Members: Implicit Call

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

If you want to access members of a procedure using only one call, you have to explicitly notate the diamond that is the call.

![](images/Input%20Output%20Parameter%20Passings.071.jpeg)

< Add some access symbols >

But the accesses can only only take place just before the call and just after.

But as I said: child diamonds can access their parent diamond’s members if the parent diamonds allows it.

![](images/Input%20Output%20Parameter%20Passings.072.jpeg)

###### An object symbol as a pointer to a procedure symbol: Implicit return value reference.

You can also let an object symbol point to a procedure symbol.

![](images/Input%20Output%20Parameter%20Passings.073.jpeg)

In that case you’re actually implicitly referencing the return value.

![](images/Input%20Output%20Parameter%20Passings.074.jpeg)

###### Implicit Call and Implicit Return Value Reference

If an object symbol is a reference to a square, it’s both an implicit call and an implicit return value reference.

![](images/Input%20Output%20Parameter%20Passings.075.jpeg)

![](images/Input%20Output%20Parameter%20Passings.076.jpeg)

![](images/Input%20Output%20Parameter%20Passings.077.jpeg)

in the second picture you see the explicit call. The third picture adds the explicit return value reference. You don’t first do the explicit call and then the explicit return value reference. That order is totally arbitrary, you can also see it like this:

![](images/Input%20Output%20Parameter%20Passings.075.jpeg)

![](images/Input%20Output%20Parameter%20Passings.078.jpeg)

![](images/Input%20Output%20Parameter%20Passings.077.jpeg)

###### Reference to Other Out Parameters

An object reference to a procedure can only be a reference to the procedure’s return value. If you want to reference other out parameters, you have to reference them explicitly.

![](images/Input%20Output%20Parameter%20Passings.079.jpeg)

(o = out, r = return)

__a__ can only be a reference to __r__, the return value. __b__ is a reference to __o__, another out parameter.

### Argument Reference

There are three ways to use arguments: state read, state write and passing by reference:

| ![](images/Input%20Output%20Parameter%20Passings.080.png) | ![](images/Input%20Output%20Parameter%20Passings.081.png) | ![](images/Input%20Output%20Parameter%20Passings.082.png)|
|:------------:|:-------------:|:-------------------:|
| *State read* | *State write* | *Pass by reference* |

There seems to be one more: *argument reference*.

![](images/Input%20Output%20Parameter%20Passings.083.png)

*Argument reference*

This is however not possible, because the argument destroys after execution, so you can’t reference it after execution, because then there is nothing left to reference anymore. Argument reference is useless.

Argument reference is actually a fictive concept.

![](images/Input%20Output%20Parameter%20Passings.083.png)

It is actually an implicit notation for a *reference argument*:

![](images/Input%20Output%20Parameter%20Passings.082.png)

There’s more to getting the explicit notation of argument reference than just inversion of direction. Consider this diagram:

![](images/Input%20Output%20Parameter%20Passings.084.png)

This diagram has two argument references in it. If you would simply invert the direction you’d get the following:

![](images/Input%20Output%20Parameter%20Passings.085.png)

*(Note that the last access symbol didn’t change, because that line isn’t an argument reference)*

It still has a argument reference in it. 

The explicit notation that solves this is the following:

![](images/Input%20Output%20Parameter%20Passings.086.png)

The child diamond is inserted as a substitute for the higher diamond it refers to. This offers a solution because the parent of the child diamond will exist when the child exists. {This might be an issue for multiple execution of a diamond. It also raises the question what happens when you consult something of the righter diamond. Is the bigger diamond executed first? What?} That’s rule two for getting to the explicit notation of parameter reference.

< I have doubts about this third rule. I think this case might be illegal. I need to find the rule on what makes it illegal and how you see the illegality of it in the implicit notation >

There’s one more problem. The explicit notation introduced so fat has a flaw: the object has two line targets! If a situation as such occurs, the directions of all flawed non-argument references are inverted:

![](images/Input%20Output%20Parameter%20Passings.087.png)

Which gives is rule three of the explicit notation of argument reference.

If a reference argument targets the argument of a parent diamond, it is not considered an argument reference.

![](images/Input%20Output%20Parameter%20Passings.088.png)

Argument reference is only the case where you *enter* a diamond.

#### Summary

So the implicit argument reference notation:

![](images/Input%20Output%20Parameter%20Passings.089.png)

Has the following explicit notation: < I know it is wrong, I should investigate later >

![](images/Input%20Output%20Parameter%20Passings.090.png)

Rule 1:

A argument reference (a line entering a diamond) is an implicit notation of the reverse direction (a reference parameter).

Rule 2:

If the line both enters and exists a diamond, then the inversion of direction doesn’t solve it. < > In that case, a child diamond is created in the diamond that holds the argument reference. The diamond references the diamond that held the argument reference target. The new child diamond is used instead. < >

Rule 3:

...

You go from implicit to explicit notation in the following steps:

![](images/Input%20Output%20Parameter%20Passings.084.png)

Reverse direction of argument references

![](images/Input%20Output%20Parameter%20Passings.085.png)

Create child diamonds where the inversion doesn’t work

![](images/Input%20Output%20Parameter%20Passings.086.png)

Invert the direction of other lines that became faulty

![](images/Input%20Output%20Parameter%20Passings.090.png)

### In, Out and Thru Argument Notation

< The out parameter access symbol isn’t required, so the notation of it *suggests* that it’s an in parameter reference >

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

#### Execution Order In Text Code

The resulting sequence of code lines corresponds to the execution order required for dependency. As you change the diagram, the order of the text code can change. You can freely more around text lines of sibling symbols.  
< The resulting sequence of code lines and the execution order within code lines. >

< Don’t cover exact text code here >

### Implicit Notations

#### Previous Texts

##### B

###### Implicit Calls

< 2008-10-08 The texts that follow use an old notation for calls: a definition is a square without a reference line, a call is a square with a reference line. >  
< Maybe diagrams can be more basic, expressing solely a concept >  
< reference a procedure parameter from an object.>  
To explain this concept I use an example where one procedure, called __Get__, returns an object that is then passed to another procedure, called __Set__. This requires two calls: first a call to __Get__ and then to __Set__.

####### Explicit Calls

The steps of this process can be described as follows:

```
Get
Set . In = Get . Out
Set
```

The out parameter of __Get__ is called __Out__ and the in parameter of __Set__ is called __In__. In diagram code, that is:

![](images/Input%20Output%20Parameter%20Passings.103.png)

*Explicit calls*

Only the blue parts are shown in the piece of text code. You can see that __Get__ is called and __Set__ is called. Both __Get__ and __Set__ have a parameter. The parameters are shown in the definition, but also in the call. In the call, the parameters are actually created and the parameters in the calls are worked with. The __Out__ of __Get__ and the __In__ of __Set__ are tied together with an object line. You can’t explicitly see the order in which __Get__ and __Set__ are called, but because the __Set__ call references a parameter in the __Get__ call, __Set__ is dependent of __Get__, therefore __Get__ is called first.

####### Implicit Calls

In text code you can write the two calls in a single code line:

```
Set ( In = Get . Out )
```

__Get . Out__ is assigned to the parameter of __Set__. You’re referencing a parameter of __Get__ without displaying the call. To read the __Out__ parameter of __Get__ requires a call and this call is implicitly made. In the text code line above you don’t see that __Get__ is called. __Get . Out__ is simply referenced. You can apply the same to diagram code:

![](images/Input%20Output%20Parameter%20Passings.104.png)

*Implicit call*

*Note that the Exit Most Borders rule determines the direction.*

You can see that the __Out__ parameter of the __Get__ procedure *definition* is referenced. This implicitly causes a call to __Get__. In *explicit calls* you reference the parameters of the procedure *call*, not the procedure *definition*.

####### Implicit Return Value Reference

__Out__ is __Get__’s return value. Therefore, the identifier __Get__ symbolizes the return value. __In__ is a parameter of __Set__ and you don’t necessarily need to mention its name in the parameter list. This all makes the text code:

```
Set ( Get )
```

__Get__’s symbolizing its return value can also be applied to diagram code:

![](images/Input%20Output%20Parameter%20Passings.105.png)

*Implicit return value reference, implicit call*

The line to __Get__ is not really a line from an object to a procedure. The return value of __Get__ is implicitly referenced.

The diagram above looks far simpler than the first diagram. So does the text code. In reality multiple steps are taken: • Call __Get__ • Read __Get . Out__ • Write __Set . In__, • Call __Set__.

In the diagram above, the return value is implicitly referenced by pointing to the procedure definition. You can also implicitly reference the return value by pointing to a procedure call square. That way, the call is explicit, but the return value reference is implicit.

![](images/Input%20Output%20Parameter%20Passings.106.png)

*Explicit cal, implicit return value reference*

####### Multiple Out Parameters

######## Implicit Return Value Reference

Implicit return value reference is only a way to reference the *return value*, not to the other out parameters. The other out parameters must be explicitly referenced. 

![](images/Input%20Output%20Parameter%20Passings.107.png)

*Implicit return value reference, explicit out parameter reference*

######## Implicit Calls

When you reference output parameters of a procedure multiple times, each reference causes its own call to be made. 

![](images/Input%20Output%20Parameter%20Passings.108.png)

*Two references to a parameter of the definition: two implicit calls*

If the diagram above is an abstract view on the system, there might only be made a single call, but officially the diagram above is showing *two* implicit calls. The meaning of the diagram above is:

< P: same system as above, now physically showing the two calls >

If you want to reference multiple output parameters of a single call, you have to explicitly display the call and reference the objects that are inside the call symbol. By referencing the parameters of the call, you only use one call.

![](images/Input%20Output%20Parameter%20Passings.109.png)

< Call in blue >

##### C

###### ? Referencing a Procedure Member

< 2008-10-08 Most of what is said in this section no longer applies, because a more explicit notation is desired, to make things less ambiguous, and some remarks have already been thought through and work differently. >  
Referencing a diamond’s members is like reading a procedure member.

![](images/Input%20Output%20Parameter%20Passings.110.jpeg)

< 20040418: this is interesting. It has to do with implicit call and I have to explore in which situation this is useful. I think that when you call a member of the top circle, then the diamond executes. It’s like calling member of the bottom circle... >

It always happens just after the diamond executes.

< The parameter objects destroy right after the call. If you use the top circle like above, every consult of the top circle will result in executing the diamond again. To persist the information contained in the argument, without having to call the procedure again, you have to do a State Copy. Another way of using output parameters is to give the execution a reference to an external symbol. Anyway: if you want return information to persist after the call, it has to be stored in external symbol: store the returned state to an object that the caller contains, or pass a reference to the caller’s object to the called procedure >

< That’s true what I just said, but there’s nothing wrong with linking directly to the parameter and executing the procedure on each consult. There’s nothing wrong with that. The link would be something like consulting a property procedure in VB, a Get, which returns a reference to an object. Every time you consult the property, the procedure is launched again. That’s normal. >

< Must denote that the notation above is not an output situation. It’s an implicit call situation >

#### Brainstorm Items

##### 1

Oh, die assignments lijken afzonderlijke referenties, waardoor je implicit calls krijgt? Of is dat alleen bij referenties naar inhoud van squares?

Oh, nee! Hè! Ik heb ergens in dit hoofdstuk iets staan over een diamond die execute telkens als je een object met een line naar een parameter beraadslaagt. Hoe zit DAT dan?

Dat is verkeerd  
\>

##### 2

*Nice wording:*  
A reference to something inside a square causes an implicit call to the square, because the procedure is required to execute in order to reference something inside of it.

##### 3

Implicit calls when referencing square contents (and their explicit diagram representations)

### Brainstorm

#### Summary of Old Subdivision

- Implicit call and Explicit call
- Implicit return value reference
- Out, In and Thru parameter usage
    - Cover procedure reference too
    - If example
- Initiation of execution:
    - Containment in other diamond
    - Consult of a parameter.

#### New Subdivision

- Out, In and Thru
    - Using reference parameters for in, out and thru (hard to control whether it’s in out or thru: you just use the object)
    - Using State as In, Out and Thru
    - Using a parameter’s line targets as Out
        - Comparison with Com regarding returning object references.
            - Persisting object reference (harder, is hardly done anyway. Or is it? Consider passing the returned object to another procedure)
            - Using the procedure parameter as object reference directly
    - Procedure reference too
    - If example

- Execution Order
    - Seeming randomly referencing diamond members.
    - Initiation of execution:
        - Containment in other diamond
        - Consult of a parameter.
    - Manual execution order

- Implicit Notations
    - Implicit call and Explicit call
    - Implicit return value reference

#### New Main Subdivision

- Out, In and Thru
- Execution Basics
- Execution Order
- Implicit Notations

#### New Brainstorm Texts

###### New

- < > The assignment destination consult is not seen as a consult. < > Consult of a parameter as assignment destination does not require execution of the parameter holder.
- Executor represents one execution per call on definition.
    - Implicit calls are not made for diamond contents reference < >

###### Old

< 2008-10-08 This talks about parameter passing, a notation for value assignment and about implicit call. Those three are spread over multiple documentation sections. But do the cross out here. >

![](images/Input%20Output%20Parameter%20Passings.111.jpeg)

In implicit argument assignment, there is no way to express state assignment.

![](images/Input%20Output%20Parameter%20Passings.112.jpeg)

If it were to become a connection between symbols, like implicit line assignments, it would definitely not behave the same as a line.

![](images/Input%20Output%20Parameter%20Passings.113.jpeg)

(*Implicit assignments*)

De assignment calls gedragen zich niet normaal, want consult van de argumenten van __A__ veroorzaken geen executie. Een soort passieve parameter consult vind plaats door de assignment calls, in het proloog van __A__. Bedenk wel: het zijn systeem procedures: niet normaal.

![](images/Input%20Output%20Parameter%20Passings.113.jpeg)![](images/Input%20Output%20Parameter%20Passings.114.jpeg)

De calls naar system procedures gedragen zich anders dan gewone calls. Ze vinden namelijk hier plaats in het proloog van de executie. Je ziet dit wèl in de text code, maar hoe zie je in diagram code of een systeem procedure apart wordt aangeroepen of in de context van een andere functie aanroep?  
Hypothese: als je bij systeem procedure aanroep een parameter betrekt in een diepere executie, dan zit het in het proloog of epiloog. Zit de parameter in de huidige of hogere executie, of is er helemaal geen parameter bij betrokken, dan wordt de systeem procedure call normaal uitgevoerd. En veroorzaakt geen executie van de sub executor.

Niet het een executor, anders verwar je het met een aparte executie! Een system procedure triggert geen executor:

![](images/Input%20Output%20Parameter%20Passings.115.jpeg)

\* dit zou A triggeren als het niet een line van een system procedure call was.

Assignment procedures = system procedure, eerste argument is het __This__ argument.

![](images/Input%20Output%20Parameter%20Passings.116.jpeg)

\* 2 consults, 1 execution. 1 executor zou er eigenlijk moeten zijn om 1 keer uitgevoerd te worden per ... definitie aanroep (afgezien van jumps) (? Hoe zit het daar dan precies mee)

Dus implicit call moet niet bestaan bij het referen naar diamond members. Dus dan heb je ook niet het probleem dat *assignment calls* speciaal geplaatst moeten worden in het proloog en epiloog: consult van diamond members vind *altijd* plaats in proloog of epiloog!  
Oh jawel! Consult vind gewoonlijk altijd plaats in epiloog, maar bij assignment van argumenten consulteerd __*system procedure*__ de argument in *proloog*.

![](images/Input%20Output%20Parameter%20Passings.117.jpeg)

![](images/Input%20Output%20Parameter%20Passings.118.jpeg)

The last picture is an acceptable substitute for implicit state assignment. It is actually explicit state assignment, but it looks like a real connection between A and B. A rule though: state assignment takes two arguments: destination = source. In the notation on the left you have to follow the direction of the line you’d get between A and B if you ignore the call thing in between to find out which is the first argument and which is the second. In text code it goed from left to right. In the diagram It goes from ... < >. B is destination A is source. I mean B is the one that gets the line. B is source of line, but destination of assignment. 

#### Argument Access Summary

##### In, Out and Thru

- Using reference parameters for in, out and thru (hard to control whether it’s in out or thru: you just use the object)
- Using State as In, Out and Thru
- Using a parameter’s line targets as Out
    - Comparison with Com regarding returning object references.
        - Persisting object reference (harder, is hardly done anyway. Or is it? Consider passing the returned object to another procedure)
        - Using the procedure parameter as object reference directly
- Procedure reference too
- If example

### Brainstorm

#### Other

__*Different Wording, Not important, though*__

In an explicit call you always see the the call displayed as a separate diamond. If the call is made, the call is like a created object. After the call it is destroyed. When the call is created, you can reference its contents from anywhere without causing another call.

## Other

There are three types of parameters: in, out and thru. In parameters go in, out parameters go out and thru parameters come in and go out.