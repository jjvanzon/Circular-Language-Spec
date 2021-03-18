Circle Language | Construct Drafts
==================================

Pointer Assignment in Text Code
-------------------------------

An assignment is actually a combination of a __Get__ and a __Set__ call. Instead of using a call to an assignment command, you could also use a call to the __Get__ and __Set__ system commands. In object reference assignment, though, no __Get__ is executed because an object reference is the direct source of the assignment, not its object.

```
B  .  Other Related Item  .  Set  (  A  )
```

But instead, we use an assignment call (__=__):

```
B  .  Other Related Item  .  Set  =  A
```

(hypothetical notation, not a real, valid notation)

When you use an assignment symbol (__=__), you do not have to display the words __Get__ and __Set__, because it is obvious, that the right operand requires a __Get__ and the left operand requires a __Set__.

(hypothetical notation, not a real, valid notation)

```
B  .  Other Related Item  =  A
```

But there is no such thing as a general assignment. The above is an object reference object assignment, that has the symbol __o=->__. When you use the symbol __o=->__, you also do not have to mention __‘.  Other Related Item’__:

```
B  o=->  A
```

So that is the actual notation of an object reference assignment.

Knowing how to use __Get__ and __Set__ commands, instead of a single assignment call, gives you a low-level understanding of assignment. This low-level understanding is important in order to create alternative forms of assignment, as explained in the article *Alternative Assignments*.