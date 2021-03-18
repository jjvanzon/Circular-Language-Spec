Circle Language | Construct Drafts
==================================

Assignment in Text Code
-----------------------

`[ Deprecated documentation ]`

An assignment is actually a combination of a __Get__ and a __Set__ call. Instead of using a call to an assignment command, you could also use a call to the __Get__ and __Set__ system commands. 

```
B  .  Object  .  Set  (  aValue  =  A  .  Object  .  Get  .  a Value  )
```

But instead, we use an assignment call (=):

```
B  .  Object  .  Set  =  A  .  Object  .  Get
```

(hypothetical notation, not a real, valid notation)

When you use an assignment symbol (__=__), you do not have to display the words __Get__ and __Set__, because it is obvious, that the right operand requires a __Get__ and the left operand requires a __Set__.

```
B  .  Object  =  A  .  Object
```

(hypothetical notation, not a real, valid notation)

But there is no such thing as a general assignment. The above is an object assignment, that has the symbol __o=__. When you use the symbol o=, you also do not have to mention __‘.  Object’__:

```
B  o=  A
```

So that is the actual notation of an assignment.

Knowing how to use __Get__ and __Set__ commands, instead of a single assignment call, gives you a low-level understanding of assignment. This low-level understanding is important in order to create alternative forms of assignment, as explained in *Alternative Assignments*.