Encircle Language Construct Drafts | Text Code
============================================

Assignment in Text Code
-----------------------

`[ Deprecated documentation ]`

### Introduction to Assignment in Text Code

The articles in this folder came out of the discontinued article group *Assignment*. It partly covered a textual assignment notation. Working out text code notations currently has a very low priority. But the unfinished text is preserved here anyway.

### Assignment in Text Code

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

### Value Assignment in Text Code

If you must have a character symbol for a value assignment, that distinguishes it from the other assignment types, it is the following symbol:

```
v=
```

This symbol is the identifier for value assignment. The letter __v__ stands for value.

### Object Assignment in Text Code

If you must have a character symbol for an object assignment, that distinguishes it from the other assignment types, it is the following symbol:

```
o=
```

This symbol is the identifier for object assignment. The letter __o__ stands for *object*.

### Class Assignment in Text Code

In text code, the symbol for class assignment is the following:

```
c=
```

The letter __c__ stands for class.

### Interface Assignment in Text Code

If you must have a character symbol for a class assignment, that distinguishes it from the other assignment types, it is the following symbol:

    i=

This symbol is the identifier for interface assignment. The letter __i__ stands for *interface*.

### Pointer Assignment in Text Code

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

### Object Pointer Assignment in Text Code

The textual symbol for an object reference object assignment is:

```
o=->
```

It can be pronounced ‘object is pointer to’.  
In an actual text code line it would look like this:

```
A  o=->  B
```

It can be pronounced ‘A object is pointer to B’.

### Class Pointer Assignment in Text Code

The textual symbol for an object reference class assignment is:

```
c=->
```

It can be pronounced ‘class is pointer to’.

In an actual text code line it would look like this:

```
A  c=->  B
```

It can be pronounced ‘A class is pointer to B’.

### Interface Pointer Assignment in Text Code

The textual symbol for an interface pointer assignment is:

    i=->

It can be pronounced ‘interface is pointer to’.  
In an actual text code line it would look like this:

    A  i=->  B

It can be pronounced ‘A interface is pointer to B’.