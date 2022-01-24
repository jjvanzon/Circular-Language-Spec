Construct Drafts | Input Output
===============================

`[ Draft ]`

The concept of input and output may be common to programming, yet the concept might not seem very present in both object oriented program code or relational database. Something simply seems to ‘become’ input or output, arbitrarily chosen by the programmer, but it might not explicitly *defined* in program code, what is the input and what is the output: it could be a return value returned by a command, a value passed along to another command, *but* it could also be reads, writes deletes and inserts into a database. Those things might be spread out all over the commands and you might not really see explicitly where something is input and where something is output. Yet, input and output seem a fundamental idea in computer programming. We sometimes talk in terms of it. In Circular language, input and output may get a more prominent position. It may even offer opportunities for resolution of concurrency and parallelism as well as better security in case of more control over the input and output.

This documentation might not seem finished up yet. It seems to contains quite some unfinished texts but also some ideas that are perhaps nice, but it might not all seem to be worked out yet. The concept of input and output might be taken further in the future.

- ## In, Out & Thru

    - What might be worked out, is a definition of what input and output is and what different forms of input and output there might be.

- ## [Auto-Determine In, Out & Thru](auto-determine-in-out-thru.md)

    - Explores an idea where the way a parameter is used, could determine whether it might be considered __Input__, __Output__ or __Thruput__. It may be of help once when making for the *Parameters* section in the *Spec*. But for now the idea is parked here.

- ## [Automatic Execution Order & More](automatic-execution-order-and-more.md)

    - This document may combine several of these input/output topics. It may once be split up into separate articles.

- ## [Input Output | Loose Ideas](input-output-loose-ideas.md)

    - Loose ideas about the topic.

- ## Command IO

    - In the end, every command may have an input / output definition, that could consist of for instance reads, writes, additions and removals of data. This might not define *exactly* what the command might do, but might define what data is affected and what data is used. Users might then be directly able to see what the input and output of a program or command might be and this may offer better security, if the user can see the input / output effect of what they may be about to run. You might further secure the system if you could allow a command to only access data, that it says it needs to access, so nothing funky might run inside a program. This definition of input and output of a command might be called the *Command IO*.

- ## Compared IO

    - When two commands seem to affect the same data, they might be in each other’s way. A definition of that overlapping usage and alteration might be called *Compared IO*. The idea might be, that when it is defined what data is mutually used, this might define the input-output dependency of commands.

- ## Outcome Dependency

    - The hope is, that the input-output dependency, or *outcome dependency*, might offer a mechanism for better managing the execution order of commands.

- ## Automatic Execution Order
 
    - Perhaps the most practical execution order of commands could be automatically determined without intervention of a programmer: *automatic execution order*. It may not be fully worked out yet, but the hope is, that this can be translated into a method for resolving concurrent access of data *(concurrency resolution)* and automatically determining whether things might run serially or if things can be processed in parallel, perhaps offering an automatic way to resolve *parallelism*.

When working out this documentation, the exact definition of the concepts above might be worked out and hopefully it may carefully explain how, by giving the concept of input and output a more prominent position in Circular and comparing different command IO definitions, this may offer opportunities for resolution of concurrency and parallelism as well as perhaps improved security.