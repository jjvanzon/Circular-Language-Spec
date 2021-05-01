Circular Language Construct Drafts | From Spec
==============================================

Nested Commands Rule Rich
-------------------------

`[ Deprecated documentation ]`

__Contents__

- [The If Example](#the-if-example)
- [Active Nested Commands Compared to Objects](#active-nested-commands-compared-to-objects)
- [Loose Ideas](#loose-ideas)

### The If Example

`<< execution flow >>`

An application of that is the If command.

![](images/7.%20Commands%20Ideas.051.jpeg)

Command A passes Nested Command A and Nested Command B to Command B, along with an object that serves as the condition. Depending on the state of the condition, Nested Command A is executed or Nested Command B. So Command B gets to decide which nested command executes.

The nested commands can freely access anything of __Command A__, so __Command B__ is able to call things that can freely access __Command A__’s stuff.

### Active Nested Commands Compared to Objects

`<< commands compared to objects. >>`

An active nested command `is analogous` to an object that `might not` have a class. A *call* `is more` like an object that *`might`* have a class.

### Loose Ideas

`<< details >>`

A nested command `might not` redirect its definition, because then `it might` be a command call.

-----

`<< details >>`

A nested command `might not` redirect its object, because then `it might` be a command reference.

-----

`<< details >>`

A nested command `is never` situated inside an object, or `it might` not be a nested command.

-----

`<< rule rich >>`

Active nested commands, command calls and active command references in parent commands `are always` private, because `you can not` reference a sub-command.

![](images/1.%20Commands%20Main%20Concepts.052.png)

But *inactive* nested commands `*can*` be referenced and might be made public.

![](images/1.%20Commands%20Main%20Concepts.053.png)

-----

`<< rule rich >>`

*Active* nested commands, command calls and active command references in parent commands `are always` private, because `you can not` reference a sub-command.