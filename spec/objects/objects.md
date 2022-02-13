Objects
=======

[back](../../)

*JJ van Zon, 2022*

<img src="images/objects-banner.png" width="700" />


__Contents__

- [Introduction](#introduction)
- [Sub-Objects](#sub-objects)
- [Object Reference](#object-reference)
- [Reference to Parent](#reference-to-parent)
- [Nothing](#nothing)
- [Multiplicity](#multiplicity)
- [Conclusion](#conclusion)

Introduction
------------

In object oriented programming, the *object* may be one of the most basic elements of a computer program. An object can represent a thing, an idea or a place, a number or a collection of other things or anything else.

An *object* in Circular is represented by a *circle:*

![](images/Objects.001.png)

Sub-Objects
-----------

One thing can be composed of other things. For that, an object may contain a number of *sub-objects*. This is drawn out in Circular as *circles* inside another *circle:*

![](images/Objects.002.png)

Object Reference
----------------

A sub-object can point to another object, residing elsewhere in the system. That sub-object is considered a link, redirecting to another object:

![](images/Objects.003.png)

The sub-object __A__ has a *line*, making it a reference, connecting to the object __B__, residing outside the __Parent__ object.

A line like that tends to point *outwards*.

Reference to Parent
-------------------

This may be an edge-case in object relationships: a *child* referencing a *parent:*

![](images/reference-to-parent.png)

The picture shows a child __B__, having an *object reference* in it, pointing to its parent __A__. It might look a bit unusual compared to the object reference notation introduced earlier, so it seemed to deserve some separate attention.

Nothing
-------

Sometimes nothing is filled in for a related object. To display that in a diagram a *cross* can be placed inside a shape:

![](images/Objects.004.png)

Multiplicity
------------

Multiplicity can be thought of as the distinction between *single* and *multiple*. A related object can be a *single* object, but sometimes it may be part of a *list*.

The concept of *single* is primarily displayed as a *circle:*

![](images/Objects.005.png)

But for a *list* a *nonagon* can be used:

![](images/Objects.006.png)

List items could be placed inside the nonagon again:

![](images/Objects.007.png)

A list can be given a *name*, while its individual items may remain nameless:

![](images/list-named-with-3-items.png)

Conclusion
----------

So far this description, of different situations of programming with *objects*, and how they might look in the *Circular language*.

[back](../../)