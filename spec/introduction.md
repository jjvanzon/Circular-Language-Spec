---
title: "📢 Circular Language Introduction"
image: "images/introduction-page.png"
description: "Circular is an idea for a computer programming language, mostly a diagram notation for visualizing computer code."
keywords:
  - circular
  - circular language
  - code visualization
  - visualization
  - programming
  - coding
  - computer programming
  - software engineering
  - software development
  - software design
  - software architecture
  - layered architecture
  - software
  - computers
---

Introduction
============

[back](..)

This articles introduces the basics of the Circular language. Circular is an idea for a computer programming language, mostly about a diagram notation for visualizing computer code. 

__Contents__

- [Splitting up Ideas](#splitting-up-ideas)
- [Reusing Ideas](#reusing-ideas)
- [Commands](#commands)
- [Command Parameters](#command-parameters)
- [Interfaces](#interfaces)
- [Reading a Diagram](#reading-a-diagram)
- [Conclusion](#conclusion)

Splitting up Ideas
------------------

One thing that can play a role in software development, is splitting up a larger idea into smaller ideas:

![](images/Circle%20Language%20Spec%20Introduction.001.png)

This picture shows the idea of *a computer*, split up into four sub ideas: a monitor, keyboard, mouse and printer.

In Circular the main symbol for an idea is a *circle:*

<img src="images/Circle%20Language%20Spec%20Introduction.002.png" height="100" />

Each sub idea works more or less independently of the others. __Monitor__ does its bit, __Keyboard__ does its bit. It's the super idea that ties all the sub ideas together. That means that the __Computer__ makes the link between monitor, keyboard, mouse and printer. The super idea combines the sub ideas and manages communication between them.

In computer programming, ideas are sometimes called *objects*. Each object is responsible for its own part of the system. Here is another example:

![](images/Circle%20Language%20Spec%20Introduction.003.png)

A sub idea can be split up into sub ideas itself. This way we can go on and on, splitting up into smaller and smaller ideas:

<img src="images/Circle%20Language%20Spec%20Introduction.004.png" height="400" />

But to see the general point of a system, only the top layers are relevant:

![](images/Circle%20Language%20Spec%20Introduction.003.png)

This makes object oriented programming a great way to keep overview over a system as it grows. A better split up into ideas makes a design easier to understand, especially the general outlines. A subdivision in objects can be quite a prominent thing in software. So splitting up an idea into sub ideas, something that most people are probably able to do, can be quite relevant when programming software.

Reusing Ideas
-------------

A division into ideas can lead to the *reusability* of ideas. For instance: the idea of a *button* might be reusable. If a good button were programmed, other people may not need to program another button again. The same idea can be *reused* everywhere a button is needed.

Any place where there's a button in a system, there is a separate object:

![](images/Circle%20Language%20Spec%20Introduction.005.png)

![](images/Circle%20Language%20Spec%20Introduction.006.png)

A button object in general is called a *type* of object.

There are quite a few object types available out of the box, that can be used in your program. __Button__ objects for instance are quite common and can be used to build a user interface. Another type, __Integer__, represents an integer number. Those are used all the time.

Commands
--------

Objects not only have sub objects. They can also contain *commands:*

![](images/Circle%20Language%20Spec%20Introduction.007.png)

Commands are denoted here by *squares.*

Sub objects can again contain commands:

<img src="images/Circle%20Language%20Spec%20Introduction.008.png" height="300" />

Software cannot execute without commands. Upon running a command, an object *does something*.

A button can have a __Set Text__ command for instance, which sets the text to display:

![](images/Circle%20Language%20Spec%20Introduction.009.png)

Other types of object might also have a __Set Text__ command. Those can be distinguished with the following text notation:

__Button . Set Text__  
__Text Box . Set Text__

A command can again consist of sub commands: the separate steps of the command, denoted here by *diamond* shapes:

<img src="images/Circle%20Language%20Spec%20Introduction.010.jpeg" height="300" />

Sub commands are not necessarily embedded inside other commands. They can exist separately:

<img src="images/Circle%20Language%20Spec%20Introduction.011.jpeg" height="300" />

And these sub commands are then *called* from the super command:

<img src="images/Circle%20Language%20Spec%20Introduction.012.jpeg" height="350" />

Calling a command has a similar effect as inserting the called command there where it was called.

The __Redraw Button__ command is rather complex. In this command, lines of a button are drawn, a text is drawn and other things that make up the button. It is built up of steps. __Redraw Button__ could call a __Draw Line__ command a number of times. So sub commands of this __Set Text__ command can themselves be composed of sub commands.

<img src="images/Circle%20Language%20Spec%20Introduction.013.jpeg" height="350" />

Here it becomes apparent, that separately defining a command can lead to *reuse* of a command. The __Draw Line__ command is reused three times in the example above. There are quite a few commands already available. Reusable commands like that can also reside inside in separate objects. A __File__ object for instance can contain commands that make it possible to deal with a computer file.

So where does this all end? If commands just continue to delegate to each other, when do things actually start happening? Well, it seems to end at a special group of commands, that do not call other commands anymore. A command like that executes a machine instruction: a basic instruction that make a computer *do* something. A computer's central processing unit performs a hardware defined *machine* command.

That way it is possible to develop big command call tree-outs, which makes a single command consist of multiple machine instructions, ranging from tens to ten-thousands of them.

But it is not necessary to see all that detail, to understand what the purpose of __Button . Set Text__ is. A simpler overview should be good enough for that:

<img src="images/Circle%20Language%20Spec%20Introduction.014.jpeg" height="200" />

Command Parameters
------------------

Commands can also have *parameters*. These are instructions passed along with a command that modify its behavior. The __Button . Set Text__ command for instance, has a __Text__ parameter, which indicates what the text of a button would become.

__Text__ is an *idea*. It is an *object*. It is usually *objects* that serve as parameters:

<img src="images/Circle%20Language%20Spec%20Introduction.015.jpeg" height="300" />

A command can do things with the parameters passed to it, in particular one of the following:

- Pass the parameter to another command or 
- Call commands of the parameter.

Here is an example of passing a __Text__ parameter on to the next command, in this case to __Format Text__:

<img src="images/Circle%20Language%20Spec%20Introduction.016.jpeg" height="300" />

Here is an example calling a command of the __Text__ parameter:

<img src="images/Circle%20Language%20Spec%20Introduction.017.jpeg" height="300" />

Interfaces
----------
 
Another capability of objects is that they can have different interfaces.

Consider how an employee looks to a customer and how to a coworker. The employee will do certain things for a coworker and other things for a customer. The employee has two *interfaces*. It depends on the party referring to the employee, which interface they get to see. Even though both parties are referring to the same person, this person will do different things for them.

Objects have a similar cabability: they can also have separate interfaces. Interfaces group object members together.

<img src="images/Circle%20Language%20Spec%20Introduction.018.jpeg" width="400" />

Interfaces are distinguished here by *triangles*.

The employee here is an advisor to a customer and to another employee a coworker. Sometimes only one specific interface is available within a certain context. In other cases you can choose. An object can also just have one interface, the same one for everybody.

Triangles can be seen as sub objects. The difference with circles is that triangles sort of melt together with their container. Triangles are a way to give different types shared characteristics. 

Reading a Diagram
-----------------

Where to start, when reading a diagram like this?

<img src="images/Circle%20Language%20Spec%20Introduction.018.jpeg" width="400" />

One option is to first read its containment structure, by starting at the largest container, and then looking at the smaller ones. After that, relationships made by the connecting lines is something to look at.

Starting with the largest container may not always be preferred. One symbol might be highlighted. Then this symbol is what the diagram is about. The focus would be on aspects of the highlighted symbol. Then start looking around from there.

There is really no one way of doing it.

Conclusion
----------

Hopefully this adequately introduced some of the basics of the Circular language.

[back](..)