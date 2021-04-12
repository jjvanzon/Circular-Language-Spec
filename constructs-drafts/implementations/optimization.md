Encircle Language Construct Drafts | Implementations
====================================================

Optimization
------------

`[ Out of Scope ]`

__Contents__

- [Loose Ideas](#loose-ideas)
- [Procedural](#procedural)
    - [Inline](#inline)
    - [Inline Module](#inline-module)
        - [Inline Module Usage](#inline-module-usage)
        - [Inlining Modules](#inlining-modules)
    - [Inline](#inline-1)
    - [Inline](#inline-2)
        - [Inline Module](#inline-module-1)
        - [Inline Module Usage](#inline-module-usage-1)
- [Machine Code](#machine-code)
    - [Machine Oriented Optimization of Code for Speed](#machine-oriented-optimization-of-code-for-speed)
- [Possibility Optimization](#possibility-optimization)
- [Access Optimization](#access-optimization)
    - [Leave Out Access](#leave-out-access)
- [Logic optimization](#logic-optimization)
- [End State Optimization](#end-state-optimization)

### Loose Ideas

Automatic optimization, by using temporary variables for the same expression, that can't change as the procedure runs. That last element is hard to determine. For that it may also be advised to make it just a suggestion. Perhaps the temporary variable may still not be put in the source code, after the suggestion has been went along with, but the temporary storage suggestions may be declared at the beginning of the procedure.

-----

- Procedurele optimalisatie
- Machine code optimalisatie
- Data structurele optimalisatie
- Space optimalisatie
- Wiskundige optimalisatie
    - Machine Code Optimizer
    - In-coder
    - In-liner

-----

Het inklappen van procedures is procedurele optimalisatie. Het inklappen van klassen is dat ook, maar ook al space optimalisatie.
Data structurele optimalisatie is nou juist wat J Data doet. 

-----

Storing values read too much... if you’re sure it won’t change...
not including unused private functions and variables..

-----

Compile so that no J Core calls are made, but assembly calls are made directly to the procedures. This is possible, but you’d lose compatibility with future (and past) versions of the component and you can’t make use of all the benefits that interfaces have. It is a useful optimization though.

-----

Figure out the ins and outs of reference argument vs. real argument.
additional J Code optimizations can be gotten from this.

-----

- Stripping code lines (e.g. omitting checks that might never be needed)
- Optimizing assembly constructions

-----

Would J Code’s compilation optimizers take away bound these checks? Consider the ComponentList’s Remove method and see what the optimizer would have to do to find out a safety check could go.

-----

An optimization: in a procedure every argument that is on the stack might be used only once. Then you can alter the order of the arguments so that it’s the order in which they are used, so that you can pop em one by one and don’t have to read them and then pop em at the end.

If all arguments are used once and another one twice, you *might* want to push the argument on the stack twice in the order that the values are used.

-----

Another method:

If a parameter of a whole set of properties or functions is the same and requires some processing in these properties and methods on every call, perhaps the joint parameter can become a property and can be removed from the properties and methods. That way the processing only needs to be done once.

If hardly any processing is required, then it may better be an argument, because this can be more convenient to program with.

But calls are slower. Can the compiler optimize this and make choices regarding this?

-----

J Code , Optimizations  
Accumulation optimization

Sometimes you use temporary variables to simplify understanding and debugging a calculation, while you don't necessary need the temporary variables. You may just use a single accumulator. Gee. I think I won't do any optimizations in J Code, because I don't permanently compile.

JJ

-----

Optimization

At some point you’re going to want to explain what happens physically when doing some high level stuff, so you can see if this is the optimal way to do it. But I don’t care that much right now, but at some point it might have to be addressed. I would do that in J Code, Fundamental Principles, but I won’t work it out straight away. Perhaps I’d just make an article about it, where I mention that it should be studied, but I don’t want to do that straight away, and why it should be studied. How things could be non-optimal and may be optimized.

JJ

-----

Encircle,

Instruction caching. If machine instructions other than calling methods are executed repeatedly, there may be a way to cache the eventually executed machine instructions, and run that instead of with all the calls around it.

JJ

### Procedural

#### Inline

Private procedures can be compiled inline except when infinite recursion is possible.

You can also choose to compile all procedures inline. This means that when you have compiled the module you don’t have separate procedures anymore, so you can’t have separate interface members, so no interfaces and no classes. That way the whole object oriented organization collapses and you have one pile of spaghetti code. Spaghetti code that is *way* faster than the organized code. However, you can’t use the classes of the module anymore. You’d have to have the module’s source code to be able to program with it again.

#### Inline Module

A module can work faster if it doesn’t supply any procedures. The only call to the module then is to simply run it. All procedures inside the module are compiled inline then. However, it might be possible for the module to create its own memory objects, even though there aren’t any separate classes anymore. The inline module doesn’t have vector tables. It does have a table with the addresses of memory object specifications. On top of that it doesn’t have procedures, but instead one pile of spaghetti code.

##### Inline Module Usage

If you choose to compile a module inline then you have a faster module. This code cannot be called by other modules though. The only way to use the module in another module is to have the source code and compile it into it inline.

However, the inline module can call another outline module’s procedures. You can’t call an inline module’s procedure, but an inline module can call an outline module’s procedures.

-----

Think over instantiating procedures when calling one. Consider recursive calls.... they do not say that instances of procedures are made and that there are classes and instances of procedures. It however needs to be so...

-----

Arguments can be passed through the stack, but sometimes you can use registers for it. Registers are way faster.

Randel Hyde is talking about making things faster. He speaks of being any good at Assembly partly is about making code as fast as possible. And yet he admits that HLA has been written prioritizing clarity SO that he seems to abolish a technique that makes code faster.

So that seems to contradicts.

you explicitly state the order of the instructions in code then if this statement of order is omitted, the assembly generator can choose its optimal combination of logical operation variations.

-----

For assembly generating software you could make tables drawing out logically equivalent operations and combinations of operations. some equivalents may generally work faster than others. The notation of an equivalent that is slower can be replaced by the equivalent that is faster by the assembly generator.

I talked about sequences of operations that perform a single logical operation.

I might call a sequence of operation that perform a single logical operation a logical operation. The multitude of assembly equivalents I might call logical operation variations.

-----

Two logical operations may have their GENERALLY fastest way, but combining the two fastest operations may not be the fastest combination. Other combinations of equivalents of perhaps generally slower equivalents may together form a faster operation.

-----

Also: the order of logical operations may effect the speed. If you explicitly state the order of the instructions in code then if this statement of order is omitted, the assembly generator can choose its optimal combination of logical operation variations.

-----

The determination of the optimal combination of logical operation variations is done sequentially. The assembly generator looks at the sequences of logical operations. Which variation is appropriate is determined by its physical upstairs and downstairs neighbors. In case of jumps, conditional jumps and probable conditional jumps the upstairs neighbors are sometimes somewhere else than physically upstairs and sometimes they are. 

Also, the flushing of the prefetch queue affects the performance. This does not mean that for comparing optimal neighbors it does not matter what the destination of a jump statement is. There are parts of the computer system other that the CPU prefetch queue that can be optimally combined as well.

Another optimization is keeping things close together in memory.

Another optimization is inlining: avoiding jumps.

I suspect that mr. Randall Hyde thinks of a computer software system as something so arbitrary that it can only be optimized by hand. That he thinks of sequences of instructions including jump statements.                  

Sometimes, when input varies arbitrarily (within certain limits), you can't know exactly what might happen in the code in a single case. So there can not be an exact determination of what might happen in case of usage of arbitrary input. There can however be a determination of the ODDS of what might happen. The possible things that might happen is large. But these possibilities are all embedded into the code. 

When you have a sequence of instructions that take an arbitrary value and limit it between -1 and 1 then this POTENTIALLY limits the possible progressions of the code.

-----

Optimizing weighing out the odds of any possibility against each other is possible, but sometimes not enough. Of the possible things a user can do there are things that users are most likely to do and things that they are less likely to do. This requires arbitrary odds setting by the programmer. The programmer can add to the exact odds a logical odds factor which the assembly generator might take into consideration.

-----

This way, apart from anything the user can do to be most optimal as a whole, some things the user can do are more optimal than other things a user can do so that the things that the user might do most frequently are optimized the most.

-----

NOT SUMMARIZED:

When I say logical I don't mean Boolean.

There are tables for optimal assembly operation combinations. Those tables are different for different CPU's and different for any combination of computer modules. There are tables with assembly synonyms for logical operations.

-----

The table with optimal assembly operation combinations determines the fastest logical operation assembly synonym. It also determines the fastest logical operation combination. This is not tying together the fastest logical operations, because the combination of logical operations affects the speed so its the combination that determines the optimal form.

You can mess around with the order of the logical operations if a different order is faster. The programmer might say when the order of logical operations matters or not. 

Jumps in code flush the prefetch queue.

Jump statements possibly vary the sequences of logical operations arbitrarily. If no arbitrary input values are used then the program might still operate in a single way. Jumps can be omitted by tying the program up in one sequence without jumps, because the program might execute in but one way. 

-----

When there is arbitrary (user) input than jumps can become conditional for real. You can't determine how a program might run.

You can however determine the possible ways the program can run. You can make an organization of the exact odds of the possible program runs. Only the sequences that CAN execute deserve optimization.

More on it later.

-----

(PUT NEXT ICQ MESSAGE ABOVE)  
Compute the optimization tables directly from the data you base these tables from, so that new computer configurations can instantly get an optimized compilation using the configuration data.

Substituting Intel mnemonics by readable names is a good idea. Being able to use the '=' sign in place of a comma would also be a great help.

Unreal forms of instructions, forms that don't exist on the 8086, but do have a logical meaning, can have synonyms that might work. Being able to use them might help.

I think that Assembly does not deserve to be used by hand. I think I should write a low level (but higher than assembly) alternative language the compiler of which looks up the fastest way to do it in assembly, so that all the darn rules of assembly are hidden into the compiler and you shouldn't worry about how to optimize, because the compiler does it for you.

Gather up what useful things can be done with assembly instructions and use statements of useful things and let the compiler do its job.

Silly synonyms, ones silly long, should also be translated to the optimal equivalent, maybe even especially silly synonyms need to do this.

Perhaps there is a way to derive the synonym table from the behavior of every instruction.

A synonym can also be a synonym if they have different effects. Let's say the synonyms are equivalent except that one flag is undefined where in the other synonym it is set. If you won't use this flag you can replace the code by the not equal faster synonym.

Can you derive what effects of an instruction are used and which not from the code?

The eventual state of all data after an instruction is all that matters. It defines whether something is a synonym or not or an 'almost synonym' and which data is effected differently and how.

Perhaps for every instruction you can define the effect on any data. If you combine several instructions you still have a single description of the effect on the data. Comparing the effects on the data might give you synonyms. Comparing the effects on the data can also give you 'almost synonyms'.

-----

Sudden idea: to manually make the tables out of human readable text you can slide the (transparent) text over the tables and use the first thing in the text to shift it into the right spot in the tables. That thing then disappears from the text. Based on what's next in the text you can move to the appropriate spot in the tables and shift it in there.

Some instruction sequences might have the same result and are both the shortest and the fastest, but then there's the heat produced by the CPU. Some instructions may produce more heat than others. When it gets too hot then the CPU might be slowed down, so limiting the heat may be something else to keep in mind.

There might be optimization several priorities. You might want to have the fastest solution, you might to limit the heat the CPU produces, you might want the solution with the least disk access... I want to offer a general optimization which favors speed, but also other things to a certain extend, but I have to keep in mind that other optimizations might also be wished.

The objective is to benefit fully from assembly, but not to have to bother with the downsides of it. On top of that there's added clarity by an alternative naming and forgetting about different instruction forms.

If you take the assembly division instructions for instance then you see that certain forms are faster. Careful use of the alternative language I might make might make faster code(?). But most optimizations are done by the compiler. The amount of tricks and things you need to know to get the optimal result is far smaller than programming in assembly.

-----

Another idea: an 'overhoring' program is still useful.

-----

The only thing you have to do to really optimize your code would be to specify with each line or group of lines what storages matter to you or maybe even this can be exactly derived from the rest of the code. Consider for instance always overwriting data previously set by an operation before you ever used that data. Then that data is unimportant and the synonyms you can choose from are allowed to produce different results for this particular data.

##### Inlining Modules

Inline modules run faster because there aren’t any procedure calls. Procedure calls require things to be put on the stack, a round trip through vector tables and a return. Procedure data needs to be dynamically allocated.

Inline modules have their procedure data in a fixed spot in memory, though seperated from the code. Calls to procedures are not made. A lot of times what otherwise be the first line of a separate procedure would be the next line in code. Other times a jump is made to another part of the code.

Not making jump statements makes the fastest code. This has to do with the CPU’s architecture. The CPU fetches opcodes from memory while it processes the current opcode so that it has the next opcode ready straight away after processing the current instruction. Also, the CPU decodes the next instruction while it is executing the current instruction. The CPU fetches the opcodes following the current operation. The prefetches operations are called the prefetch queue. A jump invalidates the prefetch queue and the decoding of the next instruction delaying the processors execution.

#### Inline

As long as you’re going to program with the module you need the system structure retained. The procedures need to be separate, because they can be arbitrarily called. Procedures that are called through public interfaces that is, because procedures that are private can be entirely inlined.

A full inline compilation is a nice option, though. This speeds up the system considerably, but you can’t program with the modules furtherly.

If you however keep the Symbol system specifications of all the modules then you don’t really need the compiled module structure per se. You can inline all the other module’s code into the new module’s code. This increases code size, but also speed.

That way, however, there can be no distributed systems without supplying the source code with it.

J Core’s task that always remains is to manage threads and memory. Calling conventions and system structure are an optional management. A module can be compiled fully inline in case of which it cannot be programmed with unless you have the source code. A module can be compiled with preservation of the structure allowing you to program with it if you have a symbol table.

J Core supports both of these methodologies at the same time. An inline compiled module cannot be called. It can however be run and have its thread. It can even call other modules that have been compiled outline. It can even create other threads. It calls J Core every now and then to allow other threads to run, but it has no division in procedures and it can only be called in one way: run it. The module has a place in the module vector table however. The jump statement at the module vector table record goes directly to the start of the module’s code.

An inline compiled module can create objects from its own classes, because the memory layout of a classes *are* compiled with it.

#### Inline

Private procedures can be compiled inline except when infinite recursion is possible.

You can also choose to compile all procedures inline. This means that when you have compiled the module you don’t have separate procedures anymore, so you can’t have separate interface members, so no interfaces and no classes. That way the whole object oriented organization collapses and you have one pile of spaghetti code. Spaghetti code that is *way* faster than the organized code. However, you can’t use the classes of the module anymore. You’d have to have the module’s source code to be able to program with it again.


##### Inline Module

A module can work faster if it doesn’t supply any procedures. The only call to the module then is to simply run it. All procedures inside the module are compiled inline then. However, it might be possible for the module to create its own memory objects, even though there aren’t any separate classes anymore. The inline module doesn’t have vector tables. It does have a table with the  addresses of memory object specifications. On top of that it doesn’t have procedures, but instead one pile of spaghetti code.


##### Inline Module Usage

If you choose to compile a module inline then you have a faster module. This code cannot be called by other modules though. The only way to use the module in another module is to have the source code and compile it into it inline.

However, the inline module can call another outline module’s procedures. You can’t call an inline module’s procedure, but an inline module can call an outline module’s procedures.

-----

I’ve gone on about the assembly side of it, now the easier interface.

<  
Even though it seems that all sorts of stuff can happen at the same time and all sorts of objects and code can work together in an incomprehensible turn-taking. This is not true. One thing happens at a time. One thread runs at a time, one procedure runs at a time, one data structure is used at a time, one module is running at a time, one class is running at a time.  
\>

The only way you want to work with J Core is to design modules that run under J Core. It is about is designing modules. Module design is programming so it continues in J Code. In J Code you can design modules in a simple matter. They can be compiled to machine code modules that can run under J Core.

So the easy way is not J Core. J Core is not one of those modules that has easy interfaces because at a level this low there are not modules yet.

Module design continues in J Code.

J Hardware requires you to design modules writing assembly language J Core procedures.

For J Data you can write the procedures in a higher level language, which nonetheless translates to assembly.

I need to make a higher level language that does not perform tasks of the modules, but provides just the neccesary to specify automation between the modules.

### Machine Code

Also: data should not be inline of the code. Jumping over data takes time, because it invalidates the prefetch queue and the decoding of the next instruction.

If jumps. Loops. Blabla jumps.

Shorter instructions also boost the performace of the prefetch queue.

Using immediate data is fastest, Using registers is fast, using aligned memory is slower, using unaligned memory is even slower. And it’s not true. Shorter instructions use up less ‘power’ of the prefetch queue, the bus is used less and can fetch memory, maybe instructions. The shorter the faster.

The pipelining in a CPU also requires you to limit jumps in the code, because when you make a jump, the pipeline gets flushed.

Gee, what could make a processor fast you can totally break to pieces with a bad compilation/assembly program.

I am still convinced that it is possible to make a compiler perform extreme optimizations that make a program more optimized by the compiler than you could ever do by hand in a reasonable amount of time.

Read over the 886, 8286, etc. of ‘Art of Assembly’, and sum up optimization tips.

The Art of Assembly does not cover operating system instructions extensively. I might look for an additional text for coverage on these instructions.

The only reason I’m reading ‘The Art of Assembly’ is to learn how you manage the modules of the machine. To have a complete overview of in what ways the machine is controlled. I’m not learning it to learn how to write a good algorithm or to learn about a flag you’ll never use. Optimization in terms of CPU time saving is interesting, but I need to focus on what I need to control in the machine.

Art of Assembly says that segment addresses don’t resolve to a memory location arithmetically. A segment address is a location in a table specifying the memory location of the address. Art of Assembly also says that it is not up to the programmer, but up to the operating system to handle this table.

#### Machine Oriented Optimization of Code for Speed

I see that knowledge of the computer adds a lot of rules to how to optimize assembly code. I was worried that this meant that J Core could not become simple and could not set simple rules, because it should embed all these optimization rules.

A while later I figured out that this wasn’t true. The instruction set that is most of the Assembly language is a clear set of instructions to use with which you can make clear code. You don’t need to be concerned with the machine to make this clear code and with good architecture, it might operate at warp speed for most purposes. It is only when you WANT to optimize for speed that you need to understand the machine. The same should go for J Core. The programming model provides a simple and clear way to work. It is only when you want to optimize things that you should be concerned with the machine.

Assembly sets this challenge: the stuff you program has effects on the speed that are totally obscure when you just understand the code. The code is a complete cloud over what effects it has on the speed. If Intel does it, then J Core can do this: the stuff you program has effects on the speed that are totally obscure when you just understand the code. The code is a complete cloud over wht effects it has on the speed.

So a message from me to me: ‘Don’t worry: design a wonderful programming model and forget about the speed implications. Everyone makes it a difficult to do machine oriented speed optimizations. I can’t correct this and I am not going to.’

An example is accessing memory: accessing memory locations near each other is faster. You can access memory locations far apart from each other all the time. A J Core programmer can too. A J Core programmer can work with unbounded consecutive stretches of memory. If he uses it in a certain way he might gain tremendous speed. He can’t be aware of this just looking at the programming model, just like in assembly.

Note: when the code is clear, everything is faster. Weird time consuming mistakes are made when code is not clear. The code might be so unclear that the programmer doesn’t even know he made a mistake at all.

-----

In regular programming languages all parameter values are put on the stack. Sigma, however, decides on its own when or when not to use the stack and optimizes the use of resources.

### Possibility Optimization

(Lines that could happen: something for another section discussing possibilities, something that also has to do with a kind of code optimization.)

### Access Optimization

The object oriented structure of the system is retained in the compiled code. This is done *only* to be able to __program__ orderly with them. 

However you don’t have the names of modules, classes and other elements. You need a symbol tables to tie names to the numbers that elements of the system have. This symbol table is only used for software development.

#### Leave Out Access

To make a system perform faster you can take away the object oriented structure. With that you gain that you don’t have to put directions on the stack and make jump statements to get to the procedure.

Another way to optimize code for speed is to inline procedures. Preferably all procedures if there isn’t a potentially infinite recurrence. (You could inline a maximum of recurrences.)

### Logic optimization

Sometimes code is executed that can be done simpler. You can recognize constructions that can be made simpler for the computer and replace them by the simpler constructions.

### End State Optimization

If a stretch of code results in nothing other than a configuration of objects and data, then you can store the end result of it in an end state. When that code is normally called, instead, the end state is loaded immediately. That saves a lot of time. This can only be done in cases where the end result of a chunk of code isn’t variable. If it is only a little variable, you could play with this optimization a little and store end states of the invariable things and calculate the variable part *or* store multiple partial end states, one for each variation.

In development, this optimization is not that much wanted, because the code changes there all the time. After compilation the code doesn’t change and therefore such an optimization is useful.