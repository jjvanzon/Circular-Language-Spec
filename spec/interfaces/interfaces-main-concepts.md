﻿Interfaces | Main Concepts
==========================

`[ Draft ]`

[back](./)

__Contents__

- [Introduction](#introduction)
- [Interface = Publics](#interface--publics)
- [Interface & Implementation](#interface--implementation)
- [Interface = Objects Melting Together](#interface--objects-melting-together)
- [Interface = Contract](#interface--contract)
- [Multiple Interfaces](#multiple-interfaces)
- [Interface Type Control](#interface-type-control)
- [Explicit Interfaces](#explicit-interfaces)
- [Implicit Interfaces](#implicit-interfaces)
- [Polymorphism](#polymorphism)
- [Interface Object Resolution](#interface-object-resolution)
- [Inheritance](#inheritance)
- [Main Usages of Contracts](#main-usages-of-contracts)
- [Command Interfaces](#command-interfaces)
- [Target Interfaces](#target-interfaces)
- [Interface Referencing and Redirecting](#interface-referencing-and-redirecting)
    - [Interface Reference](#interface-reference)
    - [Command Class Interface](#command-class-interface)
    - [Class Command Interface](#class-command-interface)
    - [Command Definition Interface Redirection](#command-definition-interface-redirection)
    - [Command Reference Interface Redirection](#command-reference-interface-redirection)
    - [Command Call Interface Redirection](#command-call-interface-redirection)
    - [Active Nested Command Interface Redirection](#active-nested-command-interface-redirection)
    - [Inactive Nested Command Interface Redirection](#inactive-nested-command-interface-redirection)
- [Relations Through Interfaces](#relations-through-interfaces)

## Introduction

Up till now the idea of interfaces was fully left out of the stories. This chapter makes the concept of interfaces catch up with the rest of the documentation. The basic concept of interfaces is covered along with its diagram notation. Also covered are: interface assignment, interface reference and relations that form through the use of interfaces. Another concept, yet to be worked out, is how commands of an object are grouped by site: an object can have commands, defined on different sites, and the commands should be grouped by site in order to judge how reliable the commands are *(grouped by source)*. As interfaces can be applied to objects, but interfaces can also be applied to *commands*.

At some point the idea was, to also cover all the different *uses* of interfaces. But the different uses of interfaces are adequately described by other literature. The focus might lie on explaining the raw concept of interfaces and their presence in Circular.

The main concepts of interfaces are explained here along with their diagram notations.

## Interface = Publics

An object’s interface consists of all of its public members.

![](images/1.%20Interfaces%20Main%20Concepts.001.png)

## Interface & Implementation

An interface defines an object’s public members. The *private* contents of an object are called the object’s *implementation*. So the concept of interfaces offers the ability to separate publics from private contents, in other words separate interface from implementation.

*Object:*

![](images/1.%20Interfaces%20Main%20Concepts.002.png)

*Interface:*

![](images/1.%20Interfaces%20Main%20Concepts.001.png)

*Implementation:*

![](images/1.%20Interfaces%20Main%20Concepts.003.png)

## Interface = Objects Melting Together

Another concept which employs the word *interfaces*, is an object (an interface) melting together with its container.

This is displayed in the diagram by a triangle that represents an interface object.

![](images/1.%20Interfaces%20Main%20Concepts.004.png)

The members of the triangle are accessible as if they are members of the large circle.

## Interface = Contract

Interfaces also offer the functionality of being a contract.  
You can establish this by defining the interface externally.

![](images/1.%20Interfaces%20Main%20Concepts.005.png)

If an object has its interface defined externally, the public contents of the object can not be freely changed. If the interface of the object needs to change, the externally defined interface needs to be changed.

## Multiple Interfaces

If you want an object to support multiple contracts you can use several triangles inside the object and define their interfaces externally.

![](images/1.%20Interfaces%20Main%20Concepts.006.png)

## Interface Type Control

Interface type control should for instance occur when you reference an object and the reference has the wrong interface. Restrictions might then be enforced.

![](images/1.%20Interfaces%20Main%20Concepts.007.png)

The situation above is not valid, because the reference might not have the same interface as the object it points to.

## Explicit Interfaces

You can speak of an explicit interface when you externally define a sub-object’s interface, you but do not let the sub-object melt together with the container.

![](images/1.%20Interfaces%20Main%20Concepts.008.png)

A reference to the parent can not automatically resolve to a reference to the interface. It requires you to refer to the interface directly in order to access it.

## Implicit Interfaces

You can speak of an implicit interface when you externally define a sub-object’s interface, but you do let the sub-object melt together with the container.

![](images/1.%20Interfaces%20Main%20Concepts.009.png)

You can reference members of the interface directly through the circle, without explicitly mentioning which interface you are accessing (see *Interface Object Resolution*).

## Polymorphism

A triangle’s difference with a circle is that triangles basically melt together with their container.

![](images/1.%20Interfaces%20Main%20Concepts.004.png)

Next to all members of the triangle being accessible as if they were members of the parent circle, the container can also be referred to as if it has the type of the triangle. That is another effect of melting the objects together.

## Interface Object Resolution

Interface object resolution happens when you reference an object and the reference has an interface defined, that the object supports. It automatically redirects the reference to the specific interface of the object.

![](images/1.%20Interfaces%20Main%20Concepts.010.png)

It is about the bit of dotted line denoted by the arrow. This is an automatic extension of the solid line on the left. Because the the reference (__R__) on the left has an externally defined interface (__I__) on the right, and the object (__O__) supports this interface, the reference’s line is automatically redirected to this particular interface of the object. Automatic redirections like that are called *object resolution*.

There are a lot of other object resolution concepts related to interfaces and inheritance, such as overriding and shadowing, but they might be covered separately in the *Object Resolution* chapter.

The situation above only works in case of implicit interfaces.  
It also might not work when the same interface is defined twice. If it is, you might refer to the interface explicitly.

Below is another example of interface object resolution, but now in case of referencing a member of the interface, while not explicitly accessing the interface:

![](images/1.%20Interfaces%20Main%20Concepts.011.png)

Again it is about the dotted piece of line in between, which expresses the automatic object resolution. Next to the picture is a bit of pseudo-code that expresses how reference __A__ points to __D__ without qualifying it with interface __C__.

## Inheritance

Traditional inheritance is related to the concept of interfaces. What happens is that an object melts together with its container and next to its interface being defined externally, the implementation is also defined externally. The result is classic inheritance: one object takes over all characteristics of another object.

![](images/1.%20Interfaces%20Main%20Concepts.012.png)

So because the triangle has an externally defined class (dashed line) instead of an externally defined interface (dotted line) the situation turns from implicit interface into classic inheritance. In the situation above one object inherits from another object. Expressing it more like one class inheriting from another class it might look as follows:

![](images/1.%20Interfaces%20Main%20Concepts.013.png)

Classic inheritance is not the only form of inheritance in Circular. Different forms of inheritance are covered separately in the chapter *Inheritance*, but it is important to point out here, that classic inheritance and interfaces are closely related.

## Main Usages of Contracts

When you externally define an interface, it becomes a contract. You can creatively use this concept for any purposes, but some of those purposes deserve to be pointed out explicitly.

It can be a contract of a *guarantee* to support a sure set of members. So this offers a guarantee to ones that might be using the object. So you know an object has *at least* those members with that exact configuration.

An interface can also serve as a contract of *usage*. This means, that an object has *exactly* the members defined by the interface. So now someone using the object might only be able to use it in an exactly defined way.

A powerful application of such a contract, is the interface as a contract of *participation*. You can give a type an already defined interface. That allows objects that can work with a certain interface, to link to objects of the new type, even when the system was not originally aware of that type. This concept makes it possible to introduce new types of objects into a system, that was not originally aware of them.

## Command Interfaces

This article is here to point out that commands can have interfaces just like objects. A command having an interface approximates the same functionality as C++ function prototypes or delegates in .NET. Only in Circular much more is possible. Because a command is an object, any interface concept is applicable to commands as well.

Here is your basic function prototype concept expressed in a Circular diagram:

![](images/1.%20Interfaces%20Main%20Concepts.014.png)

Here is the example when the command has a paramater.

![](images/1.%20Interfaces%20Main%20Concepts.015.png)

The implementation of the command can be different from its function prototype:

![](images/1.%20Interfaces%20Main%20Concepts.016.png)

But this was classic C++ function prototype. Circular has more possibilities when it comes to command interfaces, some of which are displayed below.

Command inheritance:

![](images/1.%20Interfaces%20Main%20Concepts.017.png)

Multiple command interfaces:

![](images/1.%20Interfaces%20Main%20Concepts.018.png)

So basically anything regarding interfaces that can be done with objects, can also be done with commands.

## Target Interfaces

The *target interface* is found by following a number of redirections to find the actual interface object that the publics of an object are based on.

To find the target interface, you first follow *all* the object redirections, then a maximum of *one* class redirection, then *all* the object redirections again, then a maximum of *one* interface redirection and then *all* object redirections again, and there it ends.

![](images/1.%20Interfaces%20Main%20Concepts.019.png)

Here is an example where there are no class lines involved:

![](images/1.%20Interfaces%20Main%20Concepts.020.png)

If the interface has an interface as well, this might not redirect the original object’s interface, because the second interface is *another* interface object, that the first interface is just *based* on. An object redirection is just a much tighter bond, than a class or interface redirection.

![](images/1.%20Interfaces%20Main%20Concepts.021.png)

The target interface of the object reference is the symbol __Interface__, not the symbol __Interface’s interface__. So you should not follow more than *one* interface redirection to get to the interface object.

You should also not follow more than *one* class redirection to find the target interface. If the class has again a class which has an interface, the first class might not have an interface defined at all:

![](images/1.%20Interfaces%20Main%20Concepts.022.png)

The last symbol __Class’s class’s interface__ is only the interface of __Class’s class__, not the interface of __Class__. So __Class__ is where the interface redirections end.

Also, you should follow one class redirection and one interface redirection *in that order*. Here is a less logical example, in case of which you do not follow the last class redirection:

![](images/1.%20Interfaces%20Main%20Concepts.023.png)

The last symbol may eventually *define* the interface, but it is still __Interface__ which is the __Object reference__’s interface object.

(Elsewhere you may find 'Loose Ideas about Target Interfaces' that may or may not be used as inspiration of extension/replacements of some of the content here.)

## Interface Referencing and Redirecting

This article contains examples of what different interface referencing and redirecting situations might look like in a diagram and what name we could give to this situation.

### Interface Reference

An object’s specification of which interface it has, is also called an *interface reference*.

![](images/1.%20Interfaces%20Main%20Concepts.024.png)

### Command Class Interface

![](images/1.%20Interfaces%20Main%20Concepts.025.png)

### Class Command Interface

![](images/1.%20Interfaces%20Main%20Concepts.026.png)

### Command Definition Interface Redirection

![](images/1.%20Interfaces%20Main%20Concepts.027.png)

### Command Reference Interface Redirection

![](images/1.%20Interfaces%20Main%20Concepts.028.png)

### Command Call Interface Redirection

![](images/1.%20Interfaces%20Main%20Concepts.029.png)

### Active Nested Command Interface Redirection

![](images/1.%20Interfaces%20Main%20Concepts.030.png)

### Inactive Nested Command Interface Redirection

![](images/1.%20Interfaces%20Main%20Concepts.031.png)

## Relations Through Interfaces

The most fundamental relation is a relation between two objects: one object contains a reference to another object, and the other object contains a reference back to the first object.

![](images/1.%20Interfaces%20Main%20Concepts.032.png)

Classes can put control on which other class they are related to.

![](images/1.%20Interfaces%20Main%20Concepts.033.png)

The effect is that in an object of that class, a specific reference can only point to an object of a specific other class.

![](images/1.%20Interfaces%20Main%20Concepts.034.png)

This is merely type re-enforcement. The picture below shows the classes in a bidirectional relation.

![](images/1.%20Interfaces%20Main%20Concepts.035.png)

The example above illustrates what we call a relation between two classes. This relation between classes can be *‘felt’* throughout the object structure and is ultimately *defined* inside the classes.

Relations through interfaces is the same concept but now applied to interfaces. There are two possibilities.

The first possibility is that a class defines the interface of one of its references.

![](images/1.%20Interfaces%20Main%20Concepts.036.png)

In that case it is said to be a relation between a class and an interface.

An interface can very well have a relation back to the class.

![](images/1.%20Interfaces%20Main%20Concepts.037.png)

The effect of it is that objects that have that class or interface can only refer to an object of that a specific interface or class.

![](images/1.%20Interfaces%20Main%20Concepts.038.png)

The second possibility is that an interface defines the interface of one of its references. And the other interface defines the relation back. 

![](images/1.%20Interfaces%20Main%20Concepts.039.png)

In that case it is said to be a relation between two interfaces. The effect of that is, that in objects with that interface, a specific public reference can only point to an object with that specific other interface.

![](images/1.%20Interfaces%20Main%20Concepts.040.png)

That is all there is to it. Relations between classes and interfaces are sheer type-control on the relations between objects. Also, the mutual references are kept in sync, so that the two references always mutually point to each other and not to anything else (that’s what the ring is for).

If multiple classes support the same interface, this is what we traditionally see as relations through interfaces. It actually creates an *indirect* relation between classes.

![](images/1.%20Interfaces%20Main%20Concepts.041.png)

In the picture above __A__ and __C__ are related through interfaces from a traditional point of view, but they are only not directly related in reality. They are only related through __B__.

(Elsewhere you may find 'Loose Ideas about Relations Through Interfaces' that may or may not be used as inspiration of extension/replacements of some of the content here.)