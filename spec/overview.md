Encircle Language Spec
======================

Overview
--------

This documentation is an attempt to describe a programming language called Encircle. It aims to be a diagram notation for visualizing computer code. 

The documentation tries to explain how coding concepts might be expressed in this Encircle language: concepts like objects, classes, relations, interfaces, events, commands and parameters.

The Encircle language for now is a specification in writing. At the time of this writing, no finished program was made yet. Only experiments were done.

The documentation tries to shed light on the following topics:

__Contents__

- [Introduction](#introduction)
- [Overview](#overview-1)
- [Basic Diagram Elements](#basic-diagram-elements)
- [Objects](#objects)
- [Classes](#classes)
- [Relationships](#relationships)
- [Commands](#commands)
- [Parameters](#parameters)
- [Modules](#modules)
- [Execution Flow](#execution-flow)
- [System Objects](#system-objects)
- [Black Boxes](#black-boxes)
- [Interfaces](#interfaces)
- [Events](#events)
- [Inheritance](#inheritance)
- [Type Control](#type-control)
- [Object Resolution](#object-resolution)
- [Conditions](#conditions)
- [Object Order](#object-order)
- [Pointers](#pointers)
- [Misc Diagram Topics](#misc-diagram-topics)

### [Introduction](introduction.md)

- Tries to gently introduce this language.

### Overview

- This overview, which attempts to summarize each topic. 

### [Basic Diagram Elements](basic-diagram-elements.md)

- ![](images/Circle%20Language%20Spec%20Overview.001.png)![](images/Circle%20Language%20Spec%20Overview.002.png)![](images/Circle%20Language%20Spec%20Overview.003.png) 

  Tries to make it a bit more formal with an attempt to give a more or less complete overview over the basic elements that might be seen in the diagrams, like circles, triangles, crosses, squares and lines. This documentation describes what they might mean in the diagrams. Details might follow in later text.

### [Objects](objects.md)

- ![](images/Circle%20Language%20Spec%20Overview.004.png)
 
  This documentation aims to describe what objects might be in computer technology and basic concepts about objects. It also tries to shed light on drawing out objects using the Encircle diagram notation.

### [Classes](classes)

- ![](images/Circle%20Language%20Spec%20Overview.005.png)

  This documentation attempts to demonstrate the concept of *classes*. A class is sort of like a special object, that aims to describe the characteristics and behavior of other objects. The other objects might select that special object as their class and the idea is that their behavior is then guided by the rules described by that class. The basic ideas may be explained, but the concept of *static* is intended to be worked at a later time.

### [Relationships](relationships.md)

- ![](images/Circle%20Language%20Spec%20Overview.006.png)

  When an object connects to another object, it is like a relationship between the two is established. This documentation tries to clarify the concept of relationships. Even though objects might relate to an arbitrary set of other objects, the concept might also be about how *classes* set the guidelines for the kinds of relationships objects might have. Relations between classes form a sort of *model* of relationships for objects.

### [Commands](commands)

- ![](images/Circle%20Language%20Spec%20Overview.008.png)

  Commands could be seen as executable objects. Other synonyms for commands might be *methods*, *procedures*, *routines*, *subs* and *functions*. But in the Encircle Language Spec those executable objects would be called *commands*. In some programming languages, commands might not be objects, but constructs, that are not exchangeable with objects. But in Encircle an attempt is made to see them as objects, that so happen to be executable. Commands do seem to have specific behavior. This documentation tries to evaluate this behavior.

### [Parameters](parameters)

- ![](images/Circle%20Language%20Spec%20Overview.009.png)

  Parameters are like instructions passed along with a command that could make the command behave differently. This documentation tries to view parameters as a relationship between commands and objects. It entertains an idea of how *command parameters* and *class methods* might be interchangeable, as if they might be one and the same concept. It is not sure, if this idea will still be in there in the future. Also a diagram notation of commands and parameters is suggested.

### [Modules](modules.md)

- ![](images/Circle%20Language%20Spec%20Overview.010.png)

  A module would be like a little world in which objects and commands live. A module might be a site, a computer program, a library, a name space or other kind of module. A module may group together functionality or data. Some modules might have a property that might be called *global* access to its sub-objects, which may also be described as: Anything directly inside the module can be directly referenced from anywhere within that module. A module might also be just an object with this special 'global access' property.

### [Execution Flow](execution-flow)

- ![](images/Circle%20Language%20Spec%20Overview.011.png)

  The idea of execution flow statements is that they may regulate the order in which things are executed. Several execution flow statements are proposed. The key examples might be __If__ and __For__ statements. An attempt is made to build up a complete set of execution flow statements, to explore what could be desired from the diagram notation for it.

### [System Objects](system-objects)

- ![](images/Circle%20Language%20Spec%20Overview.007.png)

  One possible application of how this language might run in practice, is one where systems may be composed of *system objects*. System objects could be the *actual* objects, that a system runs on. Maybe this is a specific use case of the language, but describing it, seems to have allowed more generally usable things to fall out. One of the intentions of system objects could be, to manage *relationships* between objects. They might also control *system aspects*, such as __Value__, __Object__, __Class__, __Interface__ and __Execution__ and __Multiplicity__. Those aspects could be controlled through *system commands* like __Get__ and __Set__. The story moves on to assignment commands. The idea is that assignment commands copy an aspect from one object to another. The *System Objects* documentation also tries to show connectors, connections and different notational forms to regulate these aspects.

### [Black Boxes](black-boxes)

- ![](images/Circle%20Language%20Spec%20Overview.012.png)

  It could be said, that *Black Boxes* have to do with *Public and Private*. *Private* might make something only accessible inside an object. *Public* could make something accessible outside an object as well. That way, the inner workings of an object may be hidden away and this might be a way to work with the input and output only.

  The notation might be changed compared to what is described here. The current version tends to focus around something, that could be called the *friend* notation. This might be because the current design of the notation seems to be made with a bit of a different view on objects and commands. Commands were sort of considered more independent and not necessarily part of an object. Which commands might access the private contents of which objects might be less obvious, when a command would not necessarily be part of any particular object. The effect seemed to be, that commands might not get access to the private contents of an object, unless that command may be declared a *friend* by the object. Friend declaration might create somewhat of a tighter bond between the command and the object. Thinking of commands as object, seems to have affected the direction into which the design black boxing went.

  In the future, a different black box method might be suggested: more like it is in other programming languages. The friend notation might still be preserved for particular use-cases.

### [Interfaces](interfaces)

- ![](images/Circle%20Language%20Spec%20Overview.013.png)

  This chapter attempts to describe the concept of interfaces along with their diagram notation. Up until now the idea of interfaces was sometimes left out of the stories. This chapter tries to catch up with that. There are also attempts to describe: interface assignment, interface reference and relations that might form through the use of interfaces. As interfaces might be applied to *objects*, interfaces might also be applied to *commands*.

### [Events](events)

- ![](images/Circle%20Language%20Spec%20Overview.014.png)

  Events might be thought of as notification calls. Call receivers might subscribe to an event. The call sender might send a call to the receivers at times. Another variation of the events concept, that the world seems to use, might be the *‘the observer pattern’*. The term observer may help here, to realize what an event is: watching out for something to take place, to possibly take action. The sender might decide what the message looks like. The receiver might supply a command, that should have an interface, suggested by the sender.

  The concept of events might be seen as a combination of constructs: an array of command references, a command interface, then supporting the command interface, registering the command inside the array of command references and then calling the commands in the array at times.

  The documentation also tries to show, how events might look in Encircle's diagram notation.

### [Inheritance](inheritance)

- ![](images/Circle%20Language%20Spec%20Overview.015.png)

  This part of the documentation attempts to describe the concept of *inheritance* inside the Encircle language. This concept seems to have been part of some object oriented programming languages for a while. In certain languages one class might inherit from another class, to take over its characteristics before the derived class might get extended or altered. When the notation in Encircle was worked out, different variations on that seemed to fall out, that might not necessarily be present in all object oriented languages. Next to *class inheritance* (could be thought of as the *traditional* form of inheritance), there could also be *object inheritance*. This might mean, that one object takes over the characteristics of a specific other object. The other object seems to melt together with the new object. When maybe changing base members of the new object, the base object’s data might also change. This could be called *object inheritance*. More forms of inheritance may be proposed. A collection might be inherited from, so that an existing 'table' of items might be extended with 'new columns'. This could be called *list inheritance*. There is also the idea for a construct, where a *system* or module can inherit from another system, taking over its characteristics, and the derived system can be altered, augmented, specialized and extended. This might be called *system inheritance* or *module inheritance*. If the original system would change, this may also change the derived systems. (Other technology might establish this with what may be called 'proxy classes' and extending auto-generated proxy-classes with additional aspects.) So the idea is that things can be inherited from to render specialized versions of a class, object, collection or module.

  Such specialization might also be applied to *commands*. The inheritance documentation also aims to describe other concepts in the area of *specialization* and *extension*. Inheritance might be thought of related to the concept of *interfaces.*

That was the more rounded up documentation. Next an attempt is made to list the documents, that might not be as well polished. The descriptions below, however, might be a rounded up reflection on the topics.

### [Type Control](type-safety-genericity-explicit.md)

- ![](images/Circle%20Language%20Spec%20Overview.016.png)

  Objects might relate to, free to choose sets of other objects. But when the class of an object is set, some relations might be determined by the class. This could be considered a form of *type control*. Another form of type control might be assigning an interface to an object reference. This may change the types of objects that might be assigned to the object reference.

  Binding an object like that could be called *explicit* declaration. Not binding an object or object reference like that might be called *generic* declaration. Both concepts could be seen as *type control*.

  This document might have ideas that are possibly not as well polished, including an original description worked out in a previous version of the design of this diagram language.

### [Object Resolution](object-resolution)

- ![](images/Circle%20Language%20Spec%20Overview.017.png)

  Object resolution might take place when a reference to one object is more or less obscured by another object, shadowing or overriding the original object. (It also might apply to commands.) A reference might be set to an object, but instead the reference might be sort of non-consentiously pulled towards another object. There may be multiple situations in which object resolution takes place, like: overriding, overloading, shadowing, ambiguity, implicit conversions and default members. At first it was thought, that these kinds of situations might be due to ambiguity and the textual nature of code, but in the Encircle diagram notation when drawing out the situation in a diagram, it seems to fall into place, that they might be more like automatically detoured references.

  This documentation might be less smooth. It may contain ideas but partly described, not as refined into polished up text.

### [Conditions](conditions.md)

- ![](images/Circle%20Language%20Spec%20Overview.018.png)

  An object might set rules for what kind of values may be filled in into it and a command might be given conditions on whether the procedure might be started or not. This might perhaps be done by adding code to a procedure (or for an object, to the __Set__ command). From that code may follow, that depending on certain conditions, the execution of the rest of the procedure is or is not run. That just may have described a low-level way to handle conditions. But conditions could be centric enough in programming, that they might become a construct in the Encircle diagram language. A (value) object or command might propose a set of conditions, to evaluate whether the value may be assigned or if the command is allowed to execute.
 
  The documentation may be not so rich yet, apart from some loose ideas.

### [Object Order](object-order.md)

- By default, objects inside a collection might be put in an arbitrary order. The *Object Order* concept may allow sorting a list, or putting things in a manually chosen order, and also perhaps a diagram notation for it.
 
- This documentation is a collection of ideas, that might be polished up to be made neater later.

### [Pointers](pointers)

- ![](images/Circle%20Language%20Spec%20Overview.019.jpeg)

  The intention could be to move pointer-related issues to this chapter instead of being spread around multiple places.
 
  This may or may not have been done yet.

### [Misc Diagram Topics](misc-diagram-topics)

- It would be nice if diagrams could be automatically drawn out: if the metrics and positions of the shapes and lines could be automatically done. Suggestions could be found this documentation about aspects of positioning, that might make diagrams look tidier. Also described might be ideas about how colors may be used to highlight things.

- This documentation might still be loose ideas from previous descriptions of this Encircle programming language.