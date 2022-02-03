Classes
=======

*JJ van Zon, 2021*

[back](..)

__Contents__

- [Introduction](#introduction)
- [Optional Dashed Shape](#optional-dashed-shape)
- [Class Redirection](#class-redirection)
- [Using Dashed Shapes](#using-dashed-shapes)
- [Using an Object as a Class](#using-an-object-as-a-class)
- [Using a Class Like an Object](#using-a-class-like-an-object)
- [Object Reference with a Class](#object-reference-with-a-class)
- [Object Reference without a Class](#object-reference-without-a-class)
- [No Class != Defines its own Class](#no-class--defines-its-own-class)
- [Object Reference might define its Own Class?](#object-reference-might-define-its-own-class)
- [Dashed Shape](#dashed-shape)
- [Conclusion](#conclusion)

## Introduction

The contents of an object might be arbitrary. Anything may be put inside an object:

<img src="images/Classes.001.png" width="200" />

But an object might also select another object to serve as its *class* or *prototype:*

<img src="images/Classes.002.png" width="200" />

The *object* on the left points at its *class* on the right.

The *dashed line* between the circles expresses pointing out a *class:*

<img src="images/dashed-line.png" width="130" />

*Classes* may be drawn as *circles* with a *dashed border:*

<img src="images/dashed-circle.png" width="70" />

When an object has a class, the contents of that object may not be so arbitrary:

<img src="images/Classes.003.png" width="200" />

The object on the left has similar contents as the class on the right. At first an object seems to contain related items and related lists that roughly correspond with the class. The object might also have a similar set of commands as the class.

An object's behavior during its lifetime might be guided by rules set by this class. A class might be like a special object, that aims to describe characteristics and behavior of other objects.

Initially an object may look the same as its class. Changeable parts of an object might initially be set to what is drawn out in the class:

<img src="images/Classes.004.png" width="200" />

An object may have a similar *structure* as its class, but may have *data* that can change freely. Values of an object's attributes and might change as well as related objects:

<img src="images/Classes.005.png" width="200" />

While the structure of the larger circle at the left might be similar to the contents of the class on the right, the data appears to have changed.

## Optional Dashed Shape

A *class circle*'s being *dashed* might be *optional*. Here is an alternative where the class symbol on the right is drawn with a solid line:

<img src="images/Classes.006.png" width="200" />

## Class Redirection

`<< repetition >>`

In these diagrams an object might be used as a class or prototype for another object. That may be expressed in a diagram by connecting an object symbol to its class with a dashed line:

<img src="images/Classes.006.png" width="200" />

The object on the left might have the class on the right. An object’s pointing out its class, could be called *class redirection*. The usage of the dashed line might have a meaning here. *Dashed lines* might symbolize *classes*.

## Using Dashed Shapes

*Dashed shapes* might be used to denote classes:

<img src="images/Classes.007.png" width="100" />

But using dashed *shapes* might be optional. 

Here an object might be used as another object’s class:

<img src="images/Classes.006.png" width="200" />

The class on the right might be drawn out with a dashed line:

<img src="images/Classes.008.png" width="200" />

But it might be optional. 

Other parts of the static (or 'class') structure might be drawn with dashed lines too, to try and make a visual distinction between static structure and object structure.

<img src="images/Classes.009.png" width="200" />

The rules do not seem to be that precise when it comes to shapes drawn with different line styles. The rules for pointing lines might be a bit stricter: dashed might point out a class.

## Using an Object as a Class

Perhaps it might be familiar that an object might be stable in its role as a prototype or class. Dashed shape notation might be helpful as more specific in meaning: to indicate that it might just be a class.

To express an object's stable role as a class, a dashed line might be used to draw its symbol:

<img src="images/Classes.010.png" width="100" />

Here is a picture that might include an object circle with a class redirection:

<img src="images/Classes.008.png" width="200" />

But the Circular notation itself might include objects to serve as a class or prototype for another object:

<img src="images/Classes.011.png" width="200" />

## Using a Class Like an Object

With object references to a class, a type might be referenced like an object.

<img src="images/Classes.012.png" width="200" />

That the line in the middle might be *solid* might mean it is an object reference.

Or possibly this expresses it neatly:

<img src="images/Classes.013.png" width="200" />

## Object Reference with a Class

Similar to an *object* might have a class, an *object reference* might also have a class. Then merely objects of that class might be referenced.

<img src="images/Classes.014.png" width="200" />

The object reference on the left might point out its class on the right. The object at the bottom might also point out its class on the right. The solid line might be ok for the object reference to point to the object, since they seem to have the same class.

## Object Reference without a Class

When an object reference might not have a class, this might suggest the possibility to point to *any* object.

<img src="images/Classes.015.png" width="200" />

The 'untyped' object reference at the top-left might point to an object of any class. It seems to point to an object at the bottom, which appears to have a class, that the'untyped' object reference might not specifically refer to.

An interpretation might be that an 'untyped' object reference could take on the class of an object it may point to. So indirectly it might have a class.

## No Class != Defines its own Class

Something might have been unclear at one point. Objects might be usable as classes. It may be tempting to think that an object *without* a class might define *its* *own* class. It might be handy to not think of it that way, but think of it as object without a class simply not having a class. Having no class might suggest something might be arbitrary.

There may be examples where this might be a helpful concept.

## Object Reference might define its Own Class?

There may be other examples, but it might be unfortunate to think of an *object reference* as defining its own class. Because then the object reference may only point to … itself?

<img src="images/Classes.016.png" width="200" />

Instead of a 'stuck on itself' situation, it may be seen as an indication that something might be *arbitrary*.

<img src="images/Classes.015.png" width="200" />

## Dashed Shape

When a shape is used as a *class*, it might be drawn with a *dashed* border.
In *Circular* a class may also be referenced as an *object*.

<img src="images/Classes.019.png" width="200" />

Drawing a shape with a dashed border, might be optional though.

## Conclusion

Hopefully this might give an impression of how class notation might be used in the Circular language.

[back](..)