Circular Language Construct Drafts
==================================

Input Output | Loose Ideas
--------------------------

`[ Preliminary documentation ]`

Advanced Command Articles,  
2008-08

The order in which the sub-commands execute can be manually set, but the technique of automatic execution order makes is possible to have the order automatically determined. Either way, the order of the sub-commands is stored inside the command definition.

For a command to execute, the sub-commands need to execute in the right order. The sub-commands again execute sub-commands. This going by the commands recursively probably needs to be present in the code base. The outer commands are machine instructions, which might also be called by the code base.

A command actually is an object, with some special properties: it executes, it contains calls to other commands, and the calls are executed in a certain order, part of which can be automatically determined.

JJ

-----

Advanced Command Articles,  
2008-08

For an object to have a reference to a command, you might be able to define a relation between a command and an object. This is only possible, if a command is an object.
If you want to do that, you might implement commands as an aspect.

A command itself can also contain related command references, which are then considered parameters of the command.

JJ

-----

Advanced Command Artices,  
2008-08

A nested command has a unary relation with its parameters, because you do not want to see the nested command as a command in the classes of a nested command's parameters.

JJ

-----

Advanced Command Topics,

You might explain things first as execution order not being automatically determined, and in, out and tru not being automatically determined,  
and then in an article after that, relieving the programmer from it,
because it is done automatically. It is a nice surprise and relieve point, and an amaze point, and an excite point.

JJ

-----

Advanced Command Topics,

Objects only make sense if they are used as input, output or throughput.

JJ

-----

Threads,  
2008-08-26

Threads as a string of commands has not been explained yet.

JJ

-----

Parameters / Input Output,  
2008-09-25

> 2008-10-01 What do I want to do with this? I moved the idea from Parameters to input-output, because I do not find it important right now. Perhaps I might find it important when thinking through Input-Output aspects, or perhaps I might find out I want to throw this away.
- A situation, where an Object Set on the inside and an Object Set on the outside has the exact same result.
The effect of an Object Set from the outside can perhaps result in the same situation as na Object Set from the inside. It might not matter whether the result of an Object Set on the outside is the same as an Object Set on the inside. This is what it is conceptually.
The effect might be that a command contains a reference to an object, whether it is an Object Out parameter, Value parameter or Reference parameter.  
I could take a look at situations, where an Object Set on the inside and an Object Set on the outside has the exact same result, but even if it might, it might not matter.

JJ

-----

Input Output,  
2008-09-09

But access controlling aspects of a parameter might give guarantees about the command's behavior. Guarantees, that might be essential for automatic execution order, concurrency resolution and user controlled access control, so a user can make a decision about the usage of a command, based on what is done with the objects passed to it.

JJ

-----

Command IO,  
2008-09-09

When a Reference parameter is a command, it can also be passed to a sub-command again.

JJ

-----

Input Output,  
2008-10-15

In Circular you might see, which things have a reference to which other things. So when you have an element of the system, you immediately which parts of the system use the element. But when you are working on a development version of something, you might have definitions to which no input or output targets are assigned yet. In that case it is handy to have an example of what the input or output might look like. This is not the same as a default value. It is an example value. In a real business environment it might become a convention, that the example input parameters establish a call upon mere test data. And when a test command is run, the example output can indicate whether anything has changed to the output since then.

JJ

-----

Input Output,  
2008-10-15

I keep speaking in terms of input and output, so why can parameters not be typed as input output yet in the Parameters documentation. That's why Input Output should be exactly defined in the Input Output documentation. It is very important to have a clear view on the exact definition of when something is input and when something is output.

JJ

-----

Data Direction,  
2009-06-17

To abstractly express data direction unspecific of what specific data, I  used a double wavy line, but I like a triple wavy line better. Triple better expresses a multitude, then just two.

JJ

-----

Input Output,  
2009-09-25

Save this idea for Input / Output, because that is where it starts to publicly matter what happens privately.

-----

2004

In the C++ programming language constant parameters can be set at run time when you call a procedure. In Symbol constants are really constant: they might not change at run time and are only set at design time

JJ






















