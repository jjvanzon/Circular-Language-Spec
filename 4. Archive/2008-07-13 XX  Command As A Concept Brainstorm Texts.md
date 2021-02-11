## **Command As A Concept Brainstorm Texts**
*Author: Jan-Joost van Zon*

*Location: Oosterhout, The Netherlands*

*June 23, 2008 – July 13, 2008*

#### ***Commands as a concept***
Keep in mind, that in earlier articles it was explained, that a command is a separate entity, as opposed to being part of a specific class.

A command is an *executable object*.

If an object represents a process, then in the new computer language the object is just a command, and no longer an object representing a process. Actually, a *command* will always be an object that represents a process. In the new computer language, a command looks just as structured as an object.

You can use all the capabilities of objects inside a command.

But a command has the special property, that it is *executable*.

But there is more to the behavior of a command, compared to a normal object.

A command definition contains a collection of other commands to execute.

The collection is sorted by the order in which these sub-commands will execute.

The command definition can also contain a set of related objects. Those are the parameters of the command. They are just input, output, throughput or downput. This input, output, throughput and downput is passed on to the sub-commands, that are given outward references to these items (the parameters of the sub-commands are pointers to pointers that way). Some parameters may become *required*, so that you have to fill them in, or have to use them as output.

A command *definition* is a permanently created object. It has to be created, because it needs to *store* what becomes the input and output of its sub-commands. For that, the sub-commands are also created objects. They have a fixed logical residence inside the command definition, even though their definition is totally elsewhere.

Sub-commands are not executed by the definition itself. A command definition is dormant, statically present and permanently created. But a call is different. A call refers to its definition, and takes over everything from the definition, but a call is only created right before it executes and destroyed short after it is done.

Each call represents an individual command object, but a new command object is created each time the call is executed. The input of a call is set right before the command is executed. The output of the command is read right after the command is executed.

A new command object is created on each call to the command. Then the input is set. After the output has been read (which means: *written* to other objects) the whole command object is erased again.

The parameters are not really a list of objects passed to the call anymore. The call is an object, that has a set of object references in it, that are individually set.

All of this behavior is implemented as the **Command** concept. The **Command** concept can be supported by any object, upon which the object becomes a command.

The code base, however, in some basic form needs to support an object’s ability to execute.

The order in which the sub-commands execute can be manually set, but the technique of automatic execution order makes is possible to have the order automatically determined. Either way, the order of the sub-commands is *stored* inside the command definition.

A command has added behavior, compared to a normal object:

\- It executes

\- It contains a collection of sub-commands to execute

\- A new command-object is created *on each call* to the procedure and the command-object is destroyed soon after the call.

\- Public writable objects are written only right before the call.

\- Public readable objects are read only right after the call.

For the rest objects and commands are identical.

The added behavior of commands is implemented as the **Command** concept. When an object supports the **Command** concept, it automatically becomes a command. The code base only needs to support an object’s ability to execute in some basic form. But most of the fuctionality for commands is programmed within the new computer language itself. The code base only supplies the basic need to facilitate it.

For a command to execute, the sub-commands need to execute in the right order. The sub-commands again execute sub-commands. This going by the commands recursively probably needs to be present in the code base. The outer commands are machine instructions, which will also be called by the code base.

A command actually *is* an object, with some special properties: it executes, it contains *calls* to other commands, and the calls are executed in a certain order, part of which can be automatically determined.

All you need to do is assign the input parameters, ‘run’ the object, and assign the output to other objects.

For an object to have a reference to a command, you *have to* be able to define a *relation* between a command and an object. This is only possible, if a command *is* an object.

If you want to do that, you *have* to implement commands as a concept.

A command itself can also contain related command references, which are then considered parameters of the command.
##### **Ideas**
Commands,

Zo uit de losse pols verzin ik nu, dat een command een object is, waarvan de procedure in de constructor zit.



JJ
#### ***Classes & commands loosely coupled as relations between commands and objects***
Parameters are the essential connection between commands and objects. If I can use a line merge in bidirectional relations between classes, does that mean that a line merge between a command parameter’s class line and a class command’s definition line should be considered a bidirectional relation between a class and a command? Should that be viewed more like a relationship, than anything else?

When a command definition gets an object with a class, this creates a relation between the command and the class definition. This means, that the class definition also gets a reference back to the command.

It looks like, when you turn a command into an executable object, without any additional effort automatically establishes the interchangability between class commands and command parameters. I didn’t expect that. If two seemingly independent concepts confirm eachother, I must be on the right track.

For objects of the class, this means, that they copy all methods of the class.

If the method changes, this changes the class configuration. The change in class configuration must then be ventilated through to all the objects of the class.

I haven’t accounted for that yet. The same effect is there for just data of objects: if the class configuration changes, the objects should change also.

Gee… you should be versioning. Objects do not change, because they link to a specific version of the class.

However when creating a command, and giving it a relation to a class, I guess I do want the command to be ventilated through to the objects? Or will I just forget about that?

Gee, the commands inside an object are no longer imaginary references. They are real ones now.

I guess, that only if you link to the development version, changes are ventilated through from the classes to the objects.

But command as a concept, as a way to establish interchangability between class commands and command parameters, also needs to subdivise the class commands into interfaces: one for each module commands are defined in.

How that is established by command as a concept is yet to be determined.

Automatic Containment for Relations is still a problem. Line merges for relations between commands and objects may have the same problem. I didn’t account for that earlier. A good example of this problem is yet to be drawn out.
##### **Giving the issues in this section a place**
Issues about casts need to be moved to the article Events. Also move changes to classes or commands to the article Events, as a primary example for the application of events.

Classes & commands loosely coupled needs to be adapted.

You can postpone explaining commands till later, explaining it first and foremost in terms of relations between commands and normal objects.

An object's references to its commands are not imaginary.

Subdividing the commands from different site into different interfaces of an object, is a separate issue to address.

Still ignore, that also for relations between objects and commands the diagram notation has discrepancies with the diagram notation of automatic containment.
#### ***Downput***
Next to the terms input, output and throughput, the term downput will be introduced. Downput is intermediate data as a helper of a process, that will eventually produce output. Temporary variables, local variables. They are all downput. Actually, in the method-call structure, a method in which output data is disposed, this output as become downput.

The term downput is good, because it is only passed *down* into sub-commands. And it is dropped after the parent command is done (dropped *down*). It is ‘put down’ / rejected after the execution. Or put down / to put something down, that you had in your hand.
#### ***Read-Write Direction As A Connection***
Formerly, the direction of input and output was indicated with an access mark on a reference line. But this created ambiguity with the indication of *reference targets*. Read-write direction is something so basic in computer language, that it deserves a separate line type. From now on, value direction will be indicated by a *wavy line*.

This is actually a good symbol for it, because it looks like a less direct connection than the other line types and *it is* a less direct connection. In fact, the two symbols *aren’t* connected at all. The wavy line looks like a less direction connection, because the complete length of the line, curves and everything, is much longer than a straight line. A wavy line also indicates *heat*, or activity, more than the other line types. Value direction is an *action*.

Read-write direction, input-output direction and value direction are synonymous terms.

A value line might not necessarily indicate yielding over the value of the object on one end of the line to the object on the other end of the line. It may be yielding over values between sub-objects. So it’s not synonym to a value assignment call.

When values are yielded over between sub-objects, then this is drawn out with a wavy line. A direct read and write is always drawn out as an assignment call. An assignment call almost looks the same as a value line, but now a diamond is there in the middle of the line. This is to distinguish direct reads and writes from indirect reads and writes.

Sometimes the command itself does not read or write from a parameter, but the parameter is passed to a sub-command, that reads or writes from the object. This yields over the in-out-thru properties of the parameter. This does give the parameter an indication of value direction, just no assignment is visible in the definition of the command. The assignments are done by a sub-command.

It is not clear yet if it is best to also use value direction to indicate addition, removal, creation and annulment of objects.
#### ***Input, output, throughput, downput***
##### **Introduction**
Input, output and throughput are parameter passing types.

They are shortened to **In**, **Out** and **Thru**.

When a command’s parameter is **In**, it means that the command reads values from the parameter. When a command’s parameter is **Out**, it means that the command writes values to the parameter. When a command’s parameter is **Thru**, it means, that the command reads values and writes values to the parameter. Throughput functions as both input and output at the same time.

When a command disposes objects after it is done, then those objects are called *downput*. Downput may have been input for sub-commands, or it could have been output of sub-commands. To the parent command, though, it is *downput*. Downput parameters will not be further considered here, because they do not have anything to do with parameter *passing*.

Input values are written to the command right before the call. Output values are read right after the call.

In that case the parameters are passed *by value*: the value of one object is *copied* to the parameter of the command to call. And after the call, the values of the output parameters are *copied* to other objects. These kinds of input and output parameters are called **Value In** and **Value Out** and **Value Thru**.

**Value In**:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.001.png)

**Value Out**:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.002.png)

**Value Thru**:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.003.png)

A read of an output parameter is always accompanied by a write to another object. A write to an input parameter is always preceded by a read from another object. A read operation is always accompanied by a write operation. A value is read from one object, only to be written to another object.

Next to passing a parameter by *value*, you can also pass a parameter by reference. For instance: instead of copying a value to an input parameter, you give the command a reference to an object outside the command.

Reference parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.004.png)

The called command can then read out of the object, that it was given a reference to. In that case it is called a **Reference In** parameter.

**Reference In** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.005.png)

When a command is passed a reference to an object, and the command writes to the parameter, it is called a **Reference Out** parameter.

**Reference Out** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.006.png)

Next to **Reference In** and **Reference Out**, there is also **Reference Thru**, which means, that the command both reads and writes to the object passed to it.

**Reference Thru** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.007.png)

When a command call has an outward reference to an object, this *does* make the object a parameter, but this *does not* determine yet whether it is input, output or throughput. The *in* and *out* in this case refer to whether values are written or read to the object reference. A reference parameter is always sort of like input, though: the parent command passes the object to the sub-command, so the parent inputs something into the sub command. Therefore it can also be called **Reference Outward, Value In** and **Reference Outward, Value Out** But those names are too long. The distinction between **Reference In** and **Reference Out** is about whether values are read or written to the object passed to the sub-command.

The other way around is also possible: the sub-command passes a reference to an object to the parent command. The parent command refers to an object in the sub-command.

**Reference Inward** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.008.png)

This is a **Reference Inward** parameter, as opposed to a **Reference Outward** parameter. The sub-command writes to the output object. The long name of this type of parameter passing is **Reference Inward, Value Out**.

**Reference Inward, Value Out**:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.009.png)

The sub-command can also read from the output object, but this doesn’t have anything to do with the parameter passing between parent- and sub-commands.

**Reference Inward, Value In**:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.010.png)

**Reference Inward, Value Thru**:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.011.png)

Because **Reference Inward, Value Out** is only relevant for the parent’s reading values from an output object, it is shortened to **Object Out**.

**Object Out**:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.008.png)

The assignments, that come with parameter passing are always done by the parent command. Whether it is **Reference Inward**, **Reference Outward**, or *values*, the assignments that come with parameter passing are always done by the parent command.

**By Value**, **Reference Outward** and **Reference Inward** are the different reference situations a parameter can have. But this tells us nothing about whether a parameter is input, output or throughput. What determines, whether it is in, out or thru is whether values are written to the parameter or read from the parameter.

So the long names of the different parameter passing types are:

\- **Value In**

\- **Value Out**

\- **Value Thru**

\- **Reference Outward, Value In**

\- **Reference Outward, Value Out**

\- **Reference Outward, Value Thru**

\- **Reference Inward, Value Out**

**Reference Inward, Value In** and **Reference Inward, Value Thru** are not relevant. The **Reference Inward** parameter *can* be *read from* by the sub-command, but that it’s just not relevant to *parameter passing* between a sub-command and a parent command.

It is important to keep understanding that there are three elements to parameter passing:

\- Values read or written

\- Parameter is a reference outward

\- Parameter is referenced from the outside

To understand how the different parameter passings came about, it is important to keep those three aspects in mind.

Here is a list of the parameter passings, with their short names, and their diagram expression:

\- **Value In**

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.001.png)

\- **Value Out**

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.002.png)

\- **Value Thru**

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.003.png)

\- **Reference In**

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.005.png)

\- **Reference Out**

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.006.png)

\- **Reference Thru**

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.007.png)

\- **Object Out**

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.008.png)

The reason why it is important to keep understanding the three aspects of parameter passing, is that **Rerefence** parameters, even though they can be **In**, **Out** or **Thru**, are always *input* in a way, because it is a reference passed from the parent command to the sub-command.

**Value In** and **Value Out** means reading and writing done by de caller. **Reference In** and **Reference Out** means reading and writing done by the called command. In both cases **In** does mean, that the called command *uses* something, and **Out** means, that the called command returns something.
##### **Parameter Passing Type Details**
###### *By Value*
Passing a parameter by value means, that the input or output is *copied* to or from the parameter object.

Parameters passed by value are really only useful for smaller amounts of data, that might be changed, but you don’t want the change to affect the original object. For an object, that only stores one value and that’s it, is is easy to just copy the value. For more complex objects, the question is, to what depth you are going to clone it. The cloning depth may be dependent on the parameter usage inside the command. Please only use passing a parameter by value for simple objects. 

By value should only be used for simple object types with a binary value stored in it, or at most simpler objects, cloned to a certain depth. You should not use by value for complex object types.

Please don’t use passing a parameter by value for complex objects and expect no operation to affect the original object, because the deeper objects of it might not be cloned. The object may be passed to sub-commands, that *will* affect the original sub-objects. I will not elaborate on all the difficult situations that it may produce.

If you want to pass more complex objects to a command, you do it by reference. If you would pass more complex objects to a command by value, expecting no operation to affect the original object, this would make the various passing by value situations too complex, which is way beyond the goal of parameter passing by value.

Perhaps for that reason, no references to original objects will be cloned for by value parameters. Only *values* of sub-objects will be cloned.

In parameter passing by value, the parameter object and the object, that is passed the value to or from, are not referring to eachother at all.

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.012.png)

A value assignment performs a yield over of value.

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.013.png)

A value assignment *does* have an invisible reference to the parameter, but you won’t see it in the diagram, because an assignment is something so basic, that the notation of it is kept very basic.

The complicated notation:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.014.png)

(the arrows are pointing to the references invisible earlier)

But this still does not tie the source and target symbols together.
###### *By Reference*
Next to passing a parameter by *value*, you can also pass a parameter by reference. For instance: instead of copying a value to an input parameter, you give the command a reference to an object outside the command.

Reference parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.004.png)

When a command call has an outward reference to an object, this *does* make the object a parameter, but this *does not* determine yet whether it is input, output or throughput. The *in* and *out* in this case refer to whether *values* are written or read to the object reference. A reference parameter is always sort of like input, though: the parent command passes the object to the sub-command, so the parent inputs something into the sub command. 

An object symbol (a circle) is always a pointer to an object, not a specific object.

So a reference parameter is a pointer to an object *reference*, not a pointer to a specific object.

So the parameter points to another pointer. The target pointer determines the eventual object pointed at.

The notation of a parameter as a pointer to a pointer, though, may become an implicit expression of just an object assignment.

In earlier programming languages one use of by reference was used to be able to pass large objects to a procedure. Another use was to be able to let the procedure have multiple return values, because in other programming languages a procedure can really only have one return value. In the new computer language, multiple return values is accomplished by having multiple **Object Out** parameters. So you do not need **Reference Out** parameters for that anymore.
###### *Value In*
A **Value In** parameter passes a value from an object to the parameter of a command. A **Value In** parameter is an object inside the command call, that is created right before the command is invoked, and a value from another object is then assigned to the parameter, before the command is run.

The command can manipulate the **Value In** parameter without affecting the original object.

A **Value In** parameter works best for a simple object, that stores a single value, but might also work for more complex objects, with more than just a single value, but that will require specifying a cloning depth, and comes with all sorts of downsides. See *By Value*.

A diagram of a command call with a **Value In** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.015.png)

Or:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.016.png)

A diagram of a command definition with a **Value In** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.017.png)

Or:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.018.png)
###### *Value Out*
A **Value Out** is a value produced by a command, that is yielded over to another object after the call is done. A **Value Out** output parameter is an object inside the command call, that is created right before the command is invoked. The parameter is written to by the command or by one of its sub-commands. The value of the output parameter is copied right after the call, assigning the value to another object.

Output values are parameters, that are not assigned before the call, but only read from after the call.

A **Value Out** parameter works best for a simple object, that stores a single value. But it might also work for more complex objects, with more than just a single value, but that will require specifying a cloning depth, and comes with all sorts of downsides. See *By Value*.

Command call with a **Value Out** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.019.png)

Or:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.020.png)

A command definition with a **Value Out** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.021.png)

Or:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.022.png)
###### *Value Thru*
Throughput by value is when a by value parameter is first written to, then changed by the command, and then the value of the parameter is read from again, and assigned to the original object.

A **Value Thru** parameter works best for a simple object, that stores a single value, but might also work for more complex objects, with more than just a single value, but that will require specifying a cloning depth, and comes with all sorts of downsides. See *By Value*.

Command call with a **Value Thru** parameter.

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.023.png)

Or:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.024.png)

In theory, the value could first come from one object, and after the call be written to another object. But that’s not regularly what a **Value Thru** parameter is used for.

Command definition with a **Value Thru** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.025.png)

Or:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.026.png)
###### *Reference In*
A **Reference In** parameter can be used to assign a reference to a complex object as the input of the command.

Because a **Reference In** parameter is input, the called command can only *read* out of the object, that it was given a reference to.

Command call with a **Reference In** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.027.png)

Or:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.028.png)

Command definition with a **Reference In** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.029.png)

Or:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.030.png)
###### *Reference Out*
A **Reference Out** parameter can be used to assign a reference to a complex object to which a command writes output.

Because a **Reference Out** parameter is output, the called command can only *write* to the object, that it was given a reference to.

Command call with a **Reference Out** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.031.png)

Or:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.032.png)

Command definition with a **Reference Out** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.033.png)

Or:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.034.png)

In a sense, a **Reference *Out*** parameter is actually *through*put.

When output is alteration of an existing object, it could be considered throughput, even though there is only *written* to the object, and nothing is *read* from the object, it is still an object passed *through* the command.

A by reference parameter can not change the target object of the parameter or overwrite the target symbol of the reference parameter with a new object. Returning a new object or another existing object is reserved for the **Object Out** parameter.
###### *Reference Thru*
A **Reference Thru** parameter can be used to assign a reference to a complex object, from which input is read and output is written to.

A **Reference Thru** parameter is a pointer to something outside the command. The object pointed to both read from and written to. 

Command call with a **Reference Thru** parameter.

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.035.png)

Or

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.036.png)

Command definition with a **Reference Thru** parameter.

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.037.png)

Or:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.038.png)
###### *Object Out*
An **Object Out** parameter is an object that resides inside the command. The **Object Out** may be a new object, or redirect to an existing object. Anyway, the command determines which object will be output. The produced object will be referenced from outside the command.

Unlike parameters passed by reference, an **Object Out** parameter is *referred to*. This is an exclusive aspect of the **Object Out** parameter passing type.

A diagram of a command call with an **Object Out** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.039.png)

A diagram of a command definition with an **Object Out** parameter:



![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.040.png)

Unlike **By Reference** and **By Value** parameters, there are no three variations for parameters referred *to*. The reason ‘**Object**’ parameter passing does not have three variations, like the **Value** and **Reference** parameter passings, is that the command’s reading and writing values to the object is irrelevant to the *parameter passing*. **Object Out** does not have anything to do with whether the command call reads or writes from the object it outputs. That is irrelevant to the parameter *passing*.

A reference to an **Object Out** parameter causes an implicit run of the command, because a command can not return anything unless it is run. A reference to an **Object Out** parameter copies the target object of the parameter. It can’t permanently refer directly to the parameter, because nothing really exists inside the call unless the call is running.
##### **Issues**
###### *Parameter Passing Notations Are Implicit*
A reference parameter is assigned an object.

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.041.png)

The assignment of an object can also be replaced with the *redirection* of an object.

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.042.png)

The target symbol is not the object itself, but an *object reference*. The parameter is a *reference* to an object reference. This makes the parameter a pointer to a pointer.

An object assignment, and a pointer to a pointer are not completely interchangable, but it is close to it.

Reference parameters could be made pointers to pointers, like in the notation, but the notation may also just be regarded an implicit notation of an object assignment.

A reference to an **Object Out** parameter is also an implicit notation for an object assignment from the parameter to a referrer. So that would nicely fit the two together: parameter references are also an implicit notation for object assignments.

The notations of value transmission for Reference parameters is also just an abstract expression:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.027.png)

It does not display which specific values are read or what the read value is copied to. It does however express the type of parameter passing.

It is an abstract display, not an implicit display.

< 2008-07-06 Any connection to or from a parameter is not really a statically present connection; it is an assignment, that is executed by the parent command on demand. >
###### *Can’t reference each parameter*
You can’t just reference each parameter. You can only reference a parameter when it is **Object Out**.

If a parameter is for instance **Reference Thru**, it can only point *to* something, but you can’t *refer to* a **Reference Thru** parameter. You can only *give it* a reference.

The caller can not redirect the **Object Out** parameter. The call itself may be able to redirect the **Object Out** parameter, but not to something outside the call, because the call is only aware of what’s reachable *inside* the call. This actually counts for objects as well. So the following situation is not possible:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.043.png)

If the caller wants all the object symbols to represent the same object, it should do it for instance like this:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.044.png)
###### *Transfer of indirect values*
Something is input, output or throughput when values are read from it or written to it. But it does not need to be the value of one object being written to another object. It can also be values of sub-objects that are yielded over from one object to another. In that case, the parent object is considered input or output parameters, even though only the values of its sub-objects are used.

For **By Value** parameters an indirect value transfer means, that the input or output object is cloned to a certain containment depth, whereas a direct value transfer means, that only the direct value of the input or output object is copied.

For **By Reference** parameters, indirect value transfer means, that values are read and written from sub-objects of the reference parameter. Direct value transfer of **By Reference** parameters means, that only the direct value of the input or output object is read or written.

For an **Object Out** parameter, the type of value transfer does not matter, so it also does not matter whether there are direct value transfers or indirect value transfers.

When it is direct value transfer, an assignment call is shown in the diagram. 

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.045.png)

The above displays a **Reference In** parameter inside the call, whose direct value is used.

If it is indirect value transfers, then the diagram does not show an assignment call.

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.046.png)

The above displays a command that uses values from the sub-objects of the **Reference In** parameter.

Because it is valuable parameter passing information, whether only the direct value of an object is accessed or also values of sub-objects, you can mention this in the name of the parameter passing type, for instance:

\- **Direct Value In**

\- **Indirect Reference Out**

This adds another aspect to the parameter passing types. This gives the parameter passing types thee aspects:

\- **In** / **Out** / **Thru**   (value direction)

\- **By Value** / **By Reference** / **Object Out**  (reference situation)

\- **Direct** / **Indirect**  (value usage)
###### *Input / output not always values*
Output is not always the assignment of a value, though. Output can also be the creation of an object, or addition of objects to a list. Output can also be assigning **Nothing** to an object reference, or removing objects from a list. It can also be the assignment of an object to an object reference.

Creation, addition, annulment, removal and object assignment are considered *indirect* value transfers. Ofcourse it is not really a *value* transfer, but it *is* output. Creation, addition, annulment, removal and object assignment only applies to output. So creation, addition, annulment, removal and object assignment specifically applies to **Indirect Reference Out** parameters.

However, input can also be merely accessing a sub-object to go to the next object. So input is also not always *value* transmission. That non-value transmission applies to **Indirect Reference In** parameters.

All in all, non-value transmissions apply to **By Reference** parameters only.
###### *Parameters of calls directly tied together*
In other programming languages, sub-commands do not directly read or write to eachother’s parameters. Parameters are only read or written by the parent command.

However, in the new computer language, parameters of sub-commands can be tied together directly.

One parameter type can only be tied to a parameter with specific other parameter type.

A **Value In** parameter can be only be tied to a **Value Out** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.047.png)

A **Value Out** parameter can only be tied to a **Value In** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.048.png)

A **Value Thru** parameter can not be tied to another parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.049.png)

This is because it creates a circularity in which one parameter writes its values to the other, and the other parameter writes its value to the first parameter. It is just an unlogical circular situation.

A **Reference In** parameter can only be tied to an **Object Out** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.050.png)

A **Reference Out** parameter can only be tied to an **Object Out** parameter.

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.051.png)

A **Reference Thru** parameter can only be tied to an **Object Out** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.052.png)

An **Object Out** parameter can be tied to a **Reference In**, **Reference Out** or **Reference Thru** parameter. In short an **Object Out** parameter can only be tied to a **Reference** parameter:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.053.png)

So to summarize it:

Only **Value In** parameters and **Value Out** parameters can be tied together:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.048.png)

Only **Object Out** and **Reference** parameters can be tied together:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.054.png)

However, these direct connections between parameters is an implicit notation of reads and writes executed by the parent.

A direct value transfer:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.055.png)

Is indeed already the explicit notation of it: the value of one parameter is assigned as the value of the other parameter.

An *in*direct value transfer:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.056.png)

is in fact an implicit notation of a cloning operation performed by the parent. For indirect value transfers between **By Value** parameters, you might indicate the cloning depth:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.057.png)

The explicit notation of the **Clone** call:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.058.png)

The command definitions with an indirect by value parameter, with a cloning depth indicated might look like this:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.059.png)

Looking at the explicit notation of the **Clone** call above, because the **By Value** parameters are referenced by the **Clone** operation, this sort of makes the by value parameters:

\- **Reference Inward, Value In**

\- **Reference Inward, Value Out**

However, this is not the way you want to look at it when programming. This is just what happens under the surface.

For object transfers between **Object Out** parameters and **Reference** parameters, the implicit notation is:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.060.png)

However, this direct connection between parameters is an implicit notation of an object assignment executed by the parent:

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.061.png)

So the connection from the **By Reference** parameter to the **Object Out** parameter isn’t really a reference to a reference; it is an object assignment.

Because the **Reference** and **Object Out** parameters are referenced by the object assignment, this sort of makes the **Reference** and **Object Out** parameters:

\- **Reference Inward, Object In**

\- **Reference Inward, Object Out**

However, this is not the way you want to look at it when programming. This is just what happens under the surface.

The object assignment does not require the parent command to have a direct reference to the object. The object assignment can just refer to the object symbols. In text code ths may look like this:

**A  (  O  o=  B  (  )  .  O  )**

Command **A** is called, and its **Reference In** parameter **O** is assigned the output **O** of the command **B**. So no temporary variable is needed to first pick up the output of **B** and then assign it as input of command **A**.

Tying parameters together directly states a direct dependency. No direct reference to the parameter objects are required inside the parent command.

Next to making sub-command directly dependent on eachother like that,

input output can also be between a sub-commands parameter and a sub-object of the parent command. This does not create a direct dependency between sub-commands, but it does create an indirect dependency.

![](images/2008-07-13%20XX%20%20Command%20As%20A%20Concept%20Brainstorm%20Texts.062.png)

The parameter of command **A** is a **Value Out** parameter that writes to object **O**. The parameter of command **B** is a **Reference Out** parameter that connects to object **O**. The parameters of command **A** and command **B** are not directly tied to eachother, but they do indirectly related to eachother. This will be further elaborated in *Automatic Execution Order*.
##### **Further parameter passing stereotyping**
Comtemplations about further thru parameter passing stereotyping will be postponed.

The thru parameter passing type can be further split up in *affected*, *used & affected*, *transformed*, *transformed same value*, *used & affected & transformed* and *used & affected & transformed same value*.

<…>

Furthermore, thru can be either *affected*, *used & affected* or *transformed* or both. Affected is considered throughput, even though nothing is read from it, because the object is still *passed through* the command.

This gives us the following number of parameter passing situations:

\- Value In

\- Object In

\- Reference In

\- Value Out

\- Object Out

\- Reference Out

\- Value Thru

\- Value Thru, Affected

Value Thru, Affected does not make sense. You’d give a parameter an initial value, that does not get used, but will be overwritten. Value In is a better choice in that case.

\- Value Thru, Transformed

\- Value Thru, Used & Affected

\- Value Thru, Used & Affected & Transformed

\- Object Thru

\- Object Thru, Affected

\- Object Thru, Transformed

~ Object Thru, Transformed Same Value

\- Object Thru, Used & Affected

\- Object Thru, Used & Affected & Transformed

\- Reference Thru

\- Reference Thru, Affected

\- Reference Thru, Transformed

~ Reference Thru, Transformed Same Value

\- Reference Thru, Used & Affected

\- Reference Thru, Used & Affected & Transformed

< When throughput it is affected and used, values are read and written from it to manipulate or coming out of other objects. When throughput is transformed, the values written to the throughput object were derived from values first read from the throughput object. >
###### *Brainstorm*
Do I really need to stereotype this many subtile variations? Isn’t the fact that it is thru enough to tie everything together?

This whole section in, out, thru is getting out of hand.

It was supposed to be simple. It wasn’t even there at first.

I have to simplify the story, keeping the split up in affected, used, transformed and ‘same value’ a detail

Then I need to work out the subjects under the assumption, that you only need to be concerned with in, out and thru.
###### *Same Value*
< Perhaps when it is the exact same variable that’s read and written, this should be stereotyped in a different way as well. It is transformed, but then specific values are both used and affected. Transformed where one part of the object is used, to affect another part of the object, is also transformation, but less rigorous, so perhaps you do need some sort of stereotyping for that. >
###### *Throughput variations*
< combinations:

not affected, not used, not transformed

\-

not affected, not used, too transformed

transformed

not affected, too used, not transformed

used

\> in, not thru

not affected, too used, too transformed

used & transformed

too affected, not used, not transformed

affected

too affected, not used, too transformed

affected & transformed

too affected, too used, not transformed

affected & used

too affected, too used, too transformed

affected & used & transformed

< only *used* is actually input, not throughput. >

The combinations, that are left, then:

affected

affected & used

transformed

used & transformed

affected & transformed

affected & used & transformed
###### *Value Thru, affected*
Does not make sense. You’d give a parameter an initial value, that does not get used, but will be overwritten.
#### ***Automatically determining what’s in, out or thru***
The terms input, output, throughput and downput were discussed earlier. Here it is discussed how to automatically determine whether a parameter is in, out, through or downput.

Input, output and throughput has to do with value assignment, but also reference-assignment and other types of assignment, and also other machine instructions that perform a read-write operation.

Not only directly contained parameters are input, output or throughput. When sub-objects of a parameter are used, the sub-objects become input, output and throughput of the command. So the configuration of direct parameters does not determine at all what exactly is input, output or throughput. The *usage* of things determines it.

To automatically determine, whether a parameter is input, output or throughput, you should not only only look at the assignments executed by the command itself. Parameters, or sub-objects of parameters, are also passed to other commands. Whether something is input, output or throughput is equally dependent on whether it is input, output or throughput of a sub-command. If something is throughput for command A, and command A is called by command B, this automatically makes it throughput of command B. (This, unless it is command B’s downput.)

A rigorous way to automatically determine whether something is input, output or throughput, would be to traverse the whole structure of command calls. The assignments are the leaves of that structure (or any other form of read-write machine instruction is also a leave of this structure). Whether something’s input, output of throughput is derived from these assignments and machine instructions. You *could* encounter circularities traversing the call structure. So this would require circularity handling.

Whether something is input, output of throughput only changes when the command definition of a sub-command changes. So instead of traversing the whole command call structure to determine whether something is in, out or thru, you also could cast a change to all callers of the command, and their callers, and their callers, upon which the callers adapt their in-out-thru configuration accordingly. This creates a huge event cast. This needs to happen with events, and all dependencies should register themselves inside what they are dependent on.

This makes it possible, that you get very wide casts for a small change in the system. In a well monitored and regulated system this should be workable. Events will create this extreme activity, but that’s just an aspect of this new system. Computer systems will be extremely active, but this is solved by regulating input and output and quota-limits in space and time.

Any way it is done, you have to *store inside* a command, whether a parameter is input, output or throughput, whether it is automatically deteremined or not. Just like the execution order of sub-commands it is stored inside a command. You have to *store* whether something’s input, output or throughput, because otherwise, you have to redetermine it too many times using a complicated procedure.

Each command defines what is its input, output or throughput, and a new command can part take over the input, output, throughput configuration from its sub-commands.

However, when a definition of a command changes, a huge cast to all its callers and their callers, and their callers is executed.

Even this big event cast can be prevented. The answer is versioning. When you use versioning, a called command never changes. Only when command A decides to link to a newer version of command B, command A’s input, output, throughput configuration may change. If command B changes, command A keeps linking to the old version of command B. So the dependencies of command A do not change, and keep pointing to an old version of command A.

Only when programming a new version of a system, you can decide to possibly link to a new version of things. A version of a system, that is in production, keeps pointing to unchanging versions of their dependencies.

A question for versioning is: when will a version of a command be created? On every change? Or will there be key moments at which an author publishes the new version of the command. These are issues for Versioning, which falls under the Editing & Authoring concepts.

Versioning of commands can prevent huge casts of changes to input, output or throughput configuration, or at least limit it in size. Only when defining a new call, you have to look at the called command to see if this changes the in, out, thru configuration of the currently edited parent command definition.
##### **Giving the issues in this section a place**
The ideas about versioning need to be moved to the article *Versioning*.

The ideas about event casts should be moved to the article *Events*. 

You should only *refer* to those articles, even when the articles are not not finished.

The rest is all part of automatically determing in-out-thru.
#### ***Automatic Execution Order***
The first thought was, that the execution order of sub-commands could be automatically determined, based connection between parameters and objects, and whether parameter is **In**, **Out** or **Thru** and **By Reference**, **By Value** or **Object Out**. But this is not true.
##### **Parameters tied together**
When the parameters of two commands are directly tied together, it is not hard to determine the order in which to execute the commands. Parameters can only be directly tied together to eachother in a limited number of ways, so that makes it quite easy. One parameters is output, that is used as input for another command. A consultation of a command requires the command to run. The sub-commands have a direct dependency on eachother and a command requires its dependencies to run first.

< Pictures >
##### **Parameters tied to objects**
However, parameters can also be tied to sub-objects of the parent command.

< Picture >

If parameters of different commands are tied to the same object, and they are all input parameters, then the execution order of the sub-commands does not matter.

But if one of them is an output parameter, then it is a question whether the input parameter wants to use the changed value or the original value of the object. So in that case the order should be manually indicated.

< Pictures >
##### **Outcome dependency**
If a reading sub-command is dependent on the outcome of a writing sub-command, then you have to manually indicate the execution order, so that the writing command runs before the reading command. The indication of execution order in that case is sort of like indicating an *outcome* dependency. If you want the original value, you can indicate the execution order, drawing out, that the reading command should run first, which is like a negative statement of outcome dependency.

*Outcome dependency is exchangable with execution order.*

Multiple things may be dependent on the outcome of a command, which means that the writing command might have multiple next-command indications. That’s right. The dependencies could all run in parallel. From this dependency can be derived, that some things can be run in parallel, and some things have to run in a serial order.
##### **Accessing parameters’ sub-objects**
An object inside the parent command has sub-objects. From the parameter you can’t tell whether the object itself is written or an object 10 levels deep is written. 

< Picture >

With reference parameters, changes and consults can be at any depth. Any object indirectly links to any other object in the world, so passing an object as a parameter makes basically any other object around the world accessible to the command. So basically anything could be changed by a command.

That used to be one argument in the claim, that automatic execution order is impossible, but help is on the way…
##### **Specific data unknown**
Another argument against automatic execution order is, that from a command *definition*, you still don’t know what specific data will be processed. This is because the parameters of the command are not yet filled in. A command definition does not have any objects assigned to the parameters yet. So it is not clear what exact data will be processed. Command definitions only indicate what *types* of object can be connected to the command, but not what *specific* objects are connected to the command. You only know what specific data is processed when a command has specific object connections. A command only has specific object connections when it actually *runs*. But even though, what a command will change seems pretty volatile, there are possibilities for predictions about what a command will change. Things considering eachother’s changings once a command actually runs, is a concurrency topic, that will be covered in *Concurrency Resolution*, but not in *Automatic Execution Order*.
##### **Parameters & IO**
Input and output are not the parameters, but what specifically is read or written *from* the parameters. The input and output of a command are not the parameters passed to it, but any piece of data *used* by the command. You just can’t see from the parameter itself exactly what is changed.

In theory there's no telling what a command may read or write, but in practice the amount of things read and written are limited. You can list out what a command reads and changes.

Here follows a textual definition of a parameter, and of the input and output; three entirely different things.



Parameter:

**Reference Thru  Document  As  Graphics  .  Document**

Input:

**Document  .  Points  .  Item  [  \*  ]  .  X**

**Document  .  Points  .  Item  [  \*  ]  .  Y**

Output:

**Document  .  Lines  .  Item  [  0  ..  \*  ]  .  Point A   .  X**

**Document  .  Lines  .  Item  [  0  ..  \*  ]  .  Point A   .  Y**

**Document  .  Lines  .  Item  [  0  ..  \*  ]  .  Point B   .  X**

**Document  .  Lines  .  Item  [  0  ..  \*  ]  .  Point B   .  Y**

There must be a limitation in the expression of what is accessed. Perhaps if only **Document**'s existance is being checked, this might be indicated. But to a certain extend the expression of what exactly is accessed should be limited. Not the entire inner workings of a command are visible from its input and output. For instance, in the input / output expression you will *not* be seeing what *sub-commands* are called.

What is written and read by a command are actually pre- and post-conditions of the command. 

Only when you are editing a command, the pre- and postconditions of the command have to be determined. The pre- and postcoditions do not change once you’ve published, versioned, the command. Once you are done designing, the input-output configuration will be stored within the command. Remember that the *structural* input and output is different from what a command will actually read and change.
##### **Compared IO**
In a command definition you only know which *structure elements* a command accesses, and not yet what specific objects. But from the structure elements used by the command, you can already see whether commands *might* be in eachother's way. This opens up possibilities to exclude or confirm, that commands might be in eachother’s way. When parameters of different reading and writing commands are tied to the same object reference and they are accessing the exact same structure elements, you can be pretty sure they will be in eachother’s way. But when you are accessing different object references, you can’t be sure whether accessing *different* object references means accessing *different* objects. The two object references may be referring to the same object all the same. Even though automatic containment of objects would indicate which object references represent the same object, this can not be seen in the diagram expression of a command *definition*, because objects are not filled in yet.

And then you have to look if there is any overlap in what one command writes and the other commands reads. The overlap might prove a possible read-write dependency. The order of the two commands would affect the outcome, so that might prove that you *have to* indicate an outcome dependency or a negative statement of outcome dependency. Or when a *different* object reference of the same class is consulted, that you *might* need to indicate outcome dependency.

When you don’t consider volatile concurrency, then when sub-commands follow the same structure paths starting at the same object, you are pretty sure, when the same object will be accessed. But in a volatile concurrency situation you are never entirely sure, unless you lock the data. But those are concurrency issues, which are for later.

**Command A** can only be outcome-dependent on **Command B**, when some of **Command B**’s output is **Command A**’s input. Input and output of a command are not the parameters, but what is read or written *from* the parameters. For command *definitions*, this means, that outcome dependency can only be indicated for sub-commands that have any possible overlap in input-output.

Building up the outcome-dependency structure of a command is only done in the design stage of the command. The outcome-dependency does not change once you’ve published, versioned, a command with sub-commands. Once you are done designing, the outcome-dependency configuration will be stored within the command.
##### **IO definition used for security**
This explicit statement of what exactly is accessed, is a great tool for security. A user can actually *see* what a command is changing. In security you have to beware how the command might be faking it.
##### **Sub-commands**
It is quite easy to see what is directly used by a command, but the command also has sub-commands, that also use certain data. The parent command passes data to the sub-commands.  

What is used by a command is a union of everything directly changed by the command and everything changed by the sub-commands and their sub-commands and so on. And what if the command call structure is recursive? This may impose even more difficulty. It may be a lot of work to gather up everything a command might change, including what their sub-commands might change, and then gather up anything a command might read, and what its sub-command might read.

But the sub-commands already store what exactly they read and write, including what they read and write from *their* sub-commands, so that makes it a lot easier.
##### **Conclusions**
In the end, automatic execution order is all about manually indicating outcome dependency between commands, instead of *explicitly* defining the execution order. Even connecting parameters together directly is indicating an *outcome dependency*.

Execution order can not be derived, without manually specifying the outcome dependency of sub-commands, because a machine does not know whether you want the altered of unaltered version of an object. But many ideas have been proposed to automate the detection whether commands can be in eachother’s way at all. Outcome dependency can only be indicated for commands, that *could* be in eachother’s way. Commands, that can’t be in eachother’s way can be run in parallel or in an arbitrary order.

That is what automatic execution order is.
##### **Use later**
Sub-commands indirectly relate to eachother through mutual references to the same object, and what they read or write from that object.

It can be determined, that part of the sub-commands can run independently. If they don’t consult the same data, they can run totally concurrently. Only if things consult the same data, and there is at least one reference that writes to it, then an order must be determined.
###### *Multiple parameters*
< Things become more complex when commands with multiple parameters start relating to eachother. >

< 2008-07-06 When commands have multiple parameters tied together complexly to other parameters, you have to resolve this in an execution order. >

< By the way: if you use multiple output parameters of a command, how does the consult of the *two* parameters result in a *single* run?> 
#### ***System interface***
There is a paradox.

A command is a special object, that can execute, but an object has system commands. A related item gets system commands. So here I want to replace a real command by an object, that can behave as a command, but an object *must* have system commands in order to function.

But it is not so much about the system commands, that are added by concepts, but about *fundamental* system commands.

Actually, no object has fundamental system commands. Only object references, symbols, have fundamental system commands.

And there aren’t many either. Just get, and set and some other few.

The other non-fundamental system commands *are* executable sub-objects of an object or a symbol or something, only they are hidden. Anyway, you don’t need to be concerned with them. The only place where the paradox is, is the fundamental system commands. And there aren’t many fundamental system commands, so you only have to consider a few.

You have to see fundamental system commands as exceptional.

It is really not that much of a problem.

Assignments also require calls to system commands. You have to consider that.
#### ***Remaining Ideas***
The implementation of a command is called a procedure.

Parameters,



Required return value: unable to execute without picking up the return value.



JJ

And how does it look to express a reference line as the assignment of a reference target?

Are those interchangable notations?

I really want the programming environment,

to not so easily accept, that a parameter

is typed throughput, when it is only read from.

Because otherwise you rely too much on 

courtesy of the programmer, to make

the whole system function correctly.

When you pass a property as a byref argument, and the procedure reads and writes from the byref parameter, you want the property get and set to be called. Does that require a pointer to a pointer to a pointer or what?

You might explain things first as execution order not being automaticaly determined, and in, out and tru not being automatically deteremined,

and then in an article after that, releaving the programmer from it,

because it is done automatically. It is a nice surprise and releave point, and an amaze point, and an excite point.
