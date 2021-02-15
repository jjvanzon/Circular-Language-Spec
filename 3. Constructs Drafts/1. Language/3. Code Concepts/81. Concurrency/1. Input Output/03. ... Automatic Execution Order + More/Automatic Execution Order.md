Automatic Execution Order
=========================

#### Newer Concept

± 2008-08

The first thought was, that the execution order of sub-commands could be automatically determined, based connection between parameters and objects, and whether parameter is __In__, __Out__ or __Thru__ and __By Reference__, __By Value__ or __Object Out__. But this is not true.

##### Parameters tied together

When the parameters of two commands are directly tied together, it is not hard to determine the order in which to execute the commands. Parameters can only be directly tied together to eachother in a limited number of ways, so that makes it quite easy. One parameters is output, that is used as input for another command. A consultation of a command requires the command to run. The sub-commands have a direct dependency on eachother and a command requires its dependencies to run first.

< Pictures >

##### Parameters tied to objects

However, parameters can also be tied to sub-objects of the parent command.

< Picture >

If parameters of different commands are tied to the same object, and they are all input parameters, then the execution order of the sub-commands does not matter.

But if one of them is an output parameter, then it is a question whether the input parameter wants to use the changed value or the original value of the object. So in that case the order should be manually indicated.

< Pictures >

##### Outcome dependency

If a reading sub-command is dependent on the outcome of a writing sub-command, then you have to manually indicate the execution order, so that the writing command runs before the reading command. The indication of execution order in that case is sort of like indicating an *outcome* dependency. If you want the original value, you can indicate the execution order, drawing out, that the reading command should run first, which is like a negative statement of outcome dependency.

*Outcome dependency is exchangable with execution order.*

Multiple things may be dependent on the outcome of a command, which means that the writing command might have multiple next-command indications. That’s right. The dependencies could all run in parallel. From this dependency can be derived, that some things can be run in parallel, and some things have to run in a serial order.

##### Accessing parameters’ sub-objects

An object inside the parent command has sub-objects. From the parameter you can’t tell whether the object itself is written or an object 10 levels deep is written. 

< Picture >

With reference parameters, changes and consults can be at any depth. Any object indirectly links to any other object in the world, so passing an object as a parameter makes basically any other object around the world accessible to the command. So basically anything could be changed by a command.

That used to be one argument in the claim, that automatic execution order is impossible, but help is on the way…

##### Specific data unknown

Another argument against automatic execution order is, that from a command *definition*, you still don’t know what specific data will be processed. This is because the parameters of the command are not yet filled in. A command definition does not have any objects assigned to the parameters yet. So it is not clear what exact data will be processed. Command definitions only indicate what *types* of object can be connected to the command, but not what *specific* objects are connected to the command. You only know what specific data is processed when a command has specific object connections. A command only has specific object connections when it actually *runs*. But even though, what a command will change seems pretty volatile, there are possibilities for predictions about what a command will change. Things considering eachother’s changings once a command actually runs, is a concurrency topic, that will be covered in *Concurrency Resolution*, but not in *Automatic Execution Order*.

##### Parameters & IO

< Better name: Command IO >

Input and output are not the parameters, but what specifically is read or written *from* the parameters. The input and output of a command are not the parameters passed to it, but any piece of data *used* by the command. You just can’t see from the parameter itself exactly what is changed.

In theory there's no telling what a command may read or write, but in practice the amount of things read and written are limited. You can list out what a command reads and changes.

Here follows a textual definition of a parameter, and of the input and output; three entirely different things.

Parameter:

```
Reference Thru  Document  As  Graphics  .  Document
```

Input:

```
Document  .  Points  .  Item  [  \*  ]  .  X
Document  .  Points  .  Item  [  \*  ]  .  Y
```

Output:

```
Document  .  Lines  .  Item  [  0  ..  \*  ]  .  Point A   .  X
Document  .  Lines  .  Item  [  0  ..  \*  ]  .  Point A   .  Y
Document  .  Lines  .  Item  [  0  ..  \*  ]  .  Point B   .  X
Document  .  Lines  .  Item  [  0  ..  \*  ]  .  Point B   .  Y
```

There must be a limitation in the expression of what is accessed. Perhaps if only __Document__'s existance is being checked, this might be indicated. But to a certain extend the expression of what exactly is accessed should be limited. Not the entire inner workings of a command are visible from its input and output. For instance, in the input / output expression you will *not* be seeing what *sub-commands* are called.

What is written and read by a command are actually pre- and post-conditions of the command. 

Only when you are editing a command, the pre- and postconditions of the command have to be determined. The pre- and postcoditions do not change once you’ve published, versioned, the command. Once you are done designing, the input-output configuration will be stored within the command. Remember that the *structural* input and output is different from what a command will actually read and change.

##### Compared IO

In a command definition you only know which *structure elements* a command accesses, and not yet what specific objects. But from the structure elements used by the command, you can already see whether commands *might* be in eachother's way. This opens up possibilities to exclude or confirm, that commands might be in eachother’s way. When parameters of different reading and writing commands are tied to the same object reference and they are accessing the exact same structure elements, you can be pretty sure they will be in eachother’s way. But when you are accessing different object references, you can’t be sure whether accessing *different* object references means accessing *different* objects. The two object references may be referring to the same object all the same. Even though automatic containment of objects would indicate which object references represent the same object, this can not be seen in the diagram expression of a command *definition*, because objects are not filled in yet.

And then you have to look if there is any overlap in what one command writes and the other commands reads. The overlap might prove a possible read-write dependency. The order of the two commands would affect the outcome, so that might prove that you *have to* indicate an outcome dependency or a negative statement of outcome dependency. Or when a *different* object reference of the same class is consulted, that you *might* need to indicate outcome dependency.

When you don’t consider volatile concurrency, then when sub-commands follow the same structure paths starting at the same object, you are pretty sure, when the same object will be accessed. But in a volatile concurrency situation you are never entirely sure, unless you lock the data. But those are concurrency issues, which are for later.

__Command A__ can only be outcome-dependent on __Command B__, when some of __Command B__’s output is __Command A__’s input. Input and output of a command are not the parameters, but what is read or written *from* the parameters. For command *definitions*, this means, that outcome dependency can only be indicated for sub-commands that have any possible overlap in input-output.

Building up the outcome-dependency structure of a command is only done in the design stage of the command. The outcome-dependency does not change once you’ve published, versioned, a command with sub-commands. Once you are done designing, the outcome-dependency configuration will be stored within the command.

##### IO definition used for security

This explicit statement of what exactly is accessed, is a great tool for security. A user can actually *see* what a command is changing. In security you have to beware how the command might be faking it.

##### Sub-commands

It is quite easy to see what is directly used by a command, but the command also has sub-commands, that also use certain data. The parent command passes data to the sub-commands.  

What is used by a command is a union of everything directly changed by the command and everything changed by the sub-commands and their sub-commands and so on. And what if the command call structure is recursive? This may impose even more difficulty. It may be a lot of work to gather up everything a command might change, including what their sub-commands might change, and then gather up anything a command might read, and what its sub-command might read.

But the sub-commands already store what exactly they read and write, including what they read and write from *their* sub-commands, so that makes it a lot easier.

##### Conclusions

In the end, automatic execution order is all about manually indicating outcome dependency between commands, instead of *explicitly* defining the execution order. Even connecting parameters together directly is indicating an *outcome dependency*.

Execution order can not be derived, without manually specifying the outcome dependency of sub-commands, because a machine does not know whether you want the altered of unaltered version of an object. But many ideas have been proposed to automate the detection whether commands can be in eachother’s way at all. Outcome dependency can only be indicated for commands, that *could* be in eachother’s way. Commands, that can’t be in eachother’s way can be run in parallel or in an arbitrary order.

That is what automatic execution order is.

##### Use later

Sub-commands indirectly relate to eachother through mutual references to the same object, and what they read or write from that object.

It can be determined, that part of the sub-commands can run independently. If they don’t consult the same data, they can run totally concurrently. Only if things consult the same data, and there is at least one reference that writes to it, then an order must be determined.

###### Multiple parameters

< Things become more complex when commands with multiple parameters start relating to eachother. >

< 2008-07-06 When commands have multiple parameters tied together complexly to other parameters, you have to resolve this in an execution order. >

< By the way: if you use multiple output parameters of a command, how does the consult of the *two* parameters result in a *single* run?> 

##### Apart from direct connection between parameters

Next to making sub-command directly dependent on eachother by directly tying them together, input output can also be between a sub-commands parameter and a sub-object of the parent command. This does not create a direct dependency between sub-commands, but it does create an indirect dependency.

![](images/Automatic%20Execution%20Order.001.png)

The parameter of command __A__ is a __Value Out__ parameter that writes to object __O__. The parameter of command __B__ is a __Reference Out__ parameter that connects to object __O__. The parameters of command __A__ and command __B__ are not directly tied to eachother, but they do indirectly related to eachother. This will be further elaborated in *Automatic Execution Order*.

##### Other Ideas

The cloning depth may be dependent on the parameter usage inside the command. 

#### Older Ideas

##### Ideas

If you don’t indicate the order in which to execute the commands, then they will execute in an arbitrary order. Sometimes this is acceptable from a functional point of view.

The order of a procedure can also be *automatically* determined by *input / output dependency*. A command, called inside a procedure, can take input, that is the output of another command. Then the other command needs to execute first, in order to pass its output on to the next command. This is called the *automatic execution order* principle, part of the flat & structured interchange principles. 

The hope that comes with automatic execution order determined by input / output dependency is to not have to define any normal order, because if parts of a procedure have not input / ouput dependency, then those parts can always execute in any arbitrary order.

##### Automatic Execution Order

Apart from auto-encapsulation, 

auto-ordering of procedure steps can also be done,

based on if all the conditions for executing a procedure step are there. If multiple procedure steps can be done in one blow, you could fork out in multiple procedure steps being executed at the same time, virtually. Logically they can be executed at the same time, but in practice, it's best for the computer to just execute them one by one in an arbitrary order. It is imposed that when conditions are met for a procedure step to be executed, then it is done. And also, a procedure step is not executed sooner than required. For instance, a variable needs only to be declared just before first taking it in use. Perhaps variable declaration has no place in JJ Code anymore, 

but it is a clear example of imposed procedural order, that

I like to work with now.

It's a tough concept, that needs further brainstorming, but it might be an idea. Not only do you not need to explicitly control the encapsulation structure yourself. You also do not need to explicitly control the procedure order yourself. It's a hypothetical concept.

##### Automatic Execution Order & Concurrency

Here follows a bunch of brainstorm texts, made when trying to solve concurrency problems with automatic execution order.

\-----

Maybe there's a mathematically defined point at which you can be sure things are logically correct...
Maybe there a way a system can determine,
what needs to be done in a single blow...
maybe you can mathematically determine,
that two parts of a procedure are independent of eachother, so could not be in eachother's way.
Perhaps not, because everything is a big method, in a way. What tells me, that something read in one part of the method,
is not expected to be exactly the same half an hour later in the method?

Perhaps in automatic execution order you can
see which things have to go parallel,
and which things have to go serially.
Perhaps that way, multiple threads running at the same time, can be interweaved, by tying all the object relations (including relations between procedure calls) together, and figuring out which things 
can go simultaneous and which things have to be done one by one.
I'm not sure. I should know more about automatic execution order for that.

The locking and transaction thing assumes that you need to understand the earthly logic behind what you are trying to do,
in order to know what locking scheme you need to apply, and what should become a separate transaction.
My gut feeling says, that you can mathematically derive what locking scheme should be applied, and what should become a separate transaction. And my gut feeling says, that this can be done by means of symbol diagrams, in which execution order is automatically determined.

In automatic execution order, something intended to run sequentially can be turned into points a which sequentiality is required, and points at which some things can run in parallel. 

I think I can do the same thing the other way around:

some things intended to run in parallel, can be converted into points that require sequality, and points at which parallel execution is allowed. I just don't know how that's going to look yet.

I have to have a clear view on the atoms of work there are, independant of the earthly meaning of the work. And how those atoms of work can influence eachother, independant of the early meaning
of them.

It's all just hunches for now.

If methods are tied to the same data...
a relational database doesn't know about that. It can be statements specified in a procedural programming environment, that the database is not aware of at all.

It just gets confronted with multiple methods that want to run when they want to run. My own system might know they can be in eachother's way, because the system sees both the data and the methods, and the way they are tied together. The data is aware of the methods that influence them, the methods and the data form a single construction of things refering to one another. A single diagram in symbol. Automatic execution order may determine which things have to go sequentially and which things need to go parallely.
I just have to list out all the different possibilities for things getting in eachother's way.
I just think that blending the procedures and objects into a single construction just gives you an opportunity to mathematically solve the equation and automatically determine what can execute concurrently and what  can not, and for how long, or up until which point.

\-----

Perhaps methods only interweave at points at which a resource is accessed by multiple things at the same time. The methods' diagram contents may be thrown in one method, automatic execution order applied, and the combined method is executed, where some things can be done

in parallel and some things must be executed serial.

Perhaps, everything's one big method in a way, you can flatten it out, and restructure it with automatic execution order... or something.

\-----

Perhaps seriality is expressed by one step calling the next, only then you get too much of a recursive structure.
Perhaps there should be a kind of call, that doesn't return,
but abandons the caller.
Perhaps when you do automatic execution order, you should consider the four

problems with concurrency identified by the SQL Server 2000 documentation.
And if they are solved by automatic execution order.

Perhaps in the SQL Server 2005 documentation they spotted more problems.
Perhaps in the SQL Server 2008 documentation they spotted even more problems.
Perhaps they didn't spot more problems, perhaps these are just it.

The four problems, I can look at and just say: 'this problem only happens, when...'
or: 'this only becomes a problem, when...'

Execution order is fixed in normal programming languages, because it is text, in which an order is a fact you cannot go around. A diagram does not have a specific order, so the order may be determined based on the non-sequential correlation between individual elements.
Perhaps this can prevent locking and waiting, and just make a single sequence out of it instead of one thing waiting on another.

#### Look at the article Parameter Order…

#### From the original Symbol documentation

##### Execution Order

Execution order is (part) determined by dependency: a procedure that renders a result used in another procedure is executed first.

Using the dependency rules, argument reference notation (the implicit one) suggests the following execution order:

![](images/Automatic%20Execution%20Order.002.png)

However, translating it to the explicit reference argument notation:

![](images/Automatic%20Execution%20Order.003.png)

The dependency looks must different. After the translation to this, execution order is determined fully by parent-child relations: parents execute first, then children.

![](images/Automatic%20Execution%20Order.004.png)

In this implicit notation __A__ *seems* to be dependent of __B__, but in fact __B__ is dependent of __A__, because it uses it as a reference argument.

###### Custom Order

Apart from execution order imposed by dependency, the programmer can set a custom execution order, which may not conflict with dependency (parent-child) order, but should only be applied where execution order is undetermined by dependency. Actual parent child relations impose execution order. Only the execution order of *actual* siblings can be custom set (not siblings in implicit or abstract notations). The order is denoted with numerical ordinals.

![](images/Automatic%20Execution%20Order.005.png)

Custom execution can be significant for instance for value transformations to happen in the right order.

###### Brainstorm

- Seeming randomly referencing diamond members.

argument reference is not the same as an implicit call (referencing a square member).

####### 1

Als een assignment een waarde uit de ene procedure (A) Get en een waarde uit een andere procedure (B) Set, dan is de executie van B afhankelijk van de executie van A. Daardoor wordt de executievolgorde bepaald. Als het ene afhankelijk is van de executie van et andere en het andere afhankelijk van de executie van het ene, dan is er een bepaald soort circularity ontstaan waar niks mee kan. De computer kan slechts de dingen een voor een uitvoeren. De compiler kapt er gewoon mee. 

####### 2

Randomly referencing call members. I thought you could only do it just before and just after

####### 3

HMMM… in sommige gevallen execute de diamond misschien meerdere keren zonder unconditional jumps en zonder z’n parent meerdere keren te executen… dat moet dan wel een specifieke uitzonderlijke situatie zijn die precies te definiëren is>

Goeie zin?:

Call finished: references to diamond contents anulled.

####### Execution Basics or Execution Order

So diamonds represent executions and calls, but not necessarily indivual executions. Multiple diamonds can represent the same execution. Actuall: only the same execution at one time, because you can execute the diamond multiple times, only no two executions at the same time.

##### Other

###### Execution order

clockwise starting at the top one or 
like reading: left to right, top to bottom or 
tied together, except for the first and last ones

Sometimes it doesn’t matter in which order something takes place, in case of which both symbols get the same execution order ordinal. Symbols are tied together parallelly instead of serially then or positioned ‘parallely’ over the clock’s arrow.


2004,

In case of equal ordinals the symbols ARE executed but the order of execution is irrelevant. Even when the order of execution is irrelevant the ordinal is the only pure way to control the positioning of the symbols.

JJ