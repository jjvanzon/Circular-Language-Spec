Objects
=======

*JJ van Zon, 2021*

[back](../../)

__Contents__

- [Introduction](#introduction)
- [Sub-Objects](#sub-objects)
- [Object Reference](#object-reference)
- [Reference to Parent](#reference-to-parent)
- [Nothing](#nothing)
- [Multiplicity](#multiplicity)

Introduction
------------

In object oriented programming, an *object* might be considered the most basic element of a computer program. An object can represent a thing, an idea or a place, a number or a collection of other things or anything else. All those things may be called objects.

An *object* in Circular is represented by a *circle:*

![](images/Objects.001.png)

Sub-Objects
-----------

One thing can be composed of other things. For that, an object may contain a number of *sub-objects*. This would drawn out in Circular as circles inside another circle:

![](images/Objects.002.png)

Object Reference
----------------

A sub-object can point to another object, residing elsewhere in the system. That way an existing object serves as another object’s sub-object. That sub-object is considered a link or reference, redirecting to another object.

The following picture shows a sub-object that has an object reference. It points to an object elsewhere:

![](images/Objects.003.png)

Sub-object __A__ is a reference to object __B__. Sub-object's symbol __A__ has a line, connecting to the object __B__, that resides outside the __Parent__ object.

The direction of a line tends to point outwards, as a notational choice in Circular.

Reference to Parent
-------------------

This may be an edge-case in object relationships: a *child* referencing a *parent*:

![](images/reference-to-parent.png)

The picture shows a child __B__, having an object reference in it, pointing to its parent __A__. It might look a bit unusual compared to the object reference notation introduced earlier, so it seemed to deserve some separate attention.

Nothing
-------

Sometimes nothing is filled in for a related object. To display that in the diagram a cross is placed inside a shape:

![](images/Objects.004.png)

Multiplicity
------------

Multiplicity can be thought of as the distinction between *single* and *multiple*. A related object can be a *single* object, but objects may also be part of a *list*.

*Single* is primarily displayed in a diagram as a *circle*:

![](images/Objects.005.png)

But in case of a *list* a *'nonagon'* is used:

![](images/Objects.006.png)

List items would be placed inside the nonagon again, as circles:

![](images/Objects.007.png)

A list can be given a name, while its individual items may remain nameless:

![](images/list-named-with-3-items.png)

[back](../../)
