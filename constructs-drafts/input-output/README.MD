Circle Language | Construct Drafts
==================================

Input Output
------------

The concept of input and output may be well-known by computer experts, yet the concept does not seem very present in both object oriented program code or relational database. Something simply seems to ‘become’ input or output, arbitrarily chosen by the programmer, but it might not explicitly *defined* in program code, what is the input and what is the output: it could be a return value returned by a procedure, a value passed along to another procedure, but it could also be reads, writes deletes and inserts into a database. Those things might be spread out all over the procedures and you might not really see explicitly where something is input and where something is output. Yet, input and output seem a fundamental idea in computer programming. It seems we sometimes do talk in terms of input / output. In Circle language, input and output may get a more prominent position. It may even offer opportunities for resolution of concurrency and parallelism as well as better security in case of more control over the input and output.

This documentation does not seem finished up yet. It seems to contains quite some unfinished texts but also some ideas that are perhaps nice, but it does not all seem to be worked out yet. The concept of input and output might be taken further in the future.

- ### In, Out & Thru

    - What might be worked out, is a definition of what input and output is and what different forms of input and output there might be.

- ### [Input Output | Parameter Passing](https://github.com/jjvanzon/Circle-Language-Spec/blob/master/constructs-drafts/input-output/input-output-parameter-passing.md)

    - This take on *Parameters* might once take preference over the one currently in the *Spec*. The *Spec* may currently speak of parameters as a loosely coupled relationship between commands and classes. That take on it might have made things rather complicated instead of being more helpful. The take here in *Construct Drafts* seemed a simpler perhaps more usable alternative. It seems to talk about subdividing parameter passings into __By Ref / By Value__ and __Input / Output / Thruput__. The idea seems to have been set aside, because of som difficulty defining what __Input__ and __Output__ mean precisely on a more detailed level as well as in grander scope. But a simplified version of this story it might be more helpful as a way to express parameters in this diagram language, that may once become part of the *Spec* again.

- ### [Thruput Parameters Affected, Used and Transformed](https://github.com/jjvanzon/Circle-Language-Spec/blob/master/constructs-drafts/input-output/thruput-parameters-affected-used-and-transformed.md)

    - Explores a slightly more detailed way of specifying variations on __Thruput__ parameters: __Affected__ / __Used__ / __Transformed__. It might not be as usable in practice. That is why the topic was set aside here.

- ### [Auto-Determine In, Out & Thru](https://github.com/jjvanzon/Circle-Language-Spec/blob/master/constructs-drafts/input-output/auto-determine-in-out-thru.md)

    - Explores an idea where the *way* a parameter is used, could determine whether it might be considered __Input__, __Output__ or __Thruput__. It may be of help once making a simpler variation on a *Parameters* section in the *Spec*. But for now the idea is parked here.

- ### [Automatic Execution Order & More](https://github.com/jjvanzon/Circle-Language-Spec/blob/master/constructs-drafts/input-output/automatic-execution-order-and-more.md)

    - This document may combine several input/output topics. It may once be split up into separate articles.

- ### [Input Output | Loose Ideas](https://github.com/jjvanzon/Circle-Language-Spec/blob/master/constructs-drafts/input-output/input-output-loose-ideas.md)

    - Loose ideas about the topic.

- ### Command IO

    - In the end, every command may have an input / output definition, that could consist of for instance reads, writes, additions and removals of data. This might not define *exactly* what the command does, but might does define what data is affected and what data is used. Users might then be directly able to see what the input and output of a program or command might be and this may offer better security, if the user can see the input / output effect of what they may be about to run. You might further secure the system if you could allow a command to only access data, that it says it needs to access, so nothing funky might run inside a program. This definition of input and output of a command might be called the *Command IO*.

- ### Compared IO

    - When two commands seem to affect the same data, they might be in each other’s way. A definition of that overlapping usage and alteration might be called *Compared IO*. The idea would be, that when it is defined what data is mutually used, this might define the input-output dependency of commands.

- ### Outcome Dependency

    - The hope is, that the input-output dependency, or *outcome dependency*, might offer a mechanism for better managing the execution order of commands.

- ### Automatic Execution Order
 
    - Perhaps the most practical execution order of commands could be automatically determined without intervention of a programmer: *automatic execution order*. It may not be fully worked out yet, but the hope is, that this can be translated into a method for resolving concurrent access of data *(concurrency resolution)* and automatically determining whether things have to run serially or if things can be processed in parallel, perhaps offering an automatic way to resolve *parallelism*.

When working out this documentation, the exact definition of the concepts above might be worked out and hopefully it may be carefully explained how, by giving the concept of input and output a more prominent position in computer language and comparing different command IO definitions, this may offer opportunities for resolution of concurrency and parallelism as well as improve security.