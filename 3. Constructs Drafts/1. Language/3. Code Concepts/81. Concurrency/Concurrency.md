|<h1>***Circle Documentation***</h1>|
| :- |
## **Concurrency**
…

### *Input Output*

The concept of input and output is well-known by computer experts, yet the concept is not very present in both object oriented program code or relational database. Something simply ‘becomes’ input or output, arbitrarily chosen by the programmer, but it is ever explicitly *defined* in program code, what is the input and what is the output: it could be a return value returned by a procedure, a value passed along to another procedure, but it could also be reads, writes deletes and inserts into a database. Those things are spread out all over the procedures and you do not really see where something is input and where something is output. Yet, input and output are fundamental in computer programming. We talk about it all the time. In the new computer language, input and output will get a more prominent position.

This documentation is not finished up yet. It contains a lot of unfinished texts but also some amazing ideas, but it is all not worked out yet. The concept of input and output will be taken further than ever before. What should be worked out, is an exact definition of what input and output is and what different forms of input and output there are. In the end, every command will have an input / output definition, that consists of for instance reads, writes, additions and removals of data. This does not define *exactly* what the command does, but it does define what data is affected and what data is used. Users can always see what the input and output of a program or command is and this offers better security, because the user can see the input / output effect of what they are about to run. You can further secure the system by allowing a command to only access data, that it says it needs to access, so nothing funky can be run inside a program. This definition of input and output of a command will be called the *Command IO*.

When two commands affect the same data, they could be in eachother’s way. The definition of that overlapping usage and alteration is called *Compared IO*. The idea is, that when you have defined what data is mutually used, you have defined the input-output dependency of commands.

The hope is, that the input-output dependency, or *outcome dependency*, will offer a mechanism for better managing the execution order of commands. Perhaps the right execution order of commands can be automatically determined without intervention of a programmer: *automatic execution order*. It is not fully worked out yet, but the hope is, that this can be translated into a new method for resolving concurrent access of data *(concurrency resolution)* and automatically determining whether things have to run serially or things can be processed in parallel, offering an automatic way to resolve *parallelism*. When working out this documentation, the exact definition of the concepts above will be worked out and hopefully it can be carefully explained how just by giving the concept of input and output a more prominent position in computer language and comparing different command IO definitions, there will be complete resolution of concurrency and parallelism as well as better security.

### *Concurrency*

Concurrency occurs when several running processes or users access the same data at the same time. This can result in several problems. There are several candidate mechanisms to solve concurrency problems. Which is the best one is yet to be determined. In this documentation folder you will find a lot of ideas about it, but the documentation is under construction. Look inside the article *Internet As A Single Computer* for a better description of the problem. The *Input Output* concept may offer a method to resolve concurrency issues in the future as well.


*Author & Copyright: Jan-Joost van Zon        Date: January 7, 2011 –  January 9, 2011        Location: Oosterhout, The Netherlands        Status: Finished*

