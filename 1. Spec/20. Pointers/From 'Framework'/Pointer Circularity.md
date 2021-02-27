Circle Language Spec | Circularity
==================================

Pointer Circularity
-------------------

### Ideas

(Out of the original Symbol documentation)

#### Circularity

Circularity is the case when the redirection eventually leads to a symbol already encountered. 

![](images/Pointer%20Circularity.001.png)

__A__ is a pointer to __B__, which is a pointer to __C__, which is a pointer to __A__ again and so on. Redirection is ended, though, when the target symbol is found to be the source symbol or intermediate symbol. In this case it can’t be said that a single symbol represents the actual object, while other symbols are regarded object references. In this case __A__, __B__ and __C__ are *all* primary representations of the object.

There’s also a question of circularity when somewhere in the redirection a bidirection is encountered.

![](images/Pointer%20Circularity.002.png)

This is because a bidirection can also be regarded to be two lines, one for each direction. The line between __B__ and __C__ can be regarded two lines: one pointing from __B__ to __C__ and one pointing from __C__ to __B__. Therefore, the line(s) between __B__ and __C__ cause a circularity: __B__ is a pointer to __C__, which is a pointer to __B__, which is a pointer to __C__ and so on. Thus, __B__ and __C__ both represent the target object. __A__ however, is a pointer *to* this *circularity*. It’s not part of the circularity.

A circularity can only be the end point of redirection, because you can’t escape from a circularity.

##### Circularity in Tracing

Tracing final targets requires following multiple line types to find a single system aspect.

![](images/Pointer%20Circularity.003.jpeg)

In a trace, multiple line types can occur in a single circularity. The following sub sections cover the details of circularity in each type of trace.

##### Circularity in an Object-Type Trace

In object-type tracing, both kinds of line can close a circularity.

If the closed circle *contains* an object line

![](images/Pointer%20Circularity.004.jpeg)

or *is pointed to* by an object line,

![](images/Pointer%20Circularity.005.jpeg)

the whole circularity represents both object and type.

If the closed circle consists of only type lines and is pointed to by only a type line, the circularity only represents the type.

![](images/Pointer%20Circularity.006.jpeg)

An object trace is the same procedure. The examples above should also clarify circularity in a type trace.

##### Circularity in a Interface Trace

All three kinds of object symbol lines can close a circularity in an interface trace. If a circularity is encountered when tracing the interface, the whole circularity represents the interface.

![](images/Pointer%20Circularity.007.jpeg)

##### Circularity in a Definition Trace

In a definition trace, only one line type is followed, so a circularity there looks the same as earlier explained.

![](images/Pointer%20Circularity.008.jpeg)

The whole circularity represents the definition.

##### Circularity in a Procedure Interface Trace

Both kinds of procedure symbol lines can close a circularity in a procedure interface trace. If a circularity in encountered when tracing the procedure interface, the whole circularity represents the procedure interface.

![](images/Pointer%20Circularity.009.jpeg)

##### Circularity in an Execution-Definition Trace

The execution-definition trace is the same process as the execution trace, so this section explains circularity in both of them.

In execution-definition tracing you follow reference lines.

If the closed circle contains a diamond

![](images/Pointer%20Circularity.010.jpeg)

then the whole circularity represents both execution and definition.

If the closed circle consists of only squares, the circularity only represents the definition.

![](images/Pointer%20Circularity.011.jpeg)