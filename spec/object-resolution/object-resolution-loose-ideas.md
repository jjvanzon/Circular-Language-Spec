Object Resolution | Loose Ideas
===============================

`[ Draft ]`

[back](./)

__Contents__

- [Inheritance en Overloading (overloaded default properties)](#inheritance-en-overloading-overloaded-default-properties)
- [From the Original Symbol Documentation](#from-the-original-symbol-documentation)
    - [Command Resolution](#command-resolution)
        - [Overriding](#overriding)
        - [Exclusion](#exclusion)
        - [Overloading](#overloading)
        - [Shadowing](#shadowing)
        - [Merging](#merging)
- [Other Ideas](#other-ideas)

## Inheritance en Overloading (overloaded default properties)

2008-06-11

< 2008-09-02  Inheritance and overloading is very tightly related if you look at it from the following perspective. Perhaps other object resolution principles could also go under inheritance this way. >

Een attribute met sub objecten, die overloaded default properties zijn:

```vb
If FutureCancellationsWipedOut = True And FutureCancellationsWipedOut > 10 Then
End If
```

FutureCancellationsWipedOut heeft dan twee default properties:

```vb
Truth As Boolean
Count As Integer
```

Als je FutureCancellationsWipedOut vergelijkt met een boolean, dan resolvet dat in het vergelijken met FutureCancellationsWipedOut's Boolean property Truth. Als je FutureCancellationsWipedOut vergelijkt met een integer, dan resolvet dat in het vergelijken van FutureCancellationsWipedOut's Integer property Count.

Default Property = Inheritance from a sub object

Iets mag wel inheriten van twee dingen met dezelfde interface, maar als je een van de twee interfaces raadpleegt, moet je wel disambiguaten, dus direct naar een bepaalde interface wijzen. Je kunt niet een referentie met interface A laten verwijzen naar object, dat van twee objecten inherit, die beide alleen maar interface A hebben. Je zult dan moeten kiezen en verwijzen naar een specifieke interface.

Als je refereert naar een default property van iets, dan heb je
in je diagram en je text code TOCH een referentie naar de parent
van de default property.

Disambiguaten moet dus toch in zowel het diagram als in text code. Als je verwijst naar een object via een referentie met een bepaalde interface, die ook wordt ondersteund door dat object, dan wijs je niet direct naar de interface van dat object, maar naar het object en implicit verwijst het door naar een specifieke interface, maar dat zie je niet. Dat zie je hooguit wel imaginarily aangegeven in het diagram, doordat de ononderbroken lijn verbonden aan het object, met een doorzichtige stippellijn doorverbonden wordt met een interface, maar dat laatste lijnstuk is imaginary.

JJ

## From the Original Symbol Documentation

### Command Resolution

The following methods let a parent mess with the commands of a child:

- Overriding
- Exclusion
- Overloading
- Shadowing
- Merging

Overloading, shadowing and merging are about which command to call if several commands have the same name. In text code you couldn’t easily see which command of the bunch is called. In diagram code it is always clearly visible which command you’re calling, but if they have the same name, then in text code it is less easy to see. Overloading, shadowing and merging work with this phenomenon.

Overriding and exclusion are techniques equally useful in both diagram code and text code. The others: overloading, merging and shadowing, are mostly useful in text code.

#### Overriding

Overriding means that a parent can replace a command of its child by another. A child decides whether a command of his is overridable or not.

![](images/0.%20Object%20Resolution%20Introduction.001.png)

This is a type with an overridable command B, called by the child. The access symbol on the right means that the Command Reference Set is public. Therefore you can make B redirect to a command that the parent defines.

![](images/0.%20Object%20Resolution%20Introduction.002.png)

The parent overrode the overridable command B. A call to B might resolve to a call to C instead. You can see that overriding means that the parent gives a child’s command a reference line to one of its own commands.

In the replacement command, you can still call the base command. That way you can both override commands of the child or extend them.

![](images/0.%20Object%20Resolution%20Introduction.002.png)

Overridden commands are called by the child and that way they’re a means for a child to call a command of the parent.

An overridable command that is only for communication to the parent is left empty by the child and is only filled in by the parent. This kind of overridable command is therefore also called a virtual command of the child.

#### Exclusion

Exclusion is already covered extensively, but it can also be regarded a command resolution technique. A parent can exclude members from a published object or base object.

#### Overloading

< Overloaded objects>

< A command can also have multiple interfaces by using triangle symbols. This enables the possibility to have multiple parameter configurations for the same command. >

< This is an example of how text code can affect the behavior of the diagram. Call line automatically changes when parameters of different types are assigned. Oh no, after compilation the text identifiers might not exist anymore. Then it’s gotta become a deep system aspect the overloading, independent of text code. Text code and diagram code might simply be affected by the overloading concept. It should be like this, because of reasons discussed in the language integration chapter. >

Overloading means that you give several commands the same name, while they have a different interface. This is handy if you wish to make different variations of similar functionality.

The operator command + for instance is richly overloaded. Operator + always has two parameters: the two operands. The two operands can be of many different types and each type configuration requires a separate command. Which command is called is determined by the types of objects assigned to the parameters.

In diagram code you may see the difference between a call to one command or the other. In text code, however, as well as in certain abstract views on the diagram the effect is more subtle and you won’t see the difference between a call to one command or the other. This is actually a nice, and wanted effect.

Given is the text code below:

```
Object Type 1
    Integer X
    Double Y
    Float Z
    Command Command 1
        X + Y
        X + Z
    End Command
End Object
```

The following might be the diagram code without mentioning the types of objects nor command calls:

![](images/0.%20Object%20Resolution%20Introduction.003.png)

The outer circle is Type 1. It declares the three basic object X, Y and Z. It also contains the command Command 1, in which are performed two plus operations to which references to the basic objects are passed.

However, when you do mention the types of objects and command calls, you see that two different commands are called.

![](images/0.%20Object%20Resolution%20Introduction.004.png)

When you display the called commands the subtlety is gone, but in this abstraction of the diagram you’ve simply *chosen* to see the difference:

![](images/0.%20Object%20Resolution%20Introduction.005.png)

All three diagrams above describe the same code, only in one diagram some parts are left out and some are visible while in another diagram other things are left out or visible. Abstract Symbol is covered in detail in another chapter < >.

The + command has a special notation: an operator notation, which is a customized representation of a command call and its parameters. This method is discussed in the ‘Text Code’ and ‘Language Integration’ chapters.

The names of commands that overload each other are always equal. The configuration of a command’s public objects determines which command is called. This configuration of public object includes: the object count, object types and object names.

Usually the count and types of parameters are varied, but if two overloaded commands only differ in parameter *names*, in text code it is required to *name* the object when you call the command.

< Picture: text code and diagram code with overloaded commands that only differ in parameter names. >

When you change a parameter to an object of a different type, then the call line of the call might automatically point to another command.

< I need pictures with that. >

#### Shadowing

< Can shadowing change so that the target of a line  is changed at run time automatically because of shadowing? If that’s so then shadowing is a way in which text code affects the behavior of the diagram. Same darn problem after compilation no text identifiers anymore >

Shadowing is handy when you use a triangle: a base type or an extra interface implementation.

![](images/0.%20Object%20Resolution%20Introduction.006.png)

The two lines are calls to the triangle’s members.

When you want to use a name that’s already used by the base type, you can shadow it and calls might be made to the shadowing member instead:

![](images/0.%20Object%20Resolution%20Introduction.007.png)

The difference with overriding is that the base type still calls its own member, not the shadowing member.

![](images/0.%20Object%20Resolution%20Introduction.008.png)

*I* still calls its own A, while P and anyone else calls P’s A.

A parent can still call the shadowed member, but this might require qualification with the interface name, or the shadowed member might be called:

A

![](images/0.%20Object%20Resolution%20Introduction.009.png)

I.A

![](images/0.%20Object%20Resolution%20Introduction.010.png)

I.A is inaccessible outside the parent, for the parent has chosen to shadow it.

A member is automatically shadowed if the parent of a triangle defines a command with exactly the same characteristics as the triangle’s command. The parent can freely shadow any member of the child.

#### Merging

When a command has the same name and configuration of public members then in text code there is no way to distinguish calls to either command. What happens automatically is that the *‘nearest’* member *shadows* the member *further* away.

![](images/0.%20Object%20Resolution%20Introduction.011.png)

A second option when you can’t distinct a call to one command from a call to the other is simply for *both* commands to be called. This is called merging the two commands and in that case the call might resolve in calling *both* commands. If you want to address a specific command, you could qualify the call with the name of the container of the command, if that might make a difference. In diagram code you can see the two commands as separate squares and you *can* see the difference between a call to command A and a call to command B.

< Picture 27: of text code call to merged command with next to it the diagram code >

< Picture 28: of text code with qualifications that call a specific command >

Merging is handy for instance when a symbol contains two interface implementations and each interface implementation contains a member with the same name and public members.

< Picture of that >

When the merging commands reside in *exactly the same container*, they can not be separately called. They are always simultaneously called. In diagram code you might be able to express a call to a specific command, but it is forbidden to make such a call, because this might be impossible to express in text code.

< Picture of that (29): the legal situation and a picture with a red cross through it showing a forbidden way of calling and showing that the call might look the same in text code >

That ensures that diagram code and text code are exchangeable and can be mutually used.

< Merging should be a technique, not embedded in the language. When it’s about calling both commands of the triangles, you might shadow those commands with a command that calls both. >

## Other Ideas

Conversion / Object Resolution,  
2009-05-12

What if you have multiple possible conversion commands? One has to be selected for implicit conversion. This has to be disambiguated in that case, through object resolution or explicit conversion. You might not be concerned with all the conversion commands in the world, just the ones out of modules you selected.

Implicit conversion is object resolution.

JJ

-----

Object Resolution,  
2010-05-18

Object resolution only happens when things are ambiguous. Things are only ambiguous if you use triangles to merge member sets (except for overloading (disputable)). Then things could start getting in each other’s way.

JJ

-----

Object Resolution,  
2020-05-24

Note that the Inheritance chapter might have content about Object Resolution topics too.

JJ