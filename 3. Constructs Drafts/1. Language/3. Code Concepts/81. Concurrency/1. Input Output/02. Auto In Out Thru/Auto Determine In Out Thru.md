|<h1>***Computer Language Coding Concepts***</h1>|
| :- |
## **Automatically Determining What’s In Out or Thru**
< Under construction >

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

A question for versioning is: when will a version of a command be created? On every change? Or will there be key moments at which an author publishes the new version of the command. These are issues for Versioning, which falls under the E	diting & Authoring concepts.

Versioning of commands can prevent huge casts of changes to input, output or throughput configuration, or at least limit it in size. Only when defining a new call, you have to look at the called command to see if this changes the in, out, thru configuration of the currently edited parent command definition.
##### ***Giving the issues in this section a place***
The ideas about versioning need to be moved to the article *Versioning*.

The ideas about event casts should be moved to the article *Events*. 

You should only *refer* to those articles, even when the articles are not not finished.

The rest is all part of automatically determing in-out-thru.

See also: *< List of articles >*


*Author & Copyright: <Jan-Joost van Zon>        Date: <May 21, 2008> – <May 22, 2008>        Location: <Oosterhout, The Netherlands>        Status: [ Under Construction | Finished | … ]*
## **Ideas**

If anything should change about the Basic Command Topics as soon as you will revise Commands & Classes Loosely Coupled, then you have to redo the Basic Command Topics during a project about Advanced Command Topics.
