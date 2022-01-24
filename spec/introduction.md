Introduction
============

*JJ van Zon, 2021*

[back](..)

This article aims to introduce the basics of Circular language. Circular language is an idea for a computer programming language, mostly a diagram notation for visualizing computer code. 

__Contents__

- [Splitting up Ideas](#splitting-up-ideas)
- [Reusing Ideas](#reusing-ideas)
- [Commands](#commands)
- [Command Parameters](#command-parameters)
- [Interfaces](#interfaces)
- [Conclusion](#conclusion)

Splitting up Ideas
------------------

Something that can play a role in making software, is splitting up a larger idea into smaller ideas.

![](images/Circle%20Language%20Spec%20Introduction.001.png)

Here you can see the idea of *the computer*, split up into four sub ideas: the monitor, keyboard, mouse and printer.

In Circular language, the main symbol for an idea might be a *circle*:

<img src="images/Circle%20Language%20Spec%20Introduction.002.png" height="100" />

Each sub idea could work more or less independently of the others. __Monitor__ might its bit, __Keyboard__ might its bit. It might be the super idea that might tie the sub ideas together. Meaning: the computer could make the link between monitor, keyboard, mouse and printer. The super idea might combine the sub ideas and might manage the communication between the sub ideas.

In computer programming, ideas, so both super ideas and sub ideas, might be called *objects*. Each object can be responsible for its own part of the system.

![](images/Circle%20Language%20Spec%20Introduction.003.png)

Each sub idea can be split up in sub ideas itself and you might go on and on splitting up ideas.

<img src="images/Circle%20Language%20Spec%20Introduction.004.png" height="400" />

But to see the general point of the system, you might only need to see the top layers of the split up.

![](images/Circle%20Language%20Spec%20Introduction.003.png)

This might make object oriented programming a way to keep overview over a system as it grows. A clear split up into ideas might help the understandability of the design, perhaps most importantly the general outlines / top layers. Depending on who you ask, a subdivision in objects might be the most important thing in software. So splitting up an idea into sub ideas, something that most people are probably able to do, might be the most important thing about programming.

Reusing Ideas
-------------

Dividing up into ideas may lead to the *reusability* of ideas. For instance: the idea of a *button* might be reusable. It could be used everywhere. If the perfect button were to be programmed, nobody might need to program a button again. The same idea might be reused whenever a button is needed.

The places where a button is used in a system, there could be a separate object:

![](images/Circle%20Language%20Spec%20Introduction.005.png)

![](images/Circle%20Language%20Spec%20Introduction.006.png)

A button object in general can be called a *type* of object. All the button objects can be considered objects of the same *type*. Sometimes the word *object* is used instead of the word *type*. For instance, you might speak of *the* button *object*, while you’re talking about the button *type*.

There could be many types already defined, that you might use one way or another. Such as the __Button__ type for instance, which you can use to build a user interface. Another type, __Integer__, represents one integer number. You might be using those all the time when you program.

Another word for type is *class*. *Type* and *class* might not precisely mean the same thing, but it is pretty close and the word *class* is used in several object oriented programming languages.

Commands
--------

Apart from a collection of sub objects, objects might contain *commands*.

![](images/Circle%20Language%20Spec%20Introduction.007.png)

Sub objects can again contain commands.

<img src="images/Circle%20Language%20Spec%20Introduction.008.png" height="300" />

Software could not execute without commands. When you might run a command, an object might *do something*.

A button could have a __Set Text__ command for instance, which might set the text displayed on the button.

![](images/Circle%20Language%20Spec%20Introduction.009.png)

Commands are denoted here by *squares*.

Other objects could also have a __Set Text__ command. To distinguish the __Set Text__ commands of different objects, you might expres this something like:

__Button . Set Text__

A command itself can consist of sub commands: the separate steps of the command.

<img src="images/Circle%20Language%20Spec%20Introduction.010.jpeg" height="300" />

Sub commands are not necessarily embedded inside other commands. They can be defined separately:

<img src="images/Circle%20Language%20Spec%20Introduction.011.jpeg" height="300" />

And the sub commands can be *called* from the super command:

<img src="images/Circle%20Language%20Spec%20Introduction.012.jpeg" height="300" />

Calling a command has almost the same effect as inserting the called command there where you call it.

The __Redraw Button__ command might be more complex. In this command the lines of the button could be drawn, the text could be drawn and whatever else might make up the display of the button. The steps of this redrawing could be delegated by yet again calling other commands. __Redraw Button__ could for instance call the __Draw Line__ command a number of times. So sub commands of the __Set Text__ command can themselves be composed of sub commands.

<img src="images/Circle%20Language%20Spec%20Introduction.013.jpeg" height="350" />

You can also see here that separately defining a command can lead to the *reuse* of commands. The __Draw Line__ command is reused three times in the example above. There may be many commands already defined, that you might use one way or another. Commands like that could also be put inside in a separate type. There could for instance be a __File__ type that contains commands with which to control a single computer file.

So where might it end? Might commands continue to delegate to one another and might nothing really actually happen? Well, it seems to end at a special group of commands, that do not call other commands anymore. Each of those command may execute a so called machine instruction: a basic instruction that is sent to the computer’s central processing unit (CPU) and make the *computer* *do* something. The CPU might perform a hardware defined *machine* command.

That way there can develop big command call tree-outs, which can make a single command consist of many, machine instructions, ranging from tens to thousands of machine instructions or even more.

But you do not necessarily need to see all those details in order to understand what the effect __Button . Set Text__ is.

<img src="images/Circle%20Language%20Spec%20Introduction.014.jpeg" height="200" />

Other names for commands could be *operations, procedures, functions, methods* or *routines.* Those might be more or less synonyms.

Command Parameters
------------------

Commands can have *parameters*. Those are like instructions passed along with the command that make the command behave differently. The __Button . Set Text__ command for instance, has a __Text__ parameter, which indicates what the new text of the button might be.

Text can also be seen as an *idea*. It can be thought of as an *object*. That way, it is *objects* that serve as parameters.

<img src="images/Circle%20Language%20Spec%20Introduction.015.jpeg" height="300" />

The command can do whatever it wants with the parameters passed to it. Arguably, all it can do with it is:

- pass the parameter to another command *or* 
- call commands of the parameter.

Pass the __Text__ parameter on to the next command (__Format Text__):

<img src="images/Circle%20Language%20Spec%20Introduction.016.jpeg" height="300" />

Call a command of the __Text__ parameter:

<img src="images/Circle%20Language%20Spec%20Introduction.017.jpeg" height="300" />

The terms *parameter* and *argument* are sometimes used interchangeably. They might not be entirely the same thing, but the difference might be too subtle to talk about right now.

Interfaces
----------

Another issue of objects is that they can have different interfaces. Try to consider how a employee looks to a customer and how she looks to one of her coworkers. She can do certain things for her coworker and different things for a customer. She has two interfaces. The party that refers to her might have determined which interface she has, but even though both parties are referring to the same person, she might do different things for them.

Objects may have the same ability. A type of object can have separate interfaces. Interfaces are groups of an object’s members. (The elements inside an object’s can also be called *members*.)

<img src="images/Circle%20Language%20Spec%20Introduction.018.jpeg" height="400" />

Interfaces are distinguished by triangles here.

The employee here is an advisor to the customer and to another employee a coworker. Another object that refers to the object can decide which interface to use, or may even only be *able* to use a certain one of its interfaces. An object can also have just one interface, the same one for everybody.

Where might you start, when you read a diagram like this? You could first read the containment structure. You start at the largest container, then the smaller ones. After that you might look at the relations made by the connecting lines.

You might not always start with the largest container. Maybe one symbol is highlighted. Then this symbol might be what the diagram is about and the focus might be mostly the aspects of the highlighted symbol. Then you might start at the highlighted symbol and look around. There is probably no one way of doing it.

Triangles might actually be sub objects too. One of the differences with circles is that triangles basically melt together with their container.

Objects, be it triangles, are an way to give different types, shared characteristics.

Conclusion
----------

Hopefully this introduced you to the basics of the Circular language.

[back](..)