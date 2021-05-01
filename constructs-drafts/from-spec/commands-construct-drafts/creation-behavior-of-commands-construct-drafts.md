Circular Language Construct Drafts | From Spec
==============================================

Creation Behavior of Commands | Construct Drafts
------------------------------------------------

`[ Deprecated documentation ]`

__Contents__

- [Loose Ideas](#loose-ideas)
    - [The Diamond Executor Can Access Members Only Just before and Just After the Execution](#the-diamond-executor-can-access-members-only-just-before-and-just-after-the-execution)
    - [Brainstorm](#brainstorm)
    - [Prolog and Epilog](#prolog-and-epilog)
    - [Writing Arguments](#writing-arguments)
    - [Summary of Old Subdivision](#summary-of-old-subdivision)
    - [New Subdivision](#new-subdivision)
    - [New](#new)
    - [More Ideas](#more-ideas)

### Loose Ideas

#### The Diamond Executor Can Access Members Only Just before and Just After the Execution

If the diamond executor accesses something of a diamond, it’ll only access it just before and just after the call.

In fact the diamond executor might only write members just before the call and might only read members just after the call.

#### Brainstorm

Using arguments always requires assignment.

Just before execution you’ll write arguments. Just after execution, you’ll read arguments. Those are the main two occasions you’ll access arguments.

#### Prolog and Epilog

Writing and reading arguments require things to be done just before and right after the execution. Things that might be done just before execution might be called the *prolog* of the execution. Things that might be done just after the execution might be called the *epilog*.

Writing arguments may take place in the prolog and reading arguments may take place in the epilog.

#### Writing Arguments

Writing an argument before execution means to set its state or line target.

#### Summary of Old Subdivision

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

#### New

- Prolog and epilog
- Parameter writes in prolog
- Parameter reads (/consults) in epilog 

- Paradox: Assignments of parameters suggests reading parameters. However, these assignments do take place in the prolog, even though they suggest reads. Assignments are different that way.

#### More Ideas

2004,

Generating the stack operations preceding and concluding function calls is called prolog and epilog code in C

JJ