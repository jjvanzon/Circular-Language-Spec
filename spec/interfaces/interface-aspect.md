Circular Language Spec | Interfaces
===================================

[back](./)

Interface Aspect
----------------

`[ Preliminary documentation ]`

__Contents__

- [Introduction](#introduction)
- [System Commands for the Interface Aspect](#system-commands-for-the-interface-aspect)
    - [Interface is Both Object-Bound and Reference-Bound](#interface-is-both-object-bound-and-reference-bound)
    - [Pointer-to-Pointer Situations](#pointer-to-pointer-situations)
    - [Set Interface to Reference](#set-interface-to-reference)
    - [Get Interface which is a Reference](#get-interface-which-is-a-reference)
    - [Use Reference As Interface](#use-reference-as-interface)
    - [The Overloads Recapitulated](#the-overloads-recapitulated)
- [System Commands for the Interface Merging Aspect](#system-commands-for-the-interface-merging-aspect)
- [Interface Aspect in System Interface](#interface-aspect-in-system-interface)
    - [Object-Interface in System Interface](#object-interface-in-system-interface)
    - [Reference-Interface in System Interface](#reference-interface-in-system-interface)
    - [Reference-Interface in System Interface of Related List](#reference-interface-in-system-interface-of-related-list)
    - [Interface Merging in System Interface](#interface-merging-in-system-interface)
- [Interface Assignment Types](#interface-assignment-types)
    - [Interface Assignment](#interface-assignment)
    - [Interface Pointer Assignment](#interface-pointer-assignment)
    - [Interface Assignment With Pointer Source](#interface-assignment-with-pointer-source)
    - [Cross-Aspect Interface Assignment](#cross-aspect-interface-assignment)
- [Interface System Command Calls](#interface-system-command-calls)
    - [Interface - System Interface - Command Call Notation](#interface---system-interface---command-call-notation)
    - [Simplified System Command Call Notation](#simplified-system-command-call-notation)
    - [System Command Call Notation with Argument](#system-command-call-notation-with-argument)
    - [Explicit Get & Set Notation](#explicit-get--set-notation)
    - [Explicit Get & Set Arguments Notation](#explicit-get--set-arguments-notation)
- [Interface Connectors](#interface-connectors)
- [Interface Connections](#interface-connections)
- [New Command with Interface Parameter](#new-command-with-interface-parameter)

### Introduction

While systems seem to be composed of a lot of different types of objects, all objects and types are in reality no more than a very limited set of types, that can be configured to look like other types. Those basic objects are called *system objects*. The behavior of those system objects is controlled by controlling their *system aspects*. System objects is covered in a separate chapter called *System Interfaces*, but there the *interface* aspect was completely left out of the story. In this part of the documentation everything about the interface aspect is laid out to make the concept of interfaces catch up with the *System Interfaces* story.

The __Interface__ aspect allows you to control how objects look on the outside, while the insides of the objects can differ completely. Another concept which employs the word *interfaces* is an object (an interface) melting together with its container. From a systematic point of view they seem to be completely unrelated concepts, however in practice they are conjoinedly used. To distinguish them we call them the __Interface__ aspect and the __Interface Merging__ aspect. The main diagram symbolization of the __Interface__ aspect is as follows:

![](images/2.%20Interface%20Aspect.001.png)

The triangle is the symbolization of the __Interface Merging__ aspect, and the dotted line is the symbolization of __Interface__ aspect.

__Interface Merging__ in the future might probably become an aspect that extends beyond the concept of interfaces, because it could for instance apply to the concept of default members too.

### System Commands for the Interface Aspect

The main system commands to control the __Interface__ aspect are:

- __Use As Interface__
- __Interface Set__
- __Reference-Interface Get__
- __Object-Interface Get__

__Use As Interface__ is a lot like the command __Object Get__, but then used for the purpose of making that object as the interface of another object. This is common usage of the interface aspect. It also makes you able to separately access control whether an object can be used as an interface.

The __Interface Set__ command is executed on an object reference. The reference can then only point to object that supports the interface. This means either that the other object has the same interface, or that the object has it as sub-object that is an implicit interface. __Interface Set__ applies only to references and not to objects, because the interface of an *object* can only be set upon creation.

The commands __Reference-Interface Get__ and __Object-Interface Get__ get the interface object that is associated with a reference or object. Those commands are less commonly used.

#### Interface is Both Object-Bound and Reference-Bound

The __Interface__ aspect applies to both objects and references, but differently. An object can have a certain interface, that is set upon creation and throughout its lifetime. A reference can also have an interface, defining which classes of object you can assign to the reference. The interfaces of an object can never change. The interface of a reference can be changed, but only to an interface supported by the object it points to or arbitrarily while the reference is __Nothing__. 

#### Pointer-to-Pointer Situations

In a standard situation the __Use As Interface__, __Interface Set__, __Reference-Interface Get__ and Object-Interface Get commands are about making an object function as another object’s interface. However, you can also make something’s interface be yet again another reference. That means that another parent object determines the eventual interface.

(However, this might create difficulty for the system to maintain an object’s constant interface. You might want another parent to determine the initial interface, but the interface of an object should not change during its lifetime.)

#### Set Interface to Reference

To be able to set the __Interface__ aspect to another related item, __Interface Set__ has two overloads:

- __Interface Set => Set Interface to Other Related Item.__  
- __Interface Set => Set Interface to Other Related List Item__

If you want a single name to express both situations, you could call it __Set Interface to Reference__.

#### Get Interface which is a Reference

Because the __Interface__ aspect can be set to another related item, the __Interface Set__ command gets extra overloads. Next to that, there are different overloads for the two types of __Interface Get__: __Reference-Interface Get__ and __Object-Interface Get__. This creates the following overloads:

- __Reference-Interface Get => Get Reference-Interface which is Another Related Item__  
__Reference-Interface Get => Get Reference-Interface which is Another Related List Item__

- __Object-Interface Get => Get Object-Interface which is Another Related Item__  
__Object-Interface Get => Get Object-Interface which is Another Related List Item__

You could also call them __Get Interface which is a Reference__.

#### Use Reference As Interface

The __Reference__ aspect can be access-controlled for different ways you can use it. Pointer-to-pointer situations require you to be able to use a reference as an *interface*. To be able to access control the different purposes for which you can use a reference, the __Reference Get__ command gets the secondary implementation:

- __Use Reference As Interface__

which delegates directly to the __Reference Get__ command.

#### The Overloads Recapitulated

Do not wreck your brain over all this delegation and overloading. It is just for pointer-to-pointer situations to have the same command names as standard situations, and also to be able to separately access-control the specific *uses* of references or objects. You might not usually see the pointer-related commands, because they might be implicitly delegated to by the main commands. This leaves us with the following commands:

- __Use As Interface__
- __Interface Set__
- __Reference-Interface Get__
- __Object-Interface Get__
- __Use Reference As Interface__

Detail: For that last command you might want to overload Object Get. But that might not work. You can not overload it, because they might both take a pointer to an object as an argument. To disambiguate, they might have a different name and you might point to a *specific* command.

### System Commands for the Interface Merging Aspect

The commands for the Interface Merging aspect are:

- __Interface Merged Get__
- __Interface Merged Set__

__Interface Merging__ is a reference-bound aspect: it only applies to references, not objects.

__Interface Merged__ is a __Boolean__, that can be either __True__ or __False__.

When an interface is merged it means that its members merge with its container and are accessible as if part of the container. Also, the container can be referenced as if it has the type of the interface.

### Interface Aspect in System Interface

System aspects can be shown in the system interface notation as worked out in the *System Interfaces* articles in the *System Interfaces* chapter. The __Interface__ aspect was not covered there, so this is a supplement to that documentation.

#### Object-Interface in System Interface

The __Interface__ aspect has *five* system commands, but only *two* of them apply to __Objects__. The other ones apply to references. The __Interface__ aspect of an __Object__ is controlled through the following commands:

- __Use As Interface__
- __Object-Interface Get__

The commands are placed inside the system interface inside a triangle that wraps together the members of the __Interface__ aspect:

![](images/2.%20Interface%20Aspect.002.png)

#### Reference-Interface in System Interface

The __Interface__ aspect has *five* system commands, but only *three* of them apply to __Related Items__:

- __Interface Set__
- __Reference-Interface Get__
- __Use Reference As Interface__

The commands are placed inside a triangle, that wraps together the members of the __Interface__ aspect:

![](images/2.%20Interface%20Aspect.003.png)

It works the same for a __Related List Item__ as it might for a __Related Item__.

#### Reference-Interface in System Interface of Related List

A list can centrally control the aspects of its items. Therefore, a list can control the __Interface__ aspect of its items, centrally setting the __Interface__ that all the items might support.

The system commands to do this are placed inside a triangle that wraps together the members to control the __Interface__ aspect:

![](images/2.%20Interface%20Aspect.004.png)

#### Interface Merging in System Interface

The __Interface Merging__ aspect only applies to __Related Items__. It is controlled through two commands:

- __Interface Merged Get__
- __Interface Merged Set__

The commands are placed inside the system interface inside a triangle, that wraps together the members of the __Interface Merging__ aspect:

![](images/2.%20Interface%20Aspect.005.png)

__Interface Merging__ might not apply to __Related List Items__, because it might not seem to be practical there.

### Interface Assignment Types

This section is a mere supplement to the *Assignment* articles in the *System Interfaces* chapter. For a general explanation of assignment, look there. This section only makes the __Interface__ aspect catch up with the rest of the explanations.


#### Interface Assignment

|         ![](images/2.%20Interface%20Aspect.006.png)          |
|:------------------------------------------------------------:|
|          __Use As Interface `<=` (~= Object Get)__           |
|                    __Interface Set `=>`__                    |
| *Makes the source become <br> the interface for the target.* |


#### Interface Pointer Assignment

|                                                                       |
|:---------------------------------------------------------------------:|
|              ![](images/2.%20Interface%20Aspect.007.png)              |
|        __Use Reference As Interface `<=` (~= Reference Get)__         |
|   __Interface Set `=>`  (~= Set Interface to Other Related Item)__    |
|                                                                       |
|              ![](images/2.%20Interface%20Aspect.008.png)              |
|        __Use Reference As Interface `<=` (~= Reference Get)__         |
| __Interface Set `=>`  (~= Set Interface to Other Related List Item)__ |
|                                                                       |
|              ![](images/2.%20Interface%20Aspect.009.png)              |
|        __Use Reference As Interface `<=` (~= Reference Get)__         |
| __Interface Set `=>`  (~= Set Interface to Other Related List Item)__ |


#### Interface Assignment With Pointer Source

|                                                                       |
|:---------------------------------------------------------------------:|
|              ![](images/2.%20Interface%20Aspect.010.png)              |
|      __Use As Interface `<=`  (~= Use Reference As Interface)__       |
|   __Interface Set `=>`  (~= Set Interface to Other Related Item)__    |
|                                                                       |
|              ![](images/2.%20Interface%20Aspect.011.png)              |
|      __Use As Interface `<=`  (~= Use Reference As Interface)__       |
| __Interface Set `=>`  (~= Set Interface to Other Related List Item)__ |


#### Cross-Aspect Interface Assignment

|                                                       |
|:-----------------------------------------------------:|
|       __Object-Interface to Object Assignment__       |
|      ![](images/2.%20Interface%20Aspect.012.png)      |
|             __Object-Interface Get `<=`__             |
|                  __Object Set `=>`__                  |
|                                                       |
|     __Reference-Interface to Object Assignment__      |
|      ![](images/2.%20Interface%20Aspect.013.png)      |
|           __Reference-Interface Get `<=`__            |
|                  __Object Set `=>`__                  |
|                                                       |
|  __Object-Interface to Reference-Class Assignment__   |
|      ![](images/2.%20Interface%20Aspect.014.png)      |
|             __Object-Interface Get `<=`__             |
|             __Reference-Class Set `=>`__              |
|                                                       |
|   __Object-Class to Reference-Interface Assignment__  |
|      ![](images/2.%20Interface%20Aspect.015.png)      |
|               __Object-Class Get `<=`__               |
|           __Reference-Interface Set `=>`__            |
|                                                       |
| __Reference-Class to Reference-Interface Assignment__ |
|      ![](images/2.%20Interface%20Aspect.016.png)      |
|             __Reference-Class Get `<=`__              |
|           __Reference-Interface Set `=>`__            |

There are more implementations of the cross-aspect assignments for cases when the source of the assignment is a pointer-to-pointer, but they are not shown here. To understand the concept look in the *Cross-Aspect Assignments* article in the *System Interfaces* chapter.

### Interface System Command Calls

The concepts of system command call notations is not explained here. Refer to the *System Command Call Notations* article in the *System Interfaces* chapter for that. this is a supplement to that documentation, covering it for the __Interface__ aspect. The __Interface Merged__ aspect is also covered.

Cross-aspect situations can apply to the __Interface__ aspect, but they are not covered. Cross-aspect situations between the __Object__ and __Class__ aspects are described in the *System Interfaces* chapter and adequately shed light on the topic.

#### Interface - System Interface - Command Call Notation

Only one example of a call to a system command of the __Interface__ aspect using the system interface notation might be given here. Below you might find this notation for a call to the __Object-Interface Get__ command:

![](images/2.%20Interface%20Aspect.017.png)

#### Simplified System Command Call Notation

Below you might find the various types of calls to a system command on the __Interface__ aspect in the *simplified system command call notation*.

|                                             |                                             |
|:-------------------------------------------:|:-------------------------------------------:|
|            __Use As Interface__             |       __Use Reference As Interface__        |
| ![](images/2.%20Interface%20Aspect.018.png) | ![](images/2.%20Interface%20Aspect.019.png) |
|                                             |                                             |
|              __Interface Set__              |                                             |
| ![](images/2.%20Interface%20Aspect.020.png) |                                             |
|                                             |                                             |
|          __Object-Interface Get__           |         __Reference-Interface Get__         |
| ![](images/2.%20Interface%20Aspect.021.png) | ![](images/2.%20Interface%20Aspect.022.png) |
|                                             |                                             |
|          __Interface Merged Get__           |          __Interface Merged Set__           |
| ![](images/2.%20Interface%20Aspect.023.png) | ![](images/2.%20Interface%20Aspect.024.png) |

#### System Command Call Notation with Argument

Below you might find the various types of calls to a system command on the __Interface__ aspect in the *system command call with argument notation*.

|                                             |                                             |                                             |
|:-------------------------------------------:|:-------------------------------------------:|:-------------------------------------------:|
|            __Use As Interface__             |       __Use Reference As Interface__        |              __Interface Set__              |
| ![](images/2.%20Interface%20Aspect.025.png) | ![](images/2.%20Interface%20Aspect.026.png) | ![](images/2.%20Interface%20Aspect.027.png) |
|          __Use As Interface `<=`__          |     __Use Reference As Interface `<=`__     |          __(Interface Get `=>`)__           |
|          __(Interface Set `=>`)__           |          __(Interface Set `=>`)__           |           __Interface Set `<=`__            |
|                                             |                                             |                                             |
|          __Object-Interface Get__           |         __Reference-Interface Get__         |                                             |
| ![](images/2.%20Interface%20Aspect.028.png) | ![](images/2.%20Interface%20Aspect.029.png) |                                             |
|        __Object-Interface Get `<=`__        |      __Reference-Interface Get `<=`__       |                                             |
|          __(Interface Set `=>`)__           |          __(Interface Set `=>`)__           |                                             |
|                                             |                                             |                                             |
|          __Interface Merged Get__           |          __Interface Merged Set__           |                                             |
| ![](images/2.%20Interface%20Aspect.030.png) | ![](images/2.%20Interface%20Aspect.031.png) |                                             |
|        __Interface Merged Get `<=`__        |            __(Value Get `=>`)__             |                                             |
|            __(Value Set `=>`)__             |        __Interface Merged Set `<=`__        |                                             |

*(For the* __Interface Merged__ *commands the argument is a* __Boolean__*.)*

#### Explicit Get & Set Notation

Below you might find some examples of the *explicit Get and Set* notation working on the __Interface__ aspect.

![](images/2.%20Interface%20Aspect.032.png)

![](images/2.%20Interface%20Aspect.033.png)

#### Explicit Get & Set Arguments Notation

Below you find various notations where __Get__ and __Set__ arguments are explicitly drawn out, in which the __Interface__ aspect is addressed.

![](images/2.%20Interface%20Aspect.034.png)

![](images/2.%20Interface%20Aspect.035.png)

![](images/2.%20Interface%20Aspect.036.png)

![](images/2.%20Interface%20Aspect.037.png)

### Interface Connectors

Below you might find an overview of the possible connectors for the __Interface__ aspect and the __Interface Merged__ aspect.

|                                             |                                             |
|:-------------------------------------------:|:-------------------------------------------:|
|            __Use As Interface__             |       __Use Reference As Interface__        |
| ![](images/2.%20Interface%20Aspect.038.png) | ![](images/2.%20Interface%20Aspect.039.png) |
|                                             |                                             |
|              __Interface Set__              |                                             |
| ![](images/2.%20Interface%20Aspect.040.png) |                                             |
|                                             |                                             |
|          __Object-Interface Get__           |         __Reference-Interface Get__         |
| ![](images/2.%20Interface%20Aspect.041.png) | ![](images/2.%20Interface%20Aspect.042.png) |
|                                             |                                             |
|          __Interface Merged Get__           |          __Interface Merged Set__           |
| ![](images/2.%20Interface%20Aspect.043.png) | ![](images/2.%20Interface%20Aspect.044.png) |

### Interface Connections

Below you might find the possible connections for the __Interface__ aspect and the __Interface Merged__ aspect. A connection is the result of a call to a system command. However, the result of call to the __Interface Merged Set__ command is that the reference becomes a triangle or a circle shape. This result is also presented in this overview.

|                                             |                                             |
|:-------------------------------------------:|:-------------------------------------------:|
|            __Use As Interface__             |              __Interface Set__              |
| ![](images/2.%20Interface%20Aspect.045.png) | ![](images/2.%20Interface%20Aspect.046.png) |
|                                             |                                             |
|         __Interface Merged = True__         |        __Interface Merged = False__         |
| ![](images/2.%20Interface%20Aspect.047.png) | ![](images/2.%20Interface%20Aspect.048.png) |

### New Command with Interface Parameter

The __New__ command was introduced in the *System Interfaces* chapter, having an optional __Class__ parameter:

![](images/2.%20Interface%20Aspect.049.png)

But now also the __Interface__ can be specified upon creation of an object. This gives the __New__ command an extra implementation:

![](images/2.%20Interface%20Aspect.050.png)

Now the __New__ command’s __Interface__ parameter is filled in. The new object might have a fixed interface, but the object might not have a class. This means the __Publics__ are fixed by the interface, but an implementation is free to fill in.

You do not need to set both __Class__ and __Interface__ parameter of the __New__ method, because if the __Class__ parameter is set, it determines the __Interface__ too.

It is also not required to set either parameter, because that might create an empty object in which you can put arbitrary content, that is not bound to a class or interface at all.