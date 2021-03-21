Circle Language | Construct Drafts
==================================

Input Output
------------

The concept of input and output may be well-known by computer experts, yet the concept does not seem very present in both object oriented program code or relational database. Something simply ‘becomes’ input or output, arbitrarily chosen by the programmer, but it might not explicitly *defined* in program code, what is the input and what is the output: it could be a return value returned by a procedure, a value passed along to another procedure, but it could also be reads, writes deletes and inserts into a database. Those things are spread out all over the procedures and you do not really see where something is input and where something is output. Yet, input and output seem a fundamental idea in computer programming. It seems we talk about it all the time. In Circle language, input and output may get a more prominent position. It may offer opportunities for resolution of concurrency and parallelism as well as better security.

This documentation is not finished up yet. It contains a lot of unfinished texts but also some ideas that are perhaps nice, but it is all not worked out yet. The concept of input and output may be taken further.

- ### In, Out & Thru

    - What might be worked out, is a definition of what input and output is and what different forms of input and output there might be.

- ### Input Output | Parameter Passing

    - ...

- ### Further Parameter Passing Stereotyping

    - ...

- ### Auto-Determine In, Out & Thru

    - ...

- ### Automatic Execution Order & More

    - This document may combine several of the topics mentioned here. It may once be split up into separate articles.

- ### Input Output | Loose Ideas

- ### Command IO

    - In the end, every command may have an input / output definition, that could consist of for instance reads, writes, additions and removals of data. This might not define *exactly* what the command does, but it does define what data is affected and what data is used. Users might then always be able to see what the input and output of a program or command might be and this offers better security, because the user can see the input / output effect of what they are about to run. You can further secure the system by allowing a command to only access data, that it says it needs to access, so nothing funky can be run inside a program. This definition of input and output of a command will be called the *Command IO*.

- ### Compared IO

    - When two commands affect the same data, they could be in each other’s way. The definition of that overlapping usage and alteration is called *Compared IO*. The idea is, that when you have defined what data is mutually used, you have defined the input-output dependency of commands.

- ### Outcome Dependency

    - The hope is, that the input-output dependency, or *outcome dependency*, will offer a mechanism for better managing the execution order of commands.

- ### Automatic Execution Order
 
    - Perhaps the right execution order of commands can be automatically determined without intervention of a programmer: *automatic execution order*. It is not fully worked out yet, but the hope is, that this can be translated into a method for resolving concurrent access of data *(concurrency resolution)* and automatically determining whether things have to run serially or things can be processed in parallel, offering an automatic way to resolve *parallelism*.

When working out this documentation, the exact definition of the concepts above will be worked out and hopefully it can be carefully explained how just by giving the concept of input and output a more prominent position in computer language and comparing different command IO definitions, it may offer opportunities for resolution of concurrency and parallelism as well as better security.