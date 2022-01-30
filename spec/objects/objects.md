Objects
=======

*JJ van Zon, 2021*

[back](../../)

__Contents__

- [Introduction](#introduction)
- [Sub-Objects](#sub-objects)
- [Object Reference](#object-reference)
- [Nothing](#nothing)
- [Multiplicity](#multiplicity)
    - [Reference to Parent](#reference-to-parent)

## Introduction

In object oriented programming, an *object* might be considered the most basic element of a computer program. An object may represent a thing, an idea or a place, a number or a collection of other things or possibly anything else. All those things might be called objects.

An object in a diagram may be represented by a circle:

![](images/Objects.001.png)

## Sub-Objects

One thing might be composed of other things. For that, an object may contain a number of *sub-objects*. This might be drawn out in a diagram as circles inside another circle.

![](images/Objects.002.png)

## Object Reference

Another possibility is a sub-object pointing to another object, that resides elsewhere in the system. That way an existing object may serve as another object’s sub-object. In that case that sub-object might be considered a link or reference, that could redirect to another object. Such an object reference may also be called a *pointer*.

The following picture tries to show a sub-object that may depict an object reference. It might be pointing to an object elsewhere.

![](images/Objects.003.png)

That sub-object's symbol may be given a line here, connected to the symbol that might represent the actual object, which may reside outside the parent object. Sub-object __A__ might be a reference to object __B__. It may be a notational choice, that the direction might point outwards.

## Nothing

Sometimes nothing may yet be filled in for a related object. To display that in the diagram a cross might be placed inside the shape:

![](images/Objects.004.png)

An object reference may then be *Nothing* or *null*. Shapes *other* than circles might also be given a cross drawn inside it, to indicate it is empty.

## Multiplicity

A simplified description of multiplicity may be that it is the distinction between *single* and *multiple*. A related object might be a *single* object, but objects may also be part of a *list*.

A single related object might hold a reference to one object. But the reference may not be filled in yet. Then it might point to no object at all. Therefore, it may be said that it might have a multiplicity of between 0 and 1. But for short it could be called multiplicity 1. A list may contain zero or more objects. In that case the multiplicity might be between 0 and n. For short it may be called just n.

In case of a single item this might be displayed in a diagram as a circle:

![](images/Objects.005.png)

In case of a *list* this may be displayed in a diagram as a 'nonagon':

![](images/Objects.006.png)

List items might be placed inside the nonagon again:

![](images/Objects.007.png)

It may be an option to give the list a name, while its individual items may remain nameless.

### Reference to Parent

This may be an edge-case in object relationships: a *child* referencing a *parent*:

![](images/reference-to-parent.png)

The picture shows a child __B__ having an object reference in it, pointing to its parent __A__. It may look a bit unusual compared to the object reference notation introduced earlier, so it seems to deserve some separate attention.

[back](../../)