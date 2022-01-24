Inheritance | Deeper Specialization
===================================

`[ Draft ]`

[back](./)

__Contents__

- [Introduction](#introduction)
- [Other Specialization Techniques](#other-specialization-techniques)
- [Deeper Exclusion](#deeper-exclusion)
- [Deeper Inclusion](#deeper-inclusion)
- [Deeper Member Addition](#deeper-member-addition)
- [Even Deeper Member Addition](#even-deeper-member-addition)
- [Deeper Shadowing](#deeper-shadowing)
- [Deeper Overriding](#deeper-overriding)
- [Deeper Command Extension](#deeper-command-extension)
- [Deeper System Command Extension](#deeper-system-command-extension)
- [Deeper System Command Overriding](#deeper-system-command-overriding)
- [Deeper System Command Shadowing](#deeper-system-command-shadowing)
- [The Deeper Specializations Structure](#the-deeper-specializations-structure)

## Introduction

The main concept of deeper specialization is that you can not only specialize direct members of an object, but you can also alter and extend members from deeper objects. A simple example is to exclude a member of a sub-object. Here is a normal object with a couple of public sub-objects:

![](images/4.%20Deeper%20Specialization.001.png)

Here is the same object inside another object which excludes one of its members, making it __Private__:

![](images/4.%20Deeper%20Specialization.002.png)

This makes it possible to create a simplified set of members for the sub-objects.

![](images/4.%20Deeper%20Specialization.003.png)

It is the higher parent object that imposes restrictions to access to the deeper objects. So the higher parent object might store those restrictions for deeper objects in a tree structure of __Deeper Specializations__. Even though this is something quite special, it still has a quite simple notation.

## Other Specialization Techniques

Specialization of deeper objects also applies to the other specialization techniques:

- Altering the Member Set:
- 
    - Member Addition
    - Member Exclusion (already covered)
    - Member Inclusion
  
- Detouring Members:

    - Overriding
    - Shadowing

- Altering Command Implementations:

    - Command Extension
    - System Command Extension
    - Overriding System Commands
    - Shadowing System Commands

These specialization techniques were already explained in the article *Specialization*. Here follow pictures of those situations in case of deeper specialization.

## Deeper Exclusion

![](images/4.%20Deeper%20Specialization.004.png)

## Deeper Inclusion

![](images/4.%20Deeper%20Specialization.005.png)

## Deeper Member Addition

Given the following situation:

![](images/4.%20Deeper%20Specialization.006.png)

If you want to add a member to __B__ that is only there when you access it through __A__, you replace __B__ by a new object, and let it object-inherit from the original __B__:

![](images/4.%20Deeper%20Specialization.007.png)

Now you can add any additional members to __A . B__:

![](images/4.%20Deeper%20Specialization.008.png)

## Even Deeper Member Addition

However, if the additional member might be added to an even deeper level, each level might be given a specialized version.

Take the following structure:

![](images/4.%20Deeper%20Specialization.009.png)

We want to add an extra member to __A__. However, we can not add them to object __A__ itself, because the members __A__ are defined inside an external class:

![](images/4.%20Deeper%20Specialization.010.png)

We might specialize each level that leads to object __A__, so first we specialize object __B__ by adding a new object __B__ giving it the original object __B__ as a base:

![](images/4.%20Deeper%20Specialization.011.png)

Then we do the same for object __A__: we add a new object __A__ to __B__, that has the original object __A__ as a base:

![](images/4.%20Deeper%20Specialization.012.png)

Now we can add members to __A__ without changing the configuration of base members:

![](images/4.%20Deeper%20Specialization.013.png)

There is one more thing we might do. There are now two members __A__ inside object __B__. We point out that the new object __A__ shadows the old object __A__ by means of a shading line:

![](images/4.%20Deeper%20Specialization.014.png)

## Deeper Shadowing

![](images/4.%20Deeper%20Specialization.015.png)

## Deeper Overriding

*Object reference notation:*

![](images/4.%20Deeper%20Specialization.016.png)

*Event notation:*

![](images/4.%20Deeper%20Specialization.017.png)

## Deeper Command Extension

![](images/4.%20Deeper%20Specialization.018.png)

## Deeper System Command Extension

![](images/4.%20Deeper%20Specialization.019.png)

## Deeper System Command Overriding

![](images/4.%20Deeper%20Specialization.020.png)

## Deeper System Command Shadowing

![](images/4.%20Deeper%20Specialization.021.png)

## The Deeper Specializations Structure

Some deeper specializations are registered inside the deeper objects themselves, such as command extensions and overriding. Here is overriding as an example:

![](images/4.%20Deeper%20Specialization.016.png)

The override is an object situated in the outer parent. The overridden member is a reference to the override, that resides inside the deeper object.

Some deeper specializations though, are not registered inside the deeper objects themselves. This is the case for member exclusions, member inclusion and shadowing. Here is shadowing as an example:

![](images/4.%20Deeper%20Specialization.015.png)

The shadowing of the deeper member is registered inside the outer parent. It might seem easier to just register a shadower inside the deeper object itself, but the problem is that the shadowing is specific to accessing the deeper object through the outer parent that defines the shadow. Through any other path, the deeper member is not shadowed.

To store shadowings, exclusions and inclusions, the outer parent contains a __Deeper Specializations__ structure, which is a parallel structure, parallel to the object structure inside the parent.

You can not *see* the __Deeper Specializations__ object in the diagram, but you do see its effect, because the specializations types each have a specific diagram notation.

![](images/4.%20Deeper%20Specialization.015.png)

The __Deeper Specializations__ structure is part of the system object, so the inner workings of an object. You get to see the inner workings of an object by opening up the interface:

![](images/4.%20Deeper%20Specialization.022.png)

Not all sub-objects are represented inside the __Deeper Specializations__ structure. Only as soon as a member gets specialized in a way that requires the __Deeper Specializations__ structure, the member gets a representation inside the __Deeper Specializations__ object. The exact implementation however, might depend on what offers best performance and efficiency.
