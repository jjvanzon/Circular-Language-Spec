---
title: "Classes"
image: "images/classes-page.png"
description: "In software programming a class determines what type an object is. A class is a special object, a blue-print, describing behavior of other objects."
keywords:
  - classes
  - prototypes
  - static structure
  - class structure
  - structure
  - type arguments
  - type system
  - type safety
  - strongly typed
  - dynamic types
  - dashes
  - circular
  - circular language
  - code visualization
  - visualization
  - visual programming
  - visual programming language
  - VPL
  - diagrammatic programming language
  - diagram notation
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

Classes
=======

[back](..)

<img src="images/classes-collage.png" width="700" />

__Contents__

- [Introduction](#introduction)
- [Basic Notation](#basic-notation)
- [Structure vs Data](#structure-vs-data)
- [Prototypes](#prototypes)
- [Static Structure](#static-structure)
- [Pointer to a Class](#pointer-to-a-class)
- [Object Reference with a Class](#object-reference-with-a-class)
- [Object Reference without a Class](#object-reference-without-a-class)
- [Conclusion](#conclusion)

## Introduction

The contents of an object can be *arbitrary*. Anything can be put inside an object:

<img src="images/object-arbitrary-contents.png" width="200" />

But an object can also select another object to serve as its *class* or *prototype*.

That *class* determines what *type* of object it is. A class can be thought of as a *special object*, a sort of *blue-print*, that aims to describe characteristics and behavior for other objects.

## Basic Notation

The *basic notation* in Circular for pointing out a *class* is as follows:

<img src="images/object-and-class.png" width="200" />

The *object* on the left points out the *class* on the right.

A *dashed line* between the circles means that it points out a *class:*

<img src="images/dashed-line-horizontal.png" width="130" />

A *line dissector* can indicate *direction*, sort of like an *arrow head:*

<img src="images/class-line-dissector.png" width="90" />

The class can be drawn out as a *dashed circle* to make it extra clear it functions as a *class:*

<img src="images/dashed-circle.png" width="70" />

## Structure vs Data

When an object has a class, the contents of that object might not be so arbitrary anymore:

<img src="images/Classes.004.png" width="250" />

An object initially shows contents *identical* to the class. An object might have the same *structure* as its class, but can have *data* that may change freely:

<img src="images/Classes.005.png" width="300" />

While the *structure* of the object is still the same, the *data* appears to have changed. *Values* may freely change as well as which *related objects* it points to.

## Prototypes

An alternative notation is a class drawn with a *solid line* shape instead:

<img src="images/object-and-class-with-solid-lined-shape.png" width="200" />

Using shapes with *dashed lines* is sort of *optional*.

This solid line shape notation, might also be used for a distinction between classes and *prototypes:* where an object is initially a copy of another object, but anything may be changed about it, even its structure.

## Static Structure

To visually distinguish *static* structure from *object* structure, other parts of the static (or class) structure could be drawn with dashed lines too:

<img src="images/object-structure-and-class-or-static-structure.png" width="300" />

The rules are not that precise when it comes to *shapes* drawn with different line styles.

## Pointer to a Class

A class can be referenced like an *object*, using an *object line*. This establishes an *pointer to a class:*

<img src="images/pointer-to-class-solid-border.png" width="200" />

That *solid* line in the middle means it is a *pointer*.

Perhaps it would look neater if the pointer is drawn with a *dashed shape* too:

<img src="images/pointer-to-class-dashed-border.png" width="225" />

In .NET and C# these pointers to classes might represent *Type objects* and *type arguments*.

## Object Reference with a Class

Just like an *object*, an *object reference* can have a class as well. In that case merely objects of *that class* can be referenced:

<img src="images/object-reference-with-class-1.png" width="250" />

The __object reference__ points out __Class A__. The __object__ also points out __Class A__. The *solid line* between object and object reference is *valid*, because they both have *the same* class.

<img src="images/object-reference-with-class-2.png" width="325" />

Now the __object reference__ still points out __Class A__. But the __object__ points out __Class B__ instead. The *solid line* between shapes is *not valid* anymore, because they have *different* types.

## Object Reference without a Class

For an object reference that *does not* have a class, *any* object can be pointed at:

<img src="images/object-reference-without-class-1.png" width="325" />

The object reference *does not* point out a class. Therefore it can point at an object of *any* class. It points at an object, which so happens to be of *Class A*.

<img src="images/object-reference-without-class-2.png" width="325" />

Here the *Object* points out *Class B* instead of Class A. But since the *object reference* does not have a class, it can point to objects of *Class B* too.

## Conclusion

Hopefully this gave an impression of how *class* notation looks in the *Circular language*. Dashes seem to be key in its notation.

[back](..)