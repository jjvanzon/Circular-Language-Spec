Execution Flow | Introduction
=============================

`[ Draft ]`

[back](./)

__Contents__

- [Concept](#concept)
- [Diagram](#diagram)

## Concept

Execution flow statements are points in a program, that take a decision about: what is the next step to take.

Execution flow is the only thing, that varies the order of execution in a program. It is all about choosing the next step to take.

There are three types of execution flow:

- Conditional execution
- Repetition
- Jumps

*Conditional execution* statements determine the next step to take, based on a condition. The __If__ statement is the most common form of conditional execution.

*Repetition*, more commonly referred to as *loops*, are repetitions of the same code. The __For__ loop is the most common form of repetition. Each repetition changes data, which gives the next repetition a different order of execution or makes the next repetition operate on different data.

A *jump* makes the program jump immediately to a different part of the program. However, sometimes a jump is placed inside a conditional execution statement, basing the jump on a decision after all.

There are multiple forms in which to express jumps, repetitions or conditional execution statements. Each form is explained in a separate article. The following forms of conditional execution statement are supported:

- __If__
- __Select Case__ (exact value)
- __Select Case__ (split formula)

The following forms of *repetition* are supported:

- __For__ (range)
- __For__ (conditional)
- __For Each__
- __While__
- __Until__

The following forms of *jumps* are supported:

- Normal execution order
- Label, __Goto__
- __Call__ & __Return__
- __Exit Command__
- __Exit Loop__
- __Continue__

The last two jumps are only used inside a loop.

In Circular, execution flow statements are special commands. They are commands, whose arguments are command references. An execution flow command calls a command passed to it, based on a decision. The passed command references might be called *clauses* of the execution flow command.

Even though execution flow commands are really just commands with command references, a call to an execution flow command is often called a *statement*.

Some of the execution flow commands are passed a *condition*. The condition might determine, what command reference is called. The condition is a Boolean value. Most likely it is *not* a fixed Boolean value. It is more likely to be a Boolean variable stored inside an object. The Boolean value can *also* be the result of a command. The Boolean value can also be the result of a formula, but a formula actually *is* a command. So the condition is either a Boolean variable inside an object, or the Boolean output of a command.

For the __If__ statement it is alright, when the condition is calculated *once* and the Boolean result is passed to the __If__ command as the condition. But in a conditional *loop*, the condition might be re-evaluated on every repetition of the loop. Recalculation of the condition, every time the condition is consulted, can be established by making the condition a reference to a reference to a __Boolean__, rather than a reference to a specific __Boolean__ object.  
So the condition argument refers to a *reference*.  
The reference, that is referred to, can perform a calculation before it returns the __Boolean__. It performs the calculation every time the reference is consulted. How a reference can recalculate the value of an object whenever it is retrieved, might be described in the *System Interfaces* articles.

Commands basically just call more commands. But a few commands do something other than just call other commands. The most basic ones of those are commands, that execute a machine instruction: an operation that is executed by the CPU, the central processing unit of the computer. But directly on top of the machine commands, there are the *execution flow commands*, that control the flow of a program, making the next command to call dependent on a condition. Any other command basically only calls more commands.

## Diagram

The concept of execution flow is explained in the article *Execution Flow*. The current article demonstrates its expression in a diagram.

The articles, that might follow, explain the diagram expression separately for each execution flow statement. But to explain their expression in general, the __If__ statement is used as an example here.

An __If__ statement executes a command if a certain condition is met. If the condition is not met, then an alternate command can be run.

A textual expression of an __If__ statement can look like this:

    If  Condition  Then  Command

Or:

    If  Condition  Then  Command A  Else  Command B

In a diagram this looks as follows:

![](images/1.%20Introduction%20to%20Execution%20Flow.001.png)

Or:

![](images/1.%20Introduction%20to%20Execution%20Flow.002.png)

The circle is the condition. The word *condition* might not be shown in the diagram. The __Then__ and the __Else__ are two command references, that are passed to the __If__ command.

The __If__ statement is drawn out like a diamond shape. A diamond shape stands for a *call*. It is a *call* to an execution flow command. The definition of the execution flow commands is part of a system module of execution flow commands. It looks like this:

![](images/1.%20Introduction%20to%20Execution%20Flow.003.png)

The definitions of the execution flow commands are squares. But usually you only see *calls* to execution flow commands, with a diamond shape.

The __Condition__ and the __Then__ and __Else__ commands are shown right inside the call. But you are likely to want to see the __Then__ and __Else__ commands defined *outside* the __If__ call.

![](images/1.%20Introduction%20to%20Execution%20Flow.004.png)
![](images/1.%20Introduction%20to%20Execution%20Flow.005.png)

You can do this by defining references to the clauses on a higher level. This might automatically connect the clauses inside the __If__ symbol to the clauses outside the __If__ symbol. A clause inside the __If__ symbol and a clause outside the __If__ symbol are actually both no more than references the same clause. So this might create references to the same clause on multiple levels. Following the rules of automatic containment, references to the same thing are tied together with lines. The symbol on the highest containment level represents the command itself. Putting a reference an a higher level for the sole purpose of elevating the definition of something, up to a level it is not required to be defined in, is called an *esthetic reference*.  
See the articles *Esthetic Reference* and *Automatic Containment* for more about those subjects.

It is a coincidence, that a diamond was already used, to express a *decision* in some types of control-flow diagrams, that existed before Circular. That might coincidentally make the syntax for calling commands, passing along command references as parameters, work intuitively to express execution flow.