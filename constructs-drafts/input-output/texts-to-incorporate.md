Circle Language Construct Drafts | Input Output
===============================================

Texts to Incorporate
--------------------

`[ Preliminary documentation ]`

Advanced Command Articles,  
2008-08

The order in which the sub-commands execute can be manually set, but the technique of automatic execution order makes is possible to have the order automatically determined. Either way, the order of the sub-commands is stored inside the command definition.

For a command to execute, the sub-commands need to execute in the right order. The sub-commands again execute sub-commands. This going by the commands recursively probably needs to be present in the code base. The outer commands are machine instructions, which will also be called by the code base.

A command actually is an object, with some special properties: it executes, it contains calls to other commands, and the calls are executed in a certain order, part of which can be automatically determined.

JJ

-----

Advanced Command Articles,  
2008-08

For an object to have a reference to a command, you have to be able to define a relation between a command and an object. This is only possible, if a command is an object.
If you want to do that, you have to implement commands as a concept.

A command itself can also contain related command references, which are then considered parameters of the command.

JJ

-----

Advanced Command Artices,  
2008-08

A clause has a unary relation with its parameters, because you do not want to see the clause as a command in the classes of a clause's parameters.

JJ

-----

Advanced Command Topics,

You might explain things first as execution order not being automatically determined, and in, out and tru not being automatically determined,  
and then in an article after that, relieving the programmer from it,
because it is done automatically. It is a nice surprise and relieve point, and an amaze point, and an excite point.

JJ

----

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

> 2008-10-01 What do I want to do with this? I moved the idea from Parameters to input-output, because I do not find it important right now. Perhaps I will find it important when thinking through Input-Output concepts, or perhaps I will find out I want to throw this away.
- A situation, where an Object Set on the inside and an Object Set on the outside has the exact same result.
The effect of an Object Set from the outside can perhaps result in the same situation as na Object Set from the inside. It might not matter whether the result of an Object Set on the outside is the same as an Object Set on the inside. This is what it is conceptually.
The effect will be that a command contains a reference to an object, whether it is an Object Out parameter, Value parameter or Reference parameter.  
I could take a look at situations, where an Object Set on the inside and an Object Set on the outside has the exact same result, but even if it does, it does not matter.

JJ

-----

Input Output,  
2008-09-09

But access controlling aspects of a parameter will give guarantees about the command's behavior. Guarantees, that might be essential for automatic execution order, concurrency resolution and user controlled access control, so a user can make a decision about the usage of a command, based on what is done with the objects passed to it.

JJ

-----

Command IO,  
2008-09-09

When a Reference parameter is a command, it can also be passed to a sub-command again.

JJ