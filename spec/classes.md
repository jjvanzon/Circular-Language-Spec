<img src="images/classes-collage.png" width="700s" />

Classes
=======

*JJ van Zon, 2022*

[back](..)

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

The contents of an object may be *arbitrary*. Anything could be put inside an object:

<img src="images/Classes.001.png" width="200" />

But an object can also select another object to serve as its *class* or *prototype*.

A class might be considered a *special object*, a sort of *blue-print*, that aims to describe characteristics and behavior for other objects.

## Basic Notation

The basic notation in Circular for pointing out a class is as follows:

<img src="images/object-and-class.png" width="200" />

The *object* on the left points out the *class* on the right.

A *dashed line* between the circles points out a *class:*

<img src="images/dashed-line.png" width="130" />

A *line dissector* can indicate direction, sort of like an *arrow head:*

<img src="images/class-line-dissector.png" width="90" />

A *dashed circle* may represent a *class:*

<img src="images/dashed-circle.png" width="70" />

Classes can have *names:*

<img src="images/dashed-circle-with-label-my-class.png" width="70" />

## Structure vs Data

When an object has a class, the contents of that object might not be so arbitrary anymore:

<img src="images/Classes.004.png" width="250" />

An object initially shows contents *identical* to the class. An object might have the same *structure* as its class, but can have *data* that may be changed freely:

<img src="images/Classes.005.png" width="300" />

While the *structure* of the object is similar to the class, the *data* appears to have changed. *Values* of an object's *attributes* can change as well as *related objects*.

## Prototypes

Here is an alternative where a class is drawn with *solid lined* shape:

<img src="images/object-and-class-with-solid-lined-shape.png" width="200" />

Shapes with *dashed lines* might be *optional*.

But this notation could also be used for a distinction between classes and *prototypes:* where an object is initially a copy of another object, but anything may be changed about it, even its structure.

## Static Structure

Other parts of the static (or 'class') structure could be drawn with dashed lines too, to try and make a visual distinction between *static* structure and *object* structure:

<img src="images/Classes.009.png" width="325" />

The rules do not seem to be that precise when it comes to *shapes* drawn with different line styles. The rules for connecting *lines* are a bit stricter.

## Pointer to a Class

A class could be referenced like an *object*, using an *object line*. That establishes an *pointer to a class*:

<img src="images/pointer-to-class-solid-border.png" width="200" />

That *solid* line in the middle means it is a *pointer*.

Perhaps it will look neater if the *pointer to a class* is drawn with a *dashed shape* too:

<img src="images/pointer-to-class-dashed-border.png" width="225" />

(In .NET and C# these pointers to classes could for instance represent *type arguments* and *Type objects*.)

## Object Reference with a Class

Similar to an *object*, an *object reference* can also have a class. In that case merely objects of that class can be referenced.

<img src="images/object-reference-with-class-1.png" width="250" />

The __object reference__ points out __Class A__. The __object__ also points out __Class A__. The *solid line* between object and object reference is *valid*, because they have *the same* class.

<img src="images/object-reference-with-class-2.png" width="325" />

Now the __object reference__ still points out __Class A__. But the __object__ points out __Class B__ instead. The *solid line* is *not valid* anymore, because the object and the object reference have *different* classes.

## Object Reference without a Class

When an object reference does not have a class, this suggests the possibility to point to *any* object.

<img src="images/object-reference-without-class-1.png" width="325" />

The object reference *does not* point out a class. Therefor it can point at an object of *any* class. It points at an object, which so happens to be of *Class A*.

<img src="images/object-reference-without-class-2.png" width="325" />

Here the *Object* points out *Class B* instead of Class A. But since the *object reference* does not have a class, it can point to objects of *Class B* too.

## Conclusion

Hopefully this gave an impression of how *class* notation could look in the *Circular language*.

[back](..)