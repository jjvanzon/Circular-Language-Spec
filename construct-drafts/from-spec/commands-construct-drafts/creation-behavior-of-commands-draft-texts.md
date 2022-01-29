Construct Drafts | From Spec | Creation Behavior of Commands | Draft Texts
==========================================================================

`[ Deprecated documentation ]`

__Contents__

- [Loose Ideas](#loose-ideas)
    - [The Diamond Executor Can Access Members Only Just before and Just After the Execution](#the-diamond-executor-can-access-members-only-just-before-and-just-after-the-execution)
    - [Brainstorm](#brainstorm)
    - [Prolog and Epilog](#prolog-and-epilog)
    - [Writing Arguments](#writing-arguments)
    - [Forming New Subdivision](#forming-new-subdivision)
        - [Old Subdivision](#old-subdivision)
        - [New Subdivision](#new-subdivision)
    - [New](#new)
    - [Created Arguments](#created-arguments)
        - [Doing Things with a Command’s Members](#doing-things-with-a-commands-members)
    - [More Ideas](#more-ideas)

## Loose Ideas

### The Diamond Executor Can Access Members Only Just before and Just After the Execution

If the diamond executor accesses something of a diamond, it’ll only access it just before and just after the call.

In fact the diamond executor might only write members just before the call and might only read members just after the call.

### Brainstorm

Using arguments always requires assignment.

Just before execution you’ll write arguments. Just after execution, you’ll read arguments. Those are the main two occasions you’ll access arguments.

### Prolog and Epilog

Writing and reading arguments require things to be done just before and right after the execution. Things that might be done just before execution might be called the *prolog* of the execution. Things that might be done just after the execution might be called the *epilog*.

Writing arguments may take place in the prolog and reading arguments may take place in the epilog.

### Writing Arguments

Writing an argument before execution means to set its state or line target.

### Forming New Subdivision

These seem fragments of an attempt to re-subdivide topics formerly inside the original Symbol documentation from 2004.

#### Old Subdivision

- Writing arguments before the call:
    - Assignment: lines or state
    - Creation
    - Possibly call members of an argument
- Reading parameters before the call:
    - Reading line targets (direct, final or intermediate)
    - Reading state
- Writing a parameter means setting a line or reading state from an object and writing it to a parameter
- Reading a parameter means writing it to another object

-----

- Diamond member access:
    - The caller of a diamond accesses members just before the call and just after
    - The callees of a diamond can access the caller's members if given references to them

#### New Subdivision

- Parameter Access
    - Writing parameters before execution
        - Assignment: lines or state
        - Creation
        - Possibly call members of an argument
    - Reading parameters after execution
        - Reading line targets (direct, final or intermediate)
        - Reading state
    - Access during execution
        - By owner
        - By child executions (~ is this the proper place for this?)
            - The callees of a diamond can access the caller's members if given references to them

### New

- Prolog and epilog
- Parameter writes in prolog
- Parameter reads (/consults) in epilog 

- Paradox: Assignments of parameters suggests reading parameters. However, these assignments do take place in the prolog, even though they suggest reads. Assignments are different that way.

### Created Arguments

`<< implementations >>`

A command can decide if an argument is a created object or not. If it is a created object, then the object is created in the prolog, even before writing arguments. The argument object is created, then it is written, then the command executes.

Arguments as such are created objects directly contained by the command. They shouldn’t have lines. 

In the epilog, first arguments are read before the created arguments are destroyed. The command only destroys objects it directly contains.

#### Doing Things with a Command’s Members

`<< interpretation >>`

Seeming randomly referencing diamond members.

It may be an idea that parameter references might all represent assignment calls. In contrast to that another interpretation might be that: a command object might still exist after it is executed. (Output) parameters might still be referenced freely. For instance when a command creates a new object and returns it there may still be pointers to the command's returned object.

### More Ideas

2004,

Generating the stack operations preceding and concluding function calls is called prolog and epilog code in C

JJ

-----

- Writing parameters before execution
    - Assignment: lines or state
    - Creation
    - Possibly call members of an argument
- Reading parameters after execution
    - Reading line targets (direct, final or intermediate)
    - Reading state

-----

`<< terminology >>`

- The terms prolog and epilog.