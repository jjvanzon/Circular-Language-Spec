﻿|<h1>***Computer Language Coding Concepts***</h1>|
| :- |
## **Pointer Circularity**
< Article text >

See also: *< List of articles >*


*Author & Copyright: <Jan-Joost van Zon>        Date: <May 21, 2008> – <May 22, 2008>        Location: <Oosterhout, The Netherlands>        Status: [ Under Construction | Finished | … ]*
## **Ideas**
### **Out of the original Symbol documentation**
#### **Circularity**
Circularity is the case when the redirection eventually leads to a symbol already encountered. 

![](Pointer%20Circularity.001.png "Circularity by pointing to itself")

**A** is a pointer to **B**, which is a pointer to **C**, which is a pointer to **A** again and so on. Redirection is ended, though, when the target symbol is found to be the source symbol or intermediate symbol. In this case it can’t be said that a single symbol represents the actual object, while other symbols are regarded object references. In this case **A**, **B** and **C** are *all* primary representations of the object.

There’s also a question of circularity when somewhere in the redirection a bidirection is encountered.

![](Pointer%20Circularity.002.png "Circularity by Ambiguity")

This is because a bidirection can also be regarded to be two lines, one for each direction. The line between **B** and **C** can be regarded two lines: one pointing from **B** to **C** and one pointing from **C** to **B**. Therefore, the line(s) between **B** and **C** cause a circularity: **B** is a pointer to **C**, which is a pointer to **B**, which is a pointer to **C** and so on. Thus, **B** and **C** both represent the target object. **A** however, is a pointer *to* this *circularity*. It’s not part of the circularity.

A circularity can only be the end point of redirection, because you can’t escape from a circularity.
##### ***Circularity in Tracing***
Tracing final targets requires following multiple line types to find a single system aspect.

![](Pointer%20Circularity.003.jpeg "Circularity in Tracing")

In a trace, multiple line types can occur in a single circularity. The following sub sections cover the details of circularity in each type of trace.
##### ***Circularity in a Object-Type Trace***
In object-type tracing, both kinds of line can close a circularity.

If the closed circle *contains* an object line

![](Pointer%20Circularity.004.jpeg "Circularity in Object-Class Trace, Containing Object Spline")

or *is pointed to* by an object line,

![](Pointer%20Circularity.005.jpeg "Circularity in Object-Class Tracem Pointed to With Object Spline")

the whole circularity represents both object and type.

If the closed circle consists of only type lines and is pointed to by only a type line, the circularity only represents the type.

![](Pointer%20Circularity.006.jpeg "Circularity in Object-Class Trace, Pointed to with Class Spline Containing only Class Splines")

An object trace is the same procedure. The examples above should also clarify circularity in a type trace.
##### ***Circularity in a Interface Trace***
All three kinds of object symbol lines can close a circularity in an interface trace. If a circularity is encountered when tracing the interface, the whole circularity represents the interface.

![](Pointer%20Circularity.007.jpeg "Circularity in Interface Trace")
##### ***Circularity in a Definition Trace***
In a definition trace, only one line type is followed, so a circularity there looks the same as earlier explained.

![](Pointer%20Circularity.008.jpeg "30")

The whole circularity represents the definition.
##### ***Circularity in a Procedure Interface Trace***
Both kinds of procedure symbol lines can close a circularity in a procedure interface trace. If a circularity in encountered when tracing the procedure interface, the whole circularity represents the procedure interface.

![](Pointer%20Circularity.009.jpeg "31")
##### ***Circularity in an Execution-Definition Trace***
The execution-definition trace is the same process as the execution trace, so this section explains circularity in both of them.

In execution-definition tracing you follow reference lines.

If the closed circle contains a diamond

![](Pointer%20Circularity.010.jpeg "32")


then the whole circularity represents both execution and definition.

If the closed circle consists of only squares, the circularity only represents the definition.

![](Pointer%20Circularity.011.jpeg "33")
