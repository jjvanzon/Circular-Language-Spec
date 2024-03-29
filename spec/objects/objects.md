﻿---
title: "Objects"
image: "images/objects-page.png"
description: "In object oriented programming, the object is one of the most basic elements of a computer program. It can represent a thing, an idea or a place, a number or a collection of other things or anything else."
keywords:
  - objects
  - object reference
  - nothing
  - null
  - multiplicity
  - circles
  - circular
  - circular language
  - shapes
  - boxes and arrows
  - code visualization
  - visualization
  - visual programming
  - visual programming language
  - VPL
  - diagrammatic programming language
  - diagram notation
  - diagrams
  - code map
  - object oriented programming
  - OO
  - OOP
  - programming
  - coding
  - computer programming
  - programming language
  - software engineering
  - software development
  - software design
  - software architecture
  - layered architecture
  - software
  - computers
---

Objects
=======

[back](../../)

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

In object oriented programming, the *object* is one of the most basic elements of a computer program. An object can represent a thing, an idea or a place, a number or a collection of other things or anything else.

In *Circular* an object is represented by a *circle:*

![](images/Objects.001.png)

Sub-Objects
-----------

One thing can be composed of other things. For that, an object may contain a number of *sub-objects*. This is drawn out as *circles* inside other *circles:*

![](images/Objects.002.png)

Object Reference
----------------

A sub-object can point to another object, residing elsewhere in the system. It is considered a link, redirecting to another object:

![](images/Objects.003.png)

The sub-object __A__ has a *line*, making it a reference. It connects *outward* of toward object __B__.

Reference to Parent
-------------------

This is an edge-case in object relationships: a *child* referencing a *parent:*

![](images/reference-to-parent.png)

The picture shows a child __B__. It has an *object reference* in it. It points to the parent __A__.

It might look a bit unusual compared to the object reference notation introduced earlier, so it seemed to deserve some separate attention here.

Nothing
-------

Sometimes nothing is filled in yet for a related object. To display that in a diagram, a *cross* is placed inside a shape:

![](images/Objects.004.png)

Multiplicity
------------

Multiplicity means the distinction between *single* and *multiple*. A related object can be a *single* object, but sometimes it is part of a *list*.

The concept of *single* is primarily displayed as a *circle:*

![](images/Objects.005.png)

But for a list, a spikey *nonagon* can be used:

![](images/Objects.006.png)

List items are then placed inside the nonagon:

![](images/Objects.007.png)

A list can be given a *name*, while its individual items may remain nameless:

![](images/list-named-with-3-items.png)

Conclusion
----------

So far this description, of different situations of programming with *objects*, and how they might look in a *Circular* diagram.

[back](../../)