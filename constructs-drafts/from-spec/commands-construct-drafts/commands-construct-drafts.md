Circular Language Construct Drafts | From Spec
==============================================

Commands Construct Drafts
-------------------------

`[ Deprecated documentation ]`

__Contents__

- [Sub-Commands](#sub-commands)
- [Active and Inactive](#active-and-inactive)
- [Sub Command](#sub-command)
- [Loose Ideas](#loose-ideas)

### Sub-Commands

`<< terminology >>`  

Sub-commands `are` active commands `contained` inside a parent command. `You can` encounter them inside `any` command symbol: both active and inactive commands symbols `can` contain sub-commands. `The` sub-commands `are` *active* commands: command calls, active nested commands or active command references.

Below `is` a picture of two sub-commands inside an inactive command:

![](images/1.%20Commands%20Main%20Concepts.048.png)

`The` __Parent Command__ `is` an inactive command, because it `is` a square. In `the` diagram above, `the` __Parent Command__ `contains` two sub-commands. `The` sub-commands `are` displayed as diamond shapes. One of `the` sub-commands `is` a call, because it `has` a dashed line `going` outside `the` __Parent Command__, `tying the` sub-command to its command definition. `The` other sub-command `is` an *active nested command*, because it `might not` redirect its command definition.

Below `is` a picture of two sub-commands inside an active command:

![](images/1.%20Commands%20Main%20Concepts.049.png)

It `is the same` picture as `the` other diagram, `only now the` __Parent Command__ `is` an executable command symbol, `not` an inactive command.

### Active and Inactive

`<< terminology >>`  

A diamond executes, a square might not. A diamond is said to be active, while a square is inactive.

### Sub Command

`<< terminology >>`

A sub command is any command symbol inside another command symbol.

![](images/7.%20Commands%20Ideas.035.png)

But sometimes it may only be the diamonds that are referred to as sub commands. That’s because the execution of a command is made up of the execution of it’s contained diamonds combined.

![](images/7.%20Commands%20Ideas.036.png)

### Loose Ideas

`<< terminology >>`

It’s *procedures* that are called. When you speak of calling an *object*, you’re talking about calling a procedure of an object (or a procedure of one of its sub objects).`

`<< terminology >>`

Here I introduce basic terms in the area of executions and parameters. Here’s a quick reference list.

- Reference
- Call
- Definition
- Nested command
- Active
- Inactive
- Active nested command
- Inactive nested command
- Deeper nested command
- Sub command 
- Parameter
- Argument
- Executor
- Execution