﻿Circular Language Spec | System Interfaces
==========================================

[back](./)

System Command Call Notations
-----------------------------

`[ Preliminary documentation ]`

__Contents__

- [Introduction](#introduction)
- [Notational Choices](#notational-choices)
    - [Distinguishing Object-Bound and Reference-Bound Aspects](#distinguishing-object-bound-and-reference-bound-aspects)
    - [System Interface Call Notation](#system-interface-call-notation)
- [System Interface Calls versus Assignment](#system-interface-calls-versus-assignment)
- [System Interface Calls](#system-interface-calls)
- [System Interface Calls with Arguments](#system-interface-calls-with-arguments)
- [Explicit Get & Set](#explicit-get--set)
- [Explicit Display of Assignment](#explicit-display-of-assignment)

### Introduction

There might be several notations for calling a system command.

Direct calls to __Get__, __Set__ and __Use__ commands might not usually be seen. Those system commands may usually be called indirectly by *assignment* commands.

But being introduced to using __Get__ and __Set__ commands, instead of a single assignment call, might give a lower-level view on assignment. This lower-level perspective might be of use when wanting to use alternative forms of assignment, that do not seem to fit into an assignment notation.

### Notational Choices

#### Distinguishing Object-Bound and Reference-Bound Aspects

There are system commands that apply to object references and to the object itself. System commands, that apply to an object reference are displayed here with a parent around the targeted reference:

![](images/3.%20System%20Command%20Call%20Notations.001.png)

System commands, that apply to the object itself are displayed without a parent around the targeted object.

![](images/3.%20System%20Command%20Call%20Notations.002.png)

#### System Interface Call Notation

One of the notations for system command calls is calling upon the command definition in the system interface:

![](images/3.%20System%20Command%20Call%20Notations.003.png)

This might be a regular way to display a command call in Circular, but now a call to a command inside the system interface.

There could be multiple ways to display the content of the system interface. They might depend on taste, application or needs. This article may go for a system interface that looks relatively simple with often a loose square in it representing a system command.

### System Interface Calls versus Assignment

System command calls to __Get__, __Set__ or __Use__ might not often be visible, because they might usually be implied by assignment calls. But for alternative types of assignment, that do not have a standard assignment notation, you can explicitly display __Get__, __Set__ and __Use__ calls. When a simpler notation might not suffice, displaying __Get__, __Use__ or __Set__ command explicitly might be needed. This basically only happens in unusual cross-aspect assignments. In abstract diagram expression though, you can always use the explicit notations to simply make a point.

### System Interface Calls

Here is an attempt to systematically display all the system commands thus far in a system interface command call notation. Where the calls look similar this might be relevant to realize, where the calls look particular this might be relevant to realize as different. Which are similar and which are different might become apparent from this full overview.

|                                                              |                                                              |
|:------------------------------------------------------------:|:------------------------------------------------------------:|
| ![](images/3.%20System%20Command%20Call%20Notations.004.png) | ![](images/3.%20System%20Command%20Call%20Notations.005.png) |
|                  (has assignment notation)                   |                  (has assignment notation)                   |
|                                                              |                                                              |
| ![](images/3.%20System%20Command%20Call%20Notations.006.png) | ![](images/3.%20System%20Command%20Call%20Notations.007.png) |
|                  (has assignment notation)                   |                  (has assignment notation)                   |
|                                                              |                                                              |
| ![](images/3.%20System%20Command%20Call%20Notations.008.png) | ![](images/3.%20System%20Command%20Call%20Notations.009.png) |
|                        (object-bound)                        |                      (reference-bound)                       |
|            (has cross-aspect assignment notation)            |            (has cross-aspect assignment notation)            |
|                                                              |                                                              |
| ![](images/3.%20System%20Command%20Call%20Notations.010.png) | ![](images/3.%20System%20Command%20Call%20Notations.011.png) |
|                  (has assignment notation)                   |                  (has assignment notation)                   |
|                                                              |                                                              |
| ![](images/3.%20System%20Command%20Call%20Notations.012.png) | ![](images/3.%20System%20Command%20Call%20Notations.013.png) |
|                                                              |                                                              |
| ![](images/3.%20System%20Command%20Call%20Notations.014.png) | ![](images/3.%20System%20Command%20Call%20Notations.015.png) |
|                                                              |                                                              |
| ![](images/3.%20System%20Command%20Call%20Notations.016.png) | ![](images/3.%20System%20Command%20Call%20Notations.017.png) |
|                                                              |                                                              |
| ![](images/3.%20System%20Command%20Call%20Notations.018.png) |                                                              |
|           (also has a basic command call notation)           |                                                              |

### System Interface Calls with Arguments

Above were shown the basic system command call notation, but most system command calls are incomplete without an argument.

The __Get Object__ command has a return value: the object. It is an *output* argument. It should be there to transfer the __Object__ aspect to another symbol. The __Get Object__ command's return value is drawn out as follows.

![](images/3.%20System%20Command%20Call%20Notations.019.png)

In the picture above the output argument of the __Get Object__ call is filled in. __Get Object__ is called upon the smaller circle contained by the larger circle. But next, an __Set Object__ is *implicitly* called upon the smaller circle in the corner. The diagram above implicitly causes an __Set Object__ to be executed upon the smaller circle in the corner.

Something similar happens in case of an __Set Object__ command. Here is the basic notation of an __Set Object__ command call:

![](images/3.%20System%20Command%20Call%20Notations.020.png)

And here the argument of the __Set Object__ command is filled in:

![](images/3.%20System%20Command%20Call%20Notations.021.png)

This causes an implicit __Get Object__ on the smaller circle in the top-right corner, followed by the explicit __Set Object__, targeting the smaller circle contained by the larger circle.

So the basic display of a basic system command call with an argument filled in, implicitly causes another system command to be called as well.

Below you might find an overview of all the system commands with their argument filled in.

Which system commands might be called implicitly, is also indicated in the overview. The implicit calls might be regarded indications of what *might* happen or what system call the connection might have been established with. But perhaps not always. It might be a good way to go to have a relaxed view on what the connection means versus the implicit calls indicated.

Some commands might not be covered by assignment notation, which might make explicit calls needed. Others might be possible with an assignment notation also, which the table below also tries to denote.

|                                                                |                                                              |
|:--------------------------------------------------------------:|:------------------------------------------------------------:|
|           __Get Object `<=`__ <br> (Set Object `=>`)           |          (Get Object `=>`) <br> __Set Object `<=`__          |
|  ![](images/3.%20System%20Command%20Call%20Notations.019.png)  | ![](images/3.%20System%20Command%20Call%20Notations.021.png) |
|                   (has assignment notation)                    |                  (has assignment notation)                   |
|                                                                |                                                              |
| __Use As Class__ (≈ Get Object) __`<=`__ <br> (Set Class `=>`) |          (Get Class `=>`) <br> __Set Class `<=`__            |
|  ![](images/3.%20System%20Command%20Call%20Notations.022.png)  | *(Might not applicable. There might <br> not be a notation for an implicit <br> Get Class call. System interface call <br> with argument might require two <br> system calls in this case: explicit Get <br> Class and explicit Set Class.)* |
|                   (has assignment notation)                    |                                                              |
|                                                                |                                                              |
|     __Get Object-Bound Class__ `<=` <br> (Set Class `=>`)      |   __Get Reference-Bound Class `<=`__ <br> (Set Class `=>`)   |
|  ![](images/3.%20System%20Command%20Call%20Notations.023.png)  | ![](images/3.%20System%20Command%20Call%20Notations.024.png) |
|                                                                |                                                              |
|   (Use As Class (≈ Get Object) `=>`) <br> __Set Class `<=`__   |                                                              |
|  ![](images/3.%20System%20Command%20Call%20Notations.025.png)  |                            __-__                             |
|                   (has assignment notation)                    |                                                              |
|                                                                |                                                              |
|     __Get Object-Bound Class `<=`__ <br> (Set Object `=>`)     |  __Get Reference-Bound Class `<=`__ <br> (Set Object `=>`)   |
|  ![](images/3.%20System%20Command%20Call%20Notations.026.png)  | ![](images/3.%20System%20Command%20Call%20Notations.027.png) |
|             (has cross-aspect assignment notation)             |            (has cross-aspect assignment notation)            |
|                                                                |                                                              |
|            __Value Get `<=`__ <br> (Value Set `=>`)            |            (Value Get `=>`) <br> __Value Set `<=`            |
|  ![](images/3.%20System%20Command%20Call%20Notations.028.png)  | ![](images/3.%20System%20Command%20Call%20Notations.029.png) |
|                   (has assignment notation)                    |                  (has assignment notation)                   |
|                                                                |                                                              |
|        __Get Clone (2) `<=`__ <br> (Set Clone (2) `=>`)        |      (Get Clone (2) `=>`) <br> __Set Clone (2) `<=`__        |
|  ![](images/3.%20System%20Command%20Call%20Notations.030.png)  | ![](images/3.%20System%20Command%20Call%20Notations.031.png) |
|                                                                |                                                              |
|             (Use As Class `=>`) <br> __New `<=`__              |      (Get Reference-Bound Class `<=`) <br> __New `<=`__      |
|  ![](images/3.%20System%20Command%20Call%20Notations.032.png)  | ![](images/3.%20System%20Command%20Call%20Notations.033.png) |
|                                                                | *(variation where class for object not provided as argument* |
|                                                                |           *but defined by class of the reference)*           |
|                           __Annul__                            |                                                              |
|                       *(no parameters)*                        |                            __-__                             |
|                                                                |                                                              |
|               (Get Object `=>`) <br> __Add `<=`__              |                          __Remove__                          |
|  ![](images/3.%20System%20Command%20Call%20Notations.034.png)  |                      *(no parameters)*                       |

### Explicit Get & Set

Assignment has a special, simplified notation covered in the *Assignment* article. But you can also display the __Get__ and __Set__ of the assignment explicitly. This notation is only required when there is no simplified notation available for what you want. However, explicit notation of __Get__ and __Set__ can always be used in *abstract* diagram expression just to make a point. The overview below aims to express different combinations of two system command calls, mainly __Get__ & __Set__ combinations, but may also mention other combinations such as a __Get Object__ and then __Add__.

|                                                              |                                                              |
|:------------------------------------------------------------:|:------------------------------------------------------------:|
|           __Get Object `<=` <br> Set Object `=>`__           | __Use As Class__ (≈ Get Object) `<=` <br> __Set Class `=>`__ |
| ![](images/3.%20System%20Command%20Call%20Notations.035.png) | ![](images/3.%20System%20Command%20Call%20Notations.036.png) |
|                                                              |                                                              |
|     __Get Object-Bound Class `<=` <br> Set Class `=>`__      |    __Get Reference-Bound Class `<=` <br> Set Class `=>`__    |
| ![](images/3.%20System%20Command%20Call%20Notations.037.png) | ![](images/3.%20System%20Command%20Call%20Notations.038.png) |
|                                                              |                                                              |
|     __Get Object-Bound Class `<=` <br> Set Object `=>`__     |   __Get Reference-Bound Class `<=` <br> Set Object `=>`__    |
| ![](images/3.%20System%20Command%20Call%20Notations.039.png) | ![](images/3.%20System%20Command%20Call%20Notations.040.png) |
|                                                              |                                                              |
|            __Get Value `<=` <br> Set Value `=>`__            |        __Get Clone (2) `<=` <br> Set Clone (2) `=>`__        |
| ![](images/3.%20System%20Command%20Call%20Notations.041.png) | ![](images/3.%20System%20Command%20Call%20Notations.042.png) |
|                                                              |                                                              |
|             __Use As Class `=>` <br> New `<=`__              |              __Get Object `=>` <br> Add `<=`__               |
| ![](images/3.%20System%20Command%20Call%20Notations.043.png) | ![](images/3.%20System%20Command%20Call%20Notations.044.png) |

The __Annul__ and __Remove__ commands' explicit notations were already covered by other sections.

|                                                              |
|:------------------------------------------------------------:|
|       __Get Reference-Bound Class `=>` <br> New `=>`__       |
| ![](images/3.%20System%20Command%20Call%20Notations.045.png) |

The workings of the __New__ command without a class argument might be internal implementation of an overload of the __New__ command in the system interface.

### Explicit Display of Assignment

An assignment has a simple notation:

![](images/3.%20System%20Command%20Call%20Notations.046.png)

But it is an implicit notation. Assignment needs such a simple notation, because it is one of the most basic kinds of commands in computer technology. Other sections have demonstrated how assignment can be displayed in a more explicit way. The current section goes as far as to display assignment completely explicitly.

The point of this article is to demonstrate how assignment works at system-level and also to demonstrate how impractical the implicit notation is.

The main thing explicitly displayed here is that the *system interface* is opened up, showing explicitly what aspects and system commands are called.

The pictures that follow might all represent the different ways to display an assignment, that differ by whether the __Get__ or __Set__ calls are displayed as explicit calls to a system interface, or as a connection or as an assignment call.

|                                                              |
|:------------------------------------------------------------:|
|             __Explicit Get Call with Argument__              |
| ![](images/3.%20System%20Command%20Call%20Notations.047.png) |
|          __Get Object `<=`__ <br> (Set Object `=>`)          |
|                                                              |
|             __Explicit Set Call with Argument__              |
| ![](images/3.%20System%20Command%20Call%20Notations.048.png) |
|          (Get Object `<=`) <br> __Set Object `=>`__          |
|                                                              |
|                 __Explicit Get & Set Calls__                 |
| ![](images/3.%20System%20Command%20Call%20Notations.049.png) |
|           __Get Object `<=` <br> Set Object `=>`__           |

But the main point is: you have now seen how system operations work internally and you can also see that it is highly unpractical to express all the assignments explicitly like that. 

You could also explicitly display the assignment call, which basically puts the whole thing inside a command:

|                Assignment Call Implementation                |
|:------------------------------------------------------------:|
| ![](images/3.%20System%20Command%20Call%20Notations.050.png) |
|           __Get Object `<=` <br> Set Object `=>`__           |

But of course a more practical notation is:

|                     Assignment Notation                      |
|:------------------------------------------------------------:|
| ![](images/3.%20System%20Command%20Call%20Notations.046.png) |
|           __Get Object `<=` <br> Set Object `=>`__           |