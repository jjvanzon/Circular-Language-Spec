Introduction
============

*JJ van Zon, 2021*

[back](..)

Here some basics might be introduced of the Circular language. Circular language is an idea for a computer programming language, mostly a diagram notation for visualizing computer code. 

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

Something that might play a role in software development, is splitting up a larger idea into smaller ideas.

![](images/Circle%20Language%20Spec%20Introduction.001.png)

This picture might display the idea of *a computer*, split up into four sub ideas: a monitor, keyboard, mouse and printer.

In Circular language, the main symbol for an idea might be a *circle:*

<img src="images/Circle%20Language%20Spec%20Introduction.002.png" height="100" />

Each sub idea might work more or less independently of the others. __Monitor__ might do its part, __Keyboard__ might do its part. It may be the super idea that could tie the sub ideas together. Meaning: the computer may make the link between a monitor, keyboard, mouse and printer. A super idea might combine the sub ideas and may manage communication between sub ideas.

In computer programming, ideas may be called *objects*. Each object might be responsible for its own part of a system.

![](images/Circle%20Language%20Spec%20Introduction.003.png)

A sub idea may be split up into sub ideas itself. Things might go on and on splitting up into smaller and smaller ideas.

<img src="images/Circle%20Language%20Spec%20Introduction.004.png" height="400" />

But to see the general point of a system, only the top layers may be relevant:

![](images/Circle%20Language%20Spec%20Introduction.003.png)

This might make object oriented programming a way to keep overview over a system as it grows. A better split up into ideas may help a design become better understandable, perhaps mainly its general outlines or top layers. A subdivision in objects might be quite a prominent thing in software. So splitting up an idea into sub ideas, something that quite a few people may be able to do, might be quite relevant when programming.

Reusing Ideas
-------------

Dividing up into ideas may lead to *reusability* of ideas. For instance: the idea of a *button* might be reusable. It might be used more than once. If quite a good button were to be programmed, other people may not need to program a button themselves. The same idea might be reused where another button is needed.

Where a button may be used in a system, there might be a separate object:

![](images/Circle%20Language%20Spec%20Introduction.005.png)

![](images/Circle%20Language%20Spec%20Introduction.006.png)

A button object in general might be called a *type* of object. The different button objects may be objects of a similar *type*. Sometimes the word *object* might be used in place of the word *type*. For instance, something might be called the button *object*, while talking about the button *type*.

There may be quite a few types available, that might be used in one way or another. A __Button__ type for instance might be used to build a user interface. Another type, __Integer__, may represent one integer number. Those might be used relatively frequently when programming.

Commands
--------

Apart from a collection of sub objects, objects may contain *commands* as well.

![](images/Circle%20Language%20Spec%20Introduction.007.png)

Sub objects may again contain even more commands.

<img src="images/Circle%20Language%20Spec%20Introduction.008.png" height="300" />

Software might not execute without commands. Upon running a command, an object may *do something*.

A button might have a __Set Text__ command for instance, which may set the text displayed on a button.

![](images/Circle%20Language%20Spec%20Introduction.009.png)

Commands might be denoted here by *squares*.

Other objects may also have a __Set Text__ command. __Set Text__ commands of different objects may be distinguished with the following text notation:

__Button . Set Text__

A command may consist of sub commands again: separate steps of the command.

<img src="images/Circle%20Language%20Spec%20Introduction.010.jpeg" height="300" />

Sub commands are not necessarily embedded inside other commands. They could exist separately:

<img src="images/Circle%20Language%20Spec%20Introduction.011.jpeg" height="300" />

And these sub commands might then be *called* from the super command:

<img src="images/Circle%20Language%20Spec%20Introduction.012.jpeg" height="350" />

Calling a command may have a similar effect as inserting the called command there where it was called.

The __Redraw Button__ command may be more complex. In this command, lines of a button might be drawn, a text might be drawn and other things that might make up the display of a button. It may be built up of steps. __Redraw Button__ may for instance call the __Draw Line__ command a number of times. So sub commands of this __Set Text__ command might themselves be composed of sub commands.

<img src="images/Circle%20Language%20Spec%20Introduction.013.jpeg" height="350" />

Here may also become apparent, that separately defining a command might lead to *reuse* of a command. The __Draw Line__ command appears to be reused three times in the example above. There may be quite a few commands available, ready to use one way or another. Commands like that might also be put inside in a separate object. There might for instance be a __File__ object that may contain commands that might allow dealing with a computer file.

So where might it end? If commands continue to delegate to each other, when might things actually start happening? Well, it seems to end at a special group of commands, that might not call other commands anymore. A command like that may execute a machine instruction: a basic instruction that make a *computer* *do* something. A computer's central processing unit might perform a hardware defined *machine* command.

That way there may develop big command call tree-outs, which might make a single command consist of multiple machine instructions, that may range from tens to thousands of machine instructions or more.

But it might not be necessary to see all those details to understand what the effect of __Button . Set Text__ might be. A simpler overview might be good enough for that:

<img src="images/Circle%20Language%20Spec%20Introduction.014.jpeg" height="200" />

Other names for commands may be: *operations, procedures, functions, methods* and *routines.* Those might mean more or less the same.

Command Parameters
------------------

Commands might have *parameters*. Those are like instructions passed along with a command that may make a command behave differently. A __Button . Set Text__ command for instance, may have a __Text__ parameter, which might indicate what the new text of a button would be.

__Text__ might also be seen as an *idea*. It may be thought of as an *object*. That way, it might be *objects* that could serve as parameters.

<img src="images/Circle%20Language%20Spec%20Introduction.015.jpeg" height="300" />

A command might do things with a parameters passed to it. It might do either one of the following:

- Passing the parameter to another command or 
- Calling commands of the parameter.

Passing a __Text__ parameter on to the next command (__Format Text__):

<img src="images/Circle%20Language%20Spec%20Introduction.016.jpeg" height="300" />

Calling a command of the __Text__ parameter:

<img src="images/Circle%20Language%20Spec%20Introduction.017.jpeg" height="300" />

Interfaces
----------

Another capability of objects might be, that they may have different interfaces.

Try to consider how a employee may look to a customer and how to a coworker. The employee might do certain things for a coworker and other things for a customer. The employee seems to have two *interfaces*. It may depend on the party referring to the employee, which interface the employee might show. Even though both parties may refer to the same person, this person might do different things for them.

Objects may have a similar ability. An object may have separate interfaces. Interfaces seem to be groups of an object's members. (Elements inside an object might also be called *members*.)

<img src="images/Circle%20Language%20Spec%20Introduction.018.jpeg" width="400" />

Interfaces may be distinguished here by triangles.

The employee here might be an advisor to a customer and to another employee a coworker. Another object that refers to the employee might decide which interface may be used, or sometimes only one specific interface might be available for specific objects. An object might also just have one interface, the same one for everybody.

Triangles might be considered sub objects too. One of the differences with circles seems to be that triangles sort of melt together with their container.

Triangles may be a way to give different types shared characteristics. Though 'normal' sub-objects might do that too.

Reading a Diagram
-----------------

Where to start, when reading a diagram like the last one? It might be an idea to first read its containment structure, by starting at the largest container, and then looking at the smaller ones. After that perhaps look at relationships made by the connecting lines.

Perhaps starting with the largest container is not always preferred. Maybe one symbol is highlighted. Then this symbol might be what the diagram is about. Then the focus might be on aspects of the highlighted symbol. Then perhaps start there and look around. There is probably no one way of doing it.

Conclusion
----------

Hopefully this introduced some of the basics of the Circular language.

[back](..)