Basic Diagram Elements
======================

`[ Draft ]`

[back](..)

__Contents__

- [Introduction](#introduction)
- [Text](#text)
- [Circles & Triangles](#circles--triangles)
- [Squares & Diamonds](#squares--diamonds)
- [Pentagons](#pentagons)
- [Nonagon](#nonagon)
- [Object Symbols](#object-symbols)
- [Command Symbols](#command-symbols)
- [Lines](#lines)
- [Solid Line](#solid-line)
- [Dashed Line](#dashed-line)
- [Dotted Line](#dotted-line)
- [Wavy Line](#wavy-line)
- [Cross](#cross)
- [Relations Between Symbols](#relations-between-symbols)
    - [Containment](#containment)
    - [Lines](#lines-1)
    - [Object Reference](#object-reference)
- [Connecting Object Symbols](#connecting-object-symbols)
    - [Object Connection](#object-connection)
    - [Class Connection](#class-connection)
    - [Interface Connection](#interface-connection)
    - [Value Connection](#value-connection)
- [Connecting Command Symbols](#connecting-command-symbols)
    - [Command Reference Connection](#command-reference-connection)
    - [Command Definition Connection](#command-definition-connection)
    - [Command Interface Connection](#command-interface-connection)
- [Straight Mark](#straight-mark)
- [Cross Mark](#cross-mark)
- [Triangular Mark](#triangular-mark)
- [Line Direction, Access Marks, Line Ownership](#line-direction-access-marks-line-ownership)
    - [Lines Pointing Outwards](#lines-pointing-outwards)
    - [Diamonds More Likely to Redirect](#diamonds-more-likely-to-redirect)
    - [Access Mark Placement](#access-mark-placement)
    - [Line Ownership](#line-ownership)
- [Object Symbols Drawn with Different Lines](#object-symbols-drawn-with-different-lines)
- [Command Symbols Drawn with Different Lines](#command-symbols-drawn-with-different-lines)
- [More Suggestions for Dashed Lines](#more-suggestions-for-dashed-lines)
    - [Commands with Dashed Lines](#commands-with-dashed-lines)
    - [Object Structure Solid, Class Structure Dashed](#object-structure-solid-class-structure-dashed)
    - [Other Ideas](#other-ideas)
- [Relational Ring](#relational-ring)
- [Line Merge](#line-merge)
- [Symbol Merge](#symbol-merge)

## Introduction

This article attempts to give a more or less formal overview of elements that might appear in the diagrams.

The diagrams might involve set of basic elements, that may include the following:

![](images/Basic%20Diagram%20Elements.001.png) ![](images/Basic%20Diagram%20Elements.002.png) ![](images/Basic%20Diagram%20Elements.003.png) ![](images/Basic%20Diagram%20Elements.004.png) ![](images/Basic%20Diagram%20Elements.005.png) ![](images/Basic%20Diagram%20Elements.006.png)

![](images/solid-line.png) ![](images/dashed-line-diagonal.png) ![](images/dotted-line.png) <img src="images/Basic%20Diagram%20Elements.010.png" width="60" /> ![](images/Basic%20Diagram%20Elements.011.png)

![](images/Basic%20Diagram%20Elements.012.png) ![](images/Basic%20Diagram%20Elements.013.png) ![](images/Basic%20Diagram%20Elements.014.png)

## Text

Diagrams might also contain text. Shapes might have names that might appear as text. Numbers and dates and other values could also appear as text.

    MyObject
    My Site
    7
    3.141593
    2005-08-14
    "Hello"
    True
    False
    On
    Off

Perhaps some of the code might not be visualized graphically, but just displayed as text expressions:

    A  =  B  +  C

## Circles & Triangles

![](images/Basic%20Diagram%20Elements.001.png) ![](images/Basic%20Diagram%20Elements.002.png)

Circles and triangles may represent objects, classes or interfaces. An object might serve as the class or prototype of another object. An object could perhaps also describe the interface for another object. A choice was made to have objects, classes and interfaces be depicted by similar shapes.

A circle might be the usual symbol for an object. A triangle might have a particular function related to interfaces, which may be clarified by other text.

## Squares & Diamonds

![](images/Basic%20Diagram%20Elements.003.png) ![](images/Basic%20Diagram%20Elements.004.png)


Squares and diamonds may stand for *commands*. A square may denote an *inactive* command, that might not run. Such a square might be use as a *definition* for other commands. A diamond might depict *execution*. A diamond might execute, while a square may not.

## Pentagons

![](images/Basic%20Diagram%20Elements.005.png)

A pentagon could represent a *module*. A module is like a little world in which objects and commands live. A module may be a site, a computer program, a library or any other kind of module. A pentagon could be considered an object just like circles and triangles, but a pentagon may have special purposes and behavior.

## Nonagon

![](images/Basic%20Diagram%20Elements.006.png)

A nonagon may stand for a collection or a list of things. Objects might be placed inside the nonagon, to group them together perhaps. Maybe nonagons might not be drawn with precisely nine corners.

## Object Symbols

Circles, triangles, pentagons and nonagons could be called *object symbols*.

![](images/Basic%20Diagram%20Elements.001.png) ![](images/Basic%20Diagram%20Elements.002.png) ![](images/Basic%20Diagram%20Elements.005.png) ![](images/Basic%20Diagram%20Elements.006.png) 

## Command Symbols

Squares and diamonds could be called *command symbols*, since they appeared to represent commands.

![](images/Basic%20Diagram%20Elements.003.png) ![](images/Basic%20Diagram%20Elements.004.png) 

## Lines

The idea is that, when symbols might be connected with lines, those symbols might have something in common.

![](images/Basic%20Diagram%20Elements.015.png)

Now follows an attempt to summarize how that might work.

## Solid Line

![](images/solid-line.png)

A solid line may point out an *object*. Symbols connected by a solid line might symbolize the same object. Other names for this line might be an object line or a reference line.

## Dashed Line

![](images/dashed-line-diagonal.png)

A dashed line could point out a *class* or *definition*. Symbols connected by dashed lines could be thought of as having the same class. These symbols may share similar behavior, while they might still be living as individual objects. Other names for this line might be a class line or a definition line.

## Dotted Line

![](images/dotted-line.png)

A dotted line might point out an *interface*. Shapes connected by dotted lines might give them the same interface. The idea behind that is that they may look the same from the outside, but might behave differently on the inside. Another name for this line might be an interface line.

## Wavy Line

<img src="images/Basic%20Diagram%20Elements.016.png" width="70" />

A wavy line could represent the concept of *values*. When shapes are connected with a wavy line, it might mean, they have the same value or perhaps soon might get the same value. Another name for this line might be a *value line*.

## Cross

A cross might be placed inside a symbol to indicate, that an symbol is *nothing / null*: it might not reference any object: it is empty.

![](images/Basic%20Diagram%20Elements.017.png)

## Relations Between Symbols

### Containment

Relations between symbols might be expressed by *containment:*

![](images/Basic%20Diagram%20Elements.018a.png)

### Lines

and then possibly by connecting them with *lines:*

<img src="images/Basic%20Diagram%20Elements.018b.png" width="110" />

### Object Reference

![](images/Basic%20Diagram%20Elements.019.png)

This object reference notation may be seen as that the bigger object on the left might contain a reference to the bigger object on the right. It is almost as if the left object contains the other object, but instead of containing it directly it might be pointing out to something on the outside.

## Connecting Object Symbols

Object symbols could be connected by different types of lines.

### Object Connection

When two object symbols might be connected by a solid line, it might mean that both symbols represent the same object.

![](images/Basic%20Diagram%20Elements.020a.png)

One symbol might be considered to represent the actual object while the other symbol might represent an *object reference*. An object line may point out which object an object symbol might point to. The solid line might be called an *object line* in this case, because it may point out the object.

### Class Connection

When two object symbols might be connected by a dashed line, it might mean that both symbols may share the same class, which could mean they may have the same behavior, while they might not represent the same individual object.

![](images/Basic%20Diagram%20Elements.020b.png)

A class line may point out, what class an object might have.

### Interface Connection

If two object symbols might be connected by a dotted line, this might depict that the symbols might have the same interface, which may mean they could look the same from the outside, but might be different on the inside.

![](images/Basic%20Diagram%20Elements.020c.png)

The two symbols might be two separate individual objects, they may also have a different class, so could behave differently, but since they seem to have the same interface, this might mean that from the outside they might look the same.

### Value Connection

When two object symbols might be connected with a wavy line, it might mean the objects might get the same value.

<img src="images/Basic%20Diagram%20Elements.021.png" width="110" />

This could express that the values of the two objects are the same. It might also mean transferring a value from one object to the next.

## Connecting Command Symbols

Connecting command symbols could be something parallel to connections between object symbols. Command symbols might also be connected with different types of lines.

### Command Reference Connection

When two command symbols might be connected by a solid line, it might mean that they might represent the same command object.

![](images/Basic%20Diagram%20Elements.022.png)

The object line might point out which command object the other command symbol might represent. A square connected with an object line might depict a *command reference:* a reference to a command definition. A diamond might also get an object line, that may point to another location, where the actual executable object may reside.

### Command Definition Connection

Command symbols might be connected by a dashed line. This may be used to indicate that both commands might have the same class (or *definition*) which may mean that they might get the same behavior, but might not be the same individual object.

![](images/Basic%20Diagram%20Elements.023.png)

This definition line might point out, what definition a command object might have. The diamond might be a replica of the definition, but it could be that it might be its own individual object: an individual execution of the command. It is not limited to diamonds and squares this way. Dashed lines might be used to connect any two command symbols to each other, to indicate mutuality of definition.

### Command Interface Connection

Two commands could have the same interface, which might mean that a command has parameters similar to the other command. Command symbols that might have the same interface might be connected using dotted lines:

![](images/Basic%20Diagram%20Elements.024.png)

A dotted line could be called an interface line.

## Straight Mark

![](images/Basic%20Diagram%20Elements.025.png)

(It is supposed to be about the smaller line, that appears to dissect the longer line.)

A straight mark might be used to indicate that a symbol might be __Public__, or accessible. 

The straight mark might be connected to a symbol as follows:

![](images/Basic%20Diagram%20Elements.026.png)

It might be used to indicate direction as well.

## Cross Mark

A cross mark:

![](images/Basic%20Diagram%20Elements.013.png)

might be used to indicate, that a symbol might be not accessible from the outside, or __Private__.

Here is how it might look when connected to a symbol:

![](images/Basic%20Diagram%20Elements.027.png)

A cross mark might be left out, if the choice is made that the absence of a straight mark might imply it might be __Private__ already, but there could be different ideas about that.

## Triangular Mark

A triangular mark:

![](images/Basic%20Diagram%20Elements.014.png)

may be used to indicate that a symbol that might own the line might be __Protected__. Protected is something that can play a role in the concept of inheritance. In the Circular language it might mean that a symbol might only be accessible if it is placed inside a triangle.

Here is how that might look if it is connected to a symbol:

![](images/Basic%20Diagram%20Elements.028.png)

A triangular mark might not represent an arrow. It might be confusing that a triangular mark looks like an arrow, but isn't, and a different notation for protected might be appropriate and introduced some time.

## Line Direction, Access Marks, Line Ownership

A line might have direction. The direction of a line could be expressed with an access mark:

![](images/Basic%20Diagram%20Elements.029.png)

`=>`

The direction might go from symbol __A__ to symbol __B__. The access mark might be placed before the object, that might be accessed.

Admittedly, there is the idea to just draw it as an arrow shape, but currently these access marks are suggested.

But access marks might not always be displayed to indicate line direction. Some suggestions are made here for when direction might be implied without using an access mark.

### Lines Pointing Outwards

The first suggestion for line direction is that a line might usually point outwards.

![](images/Basic%20Diagram%20Elements.030.png)

`=>`

Symbol __A__ has a line that might be pointing to Symbol __C__, because lines might tend to point outwards.

If the direction might not be outwards, it might be denoted with an access mark.

![](images/Basic%20Diagram%20Elements.031.png)

`<=`

Now symbol __C__ might then be like a pointer to symbol __A__.

### Diamonds More Likely to Redirect

The second suggestion for line direction might be that a diamond might be more likely to redirect to the command definition, than it might be for a command reference to redirect to a diamond.

![](images/Basic%20Diagram%20Elements.032.jpeg)

`=>`

The diamond might point to the square.

If the direction might be the other way around, it might be denoted with the use of an access symbol:

![](images/Basic%20Diagram%20Elements.033.jpeg)

`<=`


### Access Mark Placement

When a line crosses symbols’ borders, it might first exit borders and then enter borders.

![](images/Basic%20Diagram%20Elements.034.png)

*First come the exits a and b, and then come the entrances c, d and e.*

An idea is to put the access mark in the section between the exits and entrances. The access mark might then be placed in front of the border that may first be entered.

If the part of the line between exits and entrances might go out of view then perhaps the access mark might be placed where still visible. It could be placed in front of the last border in view that might be entered or exited:

![](images/Basic%20Diagram%20Elements.035.png)

It may be a problem to draw it like this:

![](images/Basic%20Diagram%20Elements.036.png)

This might suggest that the rightmost border might be entered, instead of exited.

### Line Ownership

Perhaps depending on how these diagrams might be applied, a symbol could only have one object line, one class line and one interface line. A symbol's lines may point *away* from the symbol. They could denote which other symbol may be its object, which other symbol may be its class and which other symbol may be its interface. Other lines connected to symbol could be considered to point *at* the symbol, instead of *away* from the symbol.

![](images/Basic%20Diagram%20Elements.037.png)

It might work similarly for commands. A command might have just one reference line, one definition line and one interface line.

## Object Symbols Drawn with Different Lines

There is an idea for drawing the shapes with different line types, for example: dashed or dotted.

One idea is that an object symbol only used as an object (*not* as a class or an interface) might be drawn with a *solid* line.

![](images/Basic%20Diagram%20Elements.001.png) ![](images/Basic%20Diagram%20Elements.002.png) ![](images/Basic%20Diagram%20Elements.005.png) ![](images/Basic%20Diagram%20Elements.006.png) 

If an object symbol might only used as a class, it might be drawn out with a *dashed* line. 

![](images/Basic%20Diagram%20Elements.038.png) ![](images/Basic%20Diagram%20Elements.039.png) ![](images/Basic%20Diagram%20Elements.040.png) ![](images/Basic%20Diagram%20Elements.041.png) 

An idea is also that if an object symbol may only be used as an interface, it could be traced out with a *dotted* line.

<img src="images/dotted-circle.png" width="35" /> ![](images/Basic%20Diagram%20Elements.042.png) ![](images/Basic%20Diagram%20Elements.043.png) ![](images/Basic%20Diagram%20Elements.044.png) 

There may be different ideas, for when it could be appropriate to draw shapes with different types of lines.

Perhaps if object symbols might be used in several ways, for instance as an object, as well as another object’s class, the symbol might be given multiple borders. Here might be an object symbol that could serve as both an object and a class:

![](images/Basic%20Diagram%20Elements.045.png)

That way an object symbol could also have three borders at the same time or maybe more.

It is not a hard rule to use different line types for symbols. But it might work intuitively.

## Command Symbols Drawn with Different Lines

The idea for symbols drawn with different line types might also be applied to *command* symbols.

A diamond, which might represent a command call, may regularly be an instance of a square, that could represent a command definition. When the diamond is an instantiation, it might be seen as somewhat of an *object*. But a diamond might sometimes be used as a definition, more like a *class*. When a diamond is used as a definition, it might be seen as both an object and a class, so it might be given both a solid border as well as a dashed border, indicating that it might be both an instance, and a definition.

![](images/Basic%20Diagram%20Elements.046.png)

If a diamond might not used as a definition, it might only get a solid border.

![](images/Basic%20Diagram%20Elements.047.png)

It might be that a diamond might regularly be considered an instance, so it might often have just a solid border. It may become uncommon for it to be drawn with just a dashed line:

![](images/Basic%20Diagram%20Elements.048.png)

A square may be used often as a definition. The idea was proposed that if something may be used as a definition, it might be drawn with a dashed line:

![](images/Basic%20Diagram%20Elements.049.png) 

A choice could be to not do this, because otherwise you might mostly see dashed squares.

![](images/Basic%20Diagram%20Elements.050.png)

It depends the choices of how to use this notation of borders with different line styles.

There may be a particular case where you might draw a square with a dashed line, but the suggestion for this may might wait.

Both command calls and command definitions may function as the interface for another command symbol. In that case the idea is that the command symbol may get an extra dotted border.

![](images/Basic%20Diagram%20Elements.051.png)

It could be an idea that if a square functions solely as an interface for a command, the square might be drawn with just a dotted border:

![](images/Basic%20Diagram%20Elements.052.png)

It is suggested here, that a diamond might so often be thought of as an instance, that you might choose to always show the solid line and not draw it with just a dotted border, so not like this:

![](images/Basic%20Diagram%20Elements.053.png)

But it may depend on specific notation choices.

## More Suggestions for Dashed Lines

### Commands with Dashed Lines

Previous text tried to show that command symbols might scarcely be drawn with dashed lines.

However, in a certain case it might be drawn with a dashed line. When drawing out the diagrams, the class structure inside a module could be drawn out with dashed lines. To also draw out the command structure with dashed lines, the *target definitions* of commands might be drawn out with a dashed line. Later text may show what a target definition might be.

![](images/Basic%20Diagram%20Elements.054.png)

Lines that connect commands to classes might be drawn with a dashed line.

### Object Structure Solid, Class Structure Dashed

Drawing dashed lines that way might make the structure elements and their relations be drawn out with dashed lines. It might be more intuitive that way: the class structure might be dashed, while an object structure might be drawn with solid lines.

### Other Ideas

However, there might be different ideas of how to apply dashed lines, for instance one where dashed lines are reserved for the expression of the concept of *static*. Things are open like that.

## Relational Ring

An oval shape or ring might be drawn through two lines:

<img src="images/Basic%20Diagram%20Elements.055.png" width="200" />

It might mean, that the symbols have a special relationship to each other. How this might be applied might come to light in other articles. It could be applied to the concept of *automatically synchronized bidirectional relationships*.

This notation may be a preferred alternative over the *Line Merge* and *Symbol Merge* notations introduced next.

## Line Merge

A suggestion is made here that sometimes two lines might be merged together to form one. This might be called a line merge.

The lines in the following diagram might be very closely related:

![](images/Basic%20Diagram%20Elements.056.png)

They may merge together to one line:

![](images/Basic%20Diagram%20Elements.057.png)

Lines might merge together under different circumstances, that may come to light in other articles.

There may be some reservations about using this notation, because it seem to introduce ambiguity or the suggestion of ambiguity, but the idea may still appear here and there, even though it might be deprecated.

## Symbol Merge

A symbol merge might be closely related to a line merge. In the following diagram:

![](images/Basic%20Diagram%20Elements.058.png)

Some lines and circles might merge together:

![](images/Basic%20Diagram%20Elements.059.png)

The idea of circles merging together might be called a symbol merge. How this might be applied might come to light in other articles. It could be applied to the concept of *automatically synchronized bidirectional relationships*. But the *relational ring* notation described earlier above might become the preferred alternative. The symbol merge notation may still be used here and there even though it might be deprecated.

[back](..)