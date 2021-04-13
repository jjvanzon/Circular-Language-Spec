Encircle Language Spec
======================

System Objects
--------------

`[ Preliminary documentation ]`

__Contents__

- [Introduction](#introduction)
- [The System Objects](#the-system-objects)
    - [The Object](#the-object)
    - [The Reference](#the-reference)
    - [Related List](#related-list)
    - [Related List Item](#related-list-item)
    - [System Interface](#system-interface)
    - [Related Items & Related Lists Collections](#related-items--related-lists-collections)
    - [Reflective Data](#reflective-data)
    - [Reference in a System Interface](#reference-in-a-system-interface)
    - [Symbol](#symbol)
    - [System Object](#system-object)
    - [Summary](#summary)
- [System Aspects](#system-aspects)
    - [Object](#object)
    - [Class](#class)
    - [Interface](#interface)
    - [Value](#value)
    - [Execute](#execute)
    - [List](#list)
    - [Name](#name)
    - [Existence](#existence)
    - [Data](#data)
    - [Clone](#clone)
    - [Summary](#summary-1)
- [Object-Bound & Reference Bound Aspects](#object-bound--reference-bound-aspects)
- [System Interfaces & System Commands](#system-interfaces--system-commands)
    - [System Interface Notation](#system-interface-notation)
        - [Example: System Interface of an Object](#example-system-interface-of-an-object)
        - [System Commands](#system-commands)
        - [Aspects](#aspects)
        - [System Interface might be Publics of System Objects](#system-interface-might-be-publics-of-system-objects)
        - [Origin of the System Interface Notation](#origin-of-the-system-interface-notation)
    - [System Interface of an Object](#system-interface-of-an-object)
        - [Value Aspect in the System Interface](#value-aspect-in-the-system-interface)
        - [Execute Aspect in the System Interface](#execute-aspect-in-the-system-interface)
        - [Clone Aspect in the System Interface](#clone-aspect-in-the-system-interface)
        - [Data Aspect in the System Interface](#data-aspect-in-the-system-interface)
        - [Overview of a System Interface for an Object](#overview-of-a-system-interface-for-an-object)
    - [System Interface of a Related Item](#system-interface-of-a-related-item)
        - [Object Aspect in the System Interface](#object-aspect-in-the-system-interface)
        - [Existence Aspect in the System Interface](#existence-aspect-in-the-system-interface)
        - [Name Aspect in the System Interface](#name-aspect-in-the-system-interface)
        - [Overview of a System Interface for Related Item](#overview-of-a-system-interface-for-related-item)
    - [System Interface of a Related List](#system-interface-of-a-related-list)
    - [System Interface of a Related List Item](#system-interface-of-a-related-list-item)
        - [Related List Item’s List Aspect in the System Interface](#related-list-items-list-aspect-in-the-system-interface)
        - [Overview of a System Interface for Related List Item](#overview-of-a-system-interface-for-related-list-item)
    - [System Interface for the Class Aspect](#system-interface-for-the-class-aspect)
        - [Object-Bound Class Aspect in the System Interface](#object-bound-class-aspect-in-the-system-interface)
        - [Reference-Bound Class Aspect in the System Interface](#reference-bound-class-aspect-in-the-system-interface)
        - [Class may be both Object-Bound and Reference-Bound](#class-may-be-both-object-bound-and-reference-bound)
- [Misc Design Choices](#misc-design-choices)
    - [Aspect in a Triangle](#aspect-in-a-triangle)
    - ['Use' Command Gets Another Aspect](#use-command-gets-another-aspect)
    - [System Interfaces of Objects and References](#system-interfaces-of-objects-and-references)
    - [Performance Concerns?](#performance-concerns)
    - [Preliminariness of the System Interface Notation](#preliminariness-of-the-system-interface-notation)

### Introduction

This chapter tries to demonstrate internal workings of symbols in Encircle.

Encircle Language Spec's aim might be to show the *notation* of Encircle, but this chapter tries to look at the *internal* *workings* as if it were an actual program. In doing so, finer details of Encircle might start to show. Specifically, usages of the *system interface* notation might come to light.

This hypothetical implementation supposes, that systems might be composed of *system objects*. System objects might be *actual* objects that systems might be running on.

One of the purposes of system objects could be to manage *relationships* between objects.

A system object may also manage aspects of a symbol, like its *class*, whether it *executes* or if it stores a *value*. These aspects might be controlled through *system commands*.

*Assignment commands* may also be system commands. An assignment command might copy an aspect from one object to another.

The *System Interfaces* documentation might also show *connectors, connections* and other notational forms that might come with controlling these system aspects.

### The System Objects

#### The Object

In object oriented programming, an *object* might be considered the most basic element of a computer program. An object might represent a thing, an idea or a place, a number or a collection of other things or possibly anything else. All those things might be called objects.

![](images/1.%20System%20Objects.001.png)

#### The Reference

An object might not be directly accessed. We might frequently be dealing with *references* to objects instead.

![](images/1.%20System%20Objects.002.png)

A reference might put an object into context.

Synonyms might be:

- __Related Object__
- __Related Item__
- __Pointer__
- __Item__
- __Reference__
- __Object Reference__

#### Related List

Next to related items, a parent object might also contain *related lists*.

![](images/1.%20System%20Objects.003.png)

A related list might also be a related object, but perhaps a special one that might contain a scalable collection of other objects.

#### Related List Item

A related list may contain multiple *related list items*.

![](images/1.%20System%20Objects.004.png)

A related *list* item might be like a *related item*. What applies to related items might also apply to related *list* items. In some cases though, behavior may  be different.

#### System Interface

To see how objects and references might work internally, we might crack open the 'system interface':

![](images/1.%20System%20Objects.005.png)

"and a little further"

![](images/1.%20System%20Objects.006.png)

More may follow about this system interface notation later.

#### Related Items & Related Lists Collections

Inside the system interface an object’s related items and related lists might be stored as the object’s containing two collections: __Related Items__ and __Related Lists__. The __Related Items__ collection might contain the related items of an object. The __Related Lists__ collection might contain the related lists of an object.

![](images/1.%20System%20Objects.007.png)

#### Reflective Data

It might just be an arbitrary choice to specifically have a *related items* collection and a *related lists* collection under the hood of a symbol. It favors distinction between __1__ related item and __n__ related items.

There could be variations on that.

One variation might be: having a single related objects collection:

![](images/1.%20System%20Objects.008.png)

Lists might also be in the same collection. This single related objects collection might simply contain both lists and single items.

Another variation might add another collection:

![](images/1.%20System%20Objects.009.png)

Here next to __Related Items__, __Related Lists__ there might be __Attributes__: basically a collection of simple loose values an object might hold.

It might go on. A __Commands__ collection might be added for instance, to perhaps list sub-objects that are command symbols.

By now a suspicion might be, that it could be a quite arbitrary choice of collections.

An alternative could be that there is indeed one collection of related objects, but separate enumerators to retrieve related lists, related items, attributes and commands separately.

This 'under the hood' data might be called reflective data by some. There are other systems, where you can take a class and retrieve separate lists of properties and methods and for instance the ability to read out values or call methods. That idea might be closely related to this one here. That way you might tap into data more generically based on characteristics, rather than pointing out specific sub-objects.

#### Reference in a System Interface

A related item might be the result of a relationship. A related item might wrap a reference to a related object.

![](images/1.%20System%20Objects.010.png)

The inner-most object reference is like a raw pointer while the related item that surrounds it likes to decorate it with info like its class and procedures around it, like a retrieval procedure.

#### Symbol

The term *symbol* might be used as a synonym for related item or for object. But there might be a subtle difference that a symbol might just be a shape displayed on screen. The same related item could be displayed on screen multiple times.

![](images/1.%20System%20Objects.011.png)

But the difference might be too subtle to talk about. A symbol might not be a system object, it might just a shape displayed on screen.

#### System Object

The terms above indicate different kinds of *system objects*, except for maybe the term *symbol*.

#### Summary

All the objects in this imaginary implementation of Encircle might live as these system objects.

Here is a recap of terms introduced in this section:

- __Object__
- __Item__
- __Reference__
- __Object Reference__
- __Pointer__
- __Related Object__
- __Related Item__
- __Related List__
- __Related List Item__
- __Related Items & Related Lists Collections__
- __Reflective Data__
- __Symbol__
- __System Object__

### System Aspects

Behavior of objects, references and lists might be controlled by controlling their *aspects*. This section tries to list out various aspects that objects, references and lists might have. The pictures try to show a bit of each aspect’s symbolization.

#### Object

The __Object__ aspect may determine which object is pointed to.

![](images/1.%20System%20Objects.012.png)

#### Class

The __Class__ aspect might determine which other object might function as a prototype or class of another object. It can also bind a reference to a class.

![](images/1.%20System%20Objects.013.png)

#### Interface

The __Interface__ aspect might give control over how objects might look on the outside, while the insides of the objects may be different. The __Interface__ aspect may be covered in the *Interfaces* chapter, and might not be mentioned any further in this chapter.

![](images/1.%20System%20Objects.014.png)

#### Value

The __Value__ aspect might allow storing binary content and might allow yielding over values from one object to another.

![](images/1.%20System%20Objects.015.png)

#### Execute

The __Execute__ aspect might be about the ability to execute an object as a command.

![](images/1.%20System%20Objects.016.png)

#### List

The __List__ aspect may allow adding and removing items from a list.

![](images/1.%20System%20Objects.017.png)

#### Name

The __Name__ aspect may allow giving names to objects, lists and references.

![](images/1.%20System%20Objects.018.png)

#### Existence

The __Existence__ aspect might allow creating a new object. An object reference might also be annulled. Then it may point to nothing. Another option might be an ability to *check* whether an object reference "__Nothing__" or "__null__". 

![](images/1.%20System%20Objects.019.png)

#### Data

With the data aspect the idea is to control reading or writing access. Instead of being able to access-control a single object, the __Data__ aspect might control read-write access to all of the sub-objects as well.

![](images/1.%20System%20Objects.020.png)

#### Clone

The proposed __Clone__ aspect might be related to the __Value__ aspect, but might also copy values of sub-objects.

![](images/1.%20System%20Objects.021.png)

Its use might be that more than once there may be the desire to copy an object + its child values. 

#### Summary

Here is an attempt to list the aspects again:

- __Object__
- __Class__
- __Interface__
- __Value__
- __Execute__
- __List__
- __Name__
- __Existence__
- __Data__
- __Clone__

### Object-Bound & Reference Bound Aspects

When using *system aspects*, there seems to be a subtle phenomenon that some aspects might to be bound to an *object*, while other aspects may be bound to a *reference*.

Object-bound aspects might be determined by an object. An object might also control its sub-objects’ reference-bound aspects. Therefore *reference-bound* aspects might also be called *sub-object-bound* aspects.

The following aspects may be object-bound:

- __Value__
- __Class__
- __Execute__
- __Clone__
- __Data__
- __List__

The following aspects might be reference-bound (or *sub-object-bound*):

- __Object__
- __Existence__
- __Class__
- __Name__

The __Class__ aspect seems to be both object-bound as well as reference-bound. (The __Interface__ aspect might be too, but that topic might be dealt with later.)

The idea of object-bound aspects might help an object protect some of its characteristics and not be different depending on which reference points to it.

An object seems to control its object-bound aspects as well as its sub-objects’ reference-bound aspects.

### System Interfaces & System Commands

#### System Interface Notation

Sometimes an object's normal members might be shown:

![](images/1.%20System%20Objects.022.png)

In this hypothetical Encircle system, all objects might be system objects under the hood. This might include normal objects, object references and lists. They might all be system objects deeper down. An alternative to viewing the normal members like above might be for the members of a system object to be shown instead. This might be done by breaking open the inner workings of an object and show its *system interface*:

![](images/1.%20System%20Objects.023.png)

When a system interface is shown, normal members could be hidden, visible or maybe just part of them shown. The other way around, when normal members are shown, the system interface might be shown, not shown, or part visible.

##### Example: System Interface of an Object

An __Object__'s normal members might look like this:

![](images/1.%20System%20Objects.024.png)

But when the __Object__'s system interface might be opened, then for instance the __Related Items__ and __Related Lists__ collections might be shown instead:

![](images/1.%20System%20Objects.025.png)

The __Related Items__ and __Related Lists__ might be displayed as circles here: regular objects, even when they are *commands* and even when they are *lists*. It might be an alternative to display items with their original shape. More than one thing is possible. This new view with system members might be a representation of the way an __Object__ 'actually' internally works.

##### System Commands

System *commands* could be commands of system objects, through which aspects of objects may be controlled.

##### Aspects

Next to controlling *sub-objects*, a system interface might also control *aspects*, for instance, the __Value__ aspect:

![](images/1.%20System%20Objects.026.png)

Several aspects could be given __Get__ and __Set__ commands. But each aspect might be controlled in a different way.

##### System Interface might be Publics of System Objects

One idea that system interfaces may be based on, is that a system interface might be no more than public members of a system object. When this description here about system interfaces might be incomplete, what might be missing may be derived from the idea, that a system interface may simply show public members of a system object. Another idea derived from that could be that *private* workings of system objects might not be shown in a system interface. But these may be mere guidelines to have something to hold on to.

##### Origin of the System Interface Notation

The notation for a *system interface* may be derived from *interface* notation. When an object might have several interfaces, each interface might be shown as a triangle inside the object:

![](images/1.%20System%20Objects.027.png)

But showing a system interface might be like showing the interior of 'the symbol itself'. Therefore, the triangle of a system interface might be creatively stuck to the border of the symbol:

![](images/1.%20System%20Objects.005.png)

That way the interface might look more part of the object itself, rather than being a sub-object.

To make more room inside a system interface an exaggerated notation might be used:

![](images/1.%20System%20Objects.006.png)

It may also kind of look like the shell of a symbol is broken open and showing its inner workings. Like having opened up the system and we might see its internal wiring. It might be like seeing the setup of the symbol machine.

#### System Interface of an Object

One thing that might show when opening up a system interface of an __Object__ might be __Related Items__ and __Related Lists__ collections.

![](images/1.%20System%20Objects.025.png)

But apart from sub-objects, an object might have the following aspects:

- __Value__
- __Class__
- __Execute__
- __Clone__
- __Data__

They might be controlled through system commands. Those commands might be visible inside a system interface next to sub-object collections.

##### Value Aspect in the System Interface

The __Value__ aspect might be controlled through two system commands:

- __Get Value__
- __Set Value__

The __Value__ aspect might be represented by a triangle, that could wrap together members to control the __Value__ aspect:

![](images/1.%20System%20Objects.028.png)

__Get Value__ might get the value of an object.  
__Set Value__ might set the value of an object.

##### Execute Aspect in the System Interface

The __Execute__ aspect might only apply to executable objects, or 'commands'.  
The __Execute__ aspect might be controlled through one system command:

- __Execute__

The command might be placed inside a triangle, aiming to wrap together members of the __Execute__ aspect:

![](images/1.%20System%20Objects.029.png)

The __Execute__ command might be access controlled to prevent a command from being executed. Some commands may never be meant to execute, because they might be a definition.

It might be an idea that the __Execute__ aspect might go as far as to turn a regular object into a command and back. That may ask for more system members.

##### Clone Aspect in the System Interface

The __Clone__ aspect might be controlled through two system commands:

- __Get Clone__
- __Set Clone__

The __Clone__ aspect might be related to the __Value__ aspect, but might also copy sub-objects’ values.

The commands might be placed inside a triangle, that may wrap together members of the __Clone__ aspect:

![](images/1.%20System%20Objects.030.png)

__Get Clone__ might copy an object and its sub-objects.  
__Set Clone__ might assign cloned values to another object. This might also be a new object.

Both commands might have a parameter, that could define a cloning *depth*: the depth at which the sub-objects might be cloned. With a cloning depth of __2__, it might also be expressed as:

- __Get Clone (2)__
- __Set Clone (2)__

##### Data Aspect in the System Interface

The __Data__ aspect might be controlled with two system commands:

- __Get Data__
- __Set Data__

The commands might be placed inside a triangle, that could wrap together members of the __Data__ aspect:

![](images/1.%20System%20Objects.031.png)

The __Get Data__ and __Set Data__ command might not be called. They might only be access-controlled. This might control read-write access to an object and its contents: any sub-object or deeper object.

The __Get Data__ command might abstractly represent any *read*, which might mean: any possible __Get__ call to any sub-object. The __Set Data__ command might abstractly represent any *write* to any sub-object.

##### Overview of a System Interface for an Object

Here an attempt to visualize the system interface of an __Object__ and system members introduced so far:

![](images/1.%20System%20Objects.032.png)

#### System Interface of a Related Item

When opening up the system interface for a __Related Item__, it may show system commands that might apply to __Related Items__. Aspects, that could apply to a __Related Item__ may be:

- __Object__
- __Existence__
- __Class__
- __Name__

##### Object Aspect in the System Interface

The __Object__ aspect of a __Related Item__ might be controlled through several system commands:

- __Get Object__
- __Set Object__

Commands might be placed inside a triangle, that may wrap together members of the __Object__ aspect:

![](images/1.%20System%20Objects.033.png)

__Get Object__ might retrieve the targeted object of a reference.  
__Set Object__ may change an object reference target.

##### Existence Aspect in the System Interface

The __Existence__ aspect might be controlled through the following system commands and an attribute:

- __New__
- __Annul__
- __Is Something__

Members might be placed inside a triangle, that could wrap together members of the __Existence__ aspect:

![](images/1.%20System%20Objects.034.png)

The __New__ command might have an optional __Class__ argument, which might indicate the class from which the object might be created.

There might also be a system attribute __Is Something__ which might say __True__ or __False__, which might also be represented by the terms __Something__ or __Nothing__.

##### Name Aspect in the System Interface

The __Name__ aspect might be controlled through two system commands:

- __Get Name__
- __Set Name__

The commands might be placed inside a triangle, that might wrap together members of the __Name__ aspect:

![](images/1.%20System%20Objects.035.png)

- __Get Name__ might get the name of a reference or list.
- __Set Name__ might set the name of a reference or list.

##### Overview of a System Interface for Related Item

Here an attempt to visualize the system interface of a __Related Item__ and system members introduced so far:

![](images/1.%20System%20Objects.036.png)

#### System Interface of a Related List

When opening up the system interface for a __Related List__, it may show system commands applying to __Related Lists__:

![](images/1.%20System%20Objects.037.png)

The system interface of a __Related List__ might show the __Add__ command. The __Add__ command may have an optional __Item__ argument, to maybe add an existing item to a list.

But more members may be introduced later. Specifically something to desire might be to centrally fix the __Class__ aspect of all the items in a list.

The __List__ aspect might apply to __Related Lists__. The __List__ aspect may be controlled through the following system commands:

- __Add__
- __Remove__

The __Add__ command may be part of a __List__ object. The __Add__ command might add an item to a list. This may be an existing item, passed through an optional argument __Item__. A new item might also be created for it using the __New__ command part of the __Existence__ aspect.

The __Remove__ command may be part of a __Related List Item__. It removes that item from its list.

#### System Interface of a Related List Item

When opening up the system interface for a __Related List Item__, it may show system commands applying to __Related List Items__. Aspects, that might apply to a __Related List Item__ could be:

- __Object__
- __Existence__
- __Class__
- __List__

Those might be similar to a __Related Item__, minus the __Name__ aspect, plus the __List__ aspect. Only the __List__ aspect for a __Related List Item__ might be described here. Other aspects may find their descriptions where __Related Item__ system commands were illustrated.

##### Related List Item’s List Aspect in the System Interface

The __List__ aspect of a __Related List Item__ may be represented by the following system members:

- __Remove__
- __List__

Members might be placed inside an interface triangle, that might wrap together members of the __List__ aspect:

![](images/1.%20System%20Objects.038.png)

The __Remove__ command might remove an item from a list.  
The __List__ member might be a reference to the List that a related item might be part of.

##### Overview of a System Interface for Related List Item

A __Related List Item__ might be similar to a __Related Item__, so a more complete system interface of a __Related List Item__ might show a similar set of aspects and might look as follows:

![](images/1.%20System%20Objects.039.png)

#### System Interface for the Class Aspect

The __Class__ aspect might have a bit more to say about it than other aspects.

##### Object-Bound Class Aspect in the System Interface

The __Class__ aspect might have several system commands, but two of them might apply to *objects*. Other ones might apply to *references*. The __Class__ aspect of an __Object__ might be controlled through the following commands:

- __Use As Class__
- __Get Object-Bound Class__

Commands might be placed inside a triangle, that might wrap together members of the __Class__ aspect:

![](images/1.%20System%20Objects.040.png)

__Use As Class__ might be like __Get Object__, but then for using that object as a class of another object. This may be a common usage of the class aspect. The separate system command __Use As Class__, might also be used to separately access control whether an object might be used as a class or not.

The command __Get Object-Bound Class__ may return the class object associated with an object. That command might not be used as commonly.

##### Reference-Bound Class Aspect in the System Interface

The __Class__ aspect may have several system commands, but the following two may apply to references:

- __Set Class__
- __Get Reference-Bound Class__

Commands might be placed inside a triangle, that might wrap together members of the __Class__ aspect:

![](images/1.%20System%20Objects.041.png)

The __Set Class__ command might be executed on an object reference. That reference might then only point to objects of that class. In the hypothetical system here __Set Class__ might apply only to references and possibly not to objects, because the class of an object might only be set upon creation.

The command __Get Reference-Bound Class__ may return the class object associated with the object reference. That command might not be used as commonly.

##### Class may be both Object-Bound and Reference-Bound

The __Class__ aspect might apply to both objects and references, but differently. In the example system imagined here, an object could have a certain class, that might be fixed throughout its lifetime:

![](images/1.%20System%20Objects.042.png)

It might have beem fixed upon creation of the object:

![](images/1.%20System%20Objects.043.png)

In this example system, the class of an object might never change.

A *reference* also could have a class, aiming to indicate which class of object it might point to.

![](images/1.%20System%20Objects.044.png)

When the reference might be __Nothing__ or __null__, any class might be assigned to the reference.

![](images/1.%20System%20Objects.045.png)

Both line __a__ and __b__ might both be possible.

The class of a reference might be changed, but only when it might be compatible with the object assigned to the reference. 

The __Object-Bound Class__ and __Reference-Bound Class__ could point to the same class.

![](images/1.%20System%20Objects.046.png)

The __Reference-Bound Class__ could also be a base class or an interface of the __Object-Bound Class__.

![](images/1.%20System%20Objects.047.png)

### Misc Design Choices

#### Aspect in a Triangle

An aspect might be represented by a triangle that could contain system commands:

![](images/1.%20System%20Objects.048.png)

It was a design choice to have system commands placed inside a triangle, that might represent an aspect. That way __Use As Class__ for instance might be used without putting __"Class ."__ or __"Object . "__ in front of it.

An alternative was putting it in a circle, which might make textual alternatives of commands be something like:

- __Class . Use As Class__
- __Class . Use Object As__ 
- __Object . Use As Class__

Those might all be alternatives for __Use As Class__. The idea is that this might not look as nice as just __Use As Class__.

The alternative __Object . Use As Class__ might look ok, but may place this class-related action inside the __Object__ aspect, which might not be desirable either.

So this way __Use As Class__ might be used directly instead.

This is just a design choice. It could have ended up being different.

#### 'Use' Command Gets Another Aspect

A __Use As Class__ command might be made part of the __Class__ aspect while it may __Get__ the __Object__ aspect.

![](images/1.%20System%20Objects.048.png)

A __Use__ command may __Get__ a different aspect than what it applies to. A __Use As Class__ command might be part of the __Class__ aspect but might __Get__ the __Object__ aspect.

An alternative could have been to put __Use As Class__ in the __Object__ aspect. But __Use As Class__ seems the primary use of the __Class__ aspects, so to put it in the __Object__ aspect might not be desirable.

How a __Use__ command might delegate to a __Get__ command might not be visible in a system interface, due to its being private implementation. Only public members of a system object might be shown, not its implementation.

#### System Interfaces of Objects and References

There could be system commands that may apply to __Objects__ and system commands that may apply to __References__, but when showing the system interface of a symbol, which of the two might be shown? The system interface of the __Object__ or the system interface of the __Reference__?

![](images/1.%20System%20Objects.049.png)

A solution might be that it is usually *references* to objects that are dealt with, not usually an object directly, so opening up the system interface of a symbol, the system interface of the __Reference__ might be shown. However, inside of it you might find the referenced __Object__, showing its system interface.

![](images/1.%20System%20Objects.050.png)

Different choices could be made here. Perhaps a distinction between __Reference__ and __Object__ might not be relevant for aspects that have no overlap. The __Class__ aspect may be specificied separately for an __Object__ and an __Reference__, for which a distinct notation might be desired. Perhaps it might be practical to keep most aspects one level deep. There are options and they might all be ok.

#### Performance Concerns?

Someone might wonder critically if Encircle could run fast if running on these heavy weight system objects, instead of a regularly compiled code. One option might be that these system objects could function as a certain interpreted mode, that might compile / optimize into faster machine code. System objects might be an intermediate format of some sort. Perhaps a similar distinction as text code and machine code can be seen here.

#### Preliminariness of the System Interface Notation

The system interface notation's basics might not be preliminary. But the content of a system interface might not be precisely as specified in this documentation. One idea is that Encircle might run on system objects proposed here. And that depending on how these system objects are implemented precisely, the public members of a system object could form the content of a system interface. Design choices were made in this documentation, which can influence the notation of system interface members. But hopefully it shed light on the kind of things the system interface might be used for, what roles it might play and its notation basics.
