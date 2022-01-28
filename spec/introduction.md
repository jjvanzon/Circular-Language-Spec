Introduction
============

*JJ van Zon, 2022*

[back](..)

This articles aims to introduce the basics of the Circular language. Circular language is an idea for a computer programming language, mostly a diagram notation for visualizing computer code. 

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

Something that could play a role in software development, is splitting up a larger idea into smaller ideas:

![](images/Circle%20Language%20Spec%20Introduction.001.png)

This picture tries to demonstrate the idea of *a computer*, being split up into four sub ideas: a monitor, keyboard, mouse and printer.

In Circular language the main symbol for an idea may be a *circle:*

<img src="images/Circle%20Language%20Spec%20Introduction.002.png" height="100" />

Each sub idea could work more or less independently of the others. __Monitor__ does its part, __Keyboard__ does its part. The *super* idea might tie the sub ideas together. Meaning: the computer may make the link between a monitor, keyboard, mouse and printer. A super idea could combine the sub ideas and manage communication between the sub ideas.

In computer programming, ideas may be called *objects*. Each object might be responsible for its own part of a system.

![](images/Circle%20Language%20Spec%20Introduction.003.png)

A sub idea could be split up into sub ideas itself. Things might go on and on splitting up into smaller and smaller ideas:

<img src="images/Circle%20Language%20Spec%20Introduction.004.png" height="400" />

But to see the general point of a system, only the top layers may be relevant:

![](images/Circle%20Language%20Spec%20Introduction.003.png)

Like that object oriented programming tends to be a way to keep overview over a system as it grows. A better split up into ideas may make a design easier to understand, perhaps mainly its general outlines or top layers. A subdivision in objects might be quite a prominent thing in software. So splitting up an idea into sub ideas, something that quite a few people may be able to do, might be quite relevant when programming.

Reusing Ideas
-------------

Dividing up into ideas may lead to *reusability* of ideas. For instance: the idea of a *button* might be reusable. It may be used more than once. If a quite good button were to be programmed, other people might not need to program a button themselves. The same idea may be reused where another button is needed.

Where a button might be used in a system, there could be a separate object:

![](images/Circle%20Language%20Spec%20Introduction.005.png)

![](images/Circle%20Language%20Spec%20Introduction.006.png)

A button object in general might be called a *type* of object. The different button objects may be objects of a similar *type*.

There might be quite a few types available, that may be used in one way or another. A __Button__ type for instance might be used to build a user interface. Another type, __Integer__, may represent one integer number. Those might be used relatively frequently when programming.

Commands
--------

Apart from a collection of sub objects, objects may contain *commands* as well.

![](images/Circle%20Language%20Spec%20Introduction.007.png)

Sub objects might again contain even more commands.

<img src="images/Circle%20Language%20Spec%20Introduction.008.png" height="300" />

Software may not execute without commands. Upon running a command, an object might *do something*.

A button may have a __Set Text__ command for instance, which might set the text displayed on a button.

![](images/Circle%20Language%20Spec%20Introduction.009.png)

Commands may be denoted here by *squares*.

Other objects might also have a __Set Text__ command. __Set Text__ commands of different objects may be distinguished with the following text notation:

__Button . Set Text__

A command might consist of sub commands again: separate steps of the command.

<img src="images/Circle%20Language%20Spec%20Introduction.010.jpeg" height="300" />

Sub commands are not necessarily embedded inside other commands. They could exist separately:

<img src="images/Circle%20Language%20Spec%20Introduction.011.jpeg" height="300" />

And these sub commands may then be *called* from the super command:

<img src="images/Circle%20Language%20Spec%20Introduction.012.jpeg" height="350" />

Calling a command might have a similar effect as inserting the called command there where it was called.

The __Redraw Button__ command may be more complex. In this command, lines of a button might be drawn, a text may be drawn and other things that might make up the display of a button. It may be built up of steps. __Redraw Button__ might for instance call the __Draw Line__ command a number of times. So sub commands of this __Set Text__ command may themselves be composed of sub commands.

<img src="images/Circle%20Language%20Spec%20Introduction.013.jpeg" height="350" />

Here might also become apparent, that separately defining a command may lead to *reuse* of a command. The __Draw Line__ command appears to be reused three times in the example above. There might be quite a few commands available, ready to use one way or another. Commands like that may also be put inside in a separate object. There might for instance be a __File__ object that could contain commands that may allow dealing with a computer file.

So where might it end? If commands continue to delegate to each other, when may things actually start happening? Well, it seems to end at a special group of commands, that might not call other commands anymore. A command like that may execute a machine instruction: a basic instruction that make a *computer* *do* something. A computer's central processing unit might perform a hardware defined *machine* command.

That way there may develop big command call tree-outs, which might make a single command consist of multiple machine instructions, that may range from tens to thousands of machine instructions or more.

But it might not be necessary, to see all those details, to understand what the effect of __Button . Set Text__ may be. A simpler overview might be good enough for that:

<img src="images/Circle%20Language%20Spec%20Introduction.014.jpeg" height="200" />

Command Parameters
------------------

Commands may have *parameters*. Those are like instructions passed along with a command that might make a command behave differently. A __Button . Set Text__ command for instance, may have a __Text__ parameter, which might indicate what the new text of a button would be.

__Text__ may also be seen as an *idea*. It might be thought of as an *object*. That way, it may be *objects* that could serve as parameters.

<img src="images/Circle%20Language%20Spec%20Introduction.015.jpeg" height="300" />

A command might do things with a parameters passed to it. It may do either one of the following:

- Passing the parameter to another command or 
- Calling commands of the parameter.

Passing a __Text__ parameter on to the next command (__Format Text__):

<img src="images/Circle%20Language%20Spec%20Introduction.016.jpeg" height="300" />

Calling a command of the __Text__ parameter:

<img src="images/Circle%20Language%20Spec%20Introduction.017.jpeg" height="300" />

Interfaces
----------

Another capability of objects might be, that they may have different interfaces.

Try to consider how an employee might look to a customer and how to a coworker. The employee may do certain things for a coworker and other things for a customer. The employee seems to have two *interfaces*. It might depend on the party referring to the employee, which interface the employee may show. Even though both parties might refer to the same person, this person may do different things for them.

Objects might have a similar ability. An object may have separate interfaces. Interfaces seem to be groups of an object's members.

<img src="images/Circle%20Language%20Spec%20Introduction.018.jpeg" width="400" />

Interfaces might be distinguished here by triangles.

The employee here may be an advisor to a customer and to another employee a coworker. Another object that refers to the employee might decide which interface may be used, or sometimes only one specific interface might be available for specific objects. An object may also just have one interface, the same one for everybody.

Triangles might be considered sub objects too. One of the differences with circles seems to be that triangles sort of melt together with their container.

Triangles may be a way to give different types shared characteristics. Though 'normal' sub-objects might do that too.

Reading a Diagram
-----------------

Where to start, when reading a diagram like that?

<img src="images/Circle%20Language%20Spec%20Introduction.018.jpeg" width="400" />

It may be an idea to first read its containment structure, by starting at the largest container, and then looking at the smaller ones. After that perhaps look at relationships made by the connecting lines.

Perhaps starting with the largest container is not always preferred. Maybe one symbol is highlighted. Then this symbol might be what the diagram is about. Then the focus may be on aspects of the highlighted symbol. Then perhaps start there and look around. There is probably no one way of doing it.

Conclusion
----------

Hopefully this introduced some of the basics of the Circular language.

[back](..)