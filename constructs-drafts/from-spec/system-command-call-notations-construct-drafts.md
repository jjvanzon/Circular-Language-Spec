Construct Drafts | From Spec | System Interfaces | System Command Call Notations Construct Drafts
=================================================================================================

`[ Deprecated documentation ]`

__Contents__

- [System Interface Command Call Notation](#system-interface-command-call-notation)
- [Simplified System Interface Calls](#simplified-system-interface-calls)
- [System Interface Calls with Arguments](#system-interface-calls-with-arguments)
    - [Class Assignment Extended](#class-assignment-extended)
- [Explicit Get & Set](#explicit-get--set)
- [Explicit Get & Set Arguments](#explicit-get--set-arguments)
- [Explicit Display of Assignment](#explicit-display-of-assignment)

## System Interface Command Call Notation

There might be other options for displaying a call to a system command that are laid out in the articles that follow.

## Simplified System Interface Calls

System command calls might be so fundamental, that they may the most basic notation that still fits within the language, even though it can get a more complex notation when fully drawn out.

Here is an example of the simplified system command call notation:

![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.001.png)

The line type indicates the aspect.  
A word like __Get__, __Set__ or __Use__ indicates assignment direction.  
The access mark indicates the object of which the system command is called.

Leaving out the access mark may make the notation even simpler. The access mark may not be required in this particular notation, but other notations are later derived from this notation which require the access mark for disambiguation.

Here follow the basic notations for all the system commands.

|                      |                            |
|:--------------------:|:--------------------------:|
|    __Object Get__    |       __Object Set__       |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.002.png) | ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.003.png) |
|                      |                            |
|   __Use As Class__   | __Use Reference As Class__ |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.004.png) | ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.005.png) |
|                      |                            |
|    __Class Set__     |                            |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.001.png) | |
|                      |                            |
| __Object-Class Get__ |  __Reference-Class Get__   |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.006.png) | ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.007.png) |
|                      |                            |
|    __Value Get__     |       __Value Set__        |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.008.png) | ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.009.png) |
|                      |                            |
|  __Clone (2) Get__   |     __Clone (2) Set__      |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.010.png) | ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.011.png) |
|                      |                            |
|       __New__        |         __Annul__          |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.012.png) | ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.013.png) |
|                      |                            |
|      __Execute__     |                            |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.014.png) | |
|                      |                            |
|        __Add__       |         __Remove__         |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.015.png) | ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.016.png) |

## System Interface Calls with Arguments

System commands can use a simplified argument notation.

Explicit notation of an argument of a command:

![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.017a.png)

can be simplified for system commands:

![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.017b.png)

The simplified notation is only used for system commands, because system commands are so fundamental that they need a notation that is as simple as possible.

The general use of this notation might be explained with __Object Get__ as an example. __Object Get__ might probably never use this notation, but it is easier to explain this way.

Here is the basic notation of an __Object Get__ system command:

| Object Get |
|:----------:|
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.002.png) |

The __Object Get__ command's return value is drawn out as follows, using the simplified argument notation for system commands:

`< Add comparison with system interface call notation? >`

| Object Get |
|:----------:|
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.018.png) |

| Object Set |
|:----------:|
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.003.png) |

| Object Set |
|:----------:|
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.019.png) |

`< A bit more info? >`

|    Object Get     |    Object Set     |
|:-----------------:|:-----------------:|
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.018.png) | ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.019.png) |
|  Object Get `<=`  | (Object Get `=>`) |
| (Object Set `=>`) |  Object Set `<=`  |

Yielding over __Class__ aspect:

|                        |                              |                   |
|:----------------------:|:----------------------------:|:-----------------:|
|    __Use As Class__    |  __Use Reference As Class__  |   __Class Set__   |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.020.png) | ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.021.png) | ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.022.png) |
|   Use As Class `<=`    | Use Reference As Class `<=`  | (Class Get `=>`)  |
|   (Class Set `=>`)     |       (Class Set `=>`)       |  Class Set `<=`   |
|                        |                              |                   |
|  __Object-Class Get__  |   __Reference-Class Get__    |                   |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.023.png) | ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.024.png) | |
| Object-Class Get `<=`  |   Reference-Class Get `<=`   |                   |
|    (Class Set `=>`)    |       (Class Set `=>`)       |                   |

Yielding over between __Class__ aspect and __Object__ aspect:

|                       |                           |                       |
|:---------------------:|:-------------------------:|:---------------------:|
|     __Class Set__     |  __Reference-Class Get__  |  __Object-Class Get__ |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.025.png) | ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.026.png) | ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.027.png) |
|  (Use As Class `=>`)  | Reference Class Get `<=`  | Object-Class Get `<=` |
|    Class Set `<=`     |     (Object Set `=>`)     |   (Object Set `=>`)   |
|                       |                           |                       |
|     __Value Get__     |       __Value Set__       |                       |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.028.png) | ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.029.png) |
|    Value Get `<=`     |     (Value Get `=>`)      |                       |
|   (Value Set `=>`)    |      Value Set `<=`       |                       |
|                       |                           |                       |
|   __Clone (2) Get__   |     __Clone (2) Set__     |                       |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.030.png) | ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.031.png) |
|  Clone (2) Get `<=`   |   (Clone (2) Get `=>`)    |                       |
| (Clone (2) Set `=>`)  |    Clone (2) Set `<=`     |                       |
|                       |                           |                       |
|        __New__        |                           |                       |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.032.png) | | |
|  (Use As Class `=>`)  |                           |                       |
|        New `<=`       |                           |                       |
|                       |                           |                       |
|        __Add__        |                           |                       |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.033.png) | | |
|   (Object Get `=>`)   |                           |                       |
|        Add `<=`       |                           |                       |

Most of the notations above might never be used. Only the notation for the __New__ and __Add__ arguments are common.

### Class Assignment Extended

This creates the following notations of the different ways to use a class:

|                                      |
|:------------------------------------:|
|         __Class Assignment__         |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.034.png) |
| Use As Class (≈ Get Object) `<=` |
|            Class Set `=>`            |
|                                      |
|    __Class to Object Assignment__    |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.035.png) |
|            Class Get `=>`            |
|           Object Set `<=`            |
|                                      |
| __Class Get – Class Set Assignment__ |
|                                      |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.036.png) |
|           Class Get `<=`             |
|          (Class Set `=>`)            |
|                                      |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.037.png) |
|          (Class Get `<=`)            |
|           Class Set `=>`             |

The __Class Get__ notation and the __Class Set__ notation both have the same effect, only in one case it is the __Get__ that is explicitly displayed and in the other case it is the __Set__ that is explicitly displayed. It is not yet clear which is the best one.

## Explicit Get & Set

The following are examples of explicit __Get__ and __Set__ notations. It works for any __Get__, __Set__ or __Use__ that you want to combine together.

![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.038.png)

![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.039.png)

The line types of the system commands express which aspect a command is called upon. The line in between the two system commands is basically a line type that looks best in that situation: if the whole operation is typical to the use of the __Class__ aspect you could make it dashed, if the operation is a more uncommon cross-aspect action, then you could just use a solid line by default.

When you look at the aspects introduced so far, the only time you may need the explicit __Get__ & __Set__ notation is in a __Class Get – Class Set__ assignment. 

![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.040.png)

Whenever a simpler notation is available, such as an assignment notation, the simpler notation is used, however, alternative notations can *always* be used to simply express a point in *abstract* diagram notation.

## Explicit Get & Set Arguments

This article sheds light on *explicit Get & Set argument* notations. Several notations are introduced. It is not clear yet which is the best one.

In the diagrams below, things are often implicitly notated. However, the notation of the __Get__ and __Set__ arguments is always *ex*plicit.

The most explicit way to draw out a call to a system command with the argument explicitly notated is as follows:

![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.041.png)

It is notated as calling the overloaded __Use As Class__ command with its argument filled in. 

But this notation is also possible:

![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.042.png)

Then you express the aspect *implicitly* using a different line type for the diamond. You also leave out the aspect from the identifier.

So the aspect can be expressed with a diamond line type or by explicitly expressing the aspect in the identifier.

__Get__, __Set__ and __Use__ commands are never used on their own. They always need another counterpart. The notation below shows two system command counterparts with explicit arguments:

![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.043.png)

The __Class Set__ argument is connected to the __Use As Class__ argument.

The following notation expresses the same thing:

![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.044.png)

But now the aspect is implicitly expressed by the line type of the command calls.

Note that all explicit __Get__ and __Set__ argument notations use a solid *object* line between arguments, because that is the part that is *explicit*. Other parts of the notation are implicit sometimes.

If only the object aspect is addressed, the picture looks like this:

![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.045.png)

There is also the following weirder possibility to display the __Get__ and __Set__ arguments:

![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.046.png)

But the odd thing about that notation is that there is no connection between the __Get__ and __Set__ arguments and the real __Get__ and __Set__ targets. The notation looks so strange, that we might probably never go with that.

The main point is: the diagrams above show the explicit expression of the arguments of __Get__ and __Set__ calls.

Explicit display of __Get__ and __Set__ arguments is hardly ever used, because there are simpler notations available, such as the assignment notation or if you might, the explicit __Get__ & __Set__ notation:

|                                      |
|:------------------------------------:|
|            __Assignment__            |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.047.png) |
|            Object Get `<=`           |
|            Object Set `=>`           |
|                                      |
|      Explicit __Get__ & __Set__      |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.048.png) |
|            Object Get `<=`           |
|            Object Set `=>`           |
|                                      |
| Explicit __Get__ & __Set__ Arguments |
| ![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.049.png) |
|            Object Get `<=`           |
|            Object Set `=>`           |

You might only use explicit display of __Get__ and __Set__ arguments in abstract diagram expression when you just want to make a point.

## Explicit Display of Assignment

The main thing explicitly displayed here is that the *system interface* is opened up, showing explicitly what aspects and system commands are called. The following picture demonstrates this:

![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.050.png)

The picture that follows goes even further. It also displays *access connectors*:

![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.051.png)

Perhaps you could go even further in discovering more things to explicitly display.

![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.052.png)

But of course a more practical notation is:

![](images/3.%20System%20Command%20Call%20Notations%20Construct%20Drafts.053.png)