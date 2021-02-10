﻿|<h1>***Circle Language Spec***</h1>|
| :- |
## **Introduction**
This chapter aims to introduce the basics of Circle language. Circle language is an idea for a computer programming language, mostly a diagram notation for visualizing computer code.
### ***Splitting up Ideas***
Something that can play a role in making software, is splitting up a larger idea into smaller ideas.

![](Circle%20Language%20Spec%20Introduction.001.png)

Here you can see the idea of *the computer*, split up into four sub ideas: the monitor, keyboard, mouse and printer.

In Circle language, the main symbol for an idea might be a *circle*:

![](Circle%20Language%20Spec%20Introduction.002.png)

Each sub idea could work more or less independently of the others. **Monitor** does its bit, **Keyboard** does its bit. It might be the super idea that would tie the sub ideas together. Meaning: the computer could make the link between monitor, keyboard, mouse and printer. The super idea might combine the sub ideas and might manage the communication between the sub ideas.

In computer programming, ideas, so both super ideas and sub ideas, might be called *objects*. Each object can be responsible for its own part of the system.

![](Circle%20Language%20Spec%20Introduction.003.png)

Each sub idea can be split up in sub ideas itself and you might go on and on splitting up ideas.

![](Circle%20Language%20Spec%20Introduction.004.png)

But to see the general point of the system, you might only need to see the top layers of the split up.

![](Circle%20Language%20Spec%20Introduction.003.png)

This might make object oriented programming a way to keep overview over a system as it grows. A clear the split up into ideas might help the understandability of the design, perhaps most importantly the general outlines / top layers. Depending on who you ask, a subdivision in objects might be the most important thing in software. So splitting up an idea into sub ideas, something that most people are probably able to do, might be the most important thing about programming.
### ***Reusing Ideas***
Dividing up into ideas may lead to the *reusability* of ideas. For instance: the idea of a *button* might be reusable. It could be used everywhere. If you would program the perfect button, nobody might ever need to program a button again. You could just reuse the same idea whenever you need a button.

Any place you use a button in your system, there could be a separate object:

![](Circle%20Language%20Spec%20Introduction.005.png)

![](Circle%20Language%20Spec%20Introduction.006.png)

A button object in general can be called a *type* of object. All the button objects can be considered objects of the same *type*. Sometimes the word *object* is used instead of the word *type*. For instance, you might speak of *the* button *object*, while you’re talking about the button *type*. It’s like by saying ‘panda’ you can refer to an individual panda (object), but also to the panda as a kind of animal (type).

There could be many types already defined, that you might use one way or another. Such as the **Button** type for instance, which you can use to build a user interface. Another type, **Integer**, represents one integer number. You might be using those all the time when you program.

Another word for type is *class*. *Type* and *class* might not precisely mean the same things, but it is pretty close and the word *class* is used in several object oriented programming languages.
### ***Commands***
Apart from a collection of sub objects, objects might contain *commands*.

![](Circle%20Language%20Spec%20Introduction.007.png)

Sub objects can again contain commands.

![](Circle%20Language%20Spec%20Introduction.008.png)

Software could not execute without commands. When you would run a command, an object would *do something*.

A button could have a **Set Text** command for instance, which might set the text displayed on the button.

![](Circle%20Language%20Spec%20Introduction.009.png)

Commands are denoted here by *squares*.

Other objects could also have a **Set Text** command. To distinguish the **Set Text** commands of different objects, you might expres this something like:

**Button . Set Text**

A command itself can consist of sub commands: the separate steps of the command.

![](Circle%20Language%20Spec%20Introduction.010.jpeg)

Sub commands are not necessarily embedded inside other commands. They can be defined separately:

![](Circle%20Language%20Spec%20Introduction.011.jpeg)

And the sub commands can be *called* from the super command:

![](Circle%20Language%20Spec%20Introduction.012.jpeg)

Calling a command has almost the same effect as inserting the called command there where you call it.

The **Redraw Button** command might be more complex. In this command the lines of the button could be drawn, the text could be drawn and whatever else might make up the display of the button. The steps of this redrawing could be delegated by yet again calling other commands. **Redraw Button** could for instance call the **Draw Line** command a number of times. So sub commands of the **Set Text** command can themselves be composed of sub commands.

![](Circle%20Language%20Spec%20Introduction.013.jpeg)

You can also see here that separately defining a command can lead to the *reuse* of commands. The **Draw Line** command is reused three times in the example above. There may be many commands already defined, that you might use one way or another. Commands like that could also be put inside in a separate type. There could for instance be a **File** type that contains commands with which to control a single computer file.

So where does it end? Would commands continue to delegate to one another and would nothing really actually happen? Well, it seems to end at a special group of commands, that do not call other commands anymore. Each of those command may execute a so called machine instruction: a basic instruction that is sent to the computer’s central processing unit (CPU) and make the *computer* *do* something. The CPU would perform a hardware defined *machine* command.

That way there can develop big command call tree-outs, which can make a single command consist of many, machine instructions, ranging from tens to thousands of machine instructions or even more.

But you do not necessarily need to see all those details in order to understand what the effect **Button . Set Text** is.

![](Circle%20Language%20Spec%20Introduction.014.jpeg)

Other names for commands could be *operations, procedures*, *functions, methods* or *routines.* There are more synonyms.
### ***Command Parameters***
Commands can have *parameters*. Those are like instructions passed along with the command that make the command behave differently. The **Button . Set Text** command, for instance, has a **Text** parameter, which indicates what the new text of the button will be.

Text can also be seen as an *idea*. It can be thought of as an *object*. That way, it is *objects* that serve as parameters.

![](Circle%20Language%20Spec%20Introduction.015.jpeg)

The command can do whatever it wants with the parameters passed to it. Arguably, all it can do with it is:

- pass the parameter to another command *or* 
- call commands of the parameter.

![](Circle%20Language%20Spec%20Introduction.016.jpeg)

*Pass the **Text** parameter on to the next command (**Format Text**).*

![](Circle%20Language%20Spec%20Introduction.017.jpeg)

*Call a command of the **Text** parameter.*

The terms *parameter* and *argument* are sometimes used interchangedly. They are not entirely the same thing, but the difference might be too suble to talk about right now.
### ***Interfaces***
Another issue of objects is that they can have different interfaces. Try to consider how a employee looks to a customer and how she looks to one of her coworkers. She can do certain things for her coworker and different things for a customer. She has two interfaces. The party that refers to her might have determined which interface she has, but even though both parties are referring to the same person, she might do different things for them.

Objects may have the same ability. A type of object can have separate interfaces. Interfaces are groups of an object’s members. (The elements inside an object’s can also be called *members*.)

![](Circle%20Language%20Spec%20Introduction.018.jpeg)

Interfaces are distinguished by triangles here.

The employee here is an advisor to the customer and to another employee a coworker. Another object that refers to the object can decide which interface to use, or may even only be *able* to use a certain one of its interfaces. An object can also have just one interface, the same one for everybody.

Where might you start, when you read a diagram like this? You could first read the containment structure. You start at the largest container, then the smaller ones. After that you might look at the relations made by the connecting lines.

You might not always start with the largest container. Maybe one symbol is highlighted. Then this symbol might be what the diagram is about and the focus might be mostly the aspects of the highlighted symbol. Then you might start at the highlighted symbol and look around. There is probably no one way of doing it.

Triangles might actually be sub objects too. One of the differences with circles is that triangles basically melt together with their container.

Objects, be it triangles, are an way to give different types, shared characteristics.
### ***Conclusion***
Hopefully this introduced you to the basics of the Circle language.