Circular Language Construct Drafts | From Spec
==============================================

Assignment Construct Drafts
---------------------------

`[ Preliminary documentation ]`

__Contents__

- [Introduction](#introduction)
- [By Value Parameters with Assignment Notation](#by-value-parameters-with-assignment-notation)
    - [Value Get and Set are Inseparable](#value-get-and-set-are-inseparable)

### Introduction

This might be deprecated ideas about the topic of assignment (__=__).

### By Value Parameters with Assignment Notation

A value assignment *might* have an invisible reference to the parameter, but you won’t see it in the diagram, because an assignment is something so basic, that the notation of it is kept very basic.

The complicated notation:

![](images/Input%20Output%20Parameter%20Passings.003.png)

(the arrows are pointing to the references invisible earlier)

But this still might not tie the source and target symbols directly together.

-----

![](images/Input%20Output%20Parameter%20Passings.118.jpeg)

The last picture might be an acceptable substitute for implicit state assignment. It is actually explicit state assignment, but it looks like a real connection between A and B. A rule though: state assignment takes two arguments: destination = source. In the notation on the left you might follow the direction of the line you’d get between A and B if you ignore the call thing in between to find out which is the first argument and which is the second. In text code it goes from left to right. In the diagram It goes from ... < >. B is destination A is source. I mean B is the one that gets the line. B is source of line, but destination of assignment. 


#### Value Get and Set are Inseparable

A state write is always paired with a state read and a state read is always paired with a state write.

When you read a state, the state is meant to be assigned to another object. And from the other perspective, there’s no point in reading the state if you’re not going to assign the state to another object.

< 2021-05-05: This idea might be deprecated because __Get__ might also be called for *accessing* something, not necessarily for *assigning* it to something else. >