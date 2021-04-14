Encircle Language Spec | Inheritance
====================================

Enforcing & Preventing Specialization
-------------------------------------

`[ Preliminary documentation ]`

__Contents__

- [Introduction](#introduction)
- [Protected](#protected)
- [Overriding](#overriding)
- [Optional / Required](#optional--required)
- [Requirements for Other Side of Connection](#requirements-for-other-side-of-connection)
- [Gut Feeling](#gut-feeling)
- [Applied to Concepts from Other Languages](#applied-to-concepts-from-other-languages)
- [Protected](#protected-1)
- [Virtual](#virtual)
- [Abstract Member](#abstract-member)
- [Abstract Class](#abstract-class)
- [Sealed / Final Class](#sealed--final-class)
- [Interface / Interface Member](#interface--interface-member)
    - [Rule 1: Interfaces are Abstract](#rule-1-interfaces-are-abstract)
    - [Rule 2: Interface Members are Abstract](#rule-2-interface-members-are-abstract)
    - [Rule 3: Interfaces can not Have an Implementation](#rule-3-interfaces-can-not-have-an-implementation)
    - [Gruesome](#gruesome)
- [Non-Overridable](#non-overridable)
- [More Combinations](#more-combinations)
- [Courtesy](#courtesy)
- [Enforcing & Preventing Other Specialization Methods](#enforcing--preventing-other-specialization-methods)
- [Preventing Pre-Extension with Cancellation](#preventing-pre-extension-with-cancellation)
- [Preventing & Enforcing Data Replacement](#preventing--enforcing-data-replacement)

### Introduction

The world of programming languages offers several ways to prevent *or* *enforce* specialization. This article might give this a place inside Encircle.

The concepts from other languages can be boiled down to a simpler model that has to provide the following:

- Protected
- Overriding
- Required / Optional
- Requirements for other side of connection

### Protected

The protected access connector makes sure that a member is not publicly available, is privately available, but also available to all references (triangles) that merge with their container.

__Protected Object Set__  
![](images/3.%20Enforcing%20&%20Preventing%20Specialization.001.png)

__Protected Object Get__  
![](images/3.%20Enforcing%20&%20Preventing%20Specialization.002.png)

In other words: __Protected__ might be accomplished by providing ‘public’ access through a triangle reference, but ‘private’ access through a circle reference. In the picture below the triangle offers access to the member, but the circle might not.

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.003.png)

Note that __Protected__ members are still privately accessible, which means that f objects can always access __Protected__ members as well.

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.004.png)

### Overriding

The overriding concept is already explained in the specialization article. There are two possible notations:

*Object reference notation:*  
![](images/3.%20Enforcing%20&%20Preventing%20Specialization.005.png)

*Event notation:*  
![](images/3.%20Enforcing%20&%20Preventing%20Specialization.006.png)

### Optional / Required

The concepts from other languages for preventing or enforcing specialization require imposing that something *might* be filled in. The concept of *required* is already worked out in the article *Optional & Required*. The notation looks as follows:

__Optional__  
![](images/3.%20Enforcing%20&%20Preventing%20Specialization.007.png)

__Required__  
![](images/3.%20Enforcing%20&%20Preventing%20Specialization.008.png)

*Required* is expressed by putting half of the expected symbol at the end of the connector. *Optional* might not get such a symbol, because it is the default behavior that things are optional to fill in. Required is an extra rule imposed.

### Requirements for Other Side of Connection

The concepts from other languages for preventing or enforcing specialization require being able to specify that the other end of the connection needs to be a triangle. For now this is expressed as follows:

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.009.png)

So it is a notation where the requirements for the other end of the connection are expressed at the other end of the connector. The connector line continues after the specified requirement as to not conflict with the notation for __Required__ in general, like this:

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.010.png)

### Gut Feeling

A gut feeling of mine is that __Protected__ and requirements for other side of connection could be made more alike, because both are about how the other end might be a triangle, but in one case that the direct reference might be a triangle, and in the other case the parent might be a triangle. So these requirements for it being a triangle might might be merged into one concept one day.

The notation come up with for requirements for the other side of the connection may be inspiration for a notation for a more elaborate security model one day.

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.009.png)

### Applied to Concepts from Other Languages

The following keywords from other languages that prevent or enforce specialization are covered along with how they translate to Encircle:

- __Protected__
- __Virtual__
- __Abstract__ member
- __Abstract__ class
- __Sealed__ / __Final__
- __Interface__
- __Interface__ member
- __Non-Overridable__ (the default in other languages)

### Protected

For now __Protected__ is an intrinsic part of Encircle. It has its own type of access mark: 

__Protected__  
![](images/3.%20Enforcing%20&%20Preventing%20Specialization.011.png)

### Virtual

The keyword __virtual__ from other languages means that you *can override* the member. It is also called __Overridable__. In Encircle this means that overriding should be __Public__. In the two notations for overriding this might look as follows:

|                     *Object reference notation*                      |
|:--------------------------------------------------------------------:|
|                         __Public Object Set__                        |
| ![](images/3.%20Enforcing%20&%20Preventing%20Specialization.012.png) |

|                          *Event notation:*                           |
|:--------------------------------------------------------------------:|
|                      __Public Object Override__                      |
| ![](images/3.%20Enforcing%20&%20Preventing%20Specialization.013.png) |

In some languages overriding is private by default, protecting a base class from specialization.

### Abstract Member

When the keyword __abstract__ from other languages is applied to a member, it means that you *might* override the member. It is also called __MustOverride__. In Encircle is a combination of making overriding __Public__ *and* __Required__. In the two notations for overriding this might look as follows:

|                     *Object reference notation:*                     |
|:--------------------------------------------------------------------:|
|                    __Public Required Object Set__                    |
| ![](images/3.%20Enforcing%20&%20Preventing%20Specialization.014.png) |

|                          *Event notation:*                           |
|:--------------------------------------------------------------------:|
|                 __Public Required Object Override__                  |
| ![](images/3.%20Enforcing%20&%20Preventing%20Specialization.015.png) |

### Abstract Class

When the keyword __abstract__ from other languages is applied to a class, it means that you *might* inherit from the class, or better said: you cannot just reference the class, the reference might merge with its container. It is also called __MustInherit__.

In Encircle this gets the following preliminary notation:

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.016.png)

__Private Use As Class__  
__Public Triangle Use As Class__

Or perhaps simply:

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.017.png)

__Public Triangle Use As Class__

Do not get confused: abstract applied to a class might not mean that its commands are __abstract__, so might be overridden, it just means that the class might be inherited from. An __abstract__ class *can* have method *implementations* in it. 

### Sealed / Final Class

The keywords __sealed__ and __final__ mean the same thing. A sealed class, or final class, is the opposite of an abstract class: instead of only being able to inherit from the class, you are explicitly not able to inherit from the class. It is also called __NotInheritable__.

In Encircle this gets the following preliminary notation:

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.018.png)

__Public Use As Class__  
__Private Triangle Use As Class__

Or simply just:

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.019.png)

__Private Triangle Use As Class__

Here it becomes apparent that the notation should not be just an open half triangle, because this might imply that the connector is __Required__, which it explicitly is not.

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.020.png)

The use of this enforcement is questionable to me, because with a little effort you could wrap a non-inheritable class into an inheritable class again. I can imagine that a __final__ class could not have __virtual__ or __abstract__ members, so such a trick might not make it possible to override members, but it might make it possible to do any other inheritance trick in the book.

### Interface / Interface Member

Interfaces are an intrinsic concept inside Encircle. In Encircle any object can serve as another object’s interface by using the __Use As Interface__ connector.

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.021.png)

This is a bit different from other languages.

The differences are pointed out here, but it is questionable whether it is important to do anything about those differences. In other programming languages the interface construct imposes several extra restrictions compared to the class construct. An interface is:

- abstract / might be inherited from
- only has abstract members / members might be overridden
- cannot have an implementation

Normally you do not see these restrictions. They only come to light as soon as you break a rule. That is why the interface constructs seems like a simpler construct: you can do less with it, but you could also see it as a more complex one, because compared to the class construct, *more restrictions* are imposed and these restrictions are also define somewhere. You just do not see this in other languages.

#### Rule 1: Interfaces are Abstract

The first rule for interfaces in other languages is: interfaces are abstract and might be inherited from. This rule is questionable though, since some languages allow you to declare an *explicit* interface, which basically replaces the inheritance characteristic of the interface with aggregation characteristics. In Encircle you can also choose whether to implement an interface in an implicit or explicit mannar / choose between inheritance and aggregation.  
However if you want to enforce that you can only use the interface in an inheritance way, you could express that by imposing a rule for the other side of the connection:

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.022.png)

This expresses that the other end of the connection should be a triangle.

#### Rule 2: Interface Members are Abstract

The second rule of interfaces is: members might be overridden / members are abstract. In Encircle all interface members are always present inside an implementation of an interface. This is not considered overriding: you have no say in whether to override something or not, the members are just automatically there as soon as you implement an interface.

However unnecessary, you can implicitly define that a member is abstract, which usually looks as follows:

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.023.png)

Meaning the *interface’s* *square* member has a __Public Object Set__ access connector that is __Required__.

But if you want to do that, you might might do it for all members of an interface.

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.024.png)

If you want to set this rule for all members at the same time, there is no other  notation for that, than to turn the interface into a list object, in which you can control the aspects of all list members at the same time:

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.025.png)

But all in all, you should not worry about this, because if you use an interface, automatically all members of the interface are implemented.

#### Rule 3: Interfaces can not Have an Implementation

Encircle offers no way to enforce that the interface object has no implementations. Period. You can put implementations in interfaces, only they might never be used.

Something might be considered here compared to other programming languages. In other programming languages the implementation of an interface is composed of method implementations and private members. In Encircle, method implementations are considered *private content*. So in Encircle the interface and implementation are distinguished by separating the public content from the private content.

So how this translated to implementations inside interface objects: if you make something inside an interface object private, it might never be used.  
You can make the private content usable again by either making it public again or by making the object usable as a class or plainly as a object.

#### Gruesome

In the picture below both interface members being abstract and the interface being abstract are expressed:

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.026.png)

This looks pretty gruesome for trying to define the interface construct, which should be simpler than the class construct, so please just use:

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.027.png)

The access connector is not even required, so you can also notate:

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.028.png)

### Non-Overridable

Not being able to override is the default in other languages, but in Encircle it is an imposed restriction, making overriding __Private__, which looks as follows in the two notations for overriding:

*Object reference notation:*

__Private Object Set__

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.029.png)

*Event notation:*

__Private Object Override__

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.030.png)

### More Combinations

With the concepts explained so far you can form other combinations of protection against specialization. For instance the following:

![](images/3.%20Enforcing%20&%20Preventing%20Specialization.031.png)

__Protected Required Object Set__

But this is also possible in other languages by making a member __protected abstract__.

### Courtesy

All of this is just courtesy to support all these concepts in Encircle. My gut feeling is that something simpler might be come up with in the future.

For instance the __Protected__ connector notation was come up with at a very early stage, long before the other inheritance-related modifiers were considered. My gut feeling is that I might let go of the notation for __Protected__ and go for a notation more concise and integrated with all of the other things that can be expressed. __Protected__ really might not deserve such an intrinsic notation compared to the rest of the inheritance-related modifiers.

This article is just put here to make sure that at least all of this stuff is possible in Encircle, but my gut feeling is that a replacement for all of this might be found.

### Enforcing & Preventing Other Specialization Methods

The ideas above might provide other language’s capabilities to enforce or prevent specialization. But what about the other specialization methods? How are they enforced or prevented? The following specialization methods were not covered:

- Altering the Member Set:
 
    - Member Addition
    - Member Exclusion
    - Member Inclusion

- Detouring Members:

    - Shadowing

- Altering Command Implementations:

    - Command Pre- and Post-Extension
    - System Command Pre- and Post-Extension
    - Overriding System Commands
    - Shadowing System Commands

To get it in line with the rest of the system, the following methods for protection of enforcement of specialization should become applicable to each of the specialization methods:

- Protected
- Required / Optional
- Requirements for other side of connection (for it to be a triangle)

However, these other specialization methods do not really disturb the class’s original implementation. Anything that alters the base’s behavior should be preventable. The rest is not that important to prevent. The only specialization methods proposed now that change the actual base object is overriding and cancelling on pre-extension. The rest just augments an object. The work required to work out how all specialization methods are preventable is not done right now, because it is not considered very important or worth the hassle.

### Preventing Pre-Extension with Cancellation

Pre-extension with cancellation is an alternative to overriding. It should also be preventable, because it alters the base’s behavior. Clearly when something is not overridable, you should also not be able to cancel it. The exact implementation of this is not important. The only thing that is important is that it prevention of pre-extension with cancellation *might* be implemented.

### Preventing & Enforcing Data Replacement

Data replacement is not regarded a specialization technique. However, anything inside an object is data, even the code, command names and command parameters. By default any of this data can be replaced. The way to prevent data replacement is by either making something __Private__, so that only __Friend__ objects can access it, or by making the data Static inside the class, so that the data cannot be changed through instances of the class.
