Symbol Language Basic
=====================

The New Computer Language


Introduction
------------

This first chapter explains the basics of programming. It should introduce you to programming whether you’ve programmed before or not.

### Idea Subdivision

Contemporary programming is all about splitting up a large idea into smaller ideas.

![](images/Symbol%20Language%20(2004).001.png)

Here you see the idea of *the computer*, split up into four sub ideas: the monitor, keyboard, mouse and printer.

In Symbol, the main symbol for an idea is a *circle*:

![](images/Symbol%20Language%20(2004).002.png)

Each sub idea works independently of the other ideas. __Monitor__ does its bit, __Keyboard__ does its bit, etcetera. It’s the *super* idea that ties the sub ideas together. That means that the computer makes the links between monitor, keyboard, mouse and printer. The super idea combines the sub ideas and manages the communication between the sub ideas.

Ideas, so both super ideas and sub ideas, are called objects. Each object is responsible for its own bit of the system.

![](images/Symbol%20Language%20(2004).003.png)

Each sub idea can be split up in sub ideas itself and you can go on and on splitting up ideas.

![](images/Symbol%20Language%20(2004).004.png)

But to see the general point of the system, you only need to see the top layers of the split up.

![](images/Symbol%20Language%20(2004).003.png)

This makes object programming an excellent way to keep overview over the system as its complexity builds up. The understandability of the design is dependent on how outspoken and clear the split up into ideas is, especially the top layers. I think that the subdivision in objects is the most important thing in your software. So splitting up an idea into sub ideas, something that even non-programmers can do, is the most important thing about programming.

### Reusing Ideas

Well design in grouping ideas leads to the *reusability* of ideas. For instance: the idea of a *button* is very reusable. It’s used everywhere. If you program the perfect button, nobody ever needs to program a button again. You can just reuse the same idea whenever you need a button.

Any place you use a button in your system, there is a separate object:

|![](images/Symbol%20Language%20(2004).005.png)|![](images/Symbol%20Language%20(2004).006.png)|
| :-: | :-: |

A button object in general is a *type* of object. All the button objects are objects of the same *type*. The separate buttons are so called *instances* of the type. Many times the word *object* is used instead of the word *type*. For instance, you can speak of *the* button *object*, while you’re talking about the button *type*. It’s like by saying ‘panda’ you can refer to an individual panda (object), but also to the panda as a kind of animal (type).

There are many types already defined, that you will be using one way or another. Such as the __Button__ type for instance, which you can use to quickly build a simple user interface. Another type, __Integer__, represents one integer number. You can hardly avoid using __Integers__.

### Skill comes with Time

The more experience you gain in splitting up large ideas into smaller parts, the better your designs will get, because in time you’ll get a clearer view on how to make a system complete and how to subdivide systems. At first you may imagine that the computer will do a lot of the work automatically for you. You’ll think: “When I do this and that, the rest will be done automatically.”. However, if you build a system, you have to give *everything* a place yourself.

### Programming is Never Easy

Some texts explaining programming environments try to sell it to you that software programming is easy. That is never true. Those texts are written to *sell* the programming environment, not to tell the truth. Those texts claim that the programming environment will do most of the work *for* you, while in real life, what the programming environment does *for* you, is just run existing programs, not program new software. The text will say you’ve programmed something, while you’ve really just run something that was already programmed. Only if you want to take *no* decisions on how the software is going to work, programming is easy. But then it’s not really programming. If you want to make decisions about how you want your software to be, software programming is *not* easy. In programming, you have to give everything a place *yourself*. If you reuse someone else’s object, you have to be aware of what the object will do for you. Worse, many times you encounter problems with someone else’s object that you can’t fix, because you can’t change the inner workings of the object. This can lead to wanting to program everything yourself and if you’re stubborn enough, or fed up enough, you become *me,* and actually try to start to program everything yourself. Learn to work with other people’s objects. I’m working on that too. *And* I’m trying to make *the* __Button__ for which no one wants a replacement. Or if they do want a replacement, they’ll still want to use the base of my button as a foundation.

![](images/Symbol%20Language%20(2004).007.png)

### Ancestry

The containment structure or encapsulation (structure) of ideas is also called the *ancestry*. Terms for containment are analogous to the terms for *ancestry*.

I will mention all the terms part of this analogy here at a glance.

*Deeper* objects, the smaller, contained circles, are called *ancestors*, because they are the elements that *higher* objects are composed of. Deeper objects are also called *lower* objects, analogous to lower species, that are less composite. Higher objects are called *descendants*, because they are *derived* of deeper objects and *inherit* from them. For that, containers are also called *derived objects* or *derived types*.

In more direct relations the ancestry analogy changes. The analogy changes from related to *genetics,* to *family ties*. Grandma is considered *higher* in rank than a grandchild, but if it’s your great great great great great great grandma, then she’s considered genetically less evolved and *lower*. So the ranking changes in more direct kinship. Contained objects are lower, so ancestors. Directly contained objects are also lower: children.

This is normal for those who’ve programming in other object oriented languages, but if you’re introduced for the first time it should be weird that children are ancestors. You can also speak of grandchildren and grandparents. The terms parent and child and related terms are always family rank related. In a way, a child is lower than a parent. In more distant relations, terms are related to genetic evolution: descendants are considered higher entities, while ancestors are lower.

A child object can also be called a *base*, or *base* *object*, because it forms the base of the parent.

A structure of containment is called an *ancestry*. An ancestry with a lot of *levels*, or *layers* is also called a *deep ancestry*. A system with relatively little layers can be called a *shallow ancestry*. *Deeper layers* are also called *bottom layers*. *Higher layers* are also called *top layers*. A deep layer can also be called a *foundation*.

A parent can also just be called the *container*. A child, less often, *the contained*.

The terms *sub object* and *super object* I’ve already mentioned.

Each symbol in the ancestry can also be called a *capsule*, because it encapsulates other symbols.

The parent of a child can also be called the *direct parent*, to emphasize that it’s about the capsule *directly* above the child. The same way, the parent has *direct children*. Grandchildren and deeper symbols can also be called indirect children, which makes the term indirect children a synonym for *ancestors* (Following it yet? Ancestors = indirect children. Weird.). The term direct can also be combined with the other terms, for instance *directly contained*, *direct container*.

Ancestry can also be called *object structure* in a lot of cases. But object structure really involves more than just ancestry and ancestry really involves more than just object structure, but you will hear more on that later.

Other terms of family ties can be used just as well. Words such as cousins, siblings or uncle are allowed. Sibbling would be objects directly in the same parent.

![](images/Symbol%20Language%20(2004).008.png)

Cousins are objects whose parents are sibblings.

![](images/Symbol%20Language%20(2004).009.png)

#### Terms

Here’s a list of basic terms:

|Containment|
| :-: |
|Encapsulation|
|Object structure|
|Ancestry|
|Levels|
|Layers|
|Capsule|
|Indirect|
|Direct|
|Super|Sub|
|Container|Contained|
|Parent|Child|
|Grandparent|Grandchild|
|Descendant|Ancestor|
|Shallow|Deep|
|High|Low|
|Top|Bottom|
|Above|Below|
||Foundation|
|Derived|Base|
|Derivation||
|Inheritance||
|Sibbling||
|Cousin||
|Uncle||
|Etcetera...||

### Identifiers

An identifier is a name for a symbol (for instance for a circle). It can be any string of characters. Unlike a lot of other programming languages, identifiers in Symbol can contain spaces and they can begin with numbers. Examples:

```
Id
Id1
1toNFilters
1 to N Filters
I’m an identifier
Object A
```

A type gets an identifier, but also the separate objects get their own identifiers.

The same name can be used for different symbols. Which of the *Johns* you’re talking about depends on its context (where it resides). Sibblings usually don’t have the same name, because they reside in the same context. Only in a very special case sibblings can have the same name.

### Procedures

Apart from a collection of sub objects, an object contains *procedures*.

![](images/Symbol%20Language%20(2004).010.png)

Sub objects again contain procedures.

![](images/Symbol%20Language%20(2004).011.png)

Software can’t execute without procedures. When you run a procedure, an object *does something*.

A button could have a __Set Text__ procedure for instance, which sets the text displayed on the button.

![](images/Symbol%20Language%20(2004).012.png)

Procedures are denoted by *squares*.

Other objects could also have a __Set Text__ procedure, therefore to identify the __Set Text__ procedure of the __*Button*__ object you notate:

```
Button . Set Text
```

A procedure itself consists of sub procedures: the separate steps of the procedures.

![](images/Symbol%20Language%20(2004).013.jpeg)

Sub procedures are usually not embedded inside other procedures. They are defined separately:

![](images/Symbol%20Language%20(2004).014.jpeg)

And the sub procedures are *called* from the super procedure:

![](images/Symbol%20Language%20(2004).015.jpeg)

Calling a procedure has almost the same effect as inserting the called procedure there where you call it.

The __Redraw Button__ procedure is rather complex. In this procedure lines of the button are drawn, the text is drawn and whatever else makes up the display of the button. The steps of this redrawing are delegated by yet again calling other procedures. __Redraw Button__ could for instance call the __Draw Line__ procedure a number of times. So sub procedures of the __Set Text__ procedure are themselves composed of sub procedures.

![](images/Symbol%20Language%20(2004).016.jpeg)

You can also see here that separately defining a procedure can lead to the *reuse* of procedures. The __Draw Line__ procedure is reused three times in the example above. There are many procedures already defined, that you will use one way or another. Most of these procedures are encapsulated in a type. There’s for instance a __File__ type that contains procedures with which to control a single computer file.

So where does it end? Procedures would continue to delegate to one another and nothing would really actually happen. Well, it ends at a special group of procedures that don’t call other procedures anymore. Each of those procedures executes a so called machine instruction: a basic instruction that is sent to the computer’s central processing unit (CPU) and make the *computer* *do* something. The CPU performs a hardware defined *machine* procedure.

That way there can develop a big procedure call tree-out, which makes a single procedure consist of many, many machine instructions, ranging from tens to thousands of machine instructions or even more.

Justs like with the kitchen example: you don’t necessarily need to see the details of the procedure in order to understand what the effect __Button . Set Text__ is.

![](images/Symbol%20Language%20(2004).017.jpeg)

Procedures can also be called *operations*, *functions* or *routines* and there are even more synonyms. But I will usually stick to the term *procedure*.

### Many Don’t Get It

Many think it’s not important to have a good subdivision in sub ideas and to come up with good names. They think that something just needs to work and then it’s ok. Consider what happens when you take away good naming and good subdivision: all you’re left with is procedures calling eachother for no apparent reason until they resolve in machine instructions, the names of which are fortunately already picked by Intel(\*. The clarity of code is dependant on the clarity of names and subdivision. The less clear the names and subdivision are, the less sense the code will make.

Sometimes I spend most time thinking about a subdivision of code and about names, not testing if something is doing what I want it to do. I can spend ten minutes figuring out a name. If I don’t give it a good name, the code is not going to make sense.

An identifier is the only thing that can tell something about the contents of a symbol when its contained symbols aren’t shown. A kitchen consists of hundreds of things, but if you say ‘kitchen’ you really know enough. If it’s given a bad name, then you don’t know what it does. Then the only way you can know what it does is by looking at its contents and hope that good names are used there. If the names inside are no good either, there is still no way of telling what it does. You can’t tell what it does from just procedure structure and object structure. Eventually there has to be names. If all names suck, then you rely on interpreting machine instructions. If Intel(\* would have given indistinguishable names to machine instructions then you would be lost. You can’t see anything in the code then. All you could rely on is documentation saying what’s what, if such documentation even exists. In some cases where you use proper naming, you hardly need to supply any documentation.

Even when you don’t think a lot, when giving something a name, even then naming is important. The names, however quickly and poorly chosen, are distinguishable or the consequence is that you can’t see what your code does, unless you look into what’s under the name, hoping you’ll recognize something there.

### Procedure Parameters

Procedures can have *parameters*: instructions passed along with the procedure that make the procedure behave differently. The __Button . Set Text__ procedure, for instance, has a __Text__ parameter, which indicates what the new text of the button will be.

Text is an *idea*. It is an *object*. It is *objects* that serve as parameters.

![](images/Symbol%20Language%20(2004).018.jpeg)

The procedure can do whatever it wants with the parameters passed to it. All it really can do with it is again pass the parameter to another procedure *or* call procedures of the parameter.

![](images/Symbol%20Language%20(2004).019.jpeg)

*Pass the Text parameter on to the next procedure (Format Text).*

![](images/Symbol%20Language%20(2004).020.jpeg)

*Call the a procedure of the Text parameter.*

The terms *parameter* and *argument* are often intermixed. For now you can assume that a parameter is a setting of a procedure and an argument is the value that it holds. That’s not the entire truth, though, but I’ll save the exact meaning for later.

#### Input, Output and Throughput Parameters

Parameters are commonly input (instructions) for a procedure. Parameters can also be output (returned results). They make a procedure return something to the caller. One of the output parameters can be appointed to be *the* return value, which makes it sort of like the main output parameter. Some parameters can be input, and then output again. Then the procedure uses the parameter, transforms it and gives it back in the transformed state. These parameters are called throughput parameters, or in-out parameters. There are also objects in a procedure that are only used locally. Those are not usually called parameters, but sooner called *local objects*.

### Members

An object’s sub objects and procedures are also called the object’s *members*. The parameters of a procedure can also be called *members* of the procedure. *Public members* are members that can be accessed outside their container. *Private members* can be accessed only by the object that holds them and are inaccessible to the outside.

It’s *procedures* that are called. When you speak of calling an *object*, you’re talking about calling a procedure of an object (or a procedure of one of its sub objects).

### Interfaces

Another issue of objects is that they can have different interfaces. Consider how a employee looks to a customer and how she looks to one of her coworkers. She can do certain things for her coworker and much different things for a customer. She has two interfaces. The party that refers to her determines which interface she has, but even though both parties are referring to the same person, she means two totally different things to them.

Objects have the same ability. A type of object can have separate interfaces. Interfaces are groups of an object’s members. Another object that refers to the object decides which interface to use, or may even only be able to use a certain one of its interfaces. An object can also have just one interface, the same one for everybody.

Interfaces are distinguished by triangles.

![](images/Symbol%20Language%20(2004).021.jpeg)

The employee is an advisor to the customer and to another employee a coworker.

Where to start when you read a diagram like this? You first read the containment structure. You start at the largest container, then the smallers ones. After that you look at the relations made by the connecting lines.

You don’t always start with the largest container. Sometimes one symbol is highlighted. Then this symbol is what the diagram is about and it's all about the aspects of this symbol. Then you start at the highlighted symbol and look around. There’s no one way of doing it.

Triangles are actually sub objects too. The difference with circles is that triangles basically melt together with their container.

Objects, be it triangles, are an excellent way to give different types mutual characteristics.

### Inheritance

Even though you could speak of *inheritance* concerning the whole of the ancestry, originally, in other programming languages, only what the triangle does is called inheritance: a sub object’s characteristics merge with its container.

I still employ the term inheritance when I mean an object’s merging with a container. I can also use the term inheritance in normal containment if I see it fit. Repectively, the word *base* is also used as a term for a triangular sub object, but if I see it fit I will use it for a *circular* object too.

### Programming Language

A computer program is described in a *programming language*. Formerly all programming languages were textual, just like normal language. The text that describes a program is called the program’s *code*. Symbol code consists maily of *diagrams*, though. Nevertheless, the diagrams are called *code* all the same.

### Symbol

Symbol Language comes in two main variations: text code and diagram code. Both variations can fully express a system. Sometimes a system looks clearer in a diagram and in other cases it looks clearer in text. The *Sigma Data Language* is also integrated into Symbol Language, as well as others.

One great aspect of diagram code is that apart from expressing a system in full, you can also have an abstract view on the system, leaving out details or hightlighting specific details. This way the code itself can function as the analysis of it.

Object Basics
-------------

### Notation Elements

![](images/Symbol%20Language%20(2004).022.png)

Circles and triangles represent objects. For that they are called *object symbols*.

A circle is the usual symbol for an object. A triangle is a special symbol, as I explained earlier and will elaborate on later.

When I say *symbol* in this section, I’m often talking about object symbols.

Relations between symbols are expressed by *containment*:

![](images/Symbol%20Language%20(2004).023.png)

and by connecting them with *lines*, also called *lines:*

![](images/Symbol%20Language%20(2004).023.png)

![](images/Symbol%20Language%20(2004).024.png)

Dotted lines, dashed lines and solid lines.

### Object Relations

Every circle or triangle represents an object.

Every of those objects has a type. The type determines the contents of the symbol. Every object of the same type has the same contents and the contents of these objects changes simultaniously as you edit it.

A type has one interface by default: the default interface, which is formed by every public member of the type. A type can also have multiple interfaces, which are groups of its members. The default interface includes all members of these separate interfaces.

### Objects

Each symbol represents an object:

![](images/Symbol%20Language%20(2004).025.png)

You can make two symbols represent the same object by connecting them with a line:

![](images/Symbol%20Language%20(2004).025.png)

A solid line in this case is also called an *object line*, because it denotes which symbols are the same object.

### Types

Each symbol is a type:

![](images/Symbol%20Language%20(2004).025.png)

You can make two symbols be of the same type by connecting them with a dashed line:

![](images/Symbol%20Language%20(2004).025.png)

Both symbols are of the same type, but they are separate objects.

Every symbol of the same type has the same contents. The type can be edited by editing either symbol and their contents will change simultaniously.

A dashed line in this case is also called a *type line*, because it denotes which symbols are the same type.

### Interfaces

Every symbol has an interface. The interface is represented by the *public* contents of the symbol. Anything *private* is the *implementation* of the interface.

In a normal procedure, for instance, the code lines of it are actually private and part of the implementation. Only the procedure name, its parameters and return value are public and are part of the interface.

So a symbol always has an interface: its public members.

To make two symbols have the same interface you connect them with a dotted line:

![](images/Symbol%20Language%20(2004).025.png)

This dotted kind of line is also called an *interface line*, because it denotes which symbols have the same interface. The public members of both symbols are the same, but each symbol has its own *implementation*. The symbols are not necessarily the same type nor the same object.

This way you can give a type an already defined interface.  That for instance allows objects that can work with a certain interface, to link to objects of the new type.

Editing the interface can be kind of dangerous, because if you remove an interface member, you remove all the implementations of the member in all the types that have that interface. If you do edit an interface, then the *interface* of the connected symbols changes simultaniously, but *not* the implementation.

#### Two Interfaces

You also have the ability to give a symbol two separate interfaces. For this, the triangle symbol is taken in use.

The following is the basic notation for a symbol that implements two separate interfaces:

![](images/Symbol%20Language%20(2004).026.png)

A triangle represents *the implementation of an interface*. Triangles *are*, however, often called *interfaces* of the object. Don’t start to think that *only triangles* are interfaces. Any symbol can function as an interface. A triangle is the *implementation* of an interface. 

#### Triangle Versus Circle

A triangle, just like the circle, is a:

- Type
- Object
- Interface source
- Creatable (explained soon)

![](images/Symbol%20Language%20(2004).025.png)

Using a triangle instead of a circle:

![](images/Symbol%20Language%20(2004).027.png)

Sees to it that:

- __B__’s members are accessed as if they were __A__’s own members
- You can refer to type __A__ as if it were of type __B__

![](images/Symbol%20Language%20(2004).028.png)

So a triangle is a sub object of the container, but its members are like part of the container and the container can be referred to as if it has the type of the triangle.

#### Inheritance

You can accomplish simple inheritance by using a triangle.

To give a symbol a base type you put a triangle in it and connect it to its type. This type is then the base type:

![](images/Symbol%20Language%20(2004).029.png)

__B__ is the base type, __A__ is the derived type, because it now includes __B__’s interface with __B__’s implementation.

Inheritance in Symbol is actually more refined than in the C++ programming language. In Symbol a symbol’s base object can be any object, even an object that already existed or an object that is externally defined. In C++ the derived object always contains its *own* base object.

So you can make the base object an object that already existed:

![](images/Symbol%20Language%20(2004).029.png)

__B__ is the base *object* of __A__. And you can still refer to __A__ as if it was of type __B__.

Or you can make one object serve as multiple symbols’ base object:

![](images/Symbol%20Language%20(2004).030.png)

__A__ is the base *object* of all the other circles, not only the base *type*.

Conversely, using a triangle giving a symbol an interface is *like* using inheritance, but defining the base type right inside the derived type.

![](images/Symbol%20Language%20(2004).031.png)

__A__ and __B__ are the base types of __C__, but __C__ defines these base types itself.

#### Member Grouping

Because a triangle basically merges with its container, it’s like you aren’t bothered by the borders of a triangle. That makes the triangle an easy way of grouping members, without harming the way you access the members.

You can also put a circle around members to group them. That changes the way you access the members, though. You’d have to qualify the access with the name of the grouping circle.

#### A Circle Contains But Interface Implementations

Each circle implements at least one interface. Nothing is defined outside the context of an interface implementation so inside a circle nothing else can be defined but a set of interface implementations and the interface implementations contain the rest.

Since a triangle represents an interface implementation and a circle contains but interface implementations you’d think that a circle contains at least one triangle: one interface implementation. A circle, though, is itself an interface implementation and triangles are merely used to distinguish between *separate* interface implementations.

A circle:

![](images/Symbol%20Language%20(2004).028.png)

is *not* shorthand for:

![](images/Symbol%20Language%20(2004).028.png)

because the triangle is its own object. The first diagram shows one object and the second diagram shows two.

### Same Object, Same Type

#### Same Object, Same Type

If you make two symbols the same object:

![](images/Symbol%20Language%20(2004).025.png)

They automatically are the same type, sort of like this:

![](images/Symbol%20Language%20(2004).025.png)

#### Same Type, Same Interfaces

When you make two symbols the same type:

![](images/Symbol%20Language%20(2004).025.png)

They (by default) automatically get the same interfaces, sort of like this:

![](images/Symbol%20Language%20(2004).025.png)

#### Same Object, Same Type, Same Interfaces

If you make two symbols the same object:

![](images/Symbol%20Language%20(2004).025.png)

They automaticaly have the same type with (by default) the same interfaces, sort of like this:

![](images/Symbol%20Language%20(2004).025.png)

#### Not Shorthand

However, you can’t call it *shorthand*. The following two are not precisely the same thing:

![](images/Symbol%20Language%20(2004).025.png)

![](images/Symbol%20Language%20(2004).025.png)

The lack or presence of a type line *does* make a difference, as will be explained in a later chapter.

### Creation

An object takes up memory. When an object is not used, you might not want it to exist in memory. An object symbol represents an object, but the object doesn’t necessarily need to be created. Some object symbols aren’t meant to ever be created. Object symbols that serve as just types for instance, are usually never created.

After a symbol is created, it is drawn differently. For instance by filling it:

![](images/Symbol%20Language%20(2004).032.png)

Or by drawing it with thicker lines:

![](images/Symbol%20Language%20(2004).033.png)

Or by drawing it with an alternate color:

![](images/Symbol%20Language%20(2004).028.png)

When objects are tied together with object lines, they represent the same object, but this object does not neccesarily have to be created. But when it *is* created, the connected symbols will represent the same object. In the C++(\* programming language, this is not possible.

When you create a symbol the ‘normal’ way, you create it having its own type.

|<p>*Before creation*</p><p>![](images/Symbol%20Language%20(2004).034.png)</p>|<p>*After creation*</p><p>![](images/Symbol%20Language%20(2004).035.png)</p>|
| :-: | :-: |

You can also specify an alternate type on creation.

|<p>*Before creation*</p><p>![](images/Symbol%20Language%20(2004).034.png)</p>|<p>*After creation*</p><p>![](images/Symbol%20Language%20(2004).036.png)</p>|
| :-: | :-: |

The alternative type, however *must* support the same interface. It may have completely the same interface:

|<p>*Before creation*</p><p>![](images/Symbol%20Language%20(2004).037.png)</p>|<p>*After creation*</p><p>![](images/Symbol%20Language%20(2004).038.png)</p>|
| :-: | :-: |

But the new type may also only *support* the interface of the type it had before the creation:

![](images/Symbol%20Language%20(2004).039.png)

*After Creation*

What you see is that when you create an object giving it a different type, the diagram is actually changed at run time. If you use an alternate type when the symbol is created, its type line is changed. If the symbol did not yet have a type line, then it gets one.

|<p>*Before creation*</p><p>![](images/Symbol%20Language%20(2004).040.png)</p>|<p>*After creation (specifying a type)*</p><p>![](images/Symbol%20Language%20(2004).041.png)</p>|
| :-: | :-: |

### Referencing a Parent

You can also reference a parent or descendant:

![](images/Symbol%20Language%20(2004).042.png)

I mention this separately here, because you won’t see this notation very often, but it’s possible all the same.


Procedure Basics
----------------

< a diamond is also notated pointier than a square. So this is be a diamond too:

[Picture with a pointy square]

\>

### Notation Elements

*Squares* and *diamonds* are procedure symbols. They represent elements of the procedure structure.

![](images/Symbol%20Language%20(2004).043.jpeg)

The square is the usual symbol for a procedure. The diamond is a special symbol, as I will show lateron.

Relations between procedures are expressed by *containment*:

![](images/Symbol%20Language%20(2004).044.jpeg)

And by connecting them with lines, or *lines:*

![](images/Symbol%20Language%20(2004).045.jpeg)

There can only be solid or dotted lines between procedure symbols.

### Procedures

Procedures are denoted with squares:

![](images/Symbol%20Language%20(2004).046.png)

To make two squares be the same procedure you connect them with a line:

![](images/Symbol%20Language%20(2004).047.png)

A call to either square is a call to the same procedure.

### Procedure Call

To make one procedure call another procedure, you put a diamond in the calling procedure and you connect it to the procedure to call.

![](images/Symbol%20Language%20(2004).048.jpeg)

You can say __A__ calls __B__, or __B__ is called from __A__. You could say that the line is directed outwards: the call line first exists a square, to next find its target procedure. The connected symbols here represent the same procedure. The side effect of a diamond though, is that it *executes*. __C__ is now part of procedure __A__ and it will execute when __A__ executes. It’s like the code of __B__ is inserted right into procedure __A__. Considering that, it seems that the direction of the line doesn’t really matter: both symbols simply represent the same procedure. But a procedure does have a definition in one place while the other symbols are calls or references to it. The topic of direction is looked at closer in the *Lines* chapter, but I’ll tell you now that the direction of a line is usually outwards.

If one square is called, its contained squares are called too.

![](images/Symbol%20Language%20(2004).049.jpeg)

When __A__ is called, __B__ is called. When __B__ is called, __C__, __D__ and __E__ are called.

### Procedure Reference

A diamond connected to another procedure is a call. A square connected to another procedure is a mere *reference* to the procedure.

![](images/Symbol%20Language%20(2004).050.jpeg)

A call to any square that represents the same procedure is a call to the same procedure. A reference to either of the procedure references is a reference to the same procedure.

Therefore, when you call a procedure reference, the referenced procedure is called:

![](images/Symbol%20Language%20(2004).051.jpeg)

When __A__ calls __B__, it’s actually calling __C__.

When a procedure is called, the contained procedure *references* are *not* called.

![](images/Symbol%20Language%20(2004).052.jpeg)

When __A__ is called, __B__ and __D__ are called, but not __C__.

### Procedure Clause

A diamond without a line:

![](images/Symbol%20Language%20(2004).053.jpeg)

Also executes, when its parent procedure executes, but it doesn’t delegate to another procedure, like a call does:

![](images/Symbol%20Language%20(2004).054.jpeg)

It is an undelegated part of a procedure, called a *clause*.

Because a diamond doesn’t have to be a call, it is also called an *execution* or an *execution point*.

An undelegated square inside a procedure is also considered a clause.

![](images/Symbol%20Language%20(2004).055.jpeg)

but it doesn’t execute, unless you call it.

![](images/Symbol%20Language%20(2004).056.jpeg)

A splineless diamond is also called an *active clause*, while a splineless square is also called an *inactive clause*.

### Procedure Contents

A procedure can contain anything an object can. Anything you can declare inside a type can also be declared in a procedure.

![](images/Symbol%20Language%20(2004).057.jpeg)

That way procedures are like types, but procedures have special characteristics that I’ll lay out later.

The objects inside a procedure can be regarded:

- Input parameters
- Output parameters
- Throughput parameters
- Return values
- Local variables

The input parameters of a procedure are its writable objects. The output values are its readable objects. Objects that are read-write are like in-out or thru parameters. One readable object can be chosen to be the return value, which promotes it to being the main output parameter. This does not give it extra capabilities, only an extra notation in certain places. The return value is denoted in a diagram by putting the term __Return__ near one of the parameters. The private objects are the procedure’s local variables. If __A__ is an input parameter and __B__ is an output parameter, you can also say that the procedure *takes* __A__ and *gives* __B__.

Squares inside procedures are non executing clauses or procedure references. Diamonds inside procedures are executing clauses or procedure calls.

### Procedure Versus Type

*Procedures* differ from *types* in the following ways:

- They can execute
- A new procedure object is created *on each call* to the procedure and the procedure object is destroyed soon after the call.
- The public writable objects are written only right before the call.
- The public readable objects are read only right after the call.

### Required and Optional Parameters

As a procedure is like a type it may seem that you have full freedom regarding which objects you write and which you don’t. However, many parameters of procedures are *required* parameters. This means that you *must* write something to it before the call. Optional parameters are ones that do not necessarily need to be written before the call. Required parameters are there to on one hand ensure a parameter holds a right value. That however, could have been done by the procedure’s initializing the value itself. The main point of required parameters is that a lot of times the function of a procedure just doesn’t make sense unless you write the parameters. The programmer is made extra aware of that by making the parameter required.

In diagram code, optional parameters are denoted by displaying the word __Optional__ near the optional parameter. The other parameters are required.

### Procedure Interface

A procedure has an interface too, consisting of all public contents of the procedure: public objects (in, out or thru) and public procedures (clauses, calls and references). A procedure can have an interface line. The target of this interface line must be a procedure, in case of which both procedures get the same parameters.

![](images/Symbol%20Language%20(2004).058.png)

*Procedure with an external interface*

The interface source for a procedure can only be a procedure, not an object. Also: a procedure can *not* have multiple interfaces. The effect of allowing these two things can be imagined, but the usefulness of these structural possibilties is slim, while it would add a lot more rules to the Symbol Language.

For the time being, triangles can reside in a procedure, but only for the purpose of grouping procedure members. You can’t give these triangle any lines, because that would suggest that the procedure adopts all characteristics of an object.

### Same Procedure, Same Interface

When you make two symbols the same procedure:

![](images/Symbol%20Language%20(2004).059.jpeg)

They also get the same interface, sort of like this:

![](images/Symbol%20Language%20(2004).060.jpeg)

However, the lack or presence of an interface line *does* make a difference, as will be explained later.


Lines
-----

< Must explain how the children inside parents that are the same object have the same line targets. Or the children inside diamonds that are the same execution. >

### Direction

Lines tie symbols together, saying that they share a certain aspect.

![](images/Symbol%20Language%20(2004).061.png)

*A, B, C and D share an aspect: they represent the same object. E represents another object.*

In that sense the lines have no particular direction. However, the direction of lines does matter as will become apparent in later subjects. It is of the essence to see that one symbol is pointing to the other. There are rules that determine the direction of lines.

#### Access Symbols

A *line dissector*, also called an *access symbol*, can determine the direction of a line. It sort of denotes which symbol is pointed at:

|<p>![](images/Symbol%20Language%20(2004).062.png)</p><p>*B is pointed to.*</p><p>*The direction goes to the right à.*</p><p>*In this case A points to B.*</p>|<p>![](images/Symbol%20Language%20(2004).062.png)</p><p>*A is pointed to.*</p><p>*The direction goes to the left ß.*</p><p>*In this case B points to A.*</p>|
| :-: | :-: |

You can see the line dissector as the door that lets you access a symbol. Therefore in the first example, __B__ is accessed: __B__ is pointed to by __A__, and in the second example __A__ is accessed: __A__ is pointed to by __B__.

In another situation the access symbol is placed as follows:

|<p></p><p>![](images/Symbol%20Language%20(2004).062.png)</p><p>*The direction goes to the right à.*</p><p>*A points to B.*</p>|<p></p><p>![](images/Symbol%20Language%20(2004).063.png)</p><p>*The direction goes to the left ß.*</p><p>*B points to A.*</p>|
| :-: | :-: |

In the last picture, the access symbol isn’t placed near __A__, but closer to the border of __C__. Why this is so is explained later. For now you can see the line dissector as the *door* to __C__ that lets you access __A__.

The access symbol can also be put at both ends:

![](images/Symbol%20Language%20(2004).062.png)

In that case the direction goes both ways. Actually, there’s two lines: one going one way and the other going the other way.

When an access symbol is left out:

![](images/Symbol%20Language%20(2004).064.png)

Three things can be the matter:

- The direction goes *both ways*
- The direction doesn’t matter in this view
- Other rules determine the direction

Those other rules will be covered next.

In the example above, though, no other rules determine the direction.

#### Precedence of Direction Rules

There is a precedence of rules that determines the direction of a line.

##### Access Symbols

The first rule implies that an access symbol determines the direction of a line. If other rules can determine the direction, the access symbol is usually left out. This means that if other rules *can’t* determine the direction, an access symbol is used.

The other rules determine the direction without the use of an access symbol. These rules are based on which direction is most common. The more common direction doesn’t require an access symbol. The less common direction requires an access symbol. These rules are invented to as little as possible disturb the diagram with access symbols.

Because an access symbol is decisive for the direction, the access symbol rule can be regarded the *first* rule. However, only if the other rules can’t determine the direction, an access symbol is used. In that sense it is the *last* rule: the last means for denoting direction.

Don’t go numb on the rules that follow. They only serve the following purpose: common situations don’t require an access symbol to determine the direction.

##### Outward

This rule applies when the access symbol rule doesn’t override it. If the access symbol is left out then the direction is outwards:

*Direction is Usually Outwards*

![](images/Symbol%20Language%20(2004).065.png)

*A points to B, because the direction is outwards.*

You can see __A__ as being __C__’s *eye* to __B__, so it is logically directed outwards.

##### You Sooner Exit a Procedure than an Object

The rule that follows only applies if the direction isn’t determined by the two rules above: the access symbol rule or the outward rule.

*You Sooner Exit a Procedure than an Object*

It happens more often that a procedure has a pointer to an object:

![](images/Symbol%20Language%20(2004).066.png)

à

than for an object to directly reference a procedure parameter:

![](images/Symbol%20Language%20(2004).067.png)

ß

That is actually highly uncommon. It’s *not* uncommon to reference a procedure’s object, but it *is* uncommon to reference it directly from an object.

It is very *common* for a procedure to have a reference another object’s procedure:

![](images/Symbol%20Language%20(2004).068.png)

à

Especially when it’s a diamond:

![](images/Symbol%20Language%20(2004).069.jpeg)

And it is very *uncommon* to reference a procedure clause from an object:

![](images/Symbol%20Language%20(2004).070.png)

ß

Altogether it is more common for a procedure to point to something in an object, than for an object to directly reference something in a procedure: you sooner exit a procedure than an object.

##### You Sooner Reference an Interface than Redirect It

Or: you sooner point *to* a triangle than *from* a triangle. This rule only applies if the rules above don’t determine the direction: access symbol, outward, sooner exit a procedure than an object.

![](images/Symbol%20Language%20(2004).071.png)

à

The direction goes to the right à. It’s more common for a circle to redirect to an interface implementation in another circle. The other direction is less common: it’s less common to redirect an interface implementation to some far away object.

![](images/Symbol%20Language%20(2004).072.png)

ß

In this example the direction *is* to the left ß. You *do* sooner reference an interface than redirect an interface, but the outwards rule is still dominant. In the first diagram the outwards rule didn’t apply; here it does.

##### You Sooner Redirect a Diamond than Reference It

A diamond is usually a call, so it’s most common that the diamond points at something:

![](images/Symbol%20Language%20(2004).073.jpeg)

à

You can point *to* a diamond:

![](images/Symbol%20Language%20(2004).074.jpeg)

ß

But it happens to be so that a diamond usually points *at* something. The picture above shows a reference to a diamond symbol.

##### Exit the Most Borders

This rule is derived from the outwards rule. What they have in common is:

*You sooner exit than enter.*

The outwards rule says that you exit a border rather than enter it. The exit the most borders rule says you exit more borders than you enter.

![](images/Symbol%20Language%20(2004).075.png)

*A points to B becase because you exit more than you enter.*

This rule only applies if no other rule has already determined the direction. In many cases the rule is ignored, and an access symbol is used, but there *are* situations in which it’s common to determine the direction from this rule, and there an access symbol is often left out.

##### In Short

So not looking at the precedence of rules, the rules can be viewed as follows:

- *Access symbol is decisive*
- *You sooner exit than enter*
- *You sooner exit a procedure than an object*
- *You sooner reference an interface than redirect it*
- *You sooner redirect a diamond than reference it*

#### Bidirection

If *no rule* determines direction then the direction is either not expressed in the diagram or the direction goes both ways.

|![](images/Symbol%20Language%20(2004).076.png)|<p>![](images/Symbol%20Language%20(2004).077.png)</p><p></p>|
| :-: | :-: |
|![](images/Symbol%20Language%20(2004).078.png)|![](images/Symbol%20Language%20(2004).079.png)|

The direction *certainly* goes both ways if both ends have an access symbol:

|![](images/Symbol%20Language%20(2004).080.png)|![](images/Symbol%20Language%20(2004).081.png)|![](images/Symbol%20Language%20(2004).080.png)|
| :-: | :-: | :-: |

A line going both ways is called a *bidirection*. Formally there are actually two lines: one for each direction, but only one line is shown.

#### Access Symbol Placement

When a line crosses symbol borders, it first exits borders and then enters borders. It’s impossible to mix exits and entrances.

![](images/Symbol%20Language%20(2004).082.png)

*First come the exits a and b, and then come the entrances c, d and e.*

If an access symbol is drawn to denote direction, it is by default put in the section between the exits and entrances. So not neccessarily close to the eventual symbol pointed at. In other words: the access symbol is usually put in front of the border that is first entered.

![](images/Symbol%20Language%20(2004).083.png)

If the part of the line between exits and entrances goes out of view then the access symbol can be placed where it’s still visible. It is placed in front of the last border in view that is entered or exited:

![](images/Symbol%20Language%20(2004).084.png)

Don’t draw it like this:

![](images/Symbol%20Language%20(2004).085.png)

because then you’re suggesting the other direction. Place it *in front* of the *last border in view* that is entered or exited.

### Line Ownership

#### Object Symbol Lines

Direction is important in understanding that one object symbol can have only one line of each type.

![](images/Symbol%20Language%20(2004).086.png)

An object symbol can only have one object line, one type line and one interface line. The lines point *away* from the symbol. They denote which other symbol is their object, which other symbol is their type and which other symbol is their interface. Any other lines connected to an object symbol point *at* the symbol, not *away* from the symbol.

![](images/Symbol%20Language%20(2004).087.png)

__a__ points *away* from __A__. This is __A__’s line. The other lines: __c__ and __d__, point *to* __A__. In other words: __C__ and __D__ are pointers to __A__. __A__ is a pointer to __B__. 

#### Procedure Lines

It works the same for procedures, except that procedures have reference and interface lines.

### Procedures to Procedures, Objects to Object

Procedures can be tied only to procedures.

![](images/Symbol%20Language%20(2004).088.png)

Objects can be tied only to objects.

![](images/Symbol%20Language%20(2004).064.png)

Formally, there can be no lines connecting objects and procedures:

![](images/Symbol%20Language%20(2004).089.jpeg)

However, the above *is* a valid notation. It actually denotes the object being a pointer to the *return value* of the procedure. It’s an *implicit* notation (covered later), that actually standard for something else:

![](images/Symbol%20Language%20(2004).090.jpeg)

So then object symbols point only to object symbols and procedure symbols only to procedure symbols.

However, the picture above is actually again an implicit notation for something else, but I won’t go into detail about that yet.

#### Relations between Objects and Procedures

So formally, you can’t create a relation between a procedure and an object by tying them together with lines.

However, apart from relations made by lines, symbols can also relate through containment.

Objects relate to procedures primarily by containment.

![](images/Symbol%20Language%20(2004).091.jpeg)

![](images/Symbol%20Language%20(2004).092.jpeg)

But if you redirect an object’s procedure, the object gets a relation to the procedure redirected to.

![](images/Symbol%20Language%20(2004).093.jpeg)

But only by containing a procedure related to another or being contained *in* a procedure with related to another.

![](images/Symbol%20Language%20(2004).092.jpeg)

That way symbols can relate to one another by not being tied together nor by one being contained in the other, but sherely by the relations that their ancestors or descendants have:

![](images/Symbol%20Language%20(2004).094.jpeg)

*Object* __A__ *is related to object* __B__.

### Target Symbols

#### Line Targets

Lines redirect a *system aspect* of a symbol to another symbol.

For instance: an object symbol can serve as its own object:

![](images/Symbol%20Language%20(2004).028.png)

But if it has an object line, it is no more than a pointer to an object, rather than the object itself, while te target of the line is regarded the real object. 

![](images/Symbol%20Language%20(2004).095.png)

*A is a pointer, B is the object.*

The object symbol *redirects* its *object* system aspect to another symbol. Lines *are* redirection.

An object symbol can also serve as its own type:

![](images/Symbol%20Language%20(2004).028.png)

Then it is an object that defines its own type. But if it has a type line, it redirects its type to another symbol. Then it is no longer its own type, but a mere object from an existing type, also called an instance of a type. The target of the type line is regarded the type itself.

![](images/Symbol%20Language%20(2004).096.png)

*A is an instance, B is the type.*

Similarly, an object symbol can control its own interface:

![](images/Symbol%20Language%20(2004).028.png)

But if it has an interface line, its interface is bound to that of its interface line target. The symbol is regarded an interface implementation, while the target interface serves as the interface.

![](images/Symbol%20Language%20(2004).097.png)

*B is the interface, A is an implementation of it.*

A procedure symbol can define its own procedure:

![](images/Symbol%20Language%20(2004).032.png)

But if it has a reference line it is regarded no more than a reference or call to a procedure. The target of the line is considered the procedure itself or the *definition* of the procedure.

![](images/Symbol%20Language%20(2004).098.jpeg)

*A is the reference, B is the definition.*

![](images/Symbol%20Language%20(2004).099.jpeg)

*A is the procedure reference, B is the definition.*

#### Multiple Redirection and Final Targets

If an object symbol has an object line to a symbol that again has an object line, there is redirected until a symbol without an object line is encountered: the *target object*.

![](images/Symbol%20Language%20(2004).100.png)

*C is the target object of A and B.*

The target object symbol is regarded to represent the object for real. The other symbols are references to the object.

The same way there are symbols serving as a *target type* or a *target interface*. Also a procedure has an interface target. A procedure also has a call target and reference target. In both those cases reference lines are followed.

#### Tracing Targets

##### Tracing Object Aspects

Formerly I’ve said that when you encountered a symbol that doesn’t have a type line, then it is the target type. But in *Object Basics* I said that when a symbol doesn’t have a type line, the object line functions as the type line. Therefore, if a symbol has no type line, the type can still be redirected by an object line. The same way, type lines can redirect the interface. Object lines can redirect the type and the type can redirect the interface, so an object line can also direct the interface.

Finding the aspects of a symbol, such as target object or target type, is called a *trace*.

###### Interface Trace

You’ll use all three line types to trace the interface. Follow the interface line if it exists, else follow the object line, else the type line. When you run into a symbol with no lines, then that’s the interface.

A special thing about an interface line is that you can select a single interface of a type and not use the whole type.

When there’s no interface line and the type line is followed, then the type’s *whole* interface is used.

The reason that the object line is preferred over the type line is that if there is no interface line, the *object* can determine *which* interface of the type is used.

![](images/Symbol%20Language%20(2004).101.png)

*This picture shows any combination of lines an object symbol can have and which of the lines to follow in the interface trace.*

In other words: follow interface line, otherwise object line, otherwise type line. The final symbol altogether is the interface.

###### Type Trace

You’ll use type and object lines to trace the type. Follow the type line if it exists, else follow the object line. When you run into a symbol with no type or object line, then that’s the type.

When there is no type line, the object determines the type.

![](images/Symbol%20Language%20(2004).102.jpeg)

Interface lines are not followed. Note that the target type doesn’t have to be pointed to by a type line. 

###### Object Trace

To find the target object, you’d expect to only follow object lines. However, there’s a pitfall: a situation that does not occur a lot, though.

If a type line points to a symbol with an object line, the type is a single object.

![](images/Symbol%20Language%20(2004).103.jpeg)

Each instance of the type is actually the same object. 

![](images/Symbol%20Language%20(2004).104.png)

Therefore, a type line can redirect the object of the symbol. Therefore, type lines need to be followed to find the object.

The last symbol pointed to by an object line is the object.

![](images/Symbol%20Language%20(2004).105.jpeg)

This kind of redirectioning is called an *object trace*.

Delegating the object aspect is the main type of object redirection.

###### Object-Type Trace

The last symbol in the object trace altogether:

![](images/Symbol%20Language%20(2004).106.jpeg)

is the target type.

Therefore, *object* trace can also point out to the target *type*. The difference with a *type trace* is that a type trace prefers to follow type lines over object lines and an object trace prefers to follow object lines over type lines. However, both redirections lead to the exact same symbol.

![](images/Symbol%20Language%20(2004).107.jpeg)

It happens a lot that you want to find out the object and the type in one blow. So you may as well use the redirection of the object trace for the benefit of finding the object and type in one blow. The trace is then called a *object-type trace*.

![](images/Symbol%20Language%20(2004).108.png)

The last symbol in the redirection altogether is the target type (__C__). The last symbol pointed to by an object line is the object (__O__). Note that the target type may be pointed out by an object line.

![](images/Symbol%20Language%20(2004).103.jpeg)

When you only want to find out the type, it is better to use a type trace than it is to use an object-type trace. Type trace prefers type lines over object lines. Type lines generally follow less redirections before reaching the target type than object lines do.

![](images/Symbol%20Language%20(2004).109.jpeg)

###### Object-Type-Interface Trace

It happens frequently that you need a symbol’s target object, type and interface in one blow. That requires two traces: an object-type trace and an interface trace. The full operation is an *object-type-interface trace*. It deserves a separate name for it’s a very common operation.

##### Tracing Procedure Aspects

Even though there are only *two* line types for procedure symbols, there are *three* aspects of a procedure symbol to trace:

- Execution
- Definition
- Interface

A definition is a lot like the type of the procedure, while an execution is an instance of the procedure.

###### Definition Trace

The definition trace is quite easy: follow reference lines until you bump into a symbol without a reference line. That symbol’s the definition

![](images/Symbol%20Language%20(2004).110.jpeg)

###### Procedure Interface Trace

In the *procedure interface trace* you follow both line types, but you prefer following an interface line over a reference line.

![](images/Symbol%20Language%20(2004).111.jpeg)

The last symbol of the trace is the interface.

Following any of the two line types will eventually lead to the same symbol. In that sense it doesn’t matter what line type you prefer to follow. The interface line is preferred, though, both because it’s more logical to follow, and because following them you’ll probably hit the interface sooner: probably there will be less interface redirections than reference redirections.

###### Execution Trace

To find the execution you do the following.

![](images/Symbol%20Language%20(2004).112.jpeg)

What you do is that you follow reference lines until you encounter a symbol without a reference line. The last symbol in the trace to be a *diamond* is the target execution.

Tracing the execution target only seems to be relevant when the source symbol is a diamond. It usually is. Usually you’ll only do this trace for a diamond. However, the target execution is also relevant for a square, because if a square’s redirection has a diamond in it, any call to the square is a call to the same execution.

###### Execution-Definition Trace

Just as with the object-type trace, the execution trace requires you to find the definition anyway, so when you need both, the execution trace will suffice. It’s called a *execution-definition trace* when you use an execution trace to find both execution and definition.

###### Execution-Definition-Interface Trace

It happens frequently that you need target execution, definition and interface in one blow. That requires two traces: an execution-definition trace and an interface trace. The full operation is called an *execution-definition-interface trace*. It deserves a separate name for it’s a very common operation.

###### Redirecting to an Execution

A lot of times you will redirect an execution, but you won’t redirect *to* an execution.

![](images/Symbol%20Language%20(2004).113.jpeg)

By redirecting to an execution, it is possible for multiple symbols to represent the same single execution.

![](images/Symbol%20Language%20(2004).114.jpeg)

Also note that when redirecting to an execution, the definition is always the same execution.

##### Tracing is Not Always Hard

If an object symbol has no object line or type line, then finding the target object and type is much simpler, because no redirectioning at all takes place. The symbol is its own object and type.

![](images/Symbol%20Language%20(2004).028.png)

Traces usually don’t require as many steps as in the examples above.

#### Circularity

Circularity is the case when the redirection eventually leads to a symbol already encountered. 

![](images/Symbol%20Language%20(2004).115.png)

__A__ is a pointer to __B__, which is a pointer to __C__, which is a pointer to __A__ again and so on. Redirection is ended, though, when the target symbol is found to be the source symbol or intermediate symbol. In this case it can’t be said that a single symbol represents the actual object, while other symbols are regarded object references. In this case __A__, __B__ and __C__ are *all* primary representations of the object.

There’s also a question of circularity when somewhere in the redirection a bidirection is encountered.

![](images/Symbol%20Language%20(2004).116.png)

This is because a bidirection can also be regarded to be two lines, one for each direction. The line between __B__ and __C__ can be regarded two lines: one pointing from __B__ to __C__ and one pointing from __C__ to __B__. Therefore, the line(s) between __B__ and __C__ cause a circularity: __B__ is a pointer to __C__, which is a pointer to __B__, which is a pointer to __C__ and so on. Thus, __B__ and __C__ both represent the target object. __A__ however, is a pointer *to* this *circularity*. It’s not part of the circularity.

A circularity can only be the end point of redirection, because you can’t escape from a circularity.

##### Circularity in Tracing

Tracing final targets requires following multiple line types to find a single system aspect.

![](images/Symbol%20Language%20(2004).117.jpeg)

In a trace, multiple line types can occur in a single circularity. The following sub sections cover the details of circularity in each type of trace.

##### Circularity in a Object-Type Trace

In object-type tracing, both kinds of line can close a circularity.

If the closed circle *contains* an object line

![](images/Symbol%20Language%20(2004).118.jpeg)

or *is pointed to* by an object line,

![](images/Symbol%20Language%20(2004).119.jpeg)

the whole circularity represents both object and type.

If the closed circle consists of only type lines and is pointed to by only a type line, the circularity only represents the type.

![](images/Symbol%20Language%20(2004).120.jpeg)

An object trace is the same procedure. The examples above should also clarify circularity in a type trace.

##### Circularity in a Interface Trace

All three kinds of object symbol lines can close a circularity in an interface trace. If a circularity is encountered when tracing the interface, the whole circularity represents the interface.

![](images/Symbol%20Language%20(2004).121.jpeg)

##### Circularity in a Definition Trace

In a definition trace, only one line type is followed, so a circularity there looks the same as earlier explained.

![](images/Symbol%20Language%20(2004).122.jpeg)

The whole circularity represents the definition.

##### Circularity in a Procedure Interface Trace

Both kinds of procedure symbol lines can close a circularity in a procedure interface trace. If a circularity in encountered when tracing the procedure interface, the whole circularity represents the procedure interface.

![](images/Symbol%20Language%20(2004).123.jpeg)

##### Circularity in an Execution-Definition Trace

The execution-definition trace is the same process as the execution trace, so this section explains circularity in both of them.

In execution-definition tracing you follow reference lines.

If the closed circle contains a diamond

![](images/Symbol%20Language%20(2004).124.jpeg)

then the whole circularity represents both execution and definition.

If the closed circle consists of only squares, the circularity only represents the definition.

![](images/Symbol%20Language%20(2004).125.jpeg)

#### Terms

There’s a lot to be said about the terminoligy around target symbols. I’ve put all this in this section. I kept these discussions out of the original text of ‘Target Symbols’, because it would obscure the main point.

##### Target Symbol

The target of a line, the *line target*, is also called a *target symbol*, while the line owner is can also be called the *source symbol* or, less commonly: the *line source*.

##### Source

Be careful with the term *source* in this context, though. You can speak of the source of a line:

![](images/Symbol%20Language%20(2004).126.jpeg)

__A__ is considered the line’s source. __B__ is the opposite party: the *target*. *Source* in this context expresses a party of a line. 

When you use the term *source* to denote a *relation between symbols*, it actually means *the same* as the term target. The terms are not opposites, they’re equivalents.

![](images/Symbol%20Language%20(2004).127.jpeg)

__Type__ can be considered __Object__’s type target, because __Object__’s type line points to it. __Type__ can also be considered __Object__’s type source, because __Type__ serves as the type of __Object__.

##### ‘Target’

The term *target* is used for both intermediate targets and the final target symbols. To be more exact about what target you’re talking about you can use the terms *direct*, *intermediate* and *final*. The *direct object* of __A__ in the picture < there is no picture... > above, for instance, is __B__, while the *final object* is __C__. __B__ is also regarded an *intermediate object target*, or *intermediate object*, because it’s not the final target, nor the line source. The unaugmented terms *target object*, *target type*, *target interface* and *target procedure* are by rule reserved for final targets. If you want to denote an intermediate object target, for instance use the term *object target*, instead of *target object*, or say *intermediate target object*, but don’t use the unaugmented term *target object* for an intermediate symbol. Many times out of the context it can be understood whether there is talked about a direct, intermediate or a final target, so it’s not always extra denoted. The term target *symbol* can be about any redirection step or be about any the final target of any aspect.

*Object target* is not the same as *target object*. *Object target* denotes the direct target of an object line. *Target object* denotes the symbol that is regarded to *really* represent the object.

The terms *object*, *type* and *interface* can denote the line target of an object line, type line or interface line. The terms *object*, *type* and *interface* are used for *final* targets as well as *direct* targets. The context may illustrate what I’m talking about or I’ll use a more specific term.

##### Redirection and Trace

Each *step* in a trace is called a *redirection*, because following a line is called a redirection. The whole tracing process can also be referred to as *the redirection*, even though it’s also called a *trace*.

##### Interface Definition

The final target interface is also called the *interface definition*.

##### Type Line Being called Interface Line

The term *interface target* can mean the target of the *interface line*, but there’s also a second meaning. When the interface line is missing, the interface can also be redirected by an object line or type line. The term *interface target* can also denote the symbol to which the interface is redirected, *be it* with an object line or type line. Sometimes the word *interface line* is even used where I really talk about the line that *redirects* the interface.

The same thing applies to the term *type target*. *Type target* can mean the target of the type line, but it can also mean the symbol to which the type is redirected, be it with an object line, be it with a type line. Sometimes the word *type line* is even used where I really talk about the line that *redirects* the type.

It’s the same thing with the redirection of other system aspects.

##### Object Definition

The type of an object symbol is sometimes called the definition of the object, because the type of the object determines the object’s systematics for a great part. Just like the definition of a call determines the systematics of a procedure. The term *definition of object* could also mean the target object, though, so it’s easy to say something ambiguous.

##### Object Delegation

Delegating the object aspect is the main type of object redirection. Because it is the main one, it can also be called *the* delegation or *object delegation*.

##### Procedure Definition Trace

The procedure definition trace can also be called the *procedure trace* or the *definition trace*.

### Genericity

Genericity is about the how loose or rigid a system aspect is.

For instance, if a circle has no type line, the object can be of any type. The type is *generic* in this case. If the type line is set, though, the object can only be of a single type. The type is *explicit* in that case.

There are more such phenomena. This section will cover all of them.

#### Object Symbol Genericity

This section covers the all forms of genericity for object symbols.

##### Original and Delegated Object

The first concept I will explain is quite simple.

![](images/Symbol%20Language%20(2004).128.jpeg)

If a symbol has an object line then it adopts the object of the line target. __A__ delegates to __B__. You can also say that __A__’s object aspect is *delegated* or that __A__ has a *delegated object*.

![](images/Symbol%20Language%20(2004).129.jpeg)

If a symbol doesn’t have an object line, though, it represents its own object. The symbol is an *original object*.

Synomyms for the terms *delegated* and *original* are allowed. *Delegated* has synonyms such as *diverted*, *redirected*, etcetera. All are valid. Synonyms for *original object*, can be expressions such as ‘the symbol *is its own object*’.

|Original object|<p>Object determined by no line</p><p>(no object line)</p>|
| -: | :- |
|Delegated object|<p>Object determined by a line</p><p>(object line)</p>|

The redirection of the object aspect is the main type of redirection. Therefore you can also speak of *the* delegation.

##### Original and Delegated Type

It works almost the same for the type aspect. However, the type aspect can be delegated by both a type line as well as an object line. If a symbol has a type line or object line, then it is said to have a *delegated type*.

|<p>![](images/Symbol%20Language%20(2004).130.jpeg)</p><p>*Type delegated by object line*</p>|<p>![](images/Symbol%20Language%20(2004).131.jpeg)</p><p>*Type delegated by type line*</p>|
| :-: | :-: |

If the symbol has type nor object line, it represents its own type. The symbol is said to have its *original type*.

![](images/Symbol%20Language%20(2004).129.jpeg)

The type determines the symbolic contents of a symbol. If a symbol has a delegated type, it has the same symbolic contents as its target type. If it has its own original type, then it determines the contents itself.

During execution of a system a symbol can change from having a delegated type to original type and back.

|<p>![](images/Symbol%20Language%20(2004).132.jpeg)</p><p>*Delegated type*</p>|<p>![](images/Symbol%20Language%20(2004).133.jpeg)</p><p>*Line removed, original type reappears*</p>|
| :-: | :-: |

When you remove a type line, the symbol’s  original contents reappear. So the original type definition of a symbol isn’t lost as soon as you delegate the type line. You just temporarily can’t see the original type contents. The original type systematics reappear when the type is no longer delegated. When a type is delegated, usually nothing is defined as the original type. So not every object symbol needs to store its own original systematics.

|Original type|<p>Type determined by no line</p><p>(type nor object line)</p>|
| -: | :- |
|Delegated type|<p>Type determined by a line</p><p>(type or object line)</p>|

##### Explicit and Generic Type

This is the genericity already explained in the introduction to genericity. When a type is undetermined by a type line, the symbol adopts the type of its object target, whatever type this object may be of.

|![](images/Symbol%20Language%20(2004).134.jpeg)|![](images/Symbol%20Language%20(2004).135.jpeg)|![](images/Symbol%20Language%20(2004).136.jpeg)|
| :-: | :-: | :-: |

The type is *generic* in this case. If the type line is set, however, the object can only be of a single type.

|![](images/Symbol%20Language%20(2004).137.jpeg)|<p>![](images/Symbol%20Language%20(2004).138.jpeg)</p><p></p>|
| :-: | :-: |
|![](images/Symbol%20Language%20(2004).139.jpeg)|![](images/Symbol%20Language%20(2004).140.jpeg)|

The type is *explicit* in that case. You can also say that the type is *set*.

|Explicit type|<p>Type determined by type line</p><p>(limits the possible object to objects of that type)</p>|
| -: | :- |
|Generic type|<p>Type determined by object line</p><p>(symbol adopts any type the object might have) </p>|

If the type is determined by no line at all then it has an *original type*. You can speak of neither explicit nor generic in that case. When the type is generic or explicit, it’s always delegated. If the type is explicit, the type is delegated by the type line. If the type is generic, the type is delegated by the object line.

##### Original and Delegated Interface

The interface can be determined by the target of the interface line, type line or object line, but the interface line is most determinant. If any of those line are set, the interface is diverted to the interface target, object target or type target. It is said to be *delegated*. If an object symbol has no interface line, it has its *original interface*.

![](images/Symbol%20Language%20(2004).141.jpeg)

|Original interface|<p>Interface determined by no line</p><p>(interface, type nor object line)</p>|
| -: | :- |
|Delegated interface|<p>Interface determined by a line</p><p>(interface, type or object line)</p>|

During execution the interface can change from being delegated to original and back. The original interface isn’t lost as soon as you delegate the interface. When you annull the delegation, then the original interface reappears. It was only temporarily hidden. Mostsymbols don’t define an original interface, so not every object symbol holds original interface systematics.

The use of delegation of the interface is to fix the interface and to use an already defined interface.

##### Explicit and Generic Interface

As the type can be explicitly set, the interface can also be explicitly set. It’s only about the interface set by an interface line; the other line types don’t explicitly set the interface. If the interface is set, then the type or object can only be a symbol whose type at least supports the interface.

|<p>![](images/Symbol%20Language%20(2004).142.jpeg)</p><p></p>|<p>*A*</p><p>![](images/Symbol%20Language%20(2004).143.jpeg)</p>|
| :-: | :-: |
|<p>*B*</p><p>![](images/Symbol%20Language%20(2004).144.jpeg)</p>|<p>*C*</p><p>![](images/Symbol%20Language%20(2004).145.jpeg)</p>|

*The top object can point to the left object (picture A) and to the right object (picture B). The left object has the full interface, while the right object supports the interface. Picture C is illegal, because the object target doesn’t support the interface.*

If a symbol has no interface line, the interface is said to be *generic*. It adopts the full interface of any type the interface might have, due to type delegation by either a type line or object line. 

|![](images/Symbol%20Language%20(2004).146.jpeg)|![](images/Symbol%20Language%20(2004).147.jpeg)|
| :-: | :-: |

|Explicit interface|<p>Interface determined by interface line</p><p>(one specific interface of the type is used)</p><p>(limits the possible types to ones that support the interface)</p>|
| -: | :- |
|Generic interface|<p>Interface determined by type line or object line</p><p>(type’s whole interface used)</p><p>(symbol adopts any interface the type might have)</p>|

If the interface is determined by no line at all then it has an *original interface*. You speak of neither explicit nor generic in that case. When the interface is generic or explicit, it’s always delegated. If the interface is explicit, the interface is delegated by the interface line. If the interface is generic, the interface is delegated by either type or object line.

#### Procedure Symbol Genericity

This section covers the genericity concepts around procedure symbols.

##### Original and Delegated Definition

When a procedure symbol has a reference line, it adopts the procedure definition of its line target. The symbol has a delegated definition. If the symbol has no reference line, it defines the procedure itself. It has its original definition.

![](images/Symbol%20Language%20(2004).148.jpeg)

The definition of the procedure symbol determines its symbolic contents. As a system runs, the definition can go from original to delegated and back. When you remove a reference line, the symbol regains its original contents. So the original definition of a symbol is not lost once you delegate the definition. You just temporarily can’t see the original definition. When a definition is delegated, usually nothing is defined as the original definition. So not every procedure symbol needs to store its own original systematics. 

|Original definition|<p>Definition determined by no line</p><p>(no reference line)</p>|
| -: | :- |
|Delegated definition|<p>Definition determined by a line</p><p>(a reference line)</p>|

You can also speak of *original procedure* and *delegated procedure* or *the delegation of a procedure*.

##### Original and Delegated Execution

When there’s a diamond somewhere the reference line redirection,

![](images/Symbol%20Language%20(2004).149.jpeg)

the source symbol of the redirection doesn’t represent its own execution. Its execution is delegated to the other diamond.

|Original execution|<p>Delegation doesn’t pass a diamond</p><p></p>|
| -: | :- |
|Delegated execution|<p>Delegation passes a diamond</p><p></p>|

Logically, only a diamond can represent its own original execution.

![](images/Symbol%20Language%20(2004).150.jpeg)

You don’t usually talk about *squares* having an *original execution*, however when a square delegates to a diamond, 

![](images/Symbol%20Language%20(2004).151.jpeg)

the square *is* said to have a *delegated execution*.

##### Original and Delegated Procedure Interface

The interface of a procedure can be delegated to its definition target, but it can also be delegated by an interface line. 

|![](images/Symbol%20Language%20(2004).152.jpeg)|![](images/Symbol%20Language%20(2004).153.jpeg)|
| :-: | :-: |

In both cases the interface is delegated. If a procedure symbol has no line at all, it has an original interface.

![](images/Symbol%20Language%20(2004).154.jpeg)

During execution the interface can change from being delegated to original and back. The original interface isn’t lost as soon as you delegate the interface. When you annull the delegation, then the original interface reappears. It was only temporarily hidden. Most procedure symbols don’t define an original interface, so most symbols don’t holds original interface systematics.

The *use* of delegation of the interface is to fix the interface of a procedure and to use an already defined procedure interface.

|Original interface|<p>Interface determined by no line</p><p>(interface nor reference line)</p>|
| -: | :- |
|Delegated interface|<p>Interface determined by a line</p><p>(interface or reference line)</p>|

##### Explicit and Generic Procedure Interface

If a procedure symbol has an interface line then its definition can only be one that has that particular interface. The interface is explicit.

|![](images/Symbol%20Language%20(2004).155.jpeg)|![](images/Symbol%20Language%20(2004).156.jpeg)|![](images/Symbol%20Language%20(2004).157.jpeg)|
| :-: | :-: | :-: |

If the interface line of a procedure symbol isn’t set then it adopts the interface of the target definition.

|![](images/Symbol%20Language%20(2004).158.jpeg)|![](images/Symbol%20Language%20(2004).159.jpeg)|
| :-: | :-: |

|Explicit interface|<p>Interface determined by interface line</p><p>(limits the possible procedures to ones with that interface)</p>|
| -: | :- |
|Generic interface|<p>Interface determined by reference line</p><p>(symbol adopts any interface the procedure might have)</p>|

#### Type-Interface Interaction

##### Type Interface Genericity

A special form of genericity is very important and it’s crucial for the use of interfaces at all. I’m talking about: the interface doesn’t determine the type. It’s a genericity always present.

###### Using Interface Extends Type Line

When you set the interface of a symbol then it can only point to definitions that have the interface or support the interface. I will now describe how using a supported interface works.

![](images/Symbol%20Language%20(2004).160.jpeg)

Here __Object A__ has __Type B__. It uses __Interface A__ of __Type B__.

One one hand you can a see using the supported interface as a silent extension of the type line to the triangle with the right interface:

![](images/Symbol%20Language%20(2004).161.jpeg)

But on the other hand it’s not like that, because that would mean that __Object A__ gets __Type B__. It still has __Type A__ however. When __Object A__ is created, an object of __Type A__ is is created, not __Type B__. But __Object A__ can only call upon the members of __Interface A__.

###### Object Shows Only Used Interface Implementation

The source object only shows the implementation of the interface it has:

![](images/Symbol%20Language%20(2004).162.jpeg)

Not the contents of the whole type:

![](images/Symbol%20Language%20(2004).163.jpeg)

###### Create Symbol: Create Object of the Whole Type

However, when you *create* the symbol, an object of the *full type* is created. This is useful: other symbols may be pointers to the same object, but may use a different interface.

![](images/Symbol%20Language%20(2004).164.jpeg)

*Symbol A is of Type A, but only uses Interface A. Symbol A only shows the systematics of that one interface: a circle. However, it’s an object of the __whole type__. This is important. The importance is pointed out by Symbol B. Symbol B is a pointer to Symbol A, only it uses a different interface. So it shows different systematics.*

So object symbols tied together with object lines don’t have to use the same interface at all. The picture above shows that when you use an object line (__Symbol B__ points to __Symbol A__), the target doesn’t have to have the same interface, only the same type.

###### Choose From Multiple Types

So one interesting thing about type-interface genericity is that when you’ve set a symbol’s interface line, you can still choose from multiple types.

###### No Interface Line: Follow Object Line

If there is no interface line, the *object* determines *which* interface of the type is used, as the pictures below demonstrate.

|![](images/Symbol%20Language%20(2004).165.jpeg)|![](images/Symbol%20Language%20(2004).166.jpeg)|
| :-: | :-: |

__Symbol A__ redirects the type to __Type A__. In the first picture __Symbol A__ redirects to __Object A__, in the second picture __Symbol A__ redirects to __Object B__. __Symbol A__, __Object A__ and __Object B__ are all of the same type. However, __Object A__ uses __Interface A__ and __Object B__ uses __Interface B__.

This means that the object line determines the interface sooner than the type line. That’s why in the interface trace, the object line is preferred over the type line.

##### Interface Type Generiticy

Another very important use of the separation between types and interfaces is that you can choose any *object* that supports the interface, not worrying about its type.

![](images/Symbol%20Language%20(2004).167.jpeg)

*D, E and F all have different types, while they all support interface A. G also supports interface A. G could point to D, E or F without problems, while D, E and F all have different types. However, G can only call the members of their joint interface. Specialized features of the types D, E and F are unavailable.*

Conversely, you can let a program that isn’t familiar with your type, use your type anyway, by supporting an interface that the other program *is* familiar with.

##### Interface Procedure Genericity

Interface procedure genericity is like interface type genericity. It means that if you fix the procedure interface, you can still choose from multiple procedure definitions.

##### Overview of Genericities of Type-Interface Interaction

|Interface type genericity|Fixing the interface doesn’t fix the type|
| :- | :- |
|Type interface genericity|Fixing the type doesn’t fix the interface|
|Interface-procedure genericity|Fixing the procedure interface doesn’t fix the procedure|

#### Final Issues

##### Explicit Isn’t Fixed

When a symbol has an explicit type, it’s object can only be of that type. Having an explicit type, however doesn’t mean that the type of a symbol can’t change. If you change the type line, you’ve changed the type. The only way to make the type immutable at run time is by making it impossible to change the type line at run time. How to do that is explained in a later chapter.

##### Same Object, Same Type

Earlier on, in the section *Object Basics : Same Object, Same Type* I said that if you make two symbols the same object:

![](images/Symbol%20Language%20(2004).025.png)

they automatically are the same type, sort of like this:

![](images/Symbol%20Language%20(2004).025.png)

The topics of genericity show that these two pictures aren’t synonyms. In the second picture the type is explicit, while in the first picture the type is generic. The same goes for the other comparisons in that section.

#### Delegated to Original in a Circularity

When you annull a symbol’s type line, it usually regains its original type. All symbols pointing to the reappeared original type, now also have a different type.

In a circularity it’s different. When you delegate the type to a circularity, the whole circularity represents the type.

![](images/Symbol%20Language%20(2004).168.jpeg)

When you break one of the lines in the circularity, you might think that the one loosing the line regains its original type. The reality is different: no symbols of the former circularity regains its original type.

![](images/Symbol%20Language%20(2004).169.jpeg)

If you break one of the lines in the circularity, the one loosing the line comes to represent the type and the other members of the former circularity now delegate their type to it.

#### Overview

|Object Symbol Genericity|
| :- |
||__Object__|
|||Original object|<p>Object determined by no line</p><p>(no object line)</p>|
|||Delegated object|<p>Object determined by a line</p><p>(object line)</p>|
||__Type__|
|||Original type|<p>Type determined by no line</p><p>(type nor object line)</p>|
|||Delegated type|<p>Type determined by a line</p><p>(type or object line)</p>|
|||Explicit type|<p>Type determined by type line</p><p>(limits the possible object to objects of that type)</p>|
|||Generic type|<p>Type determined by object line</p><p>(symbol adopts any type the object might have) </p>|
||__Interface__|
|||Original interface|<p>Interface determined by no line</p><p>(interface, type nor object line)</p>|
|||Delegated interface|<p>Interface determined by a line</p><p>(interface, type or object line)</p>|
|||Explicit interface|<p>Interface determined by interface line</p><p>(one specific interface of the type is used)</p><p>(limits the possible types to ones that support the interface)</p>|
|||Generic interface|<p>Interface determined by type line or object line</p><p>(type’s whole interface used)</p><p>(symbol adopts any interface the type might have)</p>|
|__Procedure Symbol Genericity__|
||__Definition__|
|||Original definition|<p>Definition determined by no line</p><p>(no reference line)</p>|
|||Delegated definition|<p>Definition determined by a line</p><p>(a reference line)</p>|
||__Execution__|
|||Original execution|Delegation doesn’t pass a diamond|
|||Delegated execution|Delegation passes a diamond|
||__Interface__|
|||Original interface|<p>Interface determined by no line</p><p>(interface nor reference line)</p>|
|||Delegated interface|<p>Interface determined by a line</p><p>(interface or reference line)</p>|
|||Explicit interface|<p>Interface determined by interface line</p><p>(limits the possible procedures to ones with that interface)</p>|
|||Generic interface|<p>Interface determined by reference line</p><p>(symbol adopts any interface the procedure might have)</p>|
|__Interface Doesn’t Determine Type__|
||Interface type genericity|Fixing the interface doesn’t fix the type|
||Type interface genericity|Fixing the type doesn’t fix the interface|
||Interface-procedure genericity|Fixing the procedure interface doesn’t fix the procedure|

### Peels

An additional notation technique exists to express information about lines. It’s called the peel notation.

![](images/Symbol%20Language%20(2004).170.png)

This symbol has three peels, which express information about a symbol’s lines. 

The notation is invented for the following purposes:

- More overview in complex situations,
  because it allows you to hide (a many) lines, while you can still read information about the lines.
- To give more information about a line if part of the diagram is out of view
- To provide an easier notation for common situations 
  in which for instance a large group of symbols has the same sort of lines and line destinations.
- To express similarity in line targets

#### Shape Peels

Sometimes a line is not drawn or the destination of a line is out of view. There can be several reasons why you don’t want to draw a line. The lines in the view might distract you from the main point or you might not care much about the line in the view. It can also be the case that the destination of a line is out of view. Anyway, if you can’t see all or part of a line you might still want to show some information about the line.

Alternative borders for shapes can tell something about the lines of the symbol.

##### Extra Borders

The basic method used is to add extra borders to a shape:

![](images/Symbol%20Language%20(2004).171.png)

![](images/Symbol%20Language%20(2004).172.png)

Each *peel* of the symbol represents a border that a lines *crosses*.

The double circle (circle drawn with a double line) suggests that the circle has a line that crosses two borders. For instance:

![](images/Symbol%20Language%20(2004).173.png)

The triple circle suggests that three borders are crossed, for instance:

![](images/Symbol%20Language%20(2004).174.png)

or:

![](images/Symbol%20Language%20(2004).175.png)

or:

![](images/Symbol%20Language%20(2004).176.png)

So multiple peels of a symbol’s border don’t say all about the ‘travelings’ of a line. They only say how many borders are crossed.

One *peel* represents one border crossed by a line. It can be any kind of border crossing, so a triple circle may mean:

|<p></p><p></p><p>![](images/Symbol%20Language%20(2004).177.png)</p>|<p></p><p></p><p></p><p>=</p>|![](images/Symbol%20Language%20(2004).175.png)|
| - | - | - |

just as well as:

|<p></p><p></p><p>![](images/Symbol%20Language%20(2004).177.png)</p>|<p></p><p></p><p>=</p>|![](images/Symbol%20Language%20(2004).176.png)|
| - | - | - |

You can do more with a symbol’s border, so that you can express more about its lines than just how many borders are crossed.

##### Exits and Entrance Separation

The exits and entrances of a line are separated by additional lines:

![](images/Symbol%20Language%20(2004).178.png)

They are called *exit-enter* marks. The inner peels are exits and the outer peels are entrances. So in the example above there are two exits and then one entrance. The exit-enter mark is reminiscent of where you put an access symbol to denote direction: between the exits and entrances. First are the exits, so the inner peels represent exits. The outer peels represent entrances.

With the exit-enter marks the symbol above could still mean:

|<p></p><p>![](images/Symbol%20Language%20(2004).179.png)</p>|<p></p><p></p><p>=</p>|![](images/Symbol%20Language%20(2004).180.png)|
| - | - | - |

but no longer: 

|<p></p><p></p><p>![](images/Symbol%20Language%20(2004).179.png)</p>|<p></p><p></p><p>≠</p>|![](images/Symbol%20Language%20(2004).181.png)|
| - | - | - |

##### Line Type

Solid peels are used to express information about the *object line*. For type lines you use dashed peels and for interface lines you use dotted peels. For instance:

![](images/Symbol%20Language%20(2004).170.png)

This border expresses that the symbol’s object line crosses one border and that the type line crosses two.

The different looking peels are called *peel types*, analogous to the term *line* types. As such you also speak of object peels, type peels and interface peels.

I’ll continue with another example:

![](images/Symbol%20Language%20(2004).182.png)

This border suggests that the type line crosses two borders and the object line crosses three. It could for instance mean the following:

![](images/Symbol%20Language%20(2004).183.png)

*The blue symbol could be drawn having the peels in the previous picture.*

The object line exits one border, after which it enters two before it reaches its destination. The type line exits one border, then enters one.

You can also draw exit-enter marks in a border with multiple peel types:

![](images/Symbol%20Language%20(2004).184.png)

When you express exit-enter distinction, you can put the object peels and type peels apart with some space or it might be hard to tell them apart:

![](images/Symbol%20Language%20(2004).185.png)

Not keeping space between the peel types when showing exit-enter marks can *not* cause ambiguity *if* you show the exit enter-marks for all peel types. But if you don’t show the exit-enter marks for all peel types, ambiguity could occur if an exit-enter mark is exactly in between peel types. The presence of another exit-enter mark annuls this ambiguity. When there is undoubted ambiguity, then it is obligatory to put space between peel types. In the other cases it’s not, but for readability it can be advised to put spacing in between peel types anyway, but if you don’t want to, you don’t have to.

In another example:

![](images/Symbol%20Language%20(2004).186.png)

You draw out the peel notation with exit-enter marks as follows:

![](images/Symbol%20Language%20(2004).187.png)

The object line exits one borders and the type line exits two.

Keeping space between the different peel types can also cause ambiguity, though, because in small symbols they could suggest that there are two symbols:

![](images/Symbol%20Language%20(2004).187.png)

In larger symbols you will see the difference more easily, though:

![](images/Symbol%20Language%20(2004).188.png)

##### Type of Crossed Border: Studs

To express the shapes of the symbols that are crossed, you can draw little shapes through the peel:

![](images/Symbol%20Language%20(2004).189.jpeg)

You can repeat the shapes multiple times if you want:

![](images/Symbol%20Language%20(2004).190.jpeg)

##### Name of Symbol Crossed

To express what symbol is entered or exited, you can put names with peels as follows:

![](images/Symbol%20Language%20(2004).191.jpeg)

##### Exceptionals

###### Single Solid Border

A single solid border:

![](images/Symbol%20Language%20(2004).192.png)

can suggest that its object line crosses one border. It could also just be an object symbol.

To denote explicitly that the line crosses one border, you have to include an exit-enter mark so that you can see that it’s a border expressing line information:

|<p>![](images/Symbol%20Language%20(2004).193.png)</p><p>*Enter one border*</p>|<p>![](images/Symbol%20Language%20(2004).194.png)</p><p>*Exit one border*</p>|
| :-: | :-: |

So in that case you are forced to draw out if it’s an exit or entrance. If you draw peels different from borders, thinner for instance, you may ignore this rule.

###### No Crossings

To express that an object symbol has a line that enters nor exits any border you use the following notation:

![](images/Symbol%20Language%20(2004).195.png)

Which can represent any of the symbols of:

![](images/Symbol%20Language%20(2004).196.png)

Which is, by the way, not used a lot.

##### Peels for Other Symbols.

The peel notation above works the same for triangle symbols. It also works for procedure symbols, except that procedure symbols have a different set of line types, so a different set of peel types: reference peels and interface peels.

##### Abstract Meaning

A border with peels can also express more abstract facts. Here are some of such meanings:

- A symbol has a line
- Line crosses many borders
- Line exits borders
- Line exits many borders
- Line enters borders
- Line enters many borders
- Line exits and enters borders
- Line exits many borders and enters many borders
- Line exits many borders and enters borders
- Line exits borders and enters many borders
- Line exits an interface
- Line enters an interface
- Etcetera

###### Symbol Has A Line

With a simple alternative shape border you can express that a symbol has a line of a certain type.

|<p>![](images/Symbol%20Language%20(2004).197.png)</p><p>*Double solid object symbol:*</p><p>*object symbol  with an object line*</p>|<p>![](images/Symbol%20Language%20(2004).198.png)</p><p>*Dashed object symbol:*</p><p>*object symbol with a type line*</p>|<p>![](images/Symbol%20Language%20(2004).199.png)</p><p>*Dotted object symbol:*</p><p>*object symbol with an interface line*</p>|
| :-: | :-: | :-: |
|<p></p><p></p>|<p>![](images/Symbol%20Language%20(2004).200.png)</p><p>*Double procedure symbol:*</p><p>*procedure symbol with a reference line*</p>|<p>![](images/Symbol%20Language%20(2004).201.png)</p><p></p><p>*Dotted procedure symbol:<br>procedure symbol with an interface line*</p>||

The solid border needs to be doubled, because otherwise you don’t see that information about the line is expressed. When you denote that a symbol has both an object line as well as a type line, you can use a single solid peel, because then it’s clear that you’re expressing line information. 

![](images/Symbol%20Language%20(2004).202.png)

When denoting the mere existance of a line, the destination of the line is undetermined, but it’s is usually just outside the parent. This assumption is analogous to the first line direction rule: the outwards rule. A line simply most commonly points outwards and most commonly only crosses a single border.

###### Symbol’s Line Crosses Many Borders

To denote that many borders are crossed, usually three peels are used. So three peels come in the place of where otherwise an exact amount of peels is put. A line that crosses many borders is also said to have a far away line target.

|<p>![](images/Symbol%20Language%20(2004).203.png)</p><p>*Triple solid object symbol:*</p><p>*object symbol  with a far away object line target*</p>|<p>![](images/Symbol%20Language%20(2004).203.png)</p><p>*Triple dashed object symbol:*</p><p>*object symbol with a far away  type line target*</p>|<p>![](images/Symbol%20Language%20(2004).202.png)</p><p>*Triple dotted object symbol:*</p><p>*object symbol with a far away  interface line target*</p>|
| :-: | :-: | :-: |
|<p></p><p></p>|<p>![](images/Symbol%20Language%20(2004).204.png)</p><p>*Triple square:*</p><p>*procedure symbol with a far away reference line target*</p>|<p>![](images/Symbol%20Language%20(2004).205.png)</p><p></p><p>*Triple dotted square:<br>procedure symbol with a far away interface line target*</p>||

###### Other Abstract Meanings

I will simply give a sum up of the other abstract meanings I’ve mentioned and give the peel notation for them.

|<p>![](images/Symbol%20Language%20(2004).194.png)</p><p>*Line exits borders.*</p>|<p>![](images/Symbol%20Language%20(2004).193.png)</p><p>*Line enters borders.*</p>|
| :-: | :-: |
|<p></p><p>![](images/Symbol%20Language%20(2004).206.png)</p><p>*Line exits many borders.*</p>|<p></p><p>![](images/Symbol%20Language%20(2004).207.png)</p><p>*Line enters many borders.*</p>|
|<p></p><p>![](images/Symbol%20Language%20(2004).208.png)</p><p>*Line exits and enters borders.*</p>|<p></p><p>![](images/Symbol%20Language%20(2004).209.png)</p><p>*Line exits many borders and enters many borders.*</p>|
|<p></p><p>![](images/Symbol%20Language%20(2004).207.png)</p><p>*Line exits many borders and enters borders.*</p>|<p></p><p>![](images/Symbol%20Language%20(2004).207.png)</p><p>*Line exits borders and enters many borders.*</p>|
|<p></p><p>![](images/Symbol%20Language%20(2004).210.jpeg)</p><p>*Line exits a triangle.*</p>|<p></p><p>![](images/Symbol%20Language%20(2004).211.jpeg)</p><p>*Line enters a triangle.*</p>|

You can come up with other abstract meanings for peel notations using your imagination.

##### Expressable in the Symbol Border

So the following about a line can be expressed in a symbol’s peels:

- Line type
- Crossings
- Exits and entrances separation
- Shape of crossed symbol

The peels can also only have a more abstract meaning.

Unless you name the peels, the only thing you can’t express in a symbol’s peels is *which* symbol is entered. You *would* know which symbol is exited, because only the parent can be exited.

That means that you can express a whole lot in a symbol’s peels. If you count names with peels, you can express everything about a line in a shape peel notation.

##### Only Use Peel Notation Where It’s Useful

Only use peels where they’re useful. Again: peels are only used in special situations, in which they provide more clarity. This can be the case:

- if a line or part of a line is out of view 

or

- the line target is hard to find

or

- lines would obscure the picture.

or

- Similarity in line destination must be emphasized

So don’t use shape peels... unless the reasons above weigh out. < zwaarder wegen? >

#### Line Peels

Peel notation can be applied to lines just as well. For example: a double line suggests that the line crosses two borders.

![](images/Symbol%20Language%20(2004).212.png)

You can use line peels when a line’s destination is out of view or if it’s not easy to find due to complexity of the diagram.

When you use line peels, shape peels are usually not used, but no rule stops you from using both.

![](images/Symbol%20Language%20(2004).213.png)

Don’t put an exit enter mark through a line, or it will seem to be an access symbol: one of the exit-enter marks is left out in the diagram above for this purpose.

In the peels of a *line* you can’t express exit-enter separation or the type of symbol crossed. You can however express that a line with a single peel expresses the amount of crossed borders, by using an extra mark:

![](images/Symbol%20Language%20(2004).214.png)

The little blue mark with the type line denotes that the line expresses the amount of borders crossed: one. If the line has more than one peel then this *crossing mark* is not required anymore. The crossing mark is analogous to the exit-enter mark you are required to add to a symbol with a single peel in order to say that the line crosses one border. If you draw line peels different from normal lines, thinner for instance, you can leave out the crossing mark.

#### Ambiguity In Peels

Here is a list of a few ambiguity risks when using peels:

- Multiple shape peel types may suggest the existance of another symbol.
- Line peels may suggest the existance of multiple lines.

Ambiguity risks will be widely covered in the ‘Diagram Metrics’ in the book ‘Symbol Language Advanced’.


Executions & Parameters
-----------------------

This section discusses all issues around executing procedures and using parameters.

### Terms

Here I introduce basic terms in the area of executions and parameters. Here’s a quick reference list.

- Reference
- Call
- Definition
- Clause
- Active
- Inactive
- Active clause
- Inactive clause
- Sub clause
- Sub procedure 
- Parameter
- Argument
- Executor
- Execution

#### Reference

The following are procedure references:

![](images/Symbol%20Language%20(2004).215.png)

It’s a square that is redirected. It’s always a *square* with a *reference line*. It is a procedure that redirects, but *does not* execute. It can point either to a square or a diamond.

#### Call

The following are calls:

![](images/Symbol%20Language%20(2004).216.png)

It’s a diamond that is redirected. It’s always a *diamond* with a *reference line*. It executes a procedure defined elsewhere. Therefore it is a call. It can point either to a square or a diamond.

#### Definition

A definition is a procedure symbol with no reference line at all.

![](images/Symbol%20Language%20(2004).217.png)

The reference line should not exist at all, not just not be shown. It’s a definition, because the contents of the procedure aren’t defined elsewhere, but defined in the symbol itself.

#### Clause

A procedure symbol inside another procedure symbol:

![](images/Symbol%20Language%20(2004).218.jpeg)

without a reference line is called a clause.

A clause is a definition contained in a procedure:

![](images/Symbol%20Language%20(2004).219.png)

This type of definition is usually not called a definition. The clause must be directly contained by a procedure. So this is not a clause:

![](images/Symbol%20Language%20(2004).220.png)

The clause can be a diamond or a square. Its container can also be a diamond as well as a square. A clause does not have a reference line, or it would have been a reference or a call, not a clause.

#### Active and Inactive

A diamond executes, a square does not. A diamond is said to be active, while a square is inactive.

#### Active Clause

A clause that is a diamond, is called an active clause:

|![](images/Symbol%20Language%20(2004).221.png)|![](images/Symbol%20Language%20(2004).222.png)|
| :-: | :-: |

It’s called active, because it executes.

#### Inactive Clause

An inactive clause is a clause that doesn’t execute. So it’s a clause that is a square:

|![](images/Symbol%20Language%20(2004).223.png)|![](images/Symbol%20Language%20(2004).224.png)|
| :-: | :-: |

It won’t execute unless you call it.

#### Sub Clause

A sub clause is a clause inside a clause. So it’s a procedure symbol without a reference line in a procedure symbol without a reference line in a procedure symbol, for instance:

![](images/Symbol%20Language%20(2004).225.png)

It doesn’t matter whether any of the symbols is a square or a diamond.

#### Sub Procedure

A sub procedure is any procedure symbol inside another procedure symbol.

![](images/Symbol%20Language%20(2004).226.png)

But usually it’s only the diamonds that are referred to as sub procedures. That’s because the execution of a procedure is made up of the execution of it’s contained diamonds combined.

![](images/Symbol%20Language%20(2004).227.png)

#### Parameter and Argument

Parameters and arguments are the *public* members of a procedure. In a square they’re called parameters. In a diamond they’re called arguments.

![](images/Symbol%20Language%20(2004).228.png)

A parameter is never created. An argument is an object that exists when the diamond executes. Therefore, an argument is a real created object, while a parameter is only a blue-print for it.

A parameter is a public member of a definition.

An argument is a public member of a diamond in execution.

#### Executor and Execution

Any diamond symbol is called an executor, because it can execute. A single diamond can execute multiple times. An individual execution of a diamond is called an *execution*.

It’s allowed to call an executor an execution, but usually only while it’s executing.

### Assignment

Before I explain using arguments, I must introduce another basic concept: *assignment*. I have to explain it, because to use input arguments you have to *assign* a values to it. Likewise, to retain output arguments, you must *assign* the output values to other objects.

*An assignment*:

> __A = B__

consists of two actions: a __Get__ and a __Set__. First you __Get B.__ Then you __Set A__. An assignment always consists of one __Get__, immediately followed by one __Set__.

There are two main types of assignment: *state assignment* and *line assignment*.

State assignment is the most basic, and the easiest to understand. The values of one object are copied to another.

> __A = B__

The value of __B__ is copied to __A__. The state assignment does not make __A__ and __B__ the same object. They are two *separate* objects that contain equal *values*. Change the value of one object and the two objects differ again.

To make __A__ and __B__ represent the same *object*, you have to do a *line assignment*:

> __A ![](images/Symbol%20Language%20(2004).229.png) B__   

*Pronounce: A’s object is B*

*It’s an equals sign with the letter o in it.*

This is an *object* line assignment. The object line of __A__ is set to symbol __B__. The result is that __A__ points to __B__.

The operator __=__ is not reserved for state assignment. Instead, the operator for state assignment is commonly: ![](images/Symbol%20Language%20(2004).230.png).

A simple diagram notation of an assignment is as follows:

|<p>![](images/Symbol%20Language%20(2004).231.jpeg)</p><p>*State assigment*</p>|<p>![](images/Symbol%20Language%20(2004).232.jpeg)</p><p>*Object assignment*</p>|
| :-: | :-: |

Or:

|<p>![](images/Symbol%20Language%20(2004).233.jpeg)</p><p>*State assigment*</p>|<p>![](images/Symbol%20Language%20(2004).234.jpeg)</p><p>*Object assignment*</p>|
| :-: | :-: |

The result of object assignment:

![](images/Symbol%20Language%20(2004).235.jpeg)

is:

![](images/Symbol%20Language%20(2004).236.jpeg)

But you can also view it the other way around. The following:

![](images/Symbol%20Language%20(2004).237.jpeg)

Is the result of an object assignment:

![](images/Symbol%20Language%20(2004).235.jpeg)

This is an important way of viewing it, because most of the times you’ll only see the result of an assignment and not the assignment operation itself. The assignment operation *is there*, however. Therefore an even simpler notation of assignment is not to show the assignment at all.

Unfortunately, the result of *state* assignment is not visible in diagram code as a line, so you have to display the explicit assignment.

![](images/Symbol%20Language%20(2004).238.jpeg)

A shorthand, quick notation of an assignment is the following:

|![](images/Symbol%20Language%20(2004).239.png)|<p></p><p>*=*</p>|![](images/Symbol%20Language%20(2004).240.png)|
| :-: | :-: | :-: |

There are more ways to draw out an assignment, but the ones here are by far the simplest and most easy to understand. Other notations are covered in another chapter.

State assignment is the most basic assignment. Line assignment is based on it. A line target is stored in an __Integer__ object. So when assigning the line target, you’re actually assigning the __State__ of this __Integer__ object. Drawing a line assignment as a state assignment is a more difficult, but useful notation. However, in this chapter I will stick to the simpler notations.

You can work with the *type* and *interface* lines the same way: there’s also type assignment and interface assignment. Likewise, you can work with line assignments for *procedure symbols*. However, I’ll mostly talk about state and object assignment.

#### Get and Set are Inseparable

A state write is always paired with a state read and a state read is always paired with a state write.

When you read a state, the state is meant to be assigned to another object. And from the other perspective, there’s no point in reading the state if you’re not going to assign the state to another object.

### Argument Access

The reason I’ve explained about assignment is that using arguments always requires assignment.

Just before execution you’ll write arguments. Just after execution, you’ll read arguments. Those are the main two occasions you’ll access arguments.

#### Prolog and Epilog

Writing and reading arguments require things to be done just before and right after the execution. Things that must be done just before execution are called the *prolog* of the execution. Things that must be done just after the execution are called the *epilog*.

Writing arguments takes place in the prolog and reading arguments takes place in the epilog.

#### Argument Assignment Requires Reading in Prolog!

Argument assignment takes place in the *prolog*. But *setting* the argument also requires *getting* the argument. However, getting the argument was said to take place in the *epilog*. For the purpose of *setting* the argument, however, *getting* happens in the *prolog*.

An assignment call:

![](images/Symbol%20Language%20(2004).241.jpeg)

*consults* the argument to *write*: *reads* the argument to *write*.

Assignment of arguments simply *must* take place in the prolog, even though they require reading the arguments.

Assignment procedures are fundamental procedures of the Symbol Language and behave much different from other procedures.

#### Writing Arguments

Writing an argument before execution means to set its state or line target.

An assignment as such, requires you to get a value from one place and set the argument to it. So writing an argument actually requires both a __Get__ and a __Set__. The fact that it’s the argument that’s __Set__ makes it writing *the argument*.

#### Reading Arguments

Reading arguments after execution requires storing the values of the arguments in other objects. This is because after execution, the executor will destroy and the arguments will no longer exist. Therefore, to retain the values of the arguments, you must copy the information to other objects. The information of a read argument can be the state of the argument. In that case, to retain it, you need to copy the state of the argument to another object. 

![](images/Symbol%20Language%20(2004).242.jpeg)

The information of a read argument can also be the line target of the argument, but this is hardly ever done.

![](images/Symbol%20Language%20(2004).243.jpeg)

If you do do it, then you’d better copy the final target of the argument to some place. I can give a notation of the effect of this assignment:

|<p>![](images/Symbol%20Language%20(2004).244.jpeg)</p><p>*Argument points to A*</p>|<p>![](images/Symbol%20Language%20(2004).245.jpeg)</p><p>*Line target copied*</p>|<p>![](images/Symbol%20Language%20(2004).245.jpeg)</p><p>*Diamond destroys. Argument’s line is annulled. Line target information is preserved.*</p>|
| :-: | :-: | :-: |

A detailed notation of this assignment is beyond the scope of this chapter. This method for procedure output is hardly ever used. Other means are adopted to have procedure output.

#### ----------------- < >

#### Input, Output and Thoughput

##### Output by Reference

< Referencing a created parameter. You don’t keep the object of it then (that should have been formulated differently). Actually something else should be done for that. I do want to keep it. But not by changing breaking the chain methodology. I have to rest. >

The procedure output method above is hardly used ever used. That’s because you can’t really tell if the target object will keep existing, unless you’ve defined the object yourself. Therefore, using output other than state output is usually done by passing a reference to an existing object to the procedure.

This, however requires you to *write* the line of an argument.

![](images/Symbol%20Language%20(2004).246.jpeg)

Nothing is *read* in the epilog in this case. Even though the argument functions as *output*, it’s still a *write* argument.

Any line going out of a diamond is set just before the diamond executes.

##### Write, Read ≠ Input, Output

As such, *read and write arguments* is not analogous to *input and output arguments*. A write argument can easily serve as an output argument.

##### Reference Arguments

Reference arguments can serve as input, output and throughput. State arguments can serve as input, output and throughput too. 

You’ll hardly use a line target as output information. You’ll probably use an argument’s line target only to pass an object by reference.

Even though an argument’s line is hardly ever read, an argument’s state *is* commonly read.

#### Using Arguments

You’ll mainly use arguments by reading and writing their state or to pass objects by reference.

#### Create Argument and Call Argument’s Members

There may be more things you want to do with an argument before passing it to a procedure. You may want to create a brand new object as an argument and you may want to call some members of the argument first. You *can’t* do these operations directly on the argument. You have to create a separate object, manipulate it and then pass it by reference

There’s a shorthand for creating a brand new object and passing it by reference. In text code this will look like this:

```vb
Procedure ( New Type )
```

It’s declared directly inside the procedure call. That is: unless the object is used elsewhere too. The above can also be notated as follows:

```vb
Object As Type       ‘Declaration
Object = New Type    ‘Creation
Procedure ( Object ) ‘Pass to Procedure
```

But if __Object__ isn’t used anywhere else, you can just type: 

```vb
Procedure ( New Type )
```

That way, the object seems to be the argument itself, even though you’re actually passing an object by reference.

In diagram code, the declaration of the object, its creation and its being passed to the procedure, looks like this: 

![](images/Symbol%20Language%20(2004).247.jpeg)

You can let the separate object seem to be the argument itself, by using a peel notation:

![](images/Symbol%20Language%20(2004).248.jpeg)

The creation will still be visible, but you’ve excluded the line, without loosing the information that it’s really an external object. 

Ofcourse you don’t have to show the implicit creation.

![](images/Symbol%20Language%20(2004).249.jpeg)

Then you just see that the object is created, and you will be satisfied knowing only *that* it is created, not where and when. This is just about exactly the effect of:

```vb
Procedure ( New Type )
```

#### Created Arguments

A procedure can decide if an argument is a created object or not. If it is a created object, then the object is created in the prolog, even before writing arguments. The argument object is created, then it is written, then the procedure executes.

Arguments as such are created objects directly contained by the procedure. They shouldn’t have lines. 

In the epilog, first arguments are read before the created arguments are destroyed. The procedure only destroys objects it directly contains.

#### Do It with a Parameter’s Members

< *Other things done with parameters*
or keeping a reference to a created parameter or __do the same with members of parameters__... Hmmm...
Except for passing procedure reference to a procedure. >

#### Accessing Arguments During Execution

Apart from writing in the prolog and reading in the epilog, there’s a third period in which you can access an argument: during execution. You can only access the arguments of a diamond *in execution*. The caller of the diamond is frozen, till the execution completes, so the caller doesn’t have any chance of accessing the arguments during execution. However, everything inside the executor is in motion. The executor itself can freely access its arguments, ofcourse, but also anything it calls, could access its arguments, if given a reference. But, as I said, the *caller* of an execution can’t access the arguments during execution.

The diagrammatic effect of this is the following. A member can be accessed by the diamond that contains it, and by all its sub diamonds:

![](images/Symbol%20Language%20(2004).250.png)

I said that procedures called by a procedure can access its arguments. That suggests that the procedure that accesses the member can be somewhere else than inside the member’s diamond:

![](images/Symbol%20Language%20(2004).251.png)

Note, however, that it’s not the definition that’s accessing member __m__. It’s the call that’s accessing member __m__, and the call is contained inside the diamond that contains member __m__.

More rules on that are covered in the *Execution Basics* section.

#### Distinguishing Assignment Source and Target

There’s one more ambiguity in argument access that I will resolve here. In an assignment call in diagram as follows:

![](images/Symbol%20Language%20(2004).252.png)

there isn’t anything that tells which is the source of the assignment and which is the target: is it __Procedure . B ![](images/Symbol%20Language%20(2004).229.png) A__ or is it __A ![](images/Symbol%20Language%20(2004).229.png) Procedure . B__ ? You could name the arguments of the ![](images/Symbol%20Language%20(2004).229.png) (*object is*) call: name them __Get__ and __Set__ to make out the difference, but usually another method is adopted.

Assuming the assignment is really __Procedure . B ![](images/Symbol%20Language%20(2004).229.png) A__, the effect of the assignment is:

![](images/Symbol%20Language%20(2004).253.png)

To show the ‘direction’ of the assignment, the access symbol of the resulting line is shown in the assignment call:

![](images/Symbol%20Language%20(2004).254.png)

In this case, the access symbol is about the *effect* of the assignment, not about the direction of ![](images/Symbol%20Language%20(2004).229.png)’s __Set__ argument.

In the case of state assignment, the result is not a line, so logically the state assignment call can’t ‘borrow’ the access symbol from the resultant line. However, in line assignment, the target of the line, the source of the assignment (!), gets the access symbol. Conversely, the source of the state assignment gets an access symbol:

![](images/Symbol%20Language%20(2004).255.png)

The rule is: the source of the assignment gets the access symbol. An oddity is that the *source* of a line assignment is the *target* of the resultant line.

Direction can be determined by assumption of the most common situation. Therefore, the access symbol can be left out it the resultant line is outwards.

|![](images/Symbol%20Language%20(2004).256.png)|![](images/Symbol%20Language%20(2004).257.png)|
| :-: | :-: |

For state assignments it’s adised to always show the access symbol. 

### ------------------------------------------------------< !!! Was here replacing call lines with diamond symbols and trying to finish up the first chapters. >

### Execution Basics

< Some things here may have a place in Execution Order >

< Which situations can only reside in a procedure? >

This section covers some basic execution situations. Each situation has certain implications. Usually the implications are quite < voor de hand liggend >, but noteworthy nevertheless.

< Deze inleiding is te denigrerend over de sectie >

#### Squares and Diamonds

![](images/Symbol%20Language%20(2004).258.jpeg)

A square doesn’t execute. Well, they only execute when you call it.

![](images/Symbol%20Language%20(2004).259.jpeg)

*A is a call to B.*

But then again: A is the one that’s executing, not B. So diamonds execute, and squares do not.

#### Diamonds Execute When Direct Parent Executes

A diamond doesn’t execute automatically. It only executes when the parent symbol executes.

![](images/Symbol%20Language%20(2004).260.jpeg)

*A executes only as B executes.*

So diamonds inside squares don’t really execute.

![](images/Symbol%20Language%20(2004).261.jpeg)

But if you call B, then you get the following:

![](images/Symbol%20Language%20(2004).262.jpeg)

Actually, The letters distinguish the different symbols. If you only use letters to distinguish which procedure definition it’s about, you get the following:

![](images/Symbol%20Language%20(2004).263.jpeg)

So in that sense, diamond A does execute. But not the definition executes, only the call executes.

#### Diamonds Can only be Directly Inside a Procedure Symbol, Diamonds Can’t be Directly Inside an Object Symbol

Because execution can only take place in a procedure, a diamond can’t be directly inside an object Symbol

![](images/Symbol%20Language%20(2004).264.jpeg)

#### You Can Only Access Members of a Diamond

You can (usually) only access members of a diamond, because a square is never created, just like you can’t access members of a non created object.

![](images/Symbol%20Language%20(2004).265.jpeg)

![](images/Symbol%20Language%20(2004).266.jpeg)

#### You can Only Access Members of a Diamond, while the Diamond is executing

Because a diamond is only created when it’s executing, you can only access members when the diamond is in execution.

Some members of a procedure can be static. In that case the member belongs to the procedure definition. Those member are the same for any reference or call to a procedure. Static member of a procedure can be freely accessed through any square or diamond that represents it.

#### The Diamond Executor Can Access Members Only Just before and Just After the Execution

If the diamond executor accesses something of a diamond, it’ll only access it just before and just after the call.

< Don’t know the notation, really >

In fact the diamond executor will only write members just before the call and will only read members just after the call.

< Don’t forget that you don’t need to read or write necessarily, you can also just call a member of the parameter instead of read or write it... explore that >

#### Accessing a Diamond Member During a Call

So how will you access a diamond member *during* a call? Well, usually only procedures called by the executing diamond can access the call parent.

![](images/Symbol%20Language%20(2004).267.jpeg)

Diamond A executes, then diamond B executes and accesses a member of diamond A. It’s not the procedure definition, the square, that accesses a member of diamond A, but it’s the specific call to the procedure that access diamond A. So usually you’ll only see child diamonds accessing parent diamonds, on top of the more common situation of write access before a call and read access after.

Multi-threading, which is ..., can also make you able to access a diamond in execution, but this is usually not a good idea. Restrictions should be opposed to multi-threading to avoid such situations.

![](images/Symbol%20Language%20(2004).268.jpeg)

Two sibling procedures are executing at the same time, in different threads, which makes it possible for one executing procedure to access the other. Thread control makes it possible to avoid such volatile situations.

(the fact that the diamonds are drawn with thicker lines above, says that they are both in execution. If they wouldn’t be thicker drawn, then the diagram above doesn’t explicitly show that there is a multithread situation. Regarding it single threadedly, the situation above is just the bigger diamond executing first, after which the smaller diamond uses its return value.)

< What happens when two threads try to initiate the same diamond or a thread tries to initiate a diamond that’s already executing. I want that one figured out >

< consider the example of diamond reference to diamond in the main argument reference example >

#### Passing an object reference to a procedure

![](images/Symbol%20Language%20(2004).269.jpeg)

When you pass an object reference to a procedure, the procedure can access the object.

In the situation above it seems the procedure could access the object anyway (because a procedure can access everything accessible to the object that contains it). It *can*, but in this case the *caller* decides which object to point to, not the called.

#### Procedure can set object reference itself too

When the caller (the parent diamond) sets the line, then the caller decides which object the call will refer to.

So lines going out of a diamond aren’t neccesarily lines set by the caller.

Procedures can’t set line going *into* the square themselves. Those are always set by the caller.

It’s important that the procedure itself sets lines, because the line targets of procedure members often serve as the output values of the procedure.

< I don’t know a notation to distinct sets by the caller and sets by the call. Well... in a more explicit notation you will see that the caller calls the set or the called calls the set. >

#### Clause Access

Clauses have special access privileges compared to delegated procedure symbols.

![](images/Symbol%20Language%20(2004).270.jpeg)

< Bad explanation following >

A clause can freely access anything of its parent clause and the parent clause’s parent clause, etcetera. If going up the procedure ancestry a procedure symbol is encountered with a reference line, the clause can access this ancestor freely, but not any higher in the procedure ancestry.

In the picture above, the top two lines could have been set by A itself. The first resides in A’s parent clause. The second resides in the *execution* that parents A, so still accessible to A. The last line, crossed out, can’t be set by A itself, because it resides outside A’s containing call. It can be set only by a symbol higher than A’s containing call, for instance B.

Squares formally can’t have outward lines, except for static members. There are situations in which non static members of squares are shown to have outward lines, but those are discussed later.

#### Passing a procedure reference

When you pass a procedure referece to a child procedure:

![](images/Symbol%20Language%20(2004).271.jpeg)

The child can call the referenced procedure at will.

#### The If example

A great application of that is the If procedure.

![](images/Symbol%20Language%20(2004).272.jpeg)

Procedure A passes Clause A and Clause B to Procedure B, along with an object that serves as the condition. Depending on the state of the condition, Clause A is executed or Clause B. So Procedure B gets to decide which clause executes.

The clauses can freely access anything of __Procedure A__, so __Procedure B__ is able to call things that can freely access __Procedure A__’s stuff.

#### Brainstorm

- Simple voor de hand liggende issues regarding execution < Which precisely? >
- For instance, diamond only inside a procedure symbol
- Stuff like that. Simple issues that you can easily understand.
- Diamond pointing to another diamond
- Recursive calls... hmmm... advanced issue. Hoef je je klomp niet over te breken. 

< Maar lijkt een Execution basics. Hmmm... de term Execution Basics is niet goed genoeg dan. De term basics is niet goed. Execution Facts... nah. >

- Wanneer wordt een diamond meerdere keren geexecute?

##### 1

Diamond represents individual calls to a definition.

In a recursive situation, though: < P >, one diamond can represent multiple calls < ? How to get that straight? >

< NO IT CAN’T. >

##### 2

A diamond pointing to another diamond: it’s a call to a call. both diamonds represent the same call. They will never execute individually.

##### 3

If eventually the original caller is called again, with one of its calls in progress... hmm... can you call upon a call on hold, because it is waiting for one of its calls to finish? Its public objects, maybe, but you can’t execute anything in it. 

![](images/Symbol%20Language%20(2004).273.png)

##### 4

(*Implicit* embedded procedure reference causes a separate implicit call)

##### 5

__*Procedures can only be Called from another Procedure*__

*Procedures can only be called directly from another procedure.*

< Because a call executes its target when its container square is executed. Actually, relate all restrictions to the fact that procedures execute. >

A procedure symbol can ony have a call line if it’s directly inside another procedure. Usually the call line first exits the procedure that contains the call. In other words: a call line usually directly exits a square.

![](images/Symbol%20Language%20(2004).274.png)

Only when you call a clause or an embedded procedure reference, the line doesn’t exit the procedure first:

![](images/Symbol%20Language%20(2004).275.jpeg)

*Call to clause*

![](images/Symbol%20Language%20(2004).276.jpeg)

*Call an internal procedure reference*

### Implicit Notations

< you can call an implicit call a parameter reference too. Mention it so you show that there’s a big difference between parameter reference and argument reference >

- Implicit call and Explicit call
- Implicit return value reference
- Implicit argument assignment

#### Previous Texts

##### A

###### Referencing Square Members: Implicit Call

It is really only allowed to reference members of diamonds:

![](images/Symbol%20Language%20(2004).277.jpeg)

When you do reference a square’s member:

![](images/Symbol%20Language%20(2004).278.jpeg)

You’re actually seeing only part of the diagram. The reference to a square member actually creates a sibling diamond which is a call to the square:

![](images/Symbol%20Language%20(2004).277.jpeg)

The diamond missing when referencing the square member is called the implicit call to the square.

Even though the Symbol code *really* *defines* a reference to a square member, when the code is executed, it’s treated as having an extra diamond. Allowing referencing a square member can simplify the notation in many cases, that’s why it’s allowed.

The implied diamond always becomes the sibbling of the reference to a member. In a more encapsulative situation, this:

![](images/Symbol%20Language%20(2004).279.jpeg)

Is the implicit notation of this:

![](images/Symbol%20Language%20(2004).280.jpeg)

The reference to a square member implicitly creates a call to the square right next to it.

Whenever you reference a square member, an implicit call is made.

![](images/Symbol%20Language%20(2004).281.jpeg)

\=

![](images/Symbol%20Language%20(2004).282.jpeg)

< Add some access symbols >

If you want to access members of a procedure using only one call, you have to explicitly notate the diamond that is the call.

![](images/Symbol%20Language%20(2004).283.jpeg)

< Add some access symbols >

But the accesses can only only take place just before the call and just after.

But as I said: child diamonds can access their parent diamond’s members if the parent diamonds allows it.

![](images/Symbol%20Language%20(2004).284.jpeg)

###### An object symbol as a pointer to a procedure symbol: Implicit return value reference.

You can also let an object symbol point to a procedure symbol.

![](images/Symbol%20Language%20(2004).285.jpeg)

In that case you’re actually implicitly referencing the return value.

![](images/Symbol%20Language%20(2004).286.jpeg)

###### Implicit Call and Implicit Return Value Reference

If an object symbol is a reference to a square, it’s both an implicit call and an implicit return value reference.

![](images/Symbol%20Language%20(2004).287.jpeg)

![](images/Symbol%20Language%20(2004).288.jpeg)

![](images/Symbol%20Language%20(2004).289.jpeg)

in the second picture you see the explicit call. The third picture adds the explicit return value reference. You don’t first do the explicit call and then the explicit return value reference. That order is totally arbitrary, you can also see it like this:

![](images/Symbol%20Language%20(2004).287.jpeg)

![](images/Symbol%20Language%20(2004).290.jpeg)

![](images/Symbol%20Language%20(2004).289.jpeg)

###### Reference to Other Out Parameters

An object reference to a procedure can only be a reference to the procedure’s return value. If you want to reference other out paramters, you have to reference them explicitly.

![](images/Symbol%20Language%20(2004).291.jpeg)

(o = out, r = return)

__a__ can only be a reference to __r__, the return value. __b__ is a reference to __o__, another out parameter.

##### B

###### Implicit Calls

< Maybe diagrams can be more basic, expressing solely a concept >

< reference a procedure parameter from an object. >

To explain this concept I use an example where one procedure, called __Get__, returns an object that is then passed to another procedure, called __Set__. This requires two calls: first a call to __Get__ and then to __Set__.

####### Explicit Calls

The steps of this process can be described as follows:

```
Get
Set . In = Get . Out
Set
```

The out parameter of __Get__ is called __Out__ and the in parameter of __Set__ is called __In__. In diagram code, that is:

![](images/Symbol%20Language%20(2004).292.png)

*Excplicit calls*

Only the blue parts are shown in the piece of text code. You can see that __Get__ is called and __Set__ is called. Both __Get__ and __Set__ have a parameter. The parameters are shown in the definition, but also in the call. In the call, the parameters are actually created and the parameters in the calls are worked with. The __Out__ of __Get__ and the __In__ of __Set__ are tied together with an object line. You can’t explicitly see the order in which __Get__ and __Set__ are called, but because the __Set__ call references a parameter in the __Get__ call, __Set__ is dependent of __Get__, therefore __Get__ is called first.

####### Implicit Calls

In text code you can write the two calls in a single code line:

```
Set ( In = Get . Out )
```

__Get . Out__ is assigned to the parameter of __Set__. You’re referencing a parameter of __Get__ without displaying the call. To read the __Out__ parameter of __Get__ requires a call and this call is implicitly made. In the text code line above you don’t see that __Get__ is called. __Get . Out__ is simply referenced. You can apply the same to diagram code:

![](images/Symbol%20Language%20(2004).293.png)

*Implicit call*

*Note that the Exit Most Borders rule determines the direction.*

You can see that the __Out__ parameter of the __Get__ procedure *definition* is referenced. This implicitly causes a call to __Get__. In *explicit calls* you reference the parameters of the procedure *call*, not the procedure *definition*.

####### Implicit Return Value Reference

__Out__ is __Get__’s return value. Therefore, the identifier __Get__ symbolizes the return value. __In__ is a parameter of __Set__ and you don’t necessarily need to mention its name in the parameter list. This all makes the text code:

```
Set ( Get )
```

__Get__’s symbolizing its return value can also be applied to diagram code:

![](images/Symbol%20Language%20(2004).294.png)

*Implicit return value reference, implicit call*

The line to __Get__ is not really a line from an object to a procedure. The return value of __Get__ is implicitly referenced.

The diagram above looks far simpler than the first diagram. So does the text code. In reality multiple steps are taken: • Call __Get__ • Read __Get . Out__ • Write __Set . In__, • Call __Set__.

In the diagram above, the return value is implicitly referenced by pointing to the procedure definition. You can also implicitly reference the return value by pointing to a procedure call square. That way, the call is explicit, but the return value reference is implicit.

![](images/Symbol%20Language%20(2004).295.png)

*Explicit cal, implicit return value reference*

####### Multiple Out Parameters

######## Implicit Return Value Reference

Implicit return value reference is only a way to reference the *return value*, not to the other out parameters. The other out parameters must be explicitly referenced. 

![](images/Symbol%20Language%20(2004).296.png)

*Implicit return value reference, explicit out parameter reference*

######## Implicit Calls

When you reference output parameters of a procedure multiple times, each reference causes its own call to be made. 

![](images/Symbol%20Language%20(2004).297.png)

*Two references to a parameter of the definition: two implicit calls*

If the diagram above is an abstract view on the system, there might only be made a single call, but officially the diagram above is showing *two* implicit calls. The meaning of the diagram above is:

< P: same system as above, now physically showing the two calls >

If you want to reference multiple output parameters of a single call, you have to expliclity display the call and reference the objects that are inside the call symbol. By referencing the parameters of the call, you only use one call.

![](images/Symbol%20Language%20(2004).298.png)

< Call in blue >

##### C

###### ? Referencing a Procedure Member

Referencing a diamond’s members is like reading a procedure member.

![](images/Symbol%20Language%20(2004).269.jpeg)

< 20040418: this is interesting. It has to do with implicit call and I have to explore in which situation this is useful. I think that when you call a member of the top circle, then the diamond executes. It’s like calling member of the bottom circle... >

It always happens just after the diamond executes.

< The parameter objects destroy right after the call. If you use the top circle like above, every consult of the top circle will result in executing the diamond again. To persist the information contained in the argument, without having to call the procedure again, you have to do a State Copy. Another way of using output parameters is to give the execution a reference to an external symbol. Anyway: if you want return information to persist after the call, it has to be stored in external symbol: store the returned state to an object that the caller contains, or pass a reference to the caller’s object to the called procedure >

< That’s true what I just said, but there’s nothing wrong with linking directly to the parameter and executing the procedure on each consult. There’s nothing wrong with that. The link would be something like consulting a property procedure in VB, a Get, which returns a reference to an object. Every time you consult the property, the procedure is launched again. That’s normal. >

< Must denote that the notation above is not an output situation. It’s an implicit call situation >

#### Brainstorm

##### 1

<
Oh, die assignments lijken afzonderlijke referenties, waardoor je implicit calls krijgt? Of is dat alleen bij referenties naar inhoud van squares?

Oh, nee! Hè! Ik heb ergens in dit hoofdstuk iets staan over een diamond die execute telkens als je een object met een line naar een parameter beraadslaagt. Hoe zit DAT dan?

Dat is verkeerd >

##### 2

*Nice wording:*

A reference to something inside a square causes an implicit call to the square, because the procedure is required to execute in order to reference something inside of it.

##### 3

Implicit calls when referencing square contents (and their explicit diagram representations)

### Argument Reference

There are three ways to use arguments: state read, state write and passing by reference:

|<p></p><p>![](images/Symbol%20Language%20(2004).299.png)</p><p>*State read*</p>|<p>![](images/Symbol%20Language%20(2004).300.png)</p><p>*State write*</p>|<p></p><p></p><p>![](images/Symbol%20Language%20(2004).301.png)</p><p>*Pass by reference*</p>|
| :-: | :-: | :-: |

There seems to be one more: *argument reference*.

![](images/Symbol%20Language%20(2004).302.png)

*Argument reference*

This is however not possible, because the argument destroys after execution, so you can’t reference it after execution, because then there is nothing left to reference anymore. Argument reference is useless.

Argument reference is actually a fictive concept.

![](images/Symbol%20Language%20(2004).302.png)

It is actually an implicit notation for a *reference argument*:

![](images/Symbol%20Language%20(2004).301.png)

There’s more to getting the explicit notation of argument reference than just inversion of direction. Consider this diagram:

![](images/Symbol%20Language%20(2004).303.png)

This diagram has two argument references in it. If you would simply invert the direction you’d get the following:

![](images/Symbol%20Language%20(2004).304.png)

*(Note that the last access symbol didn’t change, because that line isn’t an argument reference)*

It still has a argument reference in it. 

The explicit notation that solves this is the following:

![](images/Symbol%20Language%20(2004).305.png)

The child diamond is inserted as a substitute for the higher diamond it refers to. This offers a solution because the parent of the child diamond will exist when the child exists. {This might be an issue for multiple execution of a diamond. It also raises the question what happens when you consult something of the righter diamond. Is the bigger diamond executed first? What?} That’s rule two for getting to the explicit notation of parameter reference.

< I have doubts about this third rule. I think this case might be illegal. I need to find the rule on what makes it illegal and how you see the illegality of it in the implicit notation >

There’s one more problem. The explicit notation introduced so fat has a flaw: the object has two line targets! If a situation as such occurs, the directions of all flawful non-argument references are inverted:

![](images/Symbol%20Language%20(2004).306.png)

Which gives is rule three of the explicit notation of argument reference.

If a reference argument targets the argument of a parent diamond, it is not considered an argument reference.

![](images/Symbol%20Language%20(2004).307.png)

Argument reference is only the case where you *enter* a diamond.

#### Summary

So the implicit argument reference notation:

![](images/Symbol%20Language%20(2004).308.png)

Has the following explicit notation: < I know it is wrong, I should investigate later >

![](images/Symbol%20Language%20(2004).309.png)

Rule 1:

A argument reference (a line entering a diamond) is an implicit notation of the reverse direction (a reference parameter).

Rule 2:

If the line both enters and exists a diamond, then the inversion of direction doesn’t solve it. <> In that case, a child diamond is created in the diamond that holds the argument reference. The diamond references the diamond that held the argument reference target. The new child diamond is used instead. <>

Rule 3:

...

You go from implicit to explicit notation in the following steps:

![](images/Symbol%20Language%20(2004).303.png)

Reverse direction of argument references

![](images/Symbol%20Language%20(2004).304.png)

Create child diamonds where the inversion doesn’t work

![](images/Symbol%20Language%20(2004).305.png)

Invert the direction of other lines that became faulty

![](images/Symbol%20Language%20(2004).309.png)

### Execution Order

Execution order is (part) determined by dependency: a procedure that renders a result used in another procedure is executed first.

Using the dependency rules, argument reference notation (the implicit one) suggests the following execution order:

![](images/Symbol%20Language%20(2004).310.png)

However, translating it to the explicit reference argument notation:

![](images/Symbol%20Language%20(2004).311.png)

The dependency looks must different. After the translation to this, execution order is determined fully by parent-child relations: parents execute first, then children.

![](images/Symbol%20Language%20(2004).312.png)

In this implicit notation __A__ *seems* to be dependent of __B__, but in fact __B__ is dependent of __A__, because it uses it as a reference argument.

#### Custom Order

Apart from execution order imposed by dependency, the programmer can set a custom execution order, which may not conflict with dependency (parent-child) order, but should only be applied where execution order is undetermined by dependency. Actual parent child relations impose execution order. Only the execution order of *actual* siblings can be custom set (not siblings in implicit or abstract notations). The order is denoted with numerical ordinals.

![](images/Symbol%20Language%20(2004).313.png)

Custom execution can be significant for instance for value transformations to happen in the right order.

#### Brainstorm

- Seeming randomly referencing diamond members.

argument reference is not the same as an implicit call (referencing a square member).

##### 1

Als een assignment een waarde uit de ene procedure (A) Get en een waarde uit een andere procedure (B) Set, dan is de executie van B afhankelijk van de executie van A. Daardoor wordt de executievolgorde bepaald. Als het ene afhankelijk is van de executie van et andere en het andere afhankelijk van de executie van het ene, dan is er een bepaald soort circularity ontstaan waar niks mee kan. De computer kan slechts de dingen een voor een uitvoeren. De compiler kapt er gewoon mee. 

##### 2

Randomly referencing call members. I thought you could only do it just before and just after

##### 3

HMMM... in sommige gevallen execute de diamond misschien meerdere keren zonder unconditional jumps en zonder z’n parent meerdere keren te executen... dat moet dan wel een specifieke uitzonderlijke situatie zijn die precies te definiëren is>

Goeie zin?:

Call finished: references to diamond contents anulled.

##### Execution Basics or Execution Order

So diamonds represent executions and calls, but not necessarily indivual executions. Multiple diamonds can represent the same execution. Actuall: only the same execution at one time, because you can execute the diamond multiple times, only no two executions at the same time.

### In, Out and Thru Argument Notation

< The out parameter access symbol isn’t required, so the notation of it *suggests* that it’s an in parameter reference >

Argument reference notation (an implicit one):

![](images/Symbol%20Language%20(2004).314.png)

is saying that the actual reference argument:

![](images/Symbol%20Language%20(2004).315.png)

Is used as out and *not* as in.

![](images/Symbol%20Language%20(2004).316.png)

The explicit notation:

![](images/Symbol%20Language%20(2004).315.png)

can be in, thru or out. But the access symbol is usually not notated in case of outward direction:

![](images/Symbol%20Language%20(2004).317.png)

Therefore this outward notation with an access symbol suggests that it’s an in argument.

![](images/Symbol%20Language%20(2004).318.png)

Thru can be notated as:

![](images/Symbol%20Language%20(2004).319.png)

Which is not a real bidirection, because the line can’t *really* go inward anyway. It’s an implicit notation.

As such, there are six explicit argument purposes:

|<p>![](images/Symbol%20Language%20(2004).320.png)</p><p>*State in*</p><p></p>|<p></p><p>![](images/Symbol%20Language%20(2004).321.png)</p><p>*State out*</p>|<p>![](images/Symbol%20Language%20(2004).322.png)</p><p>*State thru*</p>|
| :-: | :-: | :-: |
|<p>![](images/Symbol%20Language%20(2004).323.png)</p><p>*Reference in*</p>|<p>![](images/Symbol%20Language%20(2004).324.png)</p><p>*Reference out*</p>|<p></p><p>![](images/Symbol%20Language%20(2004).325.png)</p><p>*Reference thru*</p>|

#### Execution Order In Text Code

The resulting sequence of code lines corresponds to the execution order required for dependency. As you change the diagram, the order of the text code can change. You can freely more around text lines of sibbling symbols.

< The resulting sequence of code lines and the execution order within code lines. >

< Don’t cover exact text code here >

### Other Line Types

### Brainstorm

< By the way, argument in, out and thru notatioin doesn’t cover the in, out, though notation in procedure definitions. If I will even create that >

#### Summary of Old Subdivision

- Basics of assignment
    - Line assignment
    - State assignment
    - The notation I'll use here

- Writing arguments before the call:
    - Assignment: lines or state
    - Creation
    - Possibly call members of an argument
- Reading parameters before the call:
    - Reading line targets (direct, final or intermediate)
    - Reading state
- Writing a parameter means setting a line or reading state from an object and writing it to a parameter
- Reading a parameter means writing it to another object

- Automatic execution order

- Using type procedures with the THIS argument
- State assignment is the basic assignment
- Execution basics: 
    - simple issues regarding execution
    - for instance, diamond only inside a procedure symbol
    - Stuff like that. Simple issues that you can easily understand.
- Diamond member access:
    - The caller of a diamond accesses members just before the call and just after
    - The callees of a diamond can access the caller's members if given references to them

- Implicit call and Explicit call
- Implicit return value reference
- Out, In and Thru parameter usage
    - Cover procedure reference too
    - If example

- The terms:
    - Reference
    - call
    - definition
    - clause
    - active clause
    - inactive clause
    - sub clause / sub procedure 
    - ...

- Clause access
- Differences with Com with returning object references
- Inside directly accessible, outside only 'indirectly' accessible (if line set FOR you)
- Seeming randomly referencing diamond members. 
- Exclusive establishment problemen moeten in System Aspects worden behandeld
- Definitions of the terms parameter and argument
- Recursive calls... hmmm... advanced issue. Hoef je je klomp niet over te breken.
- Wanneer wordt een diamond meerdere keren geexecute?
- Diamond pointing to another diamond
- Line of connected diamonds change simultaniously
- Initiation of execution:
    - Containment in other diamond
    - Consult of a parameter.
- Events ~ Mixed topic it seems. Not a main one, anyway.

#### New Subdivision

- Assignment
    - The terms Get and Set, introduce them
    - A Get and Set combine to an assignment
    - Line assignment
    - State assignment
    - Use the simple notation
    - ~ State assignment is the basic assignment

- Parameter Access
    - Writing parameters before execution
        - Assignment: lines or state
        - Creation
        - Possibly call members of an argument
    - Reading parameters after execution
        - Reading line targets (direct, final or intermediate)
        - Reading state
    - Access during execution
        - By owner
        - By child executions (~ is this the proper place for this?)
            - The callees of a diamond can access the caller's members if given references to them
    - Clause access

- Basic Terms
    - Reference
    - call
    - definition
    - clause
    - active clause
    - inactive clause
    - sub clause / sub procedure 
    - Definitions of the terms parameter and argument
    - <Which precisely?>
    -  ...

- Out, In and Thru
    - Using reference parameters for in, out and thru (hard to control whether it’s in out or thru: you just use the object)
    - Using State as In, Out and Thru
    - Using a parameter’s line targets as Out
        - Comparison with Com regarding returning object references.
            - Persisting object reference (harder, is hardly done anyway. Or is it? Consider passing the returned object to another procedure)
            - Using the procedure parameter as object reference directly
    - Procedure reference too
    - If example

- Execution Basics
    - Simple issues regarding execution <Which precisely?>
    - For instance, diamond only inside a procedure symbol
    - Stuff like that. Simple issues that you can easily understand.
    - Diamond pointing to another diamond
    - Recursive calls... hmmm... advanced issue. Hoef je je klomp niet over te breken. 

< Maar lijkt een Execution basics. Hmmm... de term Execution Basics is niet goed genoeg dan. De term basics is niet goed. Execution Facts... nah.

- Wanneer wordt een diamond meerdere keren geexecute?

- Execution Order
    - Seeming randomly referencing diamond members.
    - Initiation of execution:
        - Containment in other diamond
        - Consult of a parameter.
    - Manual execution order

- Implicit Notations
    - Implicit call and Explicit call
    - Implicit return value reference

?:

- Events ~ Mixed topic it seems. Not a main one, anyway.
- Line of connected diamonds change simultaniously

Don’t know if I should cover here:

- Using type procedures with the THIS argument (need a good name for the section)

Not parameters and execution:

- Inside directly accessible, outside only 'indirectly' accessible (if line set FOR you)
- Exclusive establishment problemen moeten in System Aspects worden behandeld

#### New Main Subdivision

Assignment
Parameter Access
Basic Terms
Out, In and Thru
Execution Basics
Execution Order
Implicit Notations

#### New Brainstorm Texts

##### 1

The problems proposed in this text have to do with:

- The terms prolog and epilog, prologous and epilogous
- The term executor and execution
- No implicit notation for state assignment
- Parameter assignments involve consults of parameters in prolog of procedure call, while consults are usually always in epilog.
- Diamond may only represent a single execution per definition call (not regarding unconditional jumps (? The latter is questionable.)

###### New

- Prolog and epilog
- Parameter writes in prolog
- Parameter reads (/consults) in epilog 
- No implicit notation for state assignment. An orderly explicit notation will do.
- Assignments of parameters suggests reading parameters. However, these assignments do take place in the prolog, even though they suggest reads. Assignments are different that way. <>The assignment destination consult is not seens as a consult.<> Consult of a parameter as assignment destination does not require execution of the parameter holder.
- Executor represents one execution per call on definition.        
    - Implicit calls are not made for diamond contents reference <>

###### Old

![](images/Symbol%20Language%20(2004).326.jpeg)

In implicit argument assignment, there is no way to express state assignment.

![](images/Symbol%20Language%20(2004).327.jpeg)

If it were to become a connection between symbols, like implicit line assignments, it would definitely not behave the same as a line.

![](images/Symbol%20Language%20(2004).328.jpeg)

*Implicit assignments*

De assignment calls gedragen zich niet normaal, want consult van de argumenten van __A__ veroorzaken geen executie. Een soort passieve parameter consult vind plaats door de assignment calls, in het proloog van __A__. Bedenk wel: het zijn systeeem procedures: niet normaal.

![](images/Symbol%20Language%20(2004).328.jpeg)![](images/Symbol%20Language%20(2004).329.jpeg)

De calls naar system procedures gedragen zich anders dan gewone calls. Ze vinden namelijk hier plaats in het proloog van de executie. Je ziet dit wèl in de text code, maar hoe zie je in diagram code of een systeem procedure apart wordt aangeroepen of in de context van een andere functie aanroep?

Hypothese: als je bij systeem procedure aanroep een parameter betrekt in een diepere executie, dan zit het in het proloog of epiloog. Zit de parameter in de huidige of hogere executie, of is er helemaal geen parameter bij betrokken, dan wordt de systeem procedure call normaal uitgevoerd. En veroorzaakt geen executie van de sub executor.

Niet het een executor, anders verwar je het met een aparte executie! Een system procedure triggert geen executor:

![](images/Symbol%20Language%20(2004).330.jpeg)

\* dit zou A triggeren als het niet een line van een system procedure call was.

Assignmet procedures = system procedure, eerste argument is het __This__ argument.

![](images/Symbol%20Language%20(2004).331.jpeg)

\* 2 consults, 1 execution. 1 executor zou er eigenlijk moeten zijn om 1 keer uitgevoerd te worden per ... definitie aanroep (afgezien van jumps) (? Hoe zit het daar dan precies mee)

Dus implicit call moet niet bestaan bij het referen naar diamond members. Dus dan heb je ook niet het probleem dat *assignment calls* speciaal geplaatst moeten worden in het proloog en epiloog: consult van diamond members vind *altijd* plaats in proloog of epiloog!

Oh jawel! Consult vind gewoonlijk altijd plaats in epiloog, maar bij assignment van argumenten consulteerd system procedure de argument in *proloog*.

![](images/Symbol%20Language%20(2004).332.jpeg)

![](images/Symbol%20Language%20(2004).333.jpeg)

The last picture is an acceptable substitute for implicit state assignment. It is actually explicit state assignment, but it looks like a real connection between A and B. A rule though: state assignment takes two arguments: destination = source. In the notation on the left you have to follow the direciton of the line you’d get between A and B if you ignore the call thing in between to find out which is the first argumetn and which is the second. In text code it goed from  lieft to right. In the diagram It goes from ...<>. B is destination A is source. I mean B is the one that gets the line. B is source of line, Asbut destination of assignment. 

#### Argument Access Summary

##### Argument Access

- Writing parameters before execution
    - Assignment: lines or state
    - Creation
    - Possibly call members of an argument
- Reading parameters after execution
    - Reading line targets (direct, final or intermediate)
    - Reading state
- Access during execution
    - By owner
    - By child executions (~ is this the proper place for this?)
        - The callees of a diamond can access the caller's members if given references to them

##### In, Out and Thru

- Using reference parameters for in, out and thru (hard to control whether it’s in out or thru: you just use the object)
- Using State as In, Out and Thru
- Using a parameter’s line targets as Out
    - Comparison with Com regarding returning object references.
        - Persisting object reference (harder, is hardly done anyway. Or is it? Consider passing the returned object to another procedure)
        - Using the procedure parameter as object reference directly
- Procedure reference too
- If example

- Access control State Get and State Set
- ... access control Object Get and Object Set, etcetera

### Brainstorm

#### Other

Creation and state read and write only apply to object parameters, not to parameters that are procedures.

#### Other: Explore This Situation Another Time

![](images/Symbol%20Language%20(2004).334.jpeg)

The situation above can only exist right after a call. If you want to 

< A problem: you get returned an object reference. You lead a line to it. Then the procedure returns. Line target gone. If you want to link to its object, you might want to link to its __Target Object__. But, shit, in Com, if you link to an object, it stays in memory wether the original reference holder releases or not. In Symbol, when the target object is destroyed (released) then the object is destroyed. That’s because one symbol represents the object for real. If you want a object to destroy when reference count is 0, then you have to emulate it in Symbol by creating an object symbol that represents the object. References represent references to it. The object will destroy itself if all references to it are released. It’s just a different deal in Symbol. It just is. It’s not like it’s any worse. Line methodology has too many advantages in relation to Com, to hate it for not being like Com. >

So... To do the com way, you DO have to copy the final object target.

But this still doesn’t cover the situation above

#### Other: Explore these two situations later

- Establishing permanent links to arguments. Them being annulled when the call ends.
- With the definition of that, will a more flexible procedure interface methodology be possible?

#### Other: use sentence somewhere in book

__References between siblings is uncommon.__
Nothing active can reside directly in an object.

|![](images/Symbol%20Language%20(2004).335.jpeg)|<p>__Unconditional jump = Call to sibling active clause__</p><p></p><p>If you are familiar with the term *unconditional jump*, them this is the equivalent of that in Symbol.</p><p>Can only take place directly inside a procedure.</p><p></p>|
| - | - |

#### Other: Explore Later

__*Moet ik het ook vanuit deze invalshoek uitleggen?*__

Object symbols may be tied to one another with any line type without restrictions.

Procedure lines have more restrictions and only regarding procedure calls. There are restrictions on pointing to a call and there are restrictions on where a call line points to. In other words: restrictions on *call lines* and on *lines to calls*.

#### Other

__*Different Wording, Not important, though*__

In an explicit call you always see the the call displayed as a separate diamond. If the call is made, the call is like a created object. After the call it is destroyed. When the call is created, you can reference its contents from anywhere without causing another call.

#### Other: Might contain a good text for justification of a diamond symbol rather than a call line

__This IS the text that lead me to wanting a diamond symbol instead of a call line.__

< Why on earth not, actually? Ok, you can’t do it in other languages, but why on earth can’t you do it here. Oh. When you reference a call, it makes the call line function as a reference line rather than a call line. If you want this to be different, a reference to call would become a call, which is not something you want to happen in your system. The reference target would get control over if the source will be a reference or if the source will execute. The source would have no say in that. Unacceptable. So a candidate for an alternative rule for A Call Can’t be Called or Referenced is: if you reference a call, its call line is treated as a reference line.

If you call the reference to a call... 

Een call line is eigenlijk een reference line, maar als de parent square execute, dan execute ook de call. Hmmm... het is bijna of het allemaal reference lines zijn en sommige squares executen nou eenmaal. Shit! Dat is ook zo! Clauses moeten ook kunnen executen en ik zeg nu dat iets alleen execute als het een call line heeft!!! Hmmm... shit, een call is een tag, niet een line!!!!!!!!!!!!

Een call een aparte line maken is net zo iets als een triangle een aparte line maken. Hetzelfde mankement. Dan lijkt het logisch, dat een call een apart symbool krijgt, niet een aparte line. Shit. Welk symbool. >

#### àElsewhere

__*Procedure Interface Restrictions*__

<>

A procedure has an interface too, consisting of all public contents of the procedude: public objects (in, out or thru) and public procedures (clauses, calls and references), which can also be individually referenced and called.

The interface source for a procedure can not be an object symbol. Also: a procedure can not have multiple interfaces. The effect of allowing these things can be imagined, but the usefulness of these structural possibilties is slim, while it would add a lot more rules to the Symbol Language.

For the time being, triangles can reside in a procedure, but only for the purpose of grouping procedure members. You can’t give these triangle any lines, because that would suggest that the procedure adopts all characteristics of an object.

The procedure has no interface genericity. < A word not introduced yet here. > < You can’t redirect the interface of a triangle inside a procedure either, because this would suggest that a procedure gets object characteristics.  This is a restriction of a triangle directly inside a procedure symbol. >

< I think I’m totally nervous about public procedure clauses. And that’s why I forbid interface redirection for triangles in procedures here. I should allow it. The only thing disallowed is interface genericity, because that would suggest that a triangle in a procedure can point to a procedure symbol.

Hmmm... dang. >

< A lot isn’t right in what I just said there >

< The rules I will suggest in this section can change the Procedure Basics : Procedure Interface section. >

### Events

<>

<< Is not a representation! Also: empty overridable members can also serve as events. But how would they have multiple sinks then? Would an event be a special representation of an overridable procedure and would putting them in a single interface be no more than putting all originally empty overridable procedures in a single interface? ... heck, this is material >>

Events are a means for an object to call the container. The object defines an interface that the parent should support if it wants to receive the event calls of its child. The event interface parent has to make the interface implementation accessible by its child by setting an object sink of the child.

For this purpose you can choose to hide empty members of the implementation. You can also exclude any member of an event interface.

The problem with events was that there are two ways: overriding and assigning an event sink object that supports an interface that the event source defines.

#### From Another Place

There *are* techniques for a child to communicate with its parent. There are two similar ways: a child contains a reference to the parent’s procedure, a child contains a reference to the parent’s object. The child then has to define the interface of the object or procedure to reference. The child must also accept that the object reference might not point to an existing object. These techniques will be covered again lateron.

|<p>![](images/Symbol%20Language%20(2004).336.png)</p><p>*Reference to parent procedure with an interface defined by the child.*</p>|<p>![](images/Symbol%20Language%20(2004).337.png)</p><p>*Calling procedures of a reference to a parent object with an interface that the child defines.*</p>|
| :-: | :-: |
|<p></p><p>*The dashed reference lines in these pictures could also have been notated solid.*</p>|

#### Nog

Er is naast referentie naar procedure en referentie naar object nog een manier voor Events. Je moet namelijk ‘multi-cast’ events mogelijk maken en daar vereist een collection van event sinks die allemaal simulataan aangeroepen worden.. work it out


Execution Control
-----------------

< A procedure’s calling one of its own clauses, is an unconditional jump >

< Cover text code entirely, right inside the story. Oh, yeah, should I? Or should I cover it in the Text Code chapter? >

### Basic Language Execution Control

To explain execution control in Symbol I will first introduce examples of execution control in the Basic programming language.

```vb
If X Then A Else B
```

This is called an If statement. If X returns True then A is called, else X returns False and B is called.

```vb
Select Case X
    Case 0: A
    Case 1: B
    Case 2: C
End Select
```

This is called a Select statement. If X equals 0 then A is called. If X equals 1 then B is called. If X equals 2 then C is called. This is actually shorthand for a whole bunch of Ifs, but quite handy.

```vb
For I = 0 To 5
    A(I)
Next
```

This is called a For loop. A(I) is executed 6 times. The first time I = 0, the second time I = 1, the third time I = 2 and so on until I is 5. In this example I is used as a parameter to the procedure A.

```vb
  I = 0
Do While I < 6
    A(I)
    I = I + 1
Loop
```

The same happens here as in the For loop, but it’s a different notation that allows more flexible control of the repetition. First 0 is assigned as the initial value of I. Then there will be looped while I < 6. If I becomes greater than or equal to 6 then the repetition ends. In the repetitions A(I) is called, after which I is incremented.

The blue parts in the code above are called the *clauses* of the control statements. Those clauses are the code whose execution is considered controlled. They are executed depending on the results of *expressions* and *assignments*, marked with red.

The start of the control statement and the end and whatever’s in between is considered the control statement.

### Execution Control Procedures

Execution control statements are special procedures. They are given one or more references to other procedures, the execution of which is controlled. These referenced procedures are the clauses of the control statement and also the expressions and assignments controlling their execution. The execution control procedure decides when or if any of these referenced procedures are called and how many times. How the execution control procedure will call its referenced procedures, is dependent on what the referenced procedures will do.

### Selection and Repetition

The execution control mentioned till now is also called conditional jumping. There are two general forms of conditional jumping: selection and repetition. Selection selects one thing to execute out of several or whether to execute something at all depending on a condition. Repetition repeats a procedure a number of times until a condition is met. In the repeated procedure actions can be taken that affect this condition. Select and If statements are selection. For and Do statements are repetition. Symbol defines but two procedures: Selection and Repetition. Depending on how the procedure is used it functions as an If, Select, For or Do and depending on that, appropriate names are notated with calls to the execution control procedures.

### Selection

<< Sub sectioning. >>

<< That shorthand: what if the actual reference target is two capsules up? >>

This section apart from covering the selection execution control procedure also explains a lot about execution control in general, not just selection, specifically about clauses.

Select and If statements are both accomplished by calling the Selection execution control procedure. The difference between an If and a Select is that a Select first defines the beginning of the expression to evaluate and then a list of endings for the expression. Each beginning-ending combination is treated as a separate If.

The Selection execution control procedure takes 4 kinds of procedure references:

```vb
Select
If
Then
Else
```

I call all of these procedure references *clauses*. Not all clauses have to be filled in.

If the Select clause isn’t filled in then there’s only one If clause, one Then clause and one Else clause:

```vb
If X Then A Else B
```

X, A and B are the clauses, which are separate embedded procedures. X is the If clause. A is the Then clause. B is the Else clause. The If clause procedure returns a condition that is either True or False. If it is True then the Then clause is called, if it is False then the Else clause is called.

The red clauses can be seen as the cause of the selection and the blue clauses as the result of the selection.

If you *do* fill in the Select clause then there can be multiple If, Then and Else clauses. 

```vb
Select X
    If = 0 Then A Else B
    If = 1 Then C
    If = 2 Then D
    Else E
End Select
```

Each If clause is accompanied by its own Then and Else clause. The Else clause doesn’t have to be filled in. Above, only the If that has an Else clause is the first one.

The Select clause is also accompanied by its own Else, which is executed if none of the Select statement’s Ifs returns True.

The Select clause represents the beginning of the If clauses. It can be any beginning of an expression:

```vb
Select X – 2 >
    If 0 Then A Else B
    If 1 Then C
    If 2 Then D
    Else E
End Select
```

The resulting expression of the first If would be X – 2 > 0.

Symbol text code allows various representations of Selection execution control, but the notation above uses each clause’s distinctive name. An alternate notation would be as follows:

```vb
Select X – 2 >
    Case 0: A Else B
    Case 1: C
    Case 2: D
    Case Else: E
End Select
```

This notation is used when using the Select clause. This makes it easier to distinct If and Select statements. In the Select notation the If clauses become Case clauses and the Then clauses become ‘:’ clauses. The joint Else clause becomes the Case Else clause. An additional thing about the Select notation is that you can leave out = signs in certain cases:

An alternate notation for:

```vb
Select Y
    Case = 0: A
    Case = 1: B
End Select
```

is:

```vb
Select Y
    Case 0: A
    Case 1: B
End Select
```

The method is that where appropriate an = sign is put between the Select clause and the Case clause.

In diagram notation, the Selection procedure with all its clauses looks like this:

![](images/Symbol%20Language%20(2004).338.png)

The amount of If groups can vary. I’ve notated three of them in the diagram above.

All clauses are procedure references provided to the selection procedure as parameters when you call it. For that, the diagram for a call to the Selection procedure would look like this:

![](images/Symbol%20Language%20(2004).339.png)

In text code:

```vb
Select ...
    If ... Then ... Else ...
    If ... Then ... Else ...
    If ... Then ... Else ...
Else
    ...
End If
```

The outer squares are the clauses. The squares in the larger square are the references to those clauses.

Execution control is so common and the notation above is rather complex. The notation above should even require grouping triangles around the If groups. I already left those out, but I will do more to make it look clearer. A simplified notation for a call to the Selection procedure is regularly used instead:

![](images/Symbol%20Language%20(2004).340.png)

This has the same meaning as the other notation. A square drawn with dashed lines is shorthand for a square with a reference line to outside. The dashed squares are filled in with the contents of the referenced procedure.

|![](images/Symbol%20Language%20(2004).341.png)|<p></p><p>=</p>|![](images/Symbol%20Language%20(2004).342.png)|
| - | - | - |

Even more is done to simplify the notation. Clauses that are not filled in can be hidden. The procedure name ‘Selection’ is also left out. Squares are allowed to be drawn as rectangles. When the Select clause is filled in, alternate clause names are used as explained earlier.

<< Use those rules from this point onward >>

|<p></p><p>If X Then A:</p><p></p><p>![](images/Symbol%20Language%20(2004).343.png)</p>|<p></p><p>If X Then A Else B:</p><p></p><p>![](images/Symbol%20Language%20(2004).344.png)</p>|
| :-: | :-: |
|<p></p><p>If X Then A Else If Y Then B:</p><p></p><p>![](images/Symbol%20Language%20(2004).345.png)</p>|<p></p><p>If X Then A Else If Y Then B Else C:</p><p></p><p>![](images/Symbol%20Language%20(2004).346.png)</p>|
|<p></p><p>                Select X</p><p>                    Case 0: A</p><p>                    Case 1: B</p><p>                End Select</p><p></p><p>:</p><p></p><p>![](images/Symbol%20Language%20(2004).347.png)</p>|<p></p><p>                Select X</p><p>                    Case 0: A</p><p>                    Case 1: B</p><p>                    Case Else: C</p><p>                End Select</p><p></p><p>:</p><p></p><p>![](images/Symbol%20Language%20(2004).348.png)</p>|

You can nest Selection statements as deep as you want.

|<p></p><p>![](images/Symbol%20Language%20(2004).349.png)</p>|<p></p><p></p><p>    Select X</p><p>        Case 0</p><p>            Select Y</p><p>                Case 0: A</p><p>                Case 1: B</p><p>                Case 2: C</p><p>            End Select</p><p>        Case 1</p><p>            B</p><p>        Case Else</p><p>            If Y = 2 Then D</p><p>    End Select</p>|
| - | - |

Math language (as well as text code) integrates into Symbol. When using execution selection this is very handy. Let’s take the following text code example:

```vb
If X > 3 And X < 5 Then Y = Y + X
```

Integrating math language, you can draw the following diagram:

<< Picture: almost the same as text code. Clauses are put in dashed rectangles. >>

When you don’t use math language it will look as follows:

<< Picture: See paper. >>

The = operator is an operator from text code language, not math language.

### Repetition

< Yellow doesn’t work on white paper >

Now I’ve explained a lot about clauses in Selection, I can easily explain Repetition.

Repetition has the following clauses:

```vb
For '= (Initialization)
Till
Step
Loop
```

<< Picture 33: Diagram of Repetition execution control procedure with all its clauses>>

Of each clause there can be only one, but not all need to be filled in.

I will express the two Basic repetition statements in diagram code. The colors denote the different clauses of the Repetition statement.

Text Code:

```vb
For I = 0 To 6 Step 2
    A
    B
Next
```

Diagram Code:

<< Picture 34: Square called For with four other squares: I, = 0, To 5, A B. Use the same colors and pick some nicer ones man>>

Text Code:

```vb
I = 0
Do While I <= 5
    A
    B
    I += 2
Loop
```

< >

That was the Basic like notation. Symbol usually uses the For notation:

```vb
For I = 0 Till <= 5 Step I += 2
    A
    B
Next
```

The Step clause is basically no more than the second part of the loop clause. It’s just simply executed as the second part of the loop. However, it allows a more abstract notation. When you start with a binary operator then the For clause is used as the first operand. If you only supply a term, then it is added to the For clause.

Oops the For clause isn’t a procedure anymore. It’s an object whose state is gotten and set. The Step clause can be a procedure reference, but can also be an object reference with state get and set. It’s overloaded to support

< >

Diagram Code:

<< Picture 35: Square called Do with 5 other squares: I, = 0, <= 5, ++, A B. >>

The algebra you see in the diagrams above (for instance <=5) are actually calls to algebraic procedures. The algebraic language can be integrated like that in the diagram code. The integration of other languages into diagram code is discussed in a separate chapter. Here I’ve only used it to show how using the execution control statements can look in practice.

<< Algebra covered in Math, Language embedding in a Code Language chapter >>

<< Tell not to worry about the algebraic operations and assignment.  Algebra operations and assignment are themselves procedures that can be called which are explained later. >>

<< Examples of simpler loops, in which >>

### Clauses: Embedded Procedures

The clauses discussed above are actually embedded procedures. Embedded procedures are often referred to with the word clause. They have the special characteristic that they can access the members of the procedure they’re embedded in.

<< Picture 36 >>

All clauses have access to the objects in their descendant clauses and to the objects in their embedding procedure.

<< Picture 37 >>

The reverse is not true: an embedding procedure can not access an object in a clause unless the object is public.

<< Picture 38: non public clause member, not referenced by the embedding procedure >>

And even when it’s public then it has to be written right before entering the clause, just like a procedure call.

<< Picture 39: public clause member referenced by the embedding procedure just before entrance >>

You can recognize an embedded procedure by the fact that they’re not calls, nor procedure references. So they (usually) have no lines:

<< picture 40: embedded procedures. Mark the ones that are clauses with a color >>

Perhaps jumping will change that and the clauses will get lines, but no lines that end up outside the embedding procedure.

<< Picture 41: clause that does have a line because of a jump to it >>

<< It’s like when something’s a clause, it ignores its parent’s borders. Conversely, the contents of a block are by default only accessible within that block. >>

### Unconditional Jumps

Returns and Jumps

#### Unconditional Jumps

<<

```vb
1    Call A
2    Call B
3    Jump 5
4    Call C
5    Call D
```

Line 3 will make a jump to line 5. Line 4 will be skipped.

...

Returns makes you able to exit procedures, a single repetition, a whole repetition loop, a select statement, etcetera.

A jump ...

Unconditional jumps are usually just regular calls to other procedures. Another special unconditional jump is immediately ending the procedure or the block or ending the current procedure and the next one and so on.

You could speak of conditional calls, actually. 

\>>

<<
Unconditional jumps are usually calls to other procedures indendent of a boolean state: regular calls. Another special unconditional jump is immediately ending the procedure (returning or ending a for loop) or ending the current procedure and the next one and so on (ending a nested loop and also the loop its nested in)
\>>

```vb
Select X – 2 >
    If 0 Then A Else B
    If 1 Then C
    If 2 Then D
    Else E
End If
```

Breaking, because each Case group is evaluated now.

### Text Code Blathering < >

##### Conditional Jumps

Two forms of conditional jumping are generally used: selection and iteration. Selections will do either one thing or the other depending on a Boolean state. Iterations will repeat something depending on a Boolean state.

###### Selection

Selection is performed with If and Select statements.

####### If

With an If you can choose wether or not to do something depending on a Boolean state:

```vb
If X Then A
If X returns True then A is called
```

With An If you can also choose to do either one thing or the other:

```vb
If X Then A Else B
If X returns True then A is called. IF X returns False then B is called.
```

An alternative notation of the If above is:

```vb
If X Then
    A
Else
    B
End If
```

You can nest Ifs:

```vb
If X Then
    A
Else 
    If Y Then 
        B
    Else
        C
    End If
End If
```

You can also use Else If:

```vb
  If X Then
      A
  Else If Y Then 
      B
  Else
      C
  End If
```

Or in an alternate notation:

```vb
If X Then A Else If Y Then B Else C
```

You can use alternatives for the Then keyword. You can leave it out or you can use a comma:

```vb
If X, A Else If Y, B Else C
```

```vb
If X
    A
Else
    B
Else If C
    D
End If
```

####### Select

Selects let you combine a large Else If construction to an easier notation:

```vb
If X = 0
    A
Else If X = 1
    B
Else If X = 3
    C
Else If X = Y + 1
    D
End If
```

The three conditions above all have the same beginning:

```vb
X = 0
X = 1
X = 3
X = Y + 1
```

They all begin with X = .

The Select statement lets you take advantage of that to make the notation easier:

```vb
Select Case X =
    Case 0
        A
    Case 1
        B
    Case 2
        C
    Case Y + 1 
        D
End Select
```

You can also use the comma to use the same clause for multiple conditions:

```vb
Select Case X =
    Case 0
        A
    Case 1
        B
    Case 2
        C
    Case Y + 1, 4
        D
End Select
```

You can use the : to avoid using so many lines:

```vb
Select Case X =
    Case 0: A
    Case 1: B
    Case 2: C
    Case Y + 1, 4: D
End Select
```

<< Maybe I should just first explain the concept and then introduce all them various notations. Mayve this text notation should be explained totally separately anyway. I only needed it to give an example of an If here, man. >>

A Basic Select statement:

```vb
Select Case X
    Case 0: A
    Case 1: B
    Case 2: C
End Select
```

Is notated in Symbol text code as:

```vb
If X
    = 0 Then A
    = 1 Then B
    = 2 Then C
End If
```

Or:?

```vb
Select X
    If = 0 Then A
    If = 1 Then B
    If = 2 Then C
End If
```

Or:?

```vb
Select X
    If = 0: A
    If = 1: B
    If = 2: C
End If
```

Or:?

```vb
Select X
    If = 0, A
    If = 1, B
    If = 2, C
End If
```

Or:?

```vb
If X
    = 0, A
    = 1, B
    = 2, C
End If
```

###### Iteration

```vb
For i = 0 To 10
    ...
Next

For i = 0 To 10 Step 2
    ...
Next

For i = 0 Till = 8 Step + 1
    ...
Next

For i = 0 Till > 8 Step + 1
    ...
Next

For i = 0 Till > 8 Step i++

For i < 3

For Till i < 3 

i = 0. Repeat As i >= 5, Step i++.
```

A comma can be used to separate

Maybe for should be called repeat

### Brainstorm

Maybe the procedure references of execution control procedures need to have a certain procedure interface.

About the execution of non execution controlled calls. Some calls must be made before others because the result of one call is used in another call. That defines (some of) the order of precedence of calls.

The order of the calls in a procedure is (part) determined by dependence, independent of the order the programmer gives.

The programmer can change the order of things that are arbitrarily called and insert calls into the obligatory order or calls, but if it’s not so relevant, the programmer doesn’t even provide the call order. Most of the time it is not that relevant. (or is it, to what extent can I not see the requirement of the order of calls, even when its order is very important?

If a procedure takes a reference to a clause then you can do this notation:

<< Square with loose squares and another square with squares pointing at those loose squares >>

Defining the contents of the procedure references right within the

#### Execution Control Controls which call is made next

<<
Most of what’s done inside a procedure is calling other procedures.

Apart from executing a sequence of calls linearly, you can alter the course of the calls using execution control.

A clause is like a procedure itself. For that you can see execution control as selecting which procedure will be called next. Or actually which clause will be called next.

First explain that a control statement controls which call is made next. They are responsible for the arbitrarity in execution. Otherwise there would be just one way a program can execute from start to beginning and that’s that, but execution control sees to it that there is variation in the execution of a program.

In one compiler optimization technique it is these execution control statements that are analysed. Execution control statements make execution variable and this compiler technique analyses how variable that actually is. Maybe the execution control will not be reached with too many different values, let’s say, two values. In that case you might consider removing the variation in execution by making two procedures one of which is one situation of the execution control statement and the other one is the other situation of the execution control statement. At calls to the execution control statement or indirect calls to it, you insert the variation that applies right there.
\>>

##### Nice Example

```vb
For I = 0 to 4
    A(I)
    B(I + 1)
    If I <> 0 Then 
      C
    Else
        D
    End If
Next
```

##### Execution control is call control

This means that in Symbol the definition of execution control is selecting what procedure to call next depending on a Boolean state.

You could speak of conditional calls, actually. 

Calls can be managed by execution control. Execution control manages the regular order of the calls *and* can alter the regular traversal of calls depending on a Boolean result (If, Select, For, Do). The Boolean result can spring from any combination of forms of algebra that in the end returns a Boolean result. Comparison algebra and Boolean algebra return Boolean results.

#### àExecution Control

But... if you pass a clause reference to an execution control procedure the execution control CAN call the clause, but only in the context of the procedure instance that called the execution control procedure!

Execution control procedures must call clauses in the context of a *specific call* to the clause’s procedure definition.


Access Ways
-----------

< Do neighbor access and child access protect the independence of types? As a substitute for the old, false rule: ‘Can’t call upward in the ancestry’? >

There’s several ways to access a procedure. The most common way is for procedure’s of the same object to call upon eachother. The second most common way is for a parent to access a child’s procedures. A global object is accessible from anywhere within the globality and there are more ways. I will discuss these different ways of access one by one in this section.

### Neighbor Access

< Discuss procedures within the same object accessing eachother >

### Child Access

The normal way of accessing an object is *child access*: an object can only access its what’s inside of it: its ancestors.

![](images/Symbol%20Language%20(2004).350.png)

< Dang. This is not right, I need to make a call from a procedure. The line above is a reference line. >

An access always takes place in a procedure call. In this picture Parent is accessing Child.

You can’t all anything higher in the encapsulation hierarchy, so an object can’t access anything outside the object. If it is to access anything outside the object, it needs to contain a reference to something outside the object.i

![](images/Symbol%20Language%20(2004).351.png)

The object is then accessing this *reference*, which is inside the object. The reference just happens to resolve in something outside the object, but the parent is still accessing something inside itself.

### Global Access

< Nice sentence:
    Globality makes all direct children accessible to all ancestors
\>

There’s also a way to make objects accessible not only to parents, but accessible from anywhere. This makes the accessed objects global.

A special symbol is used: a pentagon.

![](images/Symbol%20Language%20(2004).352.png)

Anything directly inside the pentagon is accessible from *anywhere*. So the (public) direct children of the pentagon are global:

![](images/Symbol%20Language%20(2004).353.png)

*The blue symbols are accessible from anywhere inside the pentagon.*

A pentagon and all its contents are also called a *globality*.

It’s like any object inside a globality has a reference to the globality object:

![](images/Symbol%20Language%20(2004).354.png)

These references don’t really exist, though. Everything global is just reachable inside every object inside a globality.

![](images/Symbol%20Language%20(2004).355.png)

In this the solid line *can* be a call, because it’s a reference to something global.

A globality can also be viewed as being a module, or software component. It is a way to order code into components. Globalities can be embedded just like as objects:

![](images/Symbol%20Language%20(2004).356.png)

In fact, a globality symbol is an object symbol too. It works as a triangle: you can access things in the globality directly, but also by qualifying it with the globality identifier, but it has the special side effect that anything it directly contains can be directly accessed from anywhere.

When you want one globality to use another, you make a reference to the other globality:

![](images/Symbol%20Language%20(2004).357.png)

The child globality can then be accessed like a circle or a triangle, but refers to an existing instance of the globality (software component). Since the globality is a direct child of another globality, anything in the contained globality is just as global as anything in the parent globality. However, if you make the child globality private, it’s not accessible outside the parent globality. It is accessible as global inside the parent globality, though.

In other languages, globalities usually contain a large amount of code, because it’s not easy to handle many globalities. In symbol it’s easier to manage globalities and whenever you need the effect of having a small, local, globality (or software component), you can easily use a globality.

This is also an invitation to making a more refined division in software components. You can not only easily work with a division in more components. You can also embed software components. And you can refinedly control referencing existing instances of software components.

The child globality in the picture above can only access things global inside itself. It can not access the global things of its parent globality.

#### Pentagons not Exchangable with Triangles and Circles

A pentagon is not exchangable with triangles and circles as much as triangles and circles are exchangable. Global has the side effect that things become accessible where otherwise inaccessible. If you suddenly replace the pentagon with a circle or triangle it would mean that things formerly global are no longer global and all sorts of accesses in the globality object are suddenly invalid. For that a pentagon stays a pentagon and a reference to it can only be a pentagon itself.

#### Extra Indication

There are two common ways to extra denote that you’re referencing something global.

Put a multiply peeled pentagon around the call:

![](images/Symbol%20Language%20(2004).358.png)

This pentagon reference doesn’t really exist, though.

You can also put a multiply peeled pentagon in the direct parent object and reference this multiply peeled pentagon, rather than the global symbol directly:

![](images/Symbol%20Language%20(2004).359.png)

This multiply peeled pentagon doesn’t exist either.

### Interface Access

The separate interfaces of an object:

![](images/Symbol%20Language%20(2004).360.png)

can be accessed through a reference to the triangle, just like you would access a circle:

![](images/Symbol%20Language%20(2004).361.png)

The special thing about a triangle, though is that its members are also directly accessible through its parent. When referencing the circle, you can access the triangle’s members as if the triangle capsules weren’t even there.

You can’t see in the picture above if the called square is referenced through the circle or through the triangle. If you want to indicate that it’s accessed through the circle, you can put an access symbol with the circle. If you want to indicate that it’s accessed through the triangle, you put an access symbol with the triangle, or with both the circle and the triangle.

|<p>![](images/Symbol%20Language%20(2004).362.png)</p><p></p><p>*Accessed through the Circle:*</p><p></p><p>__*Circle . Procedure*__</p>|<p>![](images/Symbol%20Language%20(2004).363.png)</p><p></p><p>*Accessed through <br>the Circle and the Triangle:*</p><p></p><p>__*Circle . Triangle . Procedure*__</p>|<p>![](images/Symbol%20Language%20(2004).364.png)</p><p></p><p>*Also accessed through <br>the Circle and the Triangle:*</p><p></p><p>__*Circle . Triangle . Procedure*__</p>|
| :-: | :-: | :-: |

In text code you can see the difference all the more. I’ve put the text code under the diagrams above.

So its like the borders of triangles can be ignored in inward access. You don’t have to access the triangle in order to access its members.

< This concept could have a place in Genericity. >

### Clause Access

< Nice sentence:

    A procedure makes all direct children accessible to all blocks.

Only is that true? >

Clauses are embedded procedures. In a diagram these are squares contained in other squares that have no lines. Beware that a diagram may not be showing the line, even when it exist.

![](images/Symbol%20Language%20(2004).365.png)

Clauses have access to the contents of all their descendant clauses and the procedure definition they’re in. This means that a clause can directly access its containing definition’s members:

![](images/Symbol%20Language%20(2004).366.png)

and all its encapsulating clauses:

![](images/Symbol%20Language%20(2004).367.png)

But a clause doe not have access to a clause that doesn’t encapsulate it.

![](images/Symbol%20Language%20(2004).368.png)

So its like the borders of clauses can be ignored in outward access.

### Globalities, Interfaces and Clauses

So usually only parents can access their ancestor’s things.

Globalities, interface implentations and clauses make exceptions on those rules.

The public ancestors of a globality are accessible from anywhere within the globality, the borders of triangles can be ignored and a clause can directly access anything in its descendant clauses and its procedure definition.

### Brainstorm

#### àAccess Ways

Clause members can  access the members of its ancestor procedure symbols. 


Procedure Resolution
--------------------

The following methods let a parent mess with the procedures of a child:

- Overriding
- Exclusion
- Overloading
- Shadowing
- Merging

Overloading, shadowing and merging are about which procedure to call if several procedures have the same name. In text code you couldn’t easily see which procedure of the bunch is called. In diagram code it is always clearly visible which procedure you’re calling, but if they have the same name, then in text code it is less easy to see. Overloading, shadowing and merging work with this phenomenon.

Overriding and exclusion are techniques equally useful in both diagram code and text code. The others: overloading, merging and shadowing, are mostly useful in text code.

### Overriding

Overriding means that a parent can replace a procedure of its child by another. A child decides whether a procedure of his is overridable or not.

![](images/Symbol%20Language%20(2004).369.png)

This is a type with an overridable procedure B, called by the child. The access symbol on the right means that the Procedure Reference Set is public. Therefore you can make B redirect to a procedure that the parent defines.

![](images/Symbol%20Language%20(2004).370.png)

The parent overrode the overridable procedure B. A call to B will resolve to a call to C instead. You can see that overriding means that the parent gives a child’s procedure a reference line to one of its own procedures.

In the replacement procedure, you can still call the base procedure. That way you can both override procedures of the child or extend them.

![](images/Symbol%20Language%20(2004).370.png)

Overridden procedures are called by the child and that way they’re a means for a child to call a procedure of the parent.

An overridable procedure that is only for communication to the parent is left empty by the child and is only filled in by the parent. This kind of overridable procedure is therefore also called a virtual procedure of the child.

### Exclusion

Exclusion is already covered extensively, but it can also be regarded a procedure resolution technique. A parent can exclude members from a published object or base object.

### Overloading

< Overloaded objects >

< A procedure can also have multiple interfaces by using triangle symbols. This enables the possibility to have multiple parameter configurations for the same procedure. >

< This is an example of how text code can affect the behavior of the diagram. Call line automatically changes when parameters of different types are assigned. Oh, shit, after compilation the text identifiers might not exist anymore. Then it’s gotta become a deep system aspect the overloading, independent of text code. Text code and diagram code would simply be affected by the overloading concept. It should be like this, because of reasons discussed in the language integration chapter. >

Overloading means that you give several procedures the same name, while they have a different interface. This is handy if you wish to make different variations of similar functionality.

The operator procedure + for instance is richly overloaded. Operator + always has two parameters: the two operands. The two operands can be of many different types and each type configuration requires a separate procedure. Which procedure is called is determined by the types of objects assigned to the parameters.

In diagram code you may see the difference between a call to one procedure or the other. In text code, however, as well as in certain abstract views on the diagram the effect is more subtle and you won’t see the difference between a call to one procedure or the other. This is actualy a nice, and wanted effect.

Given is the text code below:

```
Object Type 1
    Integer X
    Double Y
    Float Z
    Procedure Procedure 1
        X + Y
        X + Z
    End Procedure
End Object
```

The following would be the diagram code without mentioning the types of objects nor procedure calls:

![](images/Symbol%20Language%20(2004).371.png)

The outer circle is Type 1. It declars the three basic object X, Y and Z. It also contains the procedure Procedure 1, in which are performed two plus operations to which references to the basic objects are passed.

However, when you do mention the types of objects and procedure calls, you see that two different procedures are called.

![](images/Symbol%20Language%20(2004).372.png)

When you display the called procedures the subtlety is gone, but in this abstraction of the diagram you’ve simply *chosen* to see the difference:

![](images/Symbol%20Language%20(2004).373.png)

All three diagrams above describe the same code, only in one diagram some parts are left out and some are visible while in another diagram other things are left out or visible. Abstract Symbol is covered in detail in another chapter <>.

The + procedure has a special notation: an operator notation, which is a customized representation of a procedure call and its parameters. This method is discussed in the ‘Text Code’ and ‘Language Integration’ chapters.

The names of procedures that overload eachother are always equal. The configuration of a procedure’s public objects determines which procedure is called. This configuration of public object includes: the object count, object types and object names.

Usually the count and types of parameters are varied, but if two overloaded procedures only differ in parameter *names*, in text code it is required to *name* the object when you call the procedure.

<< Picture: text code and diagram code with overloaded procedures that only differ in parameter names. >>

When you change a parameter to an object of a different type, then the call line of the call will automatically point to another procedure.

<< I need pictures with that. >>

### Shadowing

< Can shadowing change so that the target of a line  is changed at run time automatically because of shadowing? If that’s so then shadowing is a way in which text code affects the behavior of the diagram. Same shit problem after compilation no text identifiers anymore >

Shadowing is handy when you use a triangle: a base type or an extra interface implementation.

![](images/Symbol%20Language%20(2004).374.png)

The two lines are calls to the triangle’s members.

When you want to use a name that’s already used by the base type, you can shadow it and calls will be made to the shadowing member instead:

![](images/Symbol%20Language%20(2004).375.png)

The difference with overriding is that the base type still calls its own member, not the shadowing member.

![](images/Symbol%20Language%20(2004).376.png)

*I* still calls its own A, while P and anyone else calls P’s A.

A parent can still call the shadowed member, but this would require qualification with the interface name, or the shadowed member will be called:

A

![](images/Symbol%20Language%20(2004).377.png)

I.A

![](images/Symbol%20Language%20(2004).378.png)

I.A is inaccessible outside the parent, for the parent has chosen to shadow it.

A member is automatically shadowed if the parent of a triangle defines a procedure with exactly the same characteristics as the triangle’s procedure. The parent can freely shadow any member of the child.

### Merging

When a procedure has the same name and configuration of public members then in text code there is no way to distinguish calls to either procedure. What happens automatically is that the *‘nearest’* member *shadows* the member *further* away.

![](images/Symbol%20Language%20(2004).379.png)

A second option when you can’t distinct a call to one procedure from a call to the other is simply for *both* procedures to be called. This is called merging the two procedures and in that case the call will resolve in calling *both* procedures. If you want to address a specific procedure, you could qualify the call with the name of the container of the procedure, if that would make a difference. In diagram code you can see the two procedures as separate squares and you *can* see the difference between a call to procedure A and a call to procedure B.

<< Picture 27: of text code call to merged procedure with next to it the diagram code >>

<< Picture 28: of text code with qualifications that call a specific procedure >>

Merging is handy for instance when a symbol contains two interface implementations and each interface implementation contains a member with the same name and public members.

<< Picture of that >>

When the merging procedures reside in *exactly the same container*, they can not be separately called. They are always simultaneously called. In diagram code you might be able to express a call to a specific procedure, but it is forbidden to make such a call, because this would be impossible to express in text code.

<< Picture of that (29): the legal situation and a picture with a red cross through it showing a forbidden way of calling and showing that the call would look the same in text code >>

That ensures that diagram code and text code are exchangable and can be mutually used.

< Merging should be a technique, not embedded in the language. When it’s about calling both procedures of the triangles, you have to shadow those procedures with a procedure that calls both. >


Data & Math
-----------

Data and math in Symbol are actually not part of the language. Data and math are modules written in Symbol Language that provide types and procedures to work with data and math. These modules are described in separate books. At present, it would not be convincing if the full description of a programming language should contain nothing about *strings*, *arrays*, *simple data types* and *mathematical operations*.

Therefore, in this chapter, I give a functional description of basics of the Data and Math modules.

< >


System Aspects
--------------

< I must denote somewhere that lines can be connected so very complexly if sources and targets are reachable from a high ancestor. Say that lines can look orderly, but can also be very complex all the same.>

*System aspects* are always seen as related to a single symbol. Because of that, the term *symbol aspect* can also be used.

*Line aspects* are some of the most important system aspects. The line aspects of an *object symbol* are:

- __Object__
- __Type__
- __Interface__

And those of a *procedure symbol* are:

- __Definition__
- __Interface__

This kind of aspect is redirected by lines. The __Type__ aspect of a symbol, for instance, represents the direct target of the type line.

Another group of aspects is the *target aspects*. The target aspects of an *object symbol* are:

- __Target Object__
- __Target Type__
- __Target Interface__

And those of a *procedure symbol* are:

- __Target Definition__
- __Target Execution__
- __Target Interface__

These are derived from the line aspects. By doing a trace, the target aspects are retrieved.

Another special system aspect is __State__, which stands for the data stored in an object, including the line redirections inside an object, or rather: it’s state. A related system aspect is the __Created__ aspect, which points out if the object a symbol represents is created or not.

- __State__
- __Created__

These are called the *state aspects*. {} The aspects here apply only to object symbols, but there are also state aspects for procedure symbols. {}

There are even more system aspects:

- __Parent__
- __Children__

- __Parent Object__
- __Child Objects__
- __Parent Procedure__
- __Child Procedures__

The __Parent__ and __Children__ system aspects can tell you all about the encapsulation structure. Because these aspects again return symbols, you can recursively track down the whole surrounding encapsulation structure. They are called the *encapsulation aspects* or *ancestry aspects* of a symbol. The __Parent Object__ and __Child Objects__ system aspects return the object ancestry, kind of like ignoring procedure capsules. The __Parent Procedure__ and __Child Procedures__ aspects return the encapsulation only looking at procedure capsules.

The __Shape__ system aspect returns the shape of a symbol.

- __Shape__

There are even more system aspects, because system aspects return all information about the symbol, thus all information about the system. I won’t mention the other aspects yet, for they are about concepts not yet explained. Nevertheless, the ones mentioned here are the most important ones.

#### System Procedures

*System procedures*, or *system aspect procedures*, are procedures with which you get and set aspects of a symbol. Every symbol has system procedures. The line aspects of an object symbol are represented by the following procedures:

- __Object Get__
- __Object Set__
- __Type Get__
- __Type Set__
- __Interface Get__
- __Interface Set__

And those of a procedure symbol are:

- __Definition Get__
- __Definition Set__
- __Interface Get__
- __Interface Set__

With these system procedures you can get and set the line targets of symbols. These system procedures return or take the __Symbol Id__ of the line target: a number that uniquely identifies a symbol.

The __Object Get__ and __Object Set__ procedures together can also be called the __Object__ system aspect or the __Object__ aspect. The same goes for the other aspect procedures.

All system aspects are represented by procedures. Some aspects can only be obtained, not set.

The *target aspects* can only be obtained, because they are derived from the lines of symbols. The line aspects of symbols can be controlled, but the target aspects can not be directly controlled. So the target aspect procedures of object symbols are:

- __Target Object__
- __Target Type__
- __Target Interface__

And those of procedure symbols are:

- __Target Definition__
- __Target Execution__
- __Target Interface__

The __State__ symbol aspect can be obtained and assigned too.

- __State Get__
- __State Set__

The state is obtained to be immediately assigned to another object. That way the values and line targets of one object are copied to another object, giving both objects the same state.

The __Created__ symbol aspect is primarily only *obtained*, not set. __Created__ can be controlled though, by calling te __Create__ and __Destroy__ system procedures.

- __Created Get__
- __Created Set__
- __Create__
- __Destroy__

You *can* set the __Created__ aspect, which is equivalent to calling the __Create__ or __Destroy__ procedures.

__Created = True  ≡  Create__
__Created = False  ≡  Destroy__

But I prefer using __Create__ and __Destroy__ in most cases.

Ancestry aspects can only be obtained, not set. The ancestry structure *can* change, as type and interface targets change, but the ancestry can not be directly set, except at design time. So the ancestry procedures are:

- __Parent__
- __Children__

- __Parent Object__
- __Child Object__
- __Parent Procedure__
- __Child Procedures__

The __Children__ aspect is actually an array that returns multiple symbols. More on arrays later.

The shape of a symbol can only be set at design time, not at run time, so you can only obtain the __Shape__ aspect, not set it.

- __Shape__

The last one I’ll mention for now is the __Symbol__ system procedure. It actually returns the symbol itself. More specifically: its __Symbol Id__. It can be regarded the most primary of all system procedures.

- __Symbol__

So the system procedures introduced so far are:

Object system procedures:

- __Object Get__
- __Object Set__
- __Type Get__
- __Type Set__
- __Interface Get__
- __Interface Set__

- __Target Object__
- __Target Type__
- __Target Interface__

- __State Get__
- __State Set__

- __Created Get__
- __Created Set__
- __Create__
- __Destroy__

Procedure system procedures:

- __Definition Get__
- __Definition Set__
- __Interface Get__
- __Interface Set__

- __Target Definition__
- __Target Execution__
- __Target Interface__

General system procedures:

- __Symbol__

- __Parent__
- __Children__
- __Parent Object__
- __Child Objects__
- __Parent Procedure__
- __Child Procedures__

- __Shape__

##### The System Interface

The system procedures of a symbol together form the *system interface* of a symbol. It is notated as follows:

|<p>![](images/Symbol%20Language%20(2004).380.jpeg)</p><p>*Object System Interface*</p>|<p>![](images/Symbol%20Language%20(2004).381.jpeg)</p><p>*Procedure System Interface*</p>|
| :-: | :-: |

I’ve left out the system procedures I haven’t yet introduced.

In fact, most of the times you’ll only see part of the system interface: only the procedures that are of interest in the view on the diagram, or only the procedures with which something special is going on, while the other ones behave in a standard way. How they can be special and how they can be standard will be discussed later. So a lot of times the system interface might be shown as follows:

![](images/Symbol%20Language%20(2004).382.jpeg)

The system interface is displayed sort of like an interface, but tied to the edge of the symbol, rather than being contained by the symbol. This is to denote that this interface is *not* *inferior* to the symbol.

The notation of the system interface also looks like you’ve opened up the system and can see its internal wiring.

Notation of the system interface can go together with the regular contents of the symbol.

|<p>![](images/Symbol%20Language%20(2004).383.png)</p><p>*Object Notation Only*</p>|<p>![](images/Symbol%20Language%20(2004).384.png)</p><p>*Simultaneous system interface and object members*</p>|
| :-: | :-: |

Calls to system procedures and object members are intermixed, so you have to be able to see both the system interface and the object members at the same time.

![](images/Symbol%20Language%20(2004).385.png)

*Calls to system interface and to object members*

The system interface encapsulates many triangular objects and procedures. However, those objects and procedures are not the same as normal objects and procedures. The members of the system interface are very primary. they don’t have a system interface themselves and you can’t redirect them with lines.

If you see the system interface as an object, though, you can regard the system interface to have the same type for every object symbol. Procedure symbols would have a different system type. All symbols would derive from this system type then.

#### Get and Set are Inseparable

__Get__ and __Set__ always accompany eachother. That is: there’s no point to *getting* something if you aren’t going to *assign* it to something else. Conversely, you can’t *set* something unless you’ve *gotten* something in the first place.

*Getting* a value is done solely to immediately *assign* it to something else. __Get__ and __Set__ are stuck together with superglue. There is no intermediate state of a value between the __Get__ and the __Set__. There’s no manipulating a *gotten* value before you *set* it to something else.

There are two things you can do with a value: copy it or transform it. If you transform it you always operate on a value directly. Even when you make a temporary copy of the value to operate on, manipulate it and write it back, you’re still directly manipulating the temporary copy. The whole process would be you first __Get__ the original value and immediately __Set__ the temporary copy. Then you manipulate the temporary copy, by calling one of its member or by passing it to a procedure that manipulates it. Then you __Get__ the temporary copy value and immediately __Set__ it to the original object. There *is* no room between __Get__ and __Set__.

The combination of a __Get__ and a __Set__ as such is called an *assignment*.

##### Which Aspects Can be Paired in an Assignment?

So you always need to combine a call to a __Get__ with a call to a __Set__. The __Get__ and __Set__ don’t need to be the same aspect. For instance: you can __Get__ the __Target Object__ of one symbol and use it as the __Type__ for another symbol (__Get__ the __Target Object__, __Set__ the __Type__).

You can always combine aspects that both return a __Symbol Id__. __State__ can only be combined with __State__. The __Created__ aspect can be treated like any __Boolean__ object.

__Symbol Ids__ are stored like an __Integer__ number, but they can not be used as __Integer__ objects. They can only be used among system procedures. You can’t assign an __Integer__ to a aspect returning a symbol and you can’t assign a symbol aspect to an __Integer__ number. So you can’t temporarily store a reference to a symbol inside an __Integer__.

{Is that true? In that case you can’t investigate the surrounding encapsulation and store it anywhere.}

Note that of the aspects introduced, the only ones that can be __Set__ are: line targets, __State__ and the __Created__ aspect.

All you can do with the aspects that can only be gotten, not set, is assigned it to a line target, __State__ or __Created__, or Get it for a special purpose, called __Access__, described below.

##### Assignment Example

I will cover an example here of an assignment, in which one Get and one Set will be called. In this example, one symbol will be assigned as the type of another symbol.

A simple notation for this is:

*[Picture 1]*

The diamond is a call to A’s Type Set. B is the parameter to A’s Type Set.

The textual notation of this is also quite simple:

```
A . Type = B
```

These are actually simplified notations of something far more complex that’s going on.

The common notation for this is quite easy, but 

##### Brainstorm

Ik wil hier eigenlijk heel goed het gebruik van get en set weergeven. Ik geloof dat het nog niet te vroeg is om gedetailleerd in te gaan op het aanroepen van system procedures, voordat je aspect access control en redefinition uitlegt.

Ik moet hier echt (in de toekomst) heel wat voorbeelden geven, ook in diagrammen. Ik zit in m’n hoofd alleen met. Ik kan in m’n hoofd geen volledige strings met assignments visualiseren, omdat daarbij veel met parameters gewerkt wordt en ik heb nog geen goed beeld van parameters.

But actually all system procedures could be globalized with as parameters the object to operate on. You actually already have such global procedures: the procedures of the system type can be used globally. If you use the system type members like global functions you simply use the type in a non-object oriented way. You pass the object to operate on to the procedure via the *this* argument. Using the system type procedures as a system interface for all the ‘symbol objects’ is the common conversion from procedural to object oriented.

#### Get Purposes

< There are also situations in which you want to disallow copying object reference to an argument, but only allow consult of the argument. (that’s access control of system procedures, actually) >

< This is gonna need many pictures. I just don’t draw those system procedure calls very well, yet. I have fear of drawing them >

There can be multiple purposes to Get a value for. You can for instance get one symbol’s __Symbol Id__, to assign to another symbol’s __Type__.

Access, Redirection, Copy

Copy of a symbol id gives you a whole set of purposes < > :

- to Type
- to Interface
- to Object

The distinction has to do with access control. For instance: the symbol get might be public to serve as an object, but private to serve as a type. Or rather, the symbol whose symbol get is private for type<> can not serve as a type.

##### Brainstorm

< And how about Parent get? >

< Maybe if I ask myself the question here, maybe the reader will too, and I have to give a concrete answer to that and to many more things too... >

< I think it’s something for the Get Purposes section >

< I noticed in my type Sigma . Controls . Button Style, I would like to specify separate *procedures* for copying its Style sub object or accessing the members of its Style sub object, not just separated access modifiers. That’s because if I want to access the Style object’s members, I want to return the Button Style object itself. If I want to copy Style property, I want to clone Me and return the clone. Even worse: if I want to assign a button’s Style and the source is a Style object, I can do a normal object assignment of the aValue argument, but if I want to assign a button’s Style and the source is a Button Style object, then I want .. to do something different. Anyway it’s complex >

#### Access Control on System Procedures

#### Variable and Constant

#### Redefining System Procedures

#### Exclusive Establishment

< Lines inside uncreated objects, squares and diamonds out of execution, are not real. They are imaginary and only exist when the object is really created. >

#### Static, Creation and Destruction

< You have to mention here somewhere what the normal kind of static is and that when explaining situations, you are always seeing members in their normal type of static, and the other types of static are not considered. That way in other explanations lateron, I don’t have to add to every conclusion ‘unless it is static’ >

#### State

#### Dimensions

#### Storage of Symbols, Line Targets and Objects

#### Brainstorm

##### Summary of Old Subdivision

That introduction:

- System aspect procedures get system aspects
- They return symbol id's
- State is special.
- Other system aspects that might get system aspect procedures.
- Some aspects can be Set
    - Setting lines
    - Setting State
- Automatic system aspect procedures calls
- Get and Set always accompany eachother
- State assignment
    - Conversion
- Copy, Access and Redirection purposes
    - When do they happen?
    - Every aspects its own collection of get purposes
    - They're there for access control.
- Fill in system aspect procedures yourself
- System procedures don't have system procedures themselves
- Design time and run time access controllers

- The system interface
- Contents of system procedures
- Contents of system procedures determine lines
- System interface and type code simultaneously
- Showing only part of the system interface

- Call example is not great. Shouldn't come this soon anyway.
 
- Setting lines
    - default implementation
    - What get returns determines line.

- Mutual Ancestor is not accurate
    - because the source symbol can set 
    - a design time line itself

##### New Subdivision

- __System Aspects__
    - Are ...
- __System Procedures__
    - Names
    - Diagram
    - First the main ones: the customizable ones
    - Then the secondary ones: the automatic ones
    - Showing only part of the system interface
        - System interface members don’t have system procedures themselves and you can’t redirect them with lines
        - Seeing the system interface as having a system type.
- __Get and Set Always Accompany Eachother__
- __Get Purposes__
    - Get
        - Copy
        - Access
        - Redirection
        - Use as Object
        - Use as Type
        - Use as Interface
    - Use as Procedure
    - Use as Procedure Interface
- __Access Control on System Procedure__
- __Variable and Constant__
    - (Design Time and Run Time Access Control)
    - (Only at creation or free?)
- __Redefining System Procedures__
    - Default implementation
        - Including default access modifiers
    - System procedures don't have system procedures themselves
    - (some aspects are redefinable, some automatic, some automatic but extendable)
    - Mention that you can’t really see the system interface as having a system type, if some of its procedures  can be redefined. 
        - (However, lateron, in access control, or procedure resolution, a technique to redefine procedures is given that make you able to see the system interface as having a system type again...)
- __Exclusive Establishment__
    - Contents of system procedures determine lines
- __Static, Creation and Destruction__
    - a.o. Design time lines
- __State__
    - Conversion
- __Dimensions__
- __Storage of Symbols, Line Targets and Objects__
 
- __Final Issues__
    - Immutable at Run Time
    - Symbol Roles ?
- __Discussion__
    - A separate symbol for an object symbol that serves as solely as a type?
    - Do mind that it’s important that you can have any object symbol as a 
      type.

##### New Main Subdivision

- System Aspects 
- System Procedures
- Get and Set Always Accompany Eachother
- Get Purposes
- Access Control of System Procedures 
- Variable and Constant 
- Redefining System Procedures
- Exclusive Establishment
- Static, Creation and Destruction
- State
- Dimensions
- Storage of Symbols, Line Targets and Objects

##### Other New Brainstorm Items

< How about  system aspects that return how many exits a line makes and which symbols it enters? >

Je wilt toch niet altijd de parent aan kunnen roepen? Maar ik wil het toch kunnen bereiken met het setten van design time lines. Hmmm... het is alleen in geval van access dat je de parent daar wilt bereiken.

Het is altijd zo grappig he? Het komt allemaal neer op zulke basale acties. Een hele ton get en sets lijkt het wel. De compiler is meer een plek om hier dieper op in te gaan. Daar vertaal je symbol naar fundamentele processen.

Are implicit calls mostly an alternative notation for get set actions?

#### ------------------------------------------------------

#### OLD

#### Introduction to System Aspects

*System aspect procedures* return the system aspects of a symbol. You can *‘get’* the following aspects of a symbol:

- __Symbol__
- __Object__
- __Type__
- __Interface__
- __Target Object__
- __Target Type__
- __Target Interface__
- __State__

__Symbol__ returns the id of the symbol itself.
__Object__ returns (the id of) the target of the object line
__Type__ returns the target of the type line and
__Interface__ returns the target of the interface line

__Target Object__, __Target Type__ and __Target Interface__ return respectively the id of the previously discussed *target* object, *target* type and *target* interface.

__State__ is special and returns a copy of the object as it were, which is a copy of all the data the object stores. This state must be immediately assigned to another object, which is usually of the same type.

All other system procedures return a symbol id; State returns the data of the object. I will return to __State__ lateron.

Similarly even more system procedures could be defined that return more system aspects of a symbol, like:

- Parent
- Children
- Etcetera...

Some aspects of a symbol can also be *set*. By doing so you change the system (at run time). The follow aspects can be set:

- __Object__
- __Type__
- __Interface__
- __State__

By setting a symbol’s __Object__, you change the target of the object line of the symbol. The same way, you change the target of the type line by setting the __Type__ and the target of the interface line by setting the __Interface__. The __State__ can also be set. You can also remove a line completely by assigning __Nothing__ to the __Object__, __Type__ or __Interface__.

A programmer commands when an __Object__, __Type__, __Interface__ or __State__ is *set*. *Getting* is not always done on direct command of a programmer. When a programmer wants to call a member of an object, he may *indirectly* cause a lot of __Gets__ to be done. <>On each access that the call makes, the target object and target type are figured out in one string of redirectioning<>. On each of those redirections an __Object Get__ or __Type Get__ is called. When a programmer calls __Target Object Get__ or __Target Type Get__, the same string of redirections is executed, causing automatic calls to __Object Get__ and __Type Get__.

The programmer can also initiate __Gets__ himself. This is always done paired with storing the gotten value somewhere, for instance in a variable. So a __Get__ directly initiated by a programmer is always accompanied with a __Set__.

Working with the __State__ of an object is for instance useful for __Integer__ objects. Their state is the integer value they represent. __State__ is special and returns a copy of the object as it were, which is a copy of all the data the object stores. This state must be immediately assigned to another object, which is usually of the same type. If the state isn’t assigned to the same type then a conversion must take place. 

- Symbol
    - Get  : Copy
- Object
    - Get  : Copy or Redirection
- Set
- Type
    - Get  : Copy or Redirection
- Set
- Interface
    - Get  : Copy or Redirection
    - Set
- State
    - Get  : Copy
- Set
- Target Object
    - Get  : Copy or Access
- Target Type
    - Get  : Copy or Access
- Target Interface
- Get  : Copy

When executing a __Target Object Get__ or __Target Type Get__, automatically are performed __Object Redirection Gets__ and __Type Redirection Gets__. < other place >

So Gets can have three purposes: *Copy*, *Access* or *Redirection*. *Copy Get* happens when a programmer stores the gotten value somewhere else using a Set. *Access Get* happens when the programmer accesses a member of an object. This only happens for Target Objects, and sometimes Target Types too for static elements. *Redirection Get* happens when tracing the target object, target type and target interface. Each redirection step in this process requires getting the symbol to which there’s redirected. Redirections are never directly initiated by the programmer, but are done automatically.

Every system aspect supports a different collection of get purposes. For instance you can’t get the Object for *access*. You can only get the *Target* *Object* for access. The *Object* you can only get for copy and redirection.

When the main purpose of a Get is mentioned, the word ‘Get’ is often left out. You can simply speak of for instance Object Copy or Type Redirection. 

The reason that this separation between get purposes is made is not that there are three different get procedures. The get procedure of all three purposes is the same procedure so that they return consistently the same value for all three purposes. What you can control separately for the three purpose is their access controller (not covered yet). Redirection is always public: the Symbol system can always redirect whenever it feels like it, because Symbol knows perfectly when to redirect and when not to. You *can* put restrictions on Access and Copy. If you make Access private then you can’t access the symbol (through its parent). If you make Access public then you *can* access the symbol. If you make Access public, but Copy private it means that you *can* access the symbol, but you *can’t* copy the id of the symbol. To be able to do that, Copy needs to made public. Copy is always equally or less public than Access. One of the main purposes to different access controllers for different Get purposes is to be able to access a symbol, but at the same time not be able to copy the reference to the symbol. The other important purpose is that the Get always has to be public for redirection, even when it’s private for other purposes. You can alter the access controllers of almost every system procedure and purpose, except for Redirection. That one’s always public. Public for the Symbol system that is, because programmers can never call this form of get themselves.

The Get usually returns system information. The Set usually changes a line target normally. However, as a programmer you can also decide for yourself what’s the effect of a Get or a Set.  You can totally redefine the Get and Set procedures of a symbol. With that you can also add parameters to the Get and Set procedures. So you’re able to decide yourself which symbol to return on a Get and which symbol to assign on a Set. \* You can also for instance see to it that on a Set call, the change is applied to all sorts of things, by starting procedures that apply the new value. When setting an object’s state, for instance, you can automatically apply its new state to other objects, for instance when you need to draw a text on screen every time a value changes. You can’t redefine *all* system procedures. For instance the effect of Target Object Get must stay consistent and can not be customized. And also Symbol Get always needs to return the symbol itself. You can only redefine the Object, Type, Interface and State Gets and Sets.

Just now, I’ve only discussed the system procedures of *object symbols*. Procedure symbols have system procedures too:

- Symbol
    - Get : Copy
- Call
    - Get : Copy
    - Set
- Reference
    - Get : Copy or Redirect
    - Set
- Target Procedure:
    - Get : Copy or Access

*Symbol Get* obtains the id of the symbol itself. *Call Get* obtains the call line target symbol. You can also *Set* the call target. *Reference Get* returns the symbol id of the reference line target. You can also *Set* the reference line target. The *Target Procedure* of a symbol returns the procedure at the end of the redirection: the procedure definition. *Target Procedure Copy* copies the id of this procedure. *Target Procedure Access* is the Get that occurs when you call the target procedure. Access controllers can be applied to all elements, except Symbol Get. Call and Reference Get and Set can be redefined. Mind that the access controller for Target Procedure Access determines *the* access controller for calling the procedure symbol.

Because procedures have system procedures themselves, you’d think that an system procedure also has an system procedure. That one isn’t true. System procedures don’t have system procedures themselves.

Set and Copy are used to set up lines. Lines are set up at design time, but can also be changed at run time. Sometimes you want to set a line at design time without being able to change it at run time. Therefore, Set and Copy must be able to have different access controllers at design time and run time. Just like the Get purposes can have different access controllers, it’s possible to have different access controllers for Design Time Set and Run Time Set and for Design Time Copy and Run Time Copy. Something is a constant if it can be Design Time Set, but not Run Time Set.

Object symbol system procedures and purposes:

- Symbol
    - Get  : Copy (Run Time or Design Time)
- Object
    - Get  : Copy (Run Time or Design Time) or Redirection
    - Set  : Run Time or Design Time
- Type
    - Get  : Copy (Run Time or Design Time) or Redirection
    - Set  : Run Time or Design Time
- Interface
    - Get  : Copy (Run Time or Design Time) or Redirection
    - Set  : Run Time or Design Time
- State
    - Get  : Copy (Run Time or Design Time)
    - Set  : Run Time or Design Time
- Target Object
    - Get  : Copy (Run Time or Design Time) or Access
- Target Type
    - Get  : Copy (Run Time or Design Time) or Access
- Target Interface
    - Get  : Copy (Run Time or Design Time)

Procedure symbol system procedures and purposes:

- Symbol
    - Get : Copy (Run Time or Design Time)
- Call
    - Get : Copy (Run Time or Design Time)
    - Set : Run Time or Design Time
- Reference
    - Get : Copy (Run Time or Design Time) or Redirect
    - Set : Run Time or Design Time
- Target Procedure:
    - Get : Copy (Run Time or Design Time) or Access

That seems a whole lot of Get and Set purposes. In practice, the set up of a symbol’s system procedures is not that complicated. There’s a standard setup: the most usual system procedure setup. Only deviations from the standard are additionally denoted.

There are a few more system procedures which will be gradually introduced.

#### The System Representation

The usual representation of an object symbol is one that shows the members of its type.

An alternate look on the object symbol is as a set of system procedures, each granting a different type of access to the object:

![](images/Symbol%20Language%20(2004).386.png)

This representation is called the *system representation* of the symbol. Each procedure in the system representation does what’s discussed in the previous section.

__Symbol__, __Target Object__, __Target Type__ and __Target Interface__ only have a __Get__ procedure. The word __Get__ is simply left out in naming these procedure from now on. The word __Get__ can also be left out with __Object__, __Type__, __Interface__ and __State__ __Gets__.

Now you can see that the system procedures are actual Symbol procedures (except that they don’t have system procedures themselves). You can do with them the things discussed above: you can change their access controllers. Some of these procedures can get multiple access controllers for different purposes (System procedures are the only procedures that have this capability.). The Object, Type, Interface and State’s Gets and Sets can be redefined by filling the procedures with code.

Notice that what you fill in in the Type Get procedure, determines the contents of the symbol in the ‘normal’ representation, or *type representation*, because the type represenation shows the members of the symbol’s type.

The system representation of a symbol has no lines.  The lines of the *type representation* are actually determined by what Get procedures return. Therefore, a symbol is no more than a bunch of system procedures < Interesting, but not entirely true, because it suggests you can determine thw whole system by filling in system procedures, while you can’t directly change the ancestry or change the shapes of symbols. The contents of system procedures determine the lines. The system representation is like seeing the setup of the symbol machine. >

Procedure symbols also have an system representation:

![](images/Symbol%20Language%20(2004).387.png)

##### Simultaneous System Representation and Type Representation

You can also view the system representation along with the normal representation. System procedures are called, just like other procedures are called and their being called is mixed with calls to regulare procedures, so you have to be able to see both the system procedures and type procedures at the same time.

The following notation is used for this:

|<p></p><p>*Type Representation Only* ![](images/Symbol%20Language%20(2004).388.png)</p>|*Simultaneous System and Type Representation* ![](images/Symbol%20Language%20(2004).389.png)|
| :-: | :-: |

The system representation is displayed sort of like an implementation of an extra interface, but tied to the edge of the symbol, rather than being contained by the symbol, denoting that this interface isn’t inferior to the symbol. The system representation is in this case also called the system interface. In simultaneous display it is very apparent that it’s system procedures that you’re seeing. It may be preferred to always view system procedures in simultaneous view, even when you don’t display the type contents:

![](images/Symbol%20Language%20(2004).390.png)

This way it even *looks* like you’ve opened up the symbol maching in order to change its setup.

Not always the whole system representation is shown. You might only want to show the part that you can see is called

![](images/Symbol%20Language%20(2004).391.png)

#### Call Example

< Not finished, but it takes too much time to write this section for now >

< Might need to display how system procedures are called >

I will now discuss the same complex call as before, but now denoting which system procedures are called for which purpose. This call only involves getting values, not setting them.

![](images/Symbol%20Language%20(2004).392.png)

We start at *a*, the procedure which contains a call, located near the center of the diagram. It calls b, but before that it first acceses c and then i.

c . i . b Is the expression that calls b. The period (.) is an operator, which, as will be explained later, is a procedure call.

The first period is an alternate notation of a call to c . Object. The second period is a call to i . Object. The b that follows is a call to b . Target Procedure. Symbol starts the procedure returned by b . Target Procedure.

Each call of the three (c . Object, i . Object and b . Target Procedure) is processed in steps.

c . Object is called (for the purpose of *Access*). The c . Object procedure returns d . Object. d . Object returns e . Object. e . Object returns itself: e . Symbol. This process is contained in the Object Get procedures of c, d and e. They redirect to one another until e returns itself. So c . Object returns e.

The target object and target type of e are to be found out. Symbol does this by first calling __e . Object Get__ for the purpose of Redirection.  This call is not anywhere in the diagram. It is done on Symbol’s discretion. e . Object Redirection returns Nothing, a special value that in this case indicates that there is no object line. Because there is no object line, the type line may need to be followed. Therefore Symbol calls e . Type for the purpose of Redirection. This call returns symbol f. f . Object Redirection is called, which returns Nothing, so them f . Type Redirection is called, which returns g. g . Object is called, which returns h. h . Object is called, which returns Nothing, so h . Type is called, which also returns nothing. During this redirection loop, Symbol has recorded the target object and target type of e. This concludes the access of c.

Now we know c’s object and type we continue the journey of our call line. It appears in the diagram that we have now entered c. Symbol internally is working with another symbol now, though: h, because it is the target object and type of c. 

< ... Was here >

Next the call line accesses i. i Redirects to j with an object line. j However has both a type line and an object line. A rule discussed earlier told us that in finding target type and object, a type line is ignored if also an object line is present. So we follow the object line to k. k has only a type line, making it a potential candidate for target object. k redirects to l with a type line. l has no lines. k Is the last symbol to be pointed at with an object line, so k is the object of i: Oi, and l is the type of i: Ci. Then we roll back to the call line, that can now enter i.

The call line ends up at b, the called square, but b has a procedure reference line to m. Procedure reference lines are bound just as tightly as object lines and type lines and any symbol exits and entrances are irrelevant in processing a call. m Directs to n, n directs to o. o has to be called.

o Has to be called, but it’s a call to a totally different object. You have to know what object you’re calling so you must find out this symbol’s object and type. 

Because the initially accessed object isn’t called, but another object, it may seem that performing all those previous accesses wasn’t necessary, but it was. In the target object the procedure reference target is stored, so we indeed needed to obtain the target object, and for that the target type too. This object lead us to knowing where the procedure reference leads. To know which procedure is referenced, you have to figure out its parent’s type and object. So one more obtaining of a target object and type is performed on the target procedure’s parent. This is not an access, but the same method is used.

#### Setting Lines

The default implementation of a Set procedure stores the target symbol in a *storage variable*. The associated *Get* procedure has a default implementation returning it. Lines are determined by what Get procedures return. Lines are always set by calling Set procedures. 

This means that setting a line even at design time, requires calling the Set procedures. This section discusses where they are called.

##### Mutual Descendant Sets Lines

< Mark this as kind of another line restriction, not mentioned in the Lines chapter. >

The line between two symbols is set up by another symbol: the *mutual descendant* of the source and target symbols.

|![](images/Symbol%20Language%20(2004).393.png)|![](images/Symbol%20Language%20(2004).394.png)|
| :-: | :-: |

Going upward in the encapsulation for both source and target, eventually you encounter a symbol that they’re both (indirectly) contained in. This is the *closest mutual descendant*. The closest mutual descendant makes the connection between those two symbols. Even when the line is hard coded, the line is set by another symbol. The closest mutual descendant is the closest symbol that can reach both source and target symbol.

The consequence of this is that the source symbol’s Set and the target symbol’s Copy (Get) must be accessible to the closest mutual descendant, otherwise the line can not be set at all.

In a diagram where you don’t denote publicity, potentially anything is public so lines other than call lines have no limitations to their connections to the outside. When you consider publicity however, restrictions can be laid on these outward lines. 

An descendant of the closest mutual descendant (which is also a mutual descendant) could also have set the line, be it that the source and target symbols are published as far up the encapsulation hierarchy. That is: the Set procedure of the source symbol and the Copy procedure of the target symbol must be public to it. Lines set at design time are set by the closest mutual descendant, though.

Lines set at design time are set at run time on creation of the mutual descendant. This means that lines of a symbol’s children only exist in created objects, because line targets are data stored in the created object.

<<
A flaw:

![](images/Symbol%20Language%20(2004).395.png)

If an object circularity is created and you break an object line in it, then a target object will stand up.

This flaw also occurs when 
\>>

#### Create and Destroy

< You can create a symbol giving it an alternate type >

<
__Destruction__

Destruction is not the opposite of creation. It’s a separate thing, because creation is an operator that is invokes, and destruction just happens when the reference count becomes 0.

Oops. At runtime you can set references to an object, while it isn’t even created... Oops. That’s big. That flaws the destruction methodology.
\>

##### The Create and Destroy Procedures

A subject looked at less closely till now is creation and destruction of objects. The Create and Destroy procedures are actually two system procedures that I haven’t mentioned yet. They only apply to object symbols:

![](images/Symbol%20Language%20(2004).396.png)

Like the other system procedures, their access controllers can be adapted. There can be separate access controllers for design time and run time, just like Copy Get and Set.

These access controllers are bound to the type, so each symbol of this type gets the same creation access controllers. The access controller of the Create procedure determines which parties will be able to create objects from the type.

##### Referring to Uncreated Symbols

A symbol can have a line to a non created symbol. So you can reference an object that hasn’t been created. When the object is created, all referrers refer to the created object.

##### Breaking the Chain

When you break the chain of symbols pointing to a created target object, only certain objects will still refer to a created object:

![](images/Symbol%20Language%20(2004).397.png)

![](images/Symbol%20Language%20(2004).397.png)

Only the ones still pointing to this target object still point to a created object. The ones before the break refer to a newly formed uncreated target object. Here you see the concept of direction playing a big role.

##### Breaking a Bidirection

What if you break the line between the two symbols of a created bidirection? Which symbol remains created and which becomes nothing? The solution is that a bidirection can never be broken in one blow. One direction must be broken first before the other one is broken. Then, when both directions are broken it is clear what symbol remains created and what symbol becomes uncreated.

![](images/Symbol%20Language%20(2004).398.png)

##### No Lines Inside Uncreated Symbols

Lines are set at run time. Design time lines are actually set in the Create procedure of the mutual descendant. However, in design time nothing is created. So there actually are *no lines at design time* at all.

Furthermore, *lines only* exist *in created objects*, because line targets are stored in the created object’s data. That doesn’t mean that lines can’t point *to* the insides of an uncreated symbol.

So lines can only exist in created symbols at run time.

So lines can’t exist at design time.

Lines that don’t change during the lifetime of an object can be shown in an uncreated object anyway, so also at design time. You can also show lines in an uncreated object that are set at creation of the symbol. These lines *could* change after creation. Another method is to show lines that can *possibly* exist in the lifetime of an object. You can draw the different possible lines in different colors, drawing lines that will most probably exist or exist longer in a more contrasting color. The lines shown there are merely representations of what’s going to happen or what *could* happen. The lines are instantiated for real only when an object is created.

In created objects, lines are shown that are present for real: exact lines. Inexact, possible lines can also be shown in a less contrasting color (or more transparent). In uncreated objects, lines that won’t change during the lifetime of an object can also be called exact lines.

##### Destruction

To destroy a symbol, you have to call Destroy on a target object. When you call Destroy on a non target symbol then its object line is simply set to Nothing. The target object remains. When a parent is destroyed, Destroy is called for all children. Only if the children that are target objects are destroyed for real.

###### Symbol’s Different Methodology for Destruction and Object Reference

There are differences between methodology in Symbol and former methodologies for destruction and object reference.

Symbol’s __Destroy__ is actually like Visual Basic’s __= Nothing__. It is logical that __= Nothing__ must be called on the last object reference in order to destroy the object. So you have to call __= Nothing__ (__Destroy__) on the target object. So having to call __Destroy__ is not proof of a less automatic destruction mechanism. It’s just like calling __= Nothing__ on the an object reference.

However, if a target object symbol is destroyed, other references will not point to a created object anymore. In a symbol diagram this makes sense. 

|<p></p><p></p><p>![](images/Symbol%20Language%20(2004).399.png)</p>|<p></p><p></p><p></p><p>à</p>|<p></p><p>![](images/Symbol%20Language%20(2004).400.png)</p>|<p></p><p></p><p></p><p>à</p>|<p></p><p></p><p>![](images/Symbol%20Language%20(2004).401.png)</p>|
| :-: | :-: | :- | :-: | :-: |

In Com, the object remains as long as there are referrers. Symbol just has a more refined methodology.

Another difference in methodology is that if an object is destroyed, non created symbols still refer to eachother (see picture).

<
How do you mimic Com methodology?
You’d want to make one symbol the object. Other symbols the referrers. The object must 
destroy if there are no more references.
\>

##### Creation is not State Assignment

Creation is *not* a special State assignment. State assignment fills an existing object with new values, copied from another object or derived of another object. It has nothing to do with the creation of a new object. Creation is something totally separate.

#### Set Example

Here I give the diagrams of how system procedures are called to set a line at design time, change it at run time and anull it at run time.

When you set lines at design time, you’re actually putting code into the Create procedure of the mutual descendant.

![](images/Symbol%20Language%20(2004).402.png)

The Create procedure calls Target (. Symbol Get) and then Parent . Source . Object Set passing the result of Target . Symbol Get to it. The text code line would be:

```
Parent . Source . Object Set = Target
```

This is a design time set line. You don’t need to display the symbols above all the time and more such symbols for every design time set line. You only have to display the symbols above if you find it really important to display them or when debugging the Mutual Descendant . Create procedure, which sets the lines.

After the Create procedure has executed, the diagram can be displayed as:

![](images/Symbol%20Language%20(2004).403.png)

The differences are that the access interfaces have collapsed and a line is now between Source and Target. The other diagram showed the procedure of instantiation of the line.

When debugging at any moment a line is changed, you’ll see the source and target symbol’s access interfaces temporarily opening up. When the line is changed, they close again.

*Before change:*

![](images/Symbol%20Language%20(2004).404.png)

*The change:*

![](images/Symbol%20Language%20(2004).405.png)

*After change:*

![](images/Symbol%20Language%20(2004).406.png)

You can also take away the object line completely by assigning Nothing as the symbol’s object, or *anulling* the line:

*Change:*

![](images/Symbol%20Language%20(2004).407.png)

*Result:*

![](images/Symbol%20Language%20(2004).408.png)

#### State

State is special and returns a copy of the object as it were, which is a copy of all the data the object stores. This state must be immediately assigned to another object, which is usually of the same type.

What’s actually done is that values from one object are copied to the other object.

- An object’s state includes its children’s lines.
- The states of all its ancestor *created target objects* are also part of the state.

The states of *non*-target object descendents are *not* part of the state. Those symbols point to other symbols. Their line targets *are* incorporated in the state.

##### Conversions

If the State isn’t assigned to the same type then a conversion must take place. The target type for the state assignment must define the conversion and this conversion is bound to the state source type; for each state source type, the state target type must define a conversion. If the conversion isn’t defined then it’s not possible to assign a state of that type.

Conversions can also be cast explicitly rather than being automatically performed on state assignment.

Conversion procedures are considered system procedures as well. One type can define multiple conversion procedure’s. The parameter of the conversion procedure is the source object. A conversion procedure can also have multiple parameters. That way multiple objects can be converted to a single object, sometimes grouping multiple object of the same type, sometimes grouping a combination of types.

< If you want to convert a number to text then the text object should define the conversion for all this stuff. Hmm... mayve the source object should be able to define the conversion too >

#### Conversions Aren’t Create Procedures

This comment is made because in the C++ programming language, conversion procedures *are* alternative create procedures. A conversion does not involve the creation of an object. A conversion is the assignment of new values to an existing object, values that are based on the values of an object from a different type.

#### Dimensions (Brainstorm)

< There must be a special notation for a dimensional symbol >

<>
I have to have a substitute for the array in Symbol. It seems that I need the possibility to have a series of multiple object symbols of the same kind. All I might need instead, actually, is the an object symbol with a dimension. I can do that by giving the Object property a dimension. The State property should also get a dimension then. Should I then base the storage of the object symbol on a data structure? To understand this I need to understand the storage of an object’s data. Most of the times, the storage of an object’s data is in the storage of it’s sub objects’ data. Then it goes down the ancestry, usually up until the simple object types such as Integer and Double. Line targets are also stored data, stored Integer objects as sheer identifying numbers. Arrays... are probably symbols of which system procedures have a dimensions, mainly the Object or State property. The system procedure returns something a J Data object returns. I might want to show an alternate notation of a symbol whose system procedures have one or more dimensions.

Maybe I need a small section about object data storage. How it’s delegated to J Data and to Math and that math delegates it to J Data too. I guess J Data is the one to manage the use of space.

I also need a basic explanation about the consequences of giving system procedure dimensions.

#### Brainstorm

<>
I can not seem to be able to give this sentence a place: 

The usual way of accessing most objects is by getting a reference to it and then calling a member of it. The usual way of accessing simpler objects such as Integers is by getting the *state* of it.

<< Doesn’t the fact that procedures determine lines make the symbol database as I know it invalid? Yeah. Line targets would be far from primary data. What would be primary data then? Object and procedure ancestry and call lines? Yeah. Other lines are data derived from the calls inside system procedures. >>

#### Immutable at Run Time

<>
What’s never changeable at run time. I think the encapsulative structure. Except for that you can add objects to a series.

And what *is* changeable at run time.

#### Static and Creation

< What I call type members a lot, really aren’t type members. They’re object members. Only static type members are type members. And what I call procedure members aren’t procedure members. They are call members. Only static procedure members are procedure members. So what are Type Static procedure members? They are type members that are only associated with a single procedure. Oh, but they are still procedure members than. And then object members can also be called type members. Hmmm... yes, but I overuse ‘type member’ I think. In a lot of places I can say object member. >

<
a symbol apart from an object access procedure also has a type access procedure giving you access to the type members in a static form. The object includes its types static members...(I’m explaining static here)
\>

<
Uit dit verhaal volgt dat je wel code als deel van de klasse kan zien, maar dat procedures niet deel van de klasse zijn. Als procedures static members hebben dan heeft elk object z’n eigen procedure type object. 

Als types static members hebben dan heeft elke globality instance z’n eigen type object
\>

< ik moet *makkelijker* met de static termen moeten kunnen omgaan >

< An object doesn’t define code. You could say that the type defines code and that a object only defines data. Each globality instance, though, has its own instance of the types of the globalities, even though the code of the types is still only in memory once. So you can’t really say the code resides in a type either. >

- Type static
- Procedure static
- Globality static

- Type static objects
- Procedure static objects
- Globality static objects

- Procedure static procedures
- Type static procedures
- Globality static procedures

- Type Create
- Procedure Create
- Globality Type Create

##### Memory Reservation

This text is preliminary, because there is no final design on Core object management.

Usually you won’t work with memory management. You’ll simply use for instance Integer or Array objects from the Math and Data modules. Those objects manage memory.

An object that manages its own memory can define what memory spaces it wants. Say it wants 3 memory spaces. You can can then identify these spaces with 0, 1 and 2 in your code. When an object consults a memory space it calls a Sigma Core memory management procedure. It identifies itself and the space it wants to do something with. The Sigma Core stores the real ids of the spaces and knows what space to work with. <> The object doesn’t know its own id, but the caller of the object does. < >

Every time an object is created, it gets its own initial memory spaces. Oh! Once it has one memory space it has the ability to store space id’s of other memory spaces, so then it can work with the spaces with the real space ids. So the Code must store what?

##### Static

Members usually belong to an object: every object has its own sub objects and procedures. Members of a type that are Static, however, belong to the type rather to individual objects. These members have the same configuration for every instance of the type. A change made to one object of the type changes all objects of the type. The members are considered *static* to the type.

Procedure instances are made on each call to the procedure. A call is a procedure instance. In order to make objects part of the whole procedure, rather than just the call, procedure members can be made Static to the procedure. On each call to the procedure, the static members retain their configuration.

Static members of a procedure are only the same for every call to the procedure. Static members of a procedure are different for every object that holds the procedure. In order to make procedure members static for the whole type of objects you have to make a procedure member Type Static. When I talk about static procedure members I’m talking about Procedure Static members.

Static type members are the same for every object instance. However, each globality instance has its own copy of static type members. Static type members are not the same for every globality instance. In order to make a type member, or a procedure member static to the any globality instance, you make the member Globality Static.

An effect of making type members static is that you can call the members even when the symbol isn’t created. Non-static members, or *instance members*, can only be called on a created object. Globality static members can be called even when the globality instance isn’t created, but the globality type is loaded into memory. Static members of a procedure can be accessed without running the procedure.

Procedure static members are like part of their object. They persist for as long as the object is created. Type static members persist for as long as its globality instance is created. Note here that each globality instance gets its own set of types with static members. Globality static members persist for as long as the globality type exist. A globality type exists when the Sigma module that contains it is in memory.

##### Type Creation

The Object Create procedure initializes the instance. In it you can create sub objects, set up lines and call members. Type members are initialized in another procedure: Type Create. The Type Create procedure of a symbol is called when the type is created. Types are created when a globality instance is created so the Type Create procedure of all types in a globality instances are called right after the globality’s Object Create procedure.

You can only call static type members in the Type Create procedure, because non-static, *object* members can not be accessed yet, because they can only be accessed through a created object.

A procedure has a Type Create system procedure as well, to set up the procedure’s static members.

Members of a procedure that are Type Static are initialized in the type’s Type Create procedure. Any Type Static member, be it of a procedure lives as long as its type. Type Static procedure members are like type static type members, except that they are accessed through the procedure. If the procedure declares them private, they are accessible only to the procedure itself.

A globality also have a Type Create procedure. This is called when the globality type comes to light. Globality types come to light when a Sigma module is loaded. All the Type Creates of globality types in a Sigma module are called right after the Sigma module is loaded. The Type Create of the main globality of a Sigma module serves as the module initializer. The Object Create of the main globality serves as the module instance initializer.

##### Old

###### Creation

####### Globality Creation

...

###### Static Objects

####### Type Static Objects

Sub objects belong to their container object. Static objects, however, are part of the type rather than part of individual objects. Each object then contains a sub object that is the same for each object of the type. The static object symbols are shown to all point to the object in the target type. The static object in the target type can be created while the type symbol isn’t shown as created. The target type holds the line targets and data of the static object. When an object of the type tries to change the object line of the static object, it doesn’t change the line of its own object symbol, because that line will always point to the static object of the target type. Instead, the line of the static object of the type changes.

This makes it so that lines can be tied together quite complexly, because static object symbols in object of the type always point to the static object symbol in the target type, which can be lines that travel far. On the other hand: every object of the type with a static object can set the line of the static object, meaning that the static object can point to a wide variety of locations, so it could again be a far away line. The lines of the static object symbol inside objects of the type, that point to the static object symbol of the target type, anyway, these lines don’t really exist. I still must come up with a way to make the notation different so that you can see the static systematics.

####### Procedure Static Objects

Procedures are much like types. They can hold objects too. If you want the state of an object to persist for multiple procedure calls, you can make the procedure object a *Procedure Static*.

A procedure static object does give every object of its type its own procedure static object.

By making a procedure’s object both Procedure Static *and* Type Static, the procedure object is the same for every call to every object of the type.

Procedure and Type Static objects inside procedures can also have the long lines going from all objects to the type.

< P >

####### Globality Static Objects

A Type Static sub object is the same instance for each object of the type. But each globality instance gets its own Type Static object. If you want the object to be the same for every instance of the globality, then you must make the object Globality Static.

Note that Type Static Objects that are direct ancestors of the globality are static to the globality type so automatically Globality Static.

Note that Globality Static objects are automatically also Type Static.

###### Static Procedures

####### Procedure Static Procedures

If you not just make a single procedure object Procedure Static, but the whole procedure Procedure Static, then all objects in the procedure are Procedure Static.

####### Type Static Procedures

If you make a procedure, not an object, Type Static, then the procedure static objects inside the procedure are also static for the whole type.

Another effect of making a procedure Type Static is that you can call the procedure even through an object that isn’t created.

Type Static objects and procedures can be accessed even though an uncreated object symbol, but non Type Static procedures and objects can *not* be accessed unless the object symbol is created.

####### Globality Static Procedures

The rules of Type Static procedures also apply to Globality Static procedures. Only Type Static procedures’ objects are static to *all instances* of the globality.

###### Type Create and Destroy

####### Type Create and Destroy

In order to initialize and terminate objects and procedures static to the type, object symbols have a Type Create and a Type Destroy system procedure. The Type Create procedure of an object symbol is called long before the object symbol is created and becomes a created object. The Type Create procedure is called when a globality object is created. The Type Create procedures of any ancestor object symbol of the globality is called, but not of the object symbols in sub globalities. Those object symbols’ Type Create procedures are called only when the sub globality is created. Many object symbols might not even have a Type Create procedure.

The Type Destroy procedure is called when the globality instance is Destroyed. Beware not to uninitialize Globality Static members of the type, because those belong to all instances of the globality, not just the instance of the globality that’s being destroyed.

Note that you can only initialize the members static to the type in the Type Create procedure, not instance members. This is not a restriction that the Type Create procedure imposes. It’s just that the Type Create procedure is called before any object is created and you could only access non static members through a created object, so at the time the Type Create procedure is run, instance objects and procedures are accessible.

Type Create is stuck right at the end of the globality’s Object Create.

Type Static members are like part of the globality instance, rather than the object instance.

Globality Type Static members are like part of the Sigma module, rather than the globality instance.

####### Globality Type Create and Destroy

Globality symbols also have a Type Create. New globality types come to light when a Sigma module is loaded. All the Type Creates of globality types in a Sigma module are called right after the Sigma module is loaded. The Type Create of the main globality of a Sigma module serves as the module initializer. The Object Create of the main globality serves as the module instance initializer.

####### Procedure Create and Destroy

Procedures are in many aspects the same as types. To initialize the static members of procedures. Procedure Create is called on creation of the procedure’s object. In the Procedure Create you can only call static members of the procedure, because the instance members of procedure only exist during a call to the procedure.

Procedure Create is stuck right at the end of the object’s Object Create.

Procedure Static members of a procedure are like part of the object instance, rather than the procedure instance.

##### Question

Where are type static procedure members initialized?

Type Static procedure members are like part of the globality instance. They are globality instance *specific*, but this is also called type specific, because a type belongs to a globality instance. They should be initialized along with the globality instance, so along with the type creation. Type Create can access Type Static procedure members and are initialized there.

Type Static members of both the type and its procedures are initialized in the Type Create procedure and terminated in the Type Destroy procedure.

Globality Static members of both globality, its type and procedures are initialized in the globality’s Type Create procedure and terminiated in its Type Destroy procedure.

##### Old

<
Object data

An object has its own data. Data is accessed through the objects’procedures or through the procedures of its sub objects.
\>

###### Objects and Memory Reservation

Objects reserve memory when created. In this memory their data is stored, data which represents the object. The data is manipulated in the procedures of the object, by calling basic memory management procedures. Objects you program usually don’t reserve this memory themselves. Memory is often only reserved by contained basic data objects, such as Integer or Double. They manage memory reservation and management. When those basic data objects are created, they reserve memory. The descendant can create them in its create procedure, but also at a later time. The descendant can also just *allow* creation of its contained objects.

###### Type Static

The basic things about a static procedure:

- Callable even when the object symbol isn’t created
- Data mutual for every object

The first point is just a matter of tagging it static.

The second point:

The type should contain objects that store data. How do they belong to the type rather than the individual objects? Make all system procedures static? What does that render? That makes the procedures accessible when the descendant isn’t created.

Aleen als de naar hetzelfde geheugen verwijst.

Ik volg het niet. Ik zie het niet.

####### Only Procedures of Created Objects can be Called

You can not call procedures of a symbol that isn’t created just like that. Therefore you can’t refer to a sub symbol of an uncreated descendant using any kind of line.

####### Static Members

There is a way to call procedures of a symbol that isn’t created: you can make procedure’s static. This makes them callable even when the symbol is not created. They are the type’s members rather than the object’s members. An object symbol becomes static by making one or more of its system procedures static, for instance the Symbol Get, which makes you able to link to an object symbol. You can call the type’s static members through any symbol that has that type. Static procedures aren’t passed the hidden object argument.

####### Type Create and Type Destroy

You may want static objects to always be created. Remember that static objects are objects some of whose system procedures are static. Those static objects can store static data for the type. Or you may want to reserve ‘static’ memory space for the type yourself. There’s no such thing as static memory space, but you can allocate memory and store a reference to it in a static object. To be able to have sub objects created as soon as the *type* is running, a type, apart from an object, needs a Create procedures. Therefore, object symbols have a Type Create procedure. Object symbols also have a Type Destroy procedure to be able to destroy static objects and deallocate static memory. 

####### Types’ Creation

The Type Create and Type Destroy system procedures can’t be called in your code. They are only called by Symbol automatically, just like Object Redirect is only used by Symbol itself. Type Create procedures are called when the direct globality of it is created. So when a globality is created, any Type Create procedure of any object symbol inside it is called.

####### Type Create and Type Destroy are Static nor Non Static

The Type Create and Type Destroy are considered static nor non static, because because Type Create is called before the type is created, so before static members can be called.

###### Globality Static

####### Other Issues

Globalities need to be created too.

Globalities can also have static members. Those are members of the module that can be called even when the module is not created. The globality type create procedure of all sub globalities is called as soon as the module is loaded in Sigma.

Types in a non created globality can usually not be referred to. 

There can also be static members of a globality. Those are mutual to all globality instances and can be referred to even when the globality isn’t created. Then you can refer to procedures (and objects and types) of a non created globality. The procedures must be made Globality Static in order to do that. Globality Static symbols’ Type Create procedures are called even when the globality isn’t created. To have objects run as soon as the globality type runs, the globality symbol has a Type Create and Type Destroy procedure as well, in which you can create objects to run staticly.

Types of globalities can be

Then globality static type creates should be called when the sigma module loads. Right. The module only exists when. So globalities must also have their own (Globality) Type Create and Type Destroy procedures that are runned when the Sigma module is loaded, respectively unloaded. 

So now there’s not only static symbols, but globality static symbols, which can be members of ancestors at any depth inside the globality. Only globality static members (including system procedures) can be called when a globality is not created.

Sub globality’s type creates are also called on module load. If you don’t define globality type create of syb globalities, then nothing is called ofcouse. Only if you choose to have a globality with globally static data, their globality type create procedure is called.

Sub globality’s type creates are also called on module load. Sub globality type creates are called in the super globality type create. In a globality type, Type Create procedures that are declared Globally Static of object symbols are called when the the globality type is created.

The creation of a globality must be initiated by code, because a globality symbol can also become a globality reference, in case of which Create must not be called.

Dus globally static procedures kunnen worden aangeroepen nadat module is geload. Alle globally static procedures van alle.

- Globally static procedures
- Type Create procedure of globalities
- Static procedures
- Type Create procedures of object symbols
- Object Create procedures of globalities
- Object Create procedures of object symbols
- Static procedures directly in globalities

Symbols always contain some data: their line targets. Those are static data, so when you create a globality there’s always memory reserved: for each symbol memory that stores the line targets. (by the way: doesn’t a flag need to be stored to on if the symbol is created?). Or should I store line targets in the Core’s object table? Hmmm...

Static bij procedure members.

< How can you make a type: globality static? >

#### Symbol Roles

- base
- base type
- base object
- base interface

##### Procedure Symbol Roles

A call line makes the square a call. A reference line makes it a reference. No line at all indicates that it’s a procedure definition or a clause. Lines can also be left out for abstraction reasons.

|<p></p><p>![](images/Symbol%20Language%20(2004).409.png)</p><p>*Definition*</p>|<p></p><p>![](images/Symbol%20Language%20(2004).409.png)</p><p>*Clause*</p>|<p></p><p>![](images/Symbol%20Language%20(2004).410.png)</p><p>*Call*</p>|<p>![](images/Symbol%20Language%20(2004).411.png)</p><p>![](images/Symbol%20Language%20(2004).412.png)</p><p>*Reference*</p>|<p>![](images/Symbol%20Language%20(2004).413.png)</p><p>*Illegal: a square can’t be both a call and a reference*</p>|
| - | - | - | :-: | :-: |

< Not true: a call doesn’t have to directly exit a square if it calls a procedure reference embedded in the same procedure or a clause of the procedure >

Note here that the access symbol of a solid procedure reference line is also drawn solid.

##### Reference and Call Targets

Here is a list of possible reference targets and call targets:

|<p>![](images/Symbol%20Language%20(2004).414.png)</p><p>*Reference to definition*</p><p></p><p>![](images/Symbol%20Language%20(2004).415.png)</p><p>*Reference to clause*</p><p></p><p>![](images/Symbol%20Language%20(2004).416.png)</p><p>*Reference to reference*</p>|<p>![](images/Symbol%20Language%20(2004).417.png)</p><p>*Call to definition*</p><p></p><p>![](images/Symbol%20Language%20(2004).418.png)</p><p>*Call to clause*</p><p></p><p>![](images/Symbol%20Language%20(2004).419.png)</p><p>*Call to reference <br>(A call to a reference calls the referenced procedure)*</p>|
| :-: | :-: |

#### Accesses

< __This section explains too much on traces that has already been explained in Lines. I also think that which traces are involved in an access is not for now. You might have to know what’s considered an access, so that you understand aspect procedure call purposes, but that’s all__ >

Before going into detail about system aspects, I have to define a basic concept: an *access*.

On a call you enter zero or more objects, going deeper into the ancestry or staying on the same level. Each border you *enter* is called an *access*. 

*An access is where a call line enters an object symbol.*

So access only takes place in the line of execution when one procedure calls another.

In my further explanations I’ll take the following form of call as a base:

![](images/Symbol%20Language%20(2004).420.png)

A call to a child’s procedure.

In our basic call, you access one symbol:

![](images/Symbol%20Language%20(2004).420.png)

Accessing the object requires an object-type-interface trace.

Each of those steps is called a *redirection* and they are part of the same access (the accessing of R).

#### Accesses

Any access (*a call line’s entering an object symbol*)  involves such redirectioning, in order to know which type to call, to operate on which object. If you access multiple symbols on one call, each access includes its own object-type-interface trace.

![](images/Symbol%20Language%20(2004).421.png)

*Great grandchild access requires three accesses.*

Once we’ve processed each access by following redirections, we’re not even done. When we’ve finally reached the procedure to call, we might have more redirections to follow: procedure reference lines.

*< P: Reference line entering object symbols >*

The point at which a reference line enters an object is not regarded an access. A reference line between two procedure symbols is a tighter bond than a call line. The borders of symbols that the reference line enters are simply in the way. The procedure symbols are directly tied together.

*< P: Reference target has a reference target itself. >*

When you’ve reached the reference line’s target symbol, this target symbol may have another reference line. In order to find out if it does, the object and type of the object symbol that holds the target square must be tracked down, because the object stores the line targets of its procedure.

A reference line’s entering a symbol is not another access, just like any other line entering a symbol is not another access either, even though it involves tracking down of object and type. Tracking down object and type is a more common thing than an access. It’s merely *involved* in an access, rather than being the access itself. It is also *involved* in figuring out a procedure reference line target.

Every step in finding the procedure reference target involves tracking down a type and object. The reference lines must be followed until you find the target procedure and then that’s the procedure to call.

![](images/Symbol%20Language%20(2004).422.png)

This is a call to a child’s procedure. After reaching the child’s procedure, the redirectioning isn’t done, because the child’s procedure has reference line (*r*), which is to be followed. Eventually b is called.

When the target procedure is found, it needs to be called. In order to do so, object and type must again be traced, in order to know which procedure of which object to call. This again isn’t an access, but the same kind of process is involved: the process of finding the target type and target object of a symbol.

###### A Complex Call Example

Here follows an example of one call with a ridiculously large amount of redirections of all sorts. We’re going to follow it in detail.

![](images/Symbol%20Language%20(2004).392.png)

We start at *a*, the procedure which contains a call, located near the center of the diagram. It calls b, thereby first accessing c. c Redirects to d with an object line. The entering of another object symbol there, is *not* another access. c And d are tightly bound together and go beyond any exits or entrances. There are restrictions as to how such a tight bind is established, but those issues are covered later. d Redirects to e with an object line. Again, the exit of an object symbol and the entrance of another one is not relevant in the process we’re discussing. Then e is bound to f with a type line, making ‘e’ a potential candidate for target object, but only if no other object lines will present itself in the redirection. f Redirects to g with a type line. g Redirects to h with an object line, upon which e looses its candidateship for target object. h Is the end of the redirection so h is both c’s object as well as its type, we give h the alternative names: Oc (object of c) and Cc (type of c). Now we know c’s object and type, we roll back to the access of c, and we continue the journey of our call line. Only one access has just taken place. The other steps were redirections followed for the access.

Next the call line accesses i. i Redirects to j with an object line. j However has both a type line and an object line. A rule discussed earlier told us that in finding target type and object, a type line is ignored if also an object line is present. So we follow the object line to k. k has only a type line, making it a potential candidate for target object. k redirects to l with a type line. l has no lines. k Is the last symbol to be pointed at with an object line, so k is the object of i: Oi, and l is the type of i: Ci. Then we roll back to the call line, that can now enter i.

The call line ends up at b, the called square, but b has a procedure reference line to m. Procedure reference lines are bound just as tightly as object lines and type lines and any symbol exits and entrances are irrelevant in processing a call. m Directs to n, n directs to o. o has to be called.

o Has to be called, but it’s a call to a totally different object. You have to know what object you’re calling so you must find out this symbol’s object and type. 

Because the initially accessed object isn’t called, but another object, it may seem that performing all those previous accesses wasn’t necessary, but it was. In the target object the procedure reference target is stored, so we indeed needed to obtain the target object, and for that the target type too. This object lead us to knowing where the procedure reference leads. To know which procedure is referenced, you have to figure out its parent’s type and object. So one more obtaining of a target object and type is performed on the target procedure’s parent. This is not an access, but the same method is used.

#### Brainstorm

A funny thing about state get is that it has a return value that is an object, nor a procedure. It’s so fundamental, there isn’t a symbol representation for it. ?Other system procedures at least return an integer number?

Ik met echt nog wel meer operator style behandelen.

##### All Object Symbols that are the same Objects have the Same Line Targets

Object stores line targets (except for type members, those are stored in the type). So any object reference has the same line targets. It the object shows that one of its members has a line, that member of other object references  has a line to the same target.

##### System Procedures for Globalities

System procedures of globalities are the same as for other object symbols. The only restriction is that globalities can’t have lines to objects and objects can’t have lines to globalities. Globalities can have an object line, type line and interface line just like objects.

##### New Name for System Procedures

Aspects / System Aspects?
Eigenschap. Karakteristic
Facet
Property
Characteristic
Aspect
Attribute
Determinator, determination
Determinant
Decisive
Systemizer
Formant
Formulator
System
Structure
Coordination
Regulate
Structor
Format
Formation
Formater
Syntax
Configuration
Klep open
Motor

Een beest een bloem een plant een instrument een ding.

Knop
Stopcontact
Stekkers
Bedrading
Wiring
Cords
Klink
Openbaar
Wiring
Infrastructuur
Wegen
Straat
Vertakkingen.
Infra
Wegenmaker
Wegbouw
Channel
Path
Volgen
Follow
Media
Stroom
Waterways
Knoppen
Wiring
Channels
Wire
Cable
Line
Lead
String
Thread

##### To Do

I have to involve text code in explanations about access.

What about interface lines

What about calls to clauses?

Well... maybe if calls to clauses doesn’t work too well I may just forbid it...? Does that have major consequences?

Wow, this also involves GETTING information about the diagram at run time too.

##### Remarks

- Constant parameters is totally missing. I think they’re missing in the C++ summary too!
- I think I still didn’t cover static yet.

- *In the C++ programming language constant parameters can be set at run time when you call a procedure. In Symbol constants are really constant: they will not change at run time and are only set at design time*

##### Exclusive Establishment

#### Brainstorm: How are Line Targets Stored?

Vraag 1:

*Waar en how worden line targets opgeslagen?*

- In een __Line Target__ object <geen goede naam>. Deze klasse bevat een __Exits Integer__ en een __Entrances Integer Array__. De __Exits Integer__ slaat het aantal exits op. De __Entrances__ __Integer Array__ bevat de ordinalen van de symbolen to enter. Een ordinaal is het symboolnummer binnen zijn parent.
- Elke line wordt zo opgeslagen binnen het object dat de line bevat.
- De line source hoeft niets te weten van zijn omgeving en de inhoud van children of cousins om er toch naar te verwijzen
- Pas als de echte line crossings (hoe heten deze symbolen die gecrossed worden?) moeten worden achterhaald, dan worden er traces uitgevoerd. Dit gebeurt bij opvragen van informatie over een symbool (? Oh ja? Krijg je niet gewoon de Line Target object terug? Of krijg je dan wel unieke symboolnummers terug of zo?), bijvoorbeeld bij het uittekenen van het systeem, of bij een call.
- Dit heeft tot gevolg dat bij veranderingen in het systeem, de line target naar onbedoelde symbolen verwijst. Daarom worden bij bepaalde systeemveranderingen (optioneel?) de line sources opgeheven(, of tijdelijk onschadelijk gemaakt?) < moet de term *line source* niet ergens geïntroduceerd worden? >

Dus krijgt elk zichtbaar symbool toch een nummer? Ondanks dat sytematiek opgeslagen is in de object klasse van de globality klasse?

Elke opslag entiteit krijgt een nummer. Een opslag entiteit wordt gerepresenteerd door een symbool. Een gewoon object is een opslag capaciteit. Ook een call is een opslag capaciteit. Een klasse ook, voor de type static delen. Een globality object ook, en een globality klasse ook. Binnen deze opslag entiteiten worden line targets opgeslagen. Wat voor nummer krijg je nou terug bij het aanroepen van een aspect procedure? Niet een opslag nummer, want meerdere symbolen kunnen dezelfde opslag representeren. Hmmm... Ik weet het niet.

I guess each symbol must get its own id, somehow. Recursion is not a problem in this, because recursion doesn’t create infinity, it only creates ~ possible infinity. Each symbol getting an id may be bad when the system changes at run time.

In vele gevallen hoeven er geen symboolnummers te worden gegenereerd in run time. Voor dingen die publiekelijk in de module veranderen kunnen, moeten er dan symboolnummers worden gegenereerd.

Werkt dat wel? Met symbool nummers? Hoe wordt een symboolnummer gekoppeld met een symbool?

Het probleem is nu: wat krijg je terug als je een system aspect procedure aanroept? Hoe identificeer je een symbool enkel symbool?

Het identificeren van een symbool wordt bemoeilijkt doordat een symbool makkelijk van klasse en van interface kan veranderen, waardoor een ander set symbolen ontstaat.

Een line geld voor de hele opslag entiteit van de line source. Als lines naar buiten gaan dan wordt het moeilijker, omdat 1 object bijvoorbeeld zich kan bevinden in 2 compleet verschillende parents. Een line naar buiten kan naar de ene parent z’n inhoud gaan, maar net zo goed naar de andere parent.

*[Picture 1]*

Het opslaan van zo’n __Line Target__ object heeft dus geen zin.

Je moet altijd naar een symbool wijzen in een gecreëerde opslag entiteit. Dus een line target is geïdentificeerd met het symbool in de opslag entiteit. De line source zit ook altijd in een gecreëerde opslag entiteit. Als een gecreëerde opslag entiteit al zijn sub symbolen nummert... 

*[Picture 2]*

Wijs je nou naar een symbool van een object of naar een symbool binnen de referentie van een object?

Nee, dan krijg je verschikkelijke diagrammen.

*[Picture 3]*

Dat is dus niet waar. Een line wijst naar een symbool in een object referentie, niet naar het symbol binnen het object. Dit gaat niet eens alleen over wijzen naar buiten, maar ook over wijzen naar binnen.

Maar wijzen naar binnen is gemakkelijker, want wijzen naar buiten kan 

Oh, als je niet alleen het *aantal* exits opslaat, maar de symbolen die geexit worden? Oh, maar welke ordinalen krijgt die dan. Uhhmm... 

Hè! Poe! Lines opslaan is moeilijk.

Ze worden binnen een opslag entiteit opgeslagen. Nu is het nog onduidelijk hoe de target wordt geidentificeerd.

Het is alleen moeilijk voor binnengaan en verlaten van object symbols. Of niet? Hè, fuck. De target moet gecreerd zijn, maar wijst naar een referentie

Ik weet niet hoe een target wordt opgeslagen. Ik weet niet hoe een referentie wordt geïdentificeerd.

Referenties zijn inderdaad aparte entitieten en ze verdwijnen en ontstaan bij het veranderen van type lines, interface lines en ook object lines als de *klasse* of *interface* van een symbool verandert.

Dus er moet dus maar rekening mee gehouden worden dat als je een symbool van klasse of interface doet veranderen, dat dat gevolgen heeft, vooral als je het extern kan instellen met weinig beperking. Als een symbool van klasse of interface verandert, dan moeten er oude symbolen worden gederegistreerd en nieuwe symbolen worden geregistreerd. Maar hoe koppel je dan die symbolen met hun id. Nou, de registratie zit gebonden aan de parent. Dus je moet het symbool toch identificeren met zijn parent en eventueel grandparent. Dus met een heel pad. Maar hoeveel identificaties je nodig hebt is afhankelijk van de scope. Je identificeerd alleen de diepere containers.

OH! Inderdaad wordt elk symbool in de Symbol database opgeslagen! Aleen als je van klasse of interface verandert, deregistreer en registreer je symbolen. Shit hé, kan je dan toch een symbool met 1 nummer identificeren? Ja. Maar het zit zo: hoe kom je van nummer naar oord en van oord naar nummer? Nou, de relaties tussen de symbolen zitten in een boomstructuur opgeslagen. Je kan met de symbol id naar de parents en children hoppen.

Dus, oh, jee. Ondanks veranderbaarheid van het diagram staat toch elk individueel symbool (dus ook individuele referenties naar hetzelgde object) apart geregistreerd. Je kunt dus alle symbolen identificeren met een nummer.

Als dan dus een line target verwijst naar binnen ergens en opeens verandert de inhoud en bestaat de target niet meer, dan worden de source symbol’s lines maar geannulled.

HEH. Volgens mij ben ik eruit. Je kunt gewoon symbols line targets met een enkel nummer identificeren. De symbol database (in design time, dan) is ook weer wat duidelijker.

Elk symbool krijgt een registratie. De boomstructuur wordt opgeslagen. De lines worden opgeslagen in opslag identiteiten. Elke opslag identiteit krijgt ook een registratie. Als klassen of interfaces veranderen, dan worden er symbolen geregistreerd en gederegistreerd. Een opslag identiteit verdwijnt of verschijnt ook door het veranderen van lines.

Even though a lot of the encapsulation structure can be derived by following type and interface lines, every individual symbol requires a registration, because each symbol can be individually pointed at.

In a call the source and target symbol are tied together with a tight bond. What traces are required now I know that line targets are bonded closer? Well... I’ll find out.

#### Brainstorm

Oh, making type unsettable at run time can be considered a form of genericity. Maybe I should even rename the other type genericity I mentioned. It might be called object-type genericity. Well... settability can also be called variable and constant.

See to it you mention that an explicit type does not fix the type permanently unless you make the Type Set of the symbol Runtime Inaccessible. Oh, haven’t covered access control in detail yet, but that’s not a problem really. 

Before going into

< A Target type can also be called a type definition. The target procedure can be called the procedure definition >

< Apart from brainstorm items scattered around the toughest tasks are:
- Dimensions
- Static and Creation
\>

< If I’m to make a chapter ‘system procedures’ It should cover ALL system procedures. >

< Ergens deze zinsnede:
the Symbol Get, which makes you able to link to an object symbol
\>

<< Access Modifier Get and Set are not mentioned in this sub chapter >>

<< Introduce the term Property in this section. And use it further down. Or find a better word for property. >>

I also wanna cover how lines are set and what happens when ... now I forgot what invalshoek I was talking about.

< Define *exclusive establishment* and *establishment exclusion* somewhere >

#### Brainstorm

#### àSystem Aspects

*This Argument*

< Also discuss the way to call a type’s members directly, while they are ‘object static’ (I haven’t introduced the term object static yet, I used to call it non-static, but object static seems to fit well in the system). So, discuss calling a type’s object static members directly, filling the *this* argument with a reference to the object. Then you also need to figure out a notation for this call when you see the call line. How do you see the this parameter inside the type, or do you only see it on the call to the type’s object static member? >

#### àSystem Aspects

<
*Passing a clause by reference*

```
Procedure ( Parameter . Reference Set ( Value . State = ... ) )
```

Dat is de uitgebreide notatie, in ieder geval. Een wat gebruikelijkere notatie is:

```
Procedure ( Parameter . Reference = ... )
```

\>

### àSystem Aspects

*Exclusive Establishment*

|<p>![](images/Symbol%20Language%20(2004).423.jpeg)</p><p></p>|<p>__Reference to sibling inactive clause, in a square__</p><p></p><p>Only possible for static procedure members or exclusive establishment.</p><p></p>|
| - | - |
|<p>![](images/Symbol%20Language%20(2004).424.jpeg)</p><p></p>|<p>__Reference to sibling active clause, in a square__</p><p></p><p>Only possible for static procedure members or exclusive establishment.</p><p></p>|
|<p>![](images/Symbol%20Language%20(2004).425.jpeg)</p><p></p>|<p>__Call to sibling inactive clause, in a square__</p><p></p><p>This is like a jump to a clause, that would otherwise not execute.</p><p></p><p>Only possible for static procedure members or exclusive establishment.</p><p></p>|
||<p>A diamond can be executing. Only during the execution of the diamond, lines between its non static children can be real. If the diamond isn’t executing, or it’s not a diamond, but a square, lines between the non static children are suggestive. Only lines between static members in such cases, can be real.</p><p></p>|

#### àSystem Aspects

*Exclusive Establishment*

Or to inside static (or to outside : its static, or its exclusive establishment) <?to inside never exclusive establishment because that’s determined by parent.?>

Oh, a reference pointing out of a square is possible only for static symbols, because normal, non-static references to the outside are established on a call. A square can not contain a non-static references to the outside. A diamond can.

If a clause can access anything outside then you should be able to have exclusive establishment of a line going out of a square. But this has the consequence that references to the clause could access things out of the clause’s parent. Well.. this is ok. If it isn’t a clause, but a reference, there is no possibility of this exclusive establishment of a line going out of a square unless the line target is reachable from the definition. < Create the picture in your head as you read that. Anyway, I disagree. It doesn’t matter that it’s reachable by the definition or not. All that matters is that the one setting the line could reach both source and destination. It doesn’t matter if the line source can access the line destination. Funny enough, that does matter. The line talked about is still exclusive establishment, not real, but it can be there as an imaginary line. No problem >

#### àSystem Aspects

__*Exclusive Establishment*__

Diamonds and squares with lines between internals and to internals, real to and between static members, real non-static members in diamond execution and unreal lines based on establishment exclusion in any situation: statics, non-statics, in execution or not. A square’s normal members never have real lines to the outside, only imaginary. except for static members.

#### àSystem Aspects

Referencing static members of a call doesn’t cause procedure execution at all. Static procedure members have the lifetime of the procedure’s object

#### àSystem Aspects: Exclusive Establishment

You will only lay a reference to the contents of a call in the execution of a call. So there can only be references established in places the call execution leads to. This can result in an object’s explicit reference to an argument. When the call ends, though, these reference is annulled.

#### àSystem Aspects: Can’t call Outwards in the Object Ancestry

< That’s not true at all.

What IS true is that you can’t directly access anything outward in the object ancestry. You have to be given a reference to the outside in order to access it. The line that is the call, can go outward, but the line must be set by the outside >

#### àSystem Aspects

If one diamond’s internal lines change, lines of all procedure symbols pointing to the diamond change too. If a static procedure line is changed, all procedure symbols, also all calls with that definition will change.

#### àSystem Aspects

The following rule isn’t true:

*Can’t Call Upward in the Ancestry*

An object should act independent of its surroudings. Unless it *chooses* to be dependent on its surroundings.

< You can make a call to the outside if the type allows you to set a diamonds reference line. Then the container must decide whereto the call leads >


Access Control
--------------

< Apart from system aspects, access control is one of the hardest concepts to understand for beginning programmers (Not a good formulation, right?)

System aspects is the hardest concept to understand of Symbol Language. Access control, I think, is the second hardest. Not to experienced programmers, but more to beginning programmers. Especially its usefulness may be a blur to beginning programmers: access control makes you able to limit the possibilities. <>
\>

< Access control is niet voor beginnende programmeurs. Het is ongrijpbaar misschien, maar zeker onbruikbaar, omdat ze er niet mee om kunnen gaan. 

Wat wel zo is is dat de standaard access control van system procedures er voor zorgt dat je niet *zo maar* rare dingen kan gaan doen. Erg belangrijk als je effe snel iets programmeerd, dat je de echt rare effecten uitsluit zonder extra moeite. >

< Give a story about the true meaning of an access symbol that denotes direction. That it is a syntactically correct access symbol. Access symbols can used to denote direction, because access symbols *can* point out direction. >

<< A procedure’s primary access controller is only made Inaccessible to ‘outcomment’ code. This is a rather small concept. The rest of the use of Inaccessible and Accessible is in exclusion. Therefore, I need to denote in short that this is the only use of the primary access controller. I can basically always speak of access modifiers when talking about Accessible and Inaccessible. I can use the term exclusion in a lot of places where I now use ‘access control’. I also need to put the first section ‘Accessible and Inaccessible’ in the exclusion section. >>

<< Exclusion is restriction set by a container. Level restriction is like exclusion set by a child *for* the container. >>

<< Public and Private are an application of exclusion. So then the base of the explanations can be only accessible and inaccessible.

- Accessible and Inaccessible
    - Diagram notation of those two
- Exclusion (can then already be covered)
    - Private, Public is exclusion
    - Protected
    - Access Modifiers in Globalities needs to be further thought through. It gets tricky as you put it in diagram code.
    - Level Restriction
- Friends
- Access Controllers for System Procedures

< Don’t say that procedures can’t be defined as inaccessible. They have to be definable as inaccessible or you’re not able to ‘comment out’ code. This also requires you to use the term access controllers more often. >

< The word access modification can actually be replaced by ‘exclusion’ in many places, but not everywhere by far >

#### Introduction

Access to procedures can be limited to certain parties by using access controllers.

Access to *procedures* is controlled. But access control usually defines which *objects* get access. In a special case you can control which specific *procedures* get access.

Usually, access to procedures is controlled in a *type* and each of its objects adopts those same access settings. 

Only procedures get access controllers, not objects. Access to an object is controlled by access controllers of the Target Object procedure.

#### Exclusion

##### Accessible and Inaccessible

The two basic access controllers are *Accessible* and *Inaccessible*. Their diagram notations are as follows:

|<p>![](images/Symbol%20Language%20(2004).426.png)</p><p>*Accessible*</p>|<p>![](images/Symbol%20Language%20(2004).427.png)</p><p>*Inaccessible*</p>|
| :-: | :-: |

The meaning of them is as can be expected: the Accessible square is accessible, while the Inaccessible square is inaccessible This basic notation does not show which parties get access and which do not.

The symbols used here are actualy access symbols, which I’ve already introduced. Access symbols can denote direction, and they also denote where access takes place, but they’re also used to denote access control.

##### Exclusion

< A way to pronounce access modifiers for deeper depths than 1 so access modifiers other than accessible, inaccessible, public or private >

Exclusion is the primary method for controlling which parties get access to a procedure.

A type controls which of its procedures are accessible to the outside (*Public* procedures), and which are *not* accessible to the outside (*Private* procedures). Private procedures *are* accessible to the *inside* the type.

Apart from controlling access to the type’s own procedures, a type can also control publicity of procedures *of its chilren*. That way you can publish a child, but make some of its public procedures inaccessible outside the parent. This way you can also exclude members of a base type. A parent can’t make a child’s procedure inaccessible to the child itself; it’s the child’s own procedures.

You can also exclude members of ancestors even further down the hierarchy.

Forms of exclusion other than Private are just called exclusion or privatising.

You can only make a procedure of a child *less* accesible, never *more* accessible. The parent can’t publish a child’s procedure that the child defines as Private. A child can’t put restrictions on how its members are privatised by the parent, so a parent has full control over the exclusion of the procedures its ancestors.

Exclusion access controllers are also called *access* *modifiers*, because they modify formerly set access controllers.

##### Diagram Notation of Exclusion

Public and Private are notated as follows:

|<p>![](images/Symbol%20Language%20(2004).428.png)</p><p>*Public*</p>|<p>![](images/Symbol%20Language%20(2004).429.png)</p><p>*Private*</p>|
| :-: | :-: |

The reason that the following notation won’t do:

|<p>![](images/Symbol%20Language%20(2004).430.png)</p><p>*Not Public*</p>|<p>![](images/Symbol%20Language%20(2004).431.png)</p><p>*Not Private*</p>|
| :-: | :-: |

is that this access modifier is imposed by the procedure itself, not by its parent.

The reason that the following notation won’t do:

|<p>![](images/Symbol%20Language%20(2004).432.png)</p><p>*Not Public*</p>|<p>![](images/Symbol%20Language%20(2004).433.png)</p><p>*Not Private*</p>|
| :-: | :-: |

is that the access symbols in these diagrams are about access to the object, not access to the procedure of the object.

Each descendant that has access to the procedure can impose its own access modifier upon it.

![](images/Symbol%20Language%20(2004).434.png)

In this example A privatises P. The marks and the access controller are called an access controller list. The whole access controller list can be interpreted as a single symbol, which can be called the access symbol. An access controller can be placed on each mark. Each position in the access controller list represents the access modification of a deeper laid symbol. All access modifications are imposed by A. The first position modifies access to A itself, the second position modifies access to B, the third position modifies access to C, thus the fourth position modifies access to P. The marks are called *access marks*, not to be confused with the term ‘access symbols’.

Very deep exclusion is uncommon, so you usually won’t interprent more than one or two access marks.

![](images/Symbol%20Language%20(2004).435.png)

*Privatisation is the last access modification*. Once an descendant has excluded the member, higher descendants can’t exclude the member again, because they can’t access the member.

B has excluded P, so A can’t exclude P again. Both access symbols above are about access to P. The first position of the access controller list is always about access to the symbol that defines the access controller list. Not all positions of the access controller need to be displayed. The last positions can be left out at will. That means that the last access controller doesn’t have to be about the line target, but can be about an intermediate access.

Let’s cover how to interpret the examples I’ve already mentioned.

|![](images/Symbol%20Language%20(2004).430.png)|![](images/Symbol%20Language%20(2004).431.png)|
| :-: | :-: |

With *these* access modifiers, the *procedure* is making itself accessible or inaccessible.

|![](images/Symbol%20Language%20(2004).432.png)|![](images/Symbol%20Language%20(2004).433.png)|
| :-: | :-: |

With these access modifiers, the *object* is making *itself* accessible or inaccessible.

![](images/Symbol%20Language%20(2004).428.png)

This shows the access symbol for Public. The object is making the procedure accessible to the outside.

![](images/Symbol%20Language%20(2004).436.png)

This shows the access symbol for Private. The object is making the procedure inaccessible to the outside. The procedure *is* accessible *in*side the object. You could denote this:

![](images/Symbol%20Language%20(2004).437.png)

The extra access symbol denotes that the procedure makes itself accessible. The access symbol of the object makes the procedure inaccessible to the outside. Procedures are usually accessible to the object symbol they are directly contained in, so the extra access symbol is not really required.

A parent can’t make a child procedure inaccessible to the parent. The effect of this rejected concept is basically identical to giving the child its own abstract type: a derived type that excludes members of its base:

![](images/Symbol%20Language%20(2004).438.png)

The parent contains a child object. The type of the child is defined right inside the parent: __Abstract Type__. The type is based on the complete type. The abstract type simply excludes a few members. You don’t always need to show the excluded members. In some views you will only see the published members:

![](images/Symbol%20Language%20(2004).439.png)

##### A Procedure’s Set of Access Controllers

Exclusion adds a whole set of access modifiers to a single procedure.

![](images/Symbol%20Language%20(2004).440.png)

The access symbols in blue are the procedure’s access controllers. The dark grey access symbols are also the procedure’s access controllers, but these were already defined in type A. You can see that in any other type that uses an object of type A, a new set of access modifiers can be imposed. You see that each access controller of the single procedure is shown at a different symbol. The access modifier for a procedure is shown close to the type that imposes the modifier.

##### Changing Access Modifiers at Run Time

Being able to change access modifiers at run time may be interesting. That way you can for instance change the interface of an object dependent on its settings. Changing a procedure’s access modifier is done by calling the procedure’s Access Modifier Set system procedure. There’s also an Access Modifier Get procedure to obtain the access modifier. This adds two system procedures to a square:

- __Access Modifier:__
    - __Get and Set__

The Access Modifier property procedures can be access controlled themselves, so that they can be made inaccessible, for instance when you don’t want to be able to change the access modifier at run time. The access modifiers of the Access Modifier property can’t be changed at run time themselves. In other words: the Access Controller property procedures don’t have an Access Controller property of their own. This complies with the rule: system procedures don’t have system procedures of their own. 

A single procedure can have several access modifiers so there are multiple access modifiers to get and set. This would suggest that the Accesss Modifier property has a dimension. However, when you call the Access Modifier property, you return or set the access modifier imposed by the object you’re calling from. The object you’re calling from is a hidden argument to the Access Modifier property. The access modifiers aren’t really stored inside the procedure, but in the object symbol that imposes it.

If the access modifier isn’t variable at run time, then the type defines a fixed access modifier. If the access modifier *is* variable at run time then the access modifier can be different for each instance of the type.

##### Inclusion

Apart from a *decisive* access modifier, you can also give a procedure a *suggested* access modifier. This means that when you put an object in a type, a procedure of the object will get its *suggested* access modifier, for instance Private, but if its *decisive* access controller is Public, then you can still upgrade it to Public. This is called *inclusion*. The suggested access modifier is always set to less accessible than the decisive one. A type can also give suggested access modifiers to procedures of ancestors.

##### Exclusion of System Procedures

Exclusion (and inclusion) can also be applied to system procedures. Exclusion is actually very important for system procedures. An object symbol’s Target Object procedure must be accessible to make you able to call its procedures. When you control access to the Target Object procedure, you can for instance set the object to be accessible privately, but not publically.

Exclusion of Set procedures controls who can set a symbol’s lines. Exclusion of Get procedures controls who can get information about lines or who can access the object.

Exclusion of system procedures of procedures also gives parents control over setting call or  reference lines and getting information about the lines.

##### Interesting Applications of Exclusion

So examples of interesting applications of exclusion are:

- Making procedures Public or Private
- Excluding procedures of a public object
- Excluding procedures of a base object
- A parent’s controlling *access to objects*

##### Protected

There is another basic access controller in addition to Accessible and Inaccessible: *Protected*.

![](images/Symbol%20Language%20(2004).441.png)

*Protected*

*(By the way: it’s not an arrow.)*

When a procedure is *Protected*, it means that it’s inaccessible if contained in a circle, but accessible if contained in a triangle. 

|![](images/Symbol%20Language%20(2004).442.png)|<p></p><p>≈</p>|![](images/Symbol%20Language%20(2004).443.png)|
| - | :-: | - |
|![](images/Symbol%20Language%20(2004).444.png)|<p></p><p>≈</p>|![](images/Symbol%20Language%20(2004).445.png)|

A circular descendant automatically privatises a Protected member:

|![](images/Symbol%20Language%20(2004).446.png)|<p></p><p></p><p></p><p>≈</p>|![](images/Symbol%20Language%20(2004).447.png)|
| :- | - | :-: |

The member isn’t accessible to any higher symbols than the first circular descendant.

Formally the choice of making an extra Protected access controller seems totally arbitrary. In practice there are situations in which it’s useful to work with members that can be accessible to the interface holder, but not accessible to the outside.

Protected is used in exclusion only. It can not be used for ‘outcommenting’ code.

##### Level Limitation

######## Object Level Limitation

Basic access controllers are decisive, but level limitation adds additional restriction. 

Level limitation is paired with the basic access controller.

Pairing object level limitation with the Public access modifier, makes a procedure public only to limited number of levels up the ancestry.

__Public *Up 2*__

A procedure with this access modifier is accessible but two levels up the ancestry. Outside those levels, the procedure is inaccessible.

|*No object level limitation: Public*|
| :-: |
|<p>![](images/Symbol%20Language%20(2004).448.png)</p><p></p>|<p></p><p></p><p>≈</p>|![](images/Symbol%20Language%20(2004).449.png)|
|*Object Level Limitation: Public Up 2*|
|![](images/Symbol%20Language%20(2004).450.png)|<p></p><p></p><p>≈</p>|![](images/Symbol%20Language%20(2004).451.png)|

Level limitation works the same for the Protected access modifier, but gets the additional restriction that comes with that access modifier:

__Protected *Up 2*__

A procedure with this access modifier is accessible two levels up the ancestry, but inaccessible outside the first circular descendant.

|*Protected Up 2, contained in three triangles*|
| :-: |
|<p>![](images/Symbol%20Language%20(2004).452.png)</p><p></p>|<p></p><p></p><p></p><p>≈</p>|![](images/Symbol%20Language%20(2004).453.png)|
|*Protected Up 2, contained in a triangle contained in two circles*|
|<p>![](images/Symbol%20Language%20(2004).454.png)</p><p></p>|<p></p><p></p><p>≈</p>|![](images/Symbol%20Language%20(2004).455.png)|
|*Protected Up 2, contained in three circles*|
|![](images/Symbol%20Language%20(2004).456.png)|<p></p><p></p><p>≈</p>|![](images/Symbol%20Language%20(2004).457.png)|

Level limitation can also be applied to deeper exclusion than Public and Protected. So a parent can impose level limitation on a child procedure.

|*Level limitation on deeper exclusion*|
| :-: |
|![](images/Symbol%20Language%20(2004).458.png)|<p></p><p></p><p></p><p></p><p>≈</p>|![](images/Symbol%20Language%20(2004).459.png)|

You can also apply level limitation for on symbols shalower than the target procedure.

|*Level limitation on deeper exclusion*|
| :-: |
|![](images/Symbol%20Language%20(2004).460.png)|<p></p><p></p><p></p><p></p><p>≈</p>|![](images/Symbol%20Language%20(2004).461.png)|

Level limitation is defined there where it doesn’t have effect yet. It only has effect higher in the ancestry. Basic exclusion is always defined there where it has effect. So level limitation automatically excludes members at *n* levels up the ancestry.

< Figure out a better diagram notation. >

######## Globality Level Limitation

<Pictures>

Apart from object level limitation there is also globality level limitation.

__Public *Globality Up 1*__

When an access modifier is paired with a globality level limitation, the access modifier works normally *n* level up the *globality ancestry*. But for higher globalities the member is inaccessible.

|*Public*|
| :-: |
|<p>![](images/Symbol%20Language%20(2004).462.png)</p><p></p>|<p></p><p></p><p>≈</p>|![](images/Symbol%20Language%20(2004).463.png)|
|*Public Globality Up 1*|
|<p>![](images/Symbol%20Language%20(2004).464.png)</p><p></p>|<p></p><p></p><p>≈</p>|  ![](images/Symbol%20Language%20(2004).465.png)|
|*Public Globality Up 2*|
|![](images/Symbol%20Language%20(2004).466.png)|<p></p><p></p><p>≈</p>|![](images/Symbol%20Language%20(2004).467.png)|

Protected Globality Up N works the same as Public, but adds the extra restriction that comes with protected.

< Pictures with that? >

< ‘Globality Up 2’ is too long, because Public Globality Up 1 will be used commonly. Visual Basic’s Friend access modifier is the same as Public Globality Up 1. I might need to invent a specific term for Public Globality Up 1. I won’t use ‘Friend’, because that would conflict with >

##### Exclusion in Globalities

Access modifiers in Globalities:

- Global Inaccessible
- Global Private
- Global Public

To understand what happens when procedures inside globalities are given access controllers you need to view the globality as an object, that is referenced from any of its ancestor objects:

|![](images/Symbol%20Language%20(2004).468.png)|<p></p><p></p><p></p><p>≈</p>|<p></p><p>![](images/Symbol%20Language%20(2004).469.png)</p>|
| - | :-: | - |

If a global procedure is Inaccessible, it’s just not accessible at all (*‘outcommented’*), so not really global either. If a global procedure is Private, it’s not really global either, only accessible by the globality object itself, just like something private of a circle object. If a global procedure is Public, then it *is* global. It is then accessible from any ancestor within the globality. 

When a global procedure is Public it is however also accessible *outside* the globality, as a public procedure of the globality object. For a procedure to be global inside the globality, but not accessible outside the globality you use globality level limitation: __Public Globality Up 1__.

It is not a permitted to make a global procedure Protected. A pentagon is not exchangable with a triangle, so Global Protected wouldn’t have much meaning.

#### Friends

In types, globality types, procedures and clauses you can define *Friends* of the symbol. Friends are other symbols that when defined friend get full access to all members of the befriended.

It only goes one way: the friend symbol can access private things of the befriended, but the befriended doesn’t get access to the friend’s private members. Its kind of a like a sick friendship where one likes the other, but the other doesn’t like him back. That’s why the symbol that defines his friends is called the *befriended*, not a friend itself.

A type, globality type, procedure or clause can define:

- Friend Types
- Friend Procedures
- Friend Globalities

Which grants its friends full access to the private and protected members of the befriended.

< Diagram notation >

##### Brainstorm

<< Om er een (nog) makkelijkere uitleg aan te geven:

Je hebt *eigenlijk* alleen befriended types. Befriended types geven toegang tot al hun procedures. Als je een friend toegang wilt geven tot maar een selectie van private procedures moet je de friendship bij die specifieke procedures vermelden. >>

Onderscheid tussen befriended procedures en befriended types aangeven.

Exclusion is the primary method for access control. Friends is the method to make exceptions to the privatisation imposed by exclusion. A procedure or type can make any other procedure or type they can reach a Friend, meaning that that procedure or that type has access to all members privately accessible in the befriended.

< ... Copy most from the old stuff >

#### System Procedures with Access Modifiers

< 
I don’t have a special notation for publicity of Set procedures.

Set public or not is kind of like read only or not. Maybe I need a read only notation.

Write only is also common, though. For instance of procedure reference input parameters.
\>

< Also cover constants >

Access can be controlled for regular procedures this way. You can also control access to system procedures. When you make an object Private, you’re in fact making its Target Object procedure private (which can even get different separate access controllers for Access, Run Time Copy and Design Time Copy).

When you give a system procedure an access controller, access to the procedure or object represented may get a special name and diagram notation.

An object symbol with an accessible State *Read* procedure, but no State *Write*, is called a Read Only Object.

An object symbol with only a Type Read, can be considered just a Type. Not an object or interface.

An object symbol with only an Interface Read, can be considered just an Interface. Not an object or type.

...

Etcetera, work it all out

Standaard access controllers

- Standaard zijn Add en Remove geblokkeerd. Zo zijn er nog meer dingen standaard geblokeerd

De klasse kan zelf initial access controllers aannemen die je ook weer kunt veranderen.

##### Constants (Brainstorm)

< oops the following text can not be put in the introduction >

Design Time Set and Design Time Copy *are* actually called at run time, because nothing is set at design time. Design Time Set, though, can only be called in the Create procedure of the closest mutual descendant. Actually, a set in the create procedure is actually a call to the Design Time Set and Design Time Copy.

Something is constant if it can be Design Time Set, but not Run Time Set. The initialization of constants happens in the Create procedure of the mutual descendant. < <OR THE one that defines that the set is only for design time?> Explaining that would require knowledge of exclusion.>

##### Default System Procedure Configuration

< By default everything is public. When studying the access configuration of a symbol you might only want to see what differs from the default >

##### Access Symbols of Lines, Other Than Call Lines

A line other than a call line can show access symbols, while there aren't really any access. These access symbols represent accesses made by the mutual descendant when it set the line. Accesses did occur on calls to the Set and Copy procedures of the source and target symbols when the line was set.

Access symbols are also used in a diagram only to indicate the access control. In that case there’s no question of an access either. Only of an access that might or might not occur.

##### Smaller Issues

###### Access Symbols Represent Accesses

< Just find an appropriate time to mention that each access symbol represents an access, but that it’s also used to denote direction, simply because direction can be read from it >

###### Grouping Member with Identical Access

<< ... yes this is  a section >>

Shit. What if you want to group members that are excluded. Then the parent adds a grouping to the child type. Oops this grouping is not part of the child type. Well.. it can’t be used then.

I can use this notation:

![](images/Symbol%20Language%20(2004).470.png)

###### Comparison to Other Languages

####### Visual Basic Friend Members

<< I have to note the application of the Visual Basic Friend access modifier. The basic access controller Friend isn’t required (Public Friend and Protected Friend). Friend Basic Access Controller means that you make a procedure’s own globality a Friend globality.

Yes, but for the effect of the Visual Basic Friend access modifier you also need to deprive global members from being accessed outside the globality. And that is done with globality level restriction.

So the effect of the Visual Basic Friend access controller is replaced by • making the globality a friend of the procedure and level restricting global procedures.

NO! It’s just making it Globality Up 1! Nothing Else! Do not use a Friend Globality for specific procedures! >>

####### C++ Friend Functions

####### C++ Friend Types

####### So Symbol...

Has put all of the language’s access controllers in one system and added extra useful systematics.

##### Brainstorm

< The standard access modifiers for system procedures of procedures symbols directly inside a procedure symbol are different from procedures directly inside object symbols. For instance, Symbol Get for Reference of a clause is Private by default. Symbol Get for Reference for an object member is Public by default >

< There are also situations in which you want to disallow copying object reference to an argument, but only allow consult of the argument. (that’s access control of system procedures, actually) >

#### Automatic Changes when Editing Code

When you for instance use triangles to group members of an object, then the access modifiers need to change. When first you accessed something one capsule deep, is accessed two capsules deep when you put a triangle or circle around it. Access modifiers change accordingly when you edit code:

< P: Circle with public procedure >

< P: Trangle put around public procedure, changed access modifier >

< P: Circle with public procedure >

< P: Circle put around public procedure, changed access modifier >

You can’t *always* just put circles and triangles around everything. You might have to adjust access controllers, which are explained later. < Is that so? >

#### Brainstorm

A call is by default private.

The access controllers of the procedure’s sub objects determine which purpose they serve. Maybe I should write a section about that in Access Control.

Required and Optional parameters as well as In, Out and Thru need to be rediscussed in Access Control, because it may be so that it is required for you to Object Set a parameter, while the procedure changes the state of the target 

object. This is like thru too, but a totally different fashion and there are more  ways of throughput.

Oh, optional parameters are initialized and then assigned the caller’s value. Where are those two steps performed.

Maybe it's a good rule to only show access symbols to denote:

- Direction
- Exclusion of a procedure
- Denote explicitly the publicity

If a configuration of any sort is a common one, it might be nice to make something like a typedef so you give the configuration a name of its own, Like if you commonly use ‘Public Up 1 Globality Up 2’, you might want to give it a different name.

Mayve access controllers are a step into the direction of security. Mayve security should be a kind of advanced access control.

Procedure primarily Inaccessible: This seems unuseful: why not just leave the procedure out completely? It could be used a means to temporarily deactivate code.

##### Access Controller Parts

In one access controller you can use an exclusion access controller, an object level restriction *and* a globality level restriction:

- Protected Up 1 Globality Up 2

Access controllers as such are not usual, though and *if* you use them, they’re not very diverse.

##### Brainstorm

When being a triangle:

Basically you can optionally totally redefine the access for the case when the type is a used as a triangle.

Protected is a form of that.

< When being a globality? >

Using triangles to group members with equal acccess controllers. As with exclusion, the access controller of the triangle limits access again. It won’t make things *more* accessible.

Initialization

Sometimes you want to give a specific party access to a private procedure. Such a procedure *befriends* itself with with a specific type or procedure. The friend type or procedure can access anything private or <> otherwise anything marked as friend for that type <>... 

Friend Function: a function that uses the befriended type in a way. It gets access to private members or access to a selection of private members especially selected for the function. The befriended type must be able to access the friend function in order to make it friend.

Friend types must also be accessible to the befriended type.

Only types can be befriended. Friends can be both types *and* separate procedures.

<< So you can choose to give friends access to all private members or, another method, which requires a different syntax, allows you to make a selection of private things public to friends.

I need to cover the notation of access controllers here for system procedures with multiple access controllers, unless I eventually put the Access Controllers chapter before the System Procedures chapter. In that case I have to cover the it in System Procedures.

#### Old

< Also look at Access Media  : Interface Access >

<<
Does genericity control what happens on the call of system procedures or if the call to a system procedure is illegal or not?
\>>

<< Introduce more system procedures here:

Type Generic Get
Type Generic Set
Interface Generic Get
Interface Generic Set
Procedure Reference Generic Get
Procedure Reference Generic Set

Here and no earlier

\>>

<< is that the same or different from being able to change type at creation or assignment of object reference ?>>

<<
Old:

A symbol’s type or interface can be generic or explicit.

Generic:

- Generic type: a symbol always adopts the type of its object.
- Generic interface: the interface is the default interface of the type

The type of the object may be generic too. The interface of the type might be generic too. <...>

Explicit:

- The type of the symbol is defined and must match with the type of the object
- The interface of the symbol is defined and must be supported by its type

Assignment can occur by two means: explicit assignment and generic assignment.

The type of the assigned object may be generic too. The interface of the assigned type might be generic too. But the tied together symbols change simultaniously.

Explicit:

- Explicit type:
    - When you assign the object:

It must have this type or an exception occurs

- When you assign the interface:

The type must support the interface or an exception occurs

- Explicit interface: 
    - When you assign the type:

The type must support the interface or an exception occurs

- When you assign the object:

The object must be of a type that supports the interface (?)

You can change whether or not a type or interface is generic. It is a separate aspect of the symbol. Genericity of type doesn’t mean that it’s of type Object or something, because whenever a symbol has an object, it has a specific type: the type of the object. Whether a symbol has a generic type or interface or not can be set as runtime. Except when the type has been made constant on that part: always a generic interface or always an explicit interface, always a generic type or always an explicit type. Always an explicit type does not mean that the type is constant. The type just always needs to be assigned explicitly, but *can* vary.

\>>

If a symbol already has a type line it has to have that type. If it doesn’t have a type line then it gets the type of the object it’s pointing at (not considering the interface problem below) 

##### Interface <>

Something like this should be possible:

![](images/Symbol%20Language%20(2004).471.png)

The point is in the lines of the child of the top symbol. It’s type line points to the center symbol, but it’s interface line points to the interface of ONE of its types interface implementations, not to the joint interface implementation of the type. You have to be able to do this.

But it goes against rules I set up earlier. So there has to be more flexibility with interfaces.

The type line no longer determines the interface line.

Ah, more rules need to be invented for working with interfaces.

The type line is pointing at the center circle, but implicitly points at one of the right triangle. So there’s an invisible extension to the type line. The extension changes with the interface line of the source symbol. However... the interface of the child determines which interface is implicitly pointed at by the type line. This seems an explicit/implicit subject.

Another direction rule can be added I guess, looking at the implicit piece of the type line: Sooner to exit from a circle as line source than to exit from a triangle as the line source. <that rule needs some reformulating, though.>

The rule about the type line determines the interface line stays. It’s just that there’s an implicit extension to the type line, which can be generic, pointing at the interface that is the interface of the child...

##### Type

If you redirect with an object line then the object reference gets the same type as the target object (except when you use a different interface, the previous problem I introduced). Not all the symbols will get a line to the type, though.

##### Operators

|Type Generic Get:|~::|
| -: | - |
|Type Generic Set:|~:: =|
|Interface Generic Get:|~:|
|Interface Generic Set:|~: =|

<< Maybe I’ll do special operator symbols in text code that represent the object relations. Actually, that’s what I’d like a little. Except member access. I wanna keep that. >>

##### Exchangable Object and Procedure Notation

###### Access in Object Representation

In the object representation, You don’t see that you’re calling a system procedure when you call an Access or Get procedure. In the diagram that looks just like referencing a symbol using an object line, type line or interface line:

<< Picture >>

###### Access in System Representation

In the system representation you see all access to an object as a call to one of its system procedures. 

<< Picture >>

And here I draw out both representations on top of eachother, one representation in one color and the other representation in another color.

<< Picture >>

###### Other

####### 1

<< The exchangability of method and object notation >>

<< You CAN display a method as an object. You’d then display it as its return value(s) >>

###### 2

You can view a procedure as the object that it returns.

< Picture: Procedure with some private contents and one public object with some contents >

\=

< Picture: Object returned >

Actually, the objects symbols I’ve introduced before *are* the object representation of procedures. They are representations of procedures that return objects.

Here you see that you have multiple representations of something: you can see the system as a bunch of procedures or you can see it as a bunch of objects, but it’s still the same system.

If you regard something a property, which you often will, the primary representatioin of it is its object representation. If you regard something a method or if the procedure doesn’t return a value, then its primary representation is the procedure representation.

####### 3

Conversely, a procedure can apart from it’s usual representation, be represented as the object that it returns.

Procedures

Previous explanations were required before I could go into the more advanced topics about procedures.

##### Brainstorm

Er moet access control zijn voor het stellen van lines, bijvoorbeeld naar de inhoud van een parent.


Text Code
---------

Brainstorm
----------

I need changed events to exist automatically

Perhaps include some appendices that now ended up in Advanced Symbol Language.

< op veel plekken ontbreekt de uitleg van de toepassing. Het lijkt alsof als ik de theorie op papier heb, ik de toepassing maar uitwis. Introduction gaat helemaal over de toepassing. Objects Basics en Procedure Basics daar is de toepassing compleet zoek. Access Control daarbij is de toepassing ook helemaal zoek. Waarom heb je dat soort access controllers? Waarom moet je global access hebben en waarom clause access? In Lines lijk ik nu wel wat meer voorbeelden te behandelen, maar alleen maar omdat ik er aan werk. Als ik dit nu niet op zou hebben gemerkt zou ik straks een theorie hebben geformuleerd in lines en de toepassing compleet weggeveegd. Ik moet meer de theorie en toepassing combineren. Ok, je moet een theorie *vormen*, en uiteindelijk moet je de theorie apart op papier hebben, maar na het vormen van de thoerie is uitleggen van de toepassing niet opeen onbelangrijk. Dit gebeurt echt vaak in boeken. Ze komen maar met de theorie en de voorbeelden ervan zijn compleet achter wege gelaten. >

In C++ bepaal je de redirection diepte vooraf:

Int \*\*\*TripleRedirected

In Symbol kan je de redirection diepte achteraf bepalen

Als je in C++ een object referenties toewijst aan een object referentie, dan wijs je niet naar de object referentie, maar naar het target object. Symbol heeft meer structurering hier.

Een vergelijking C++ – Symbol is als bijlage misschien wel mooi.


Symbol Language Advanced
========================

### About These Advanced Topics

The topics above are essential. Unfortunately, other parts documentation is also needed to describe essential things to complete the language.

__Language Integration__ required for e.g. __Literals__ and __Operators__.

Part of __Data__ is required for e.g. __Arrays__ and __Strings__.

Part of __Sigma Math__ is required for __Arithmetic, Comparative and Logical Algebra__

Other topics can be considered advanced, because the basic topics contain everything supported by C++. The advanced topics only add to that.

Perhaps, quite possibly, a functional description of Basic Sigma Math must be contained in this book. As such, also the functional description of the data modules for Arrays and Strings. 

The functional use of Math objects and simple Data objects is actually a very simple subject. I should be able to devote a chapter to it in the Symbol book.

*If* I put a simple description of the use of *literals* in *System Aspects* and a simple description of *operators* in *Data & Math*, then I could make the topics above a separate book. Then I can make a book *Basic Symbol Language* and a book *Advanced Symbol Language*.

This all just in order to finish a book. And to finish a description of those parts of the programming language that  contain everything C++ does.

### Overlapping Hierarchies

< Traingles can converge types, right? Give a symbol three types? Think about that. >

< ook geen objects onderwerp >

< Rename this section >

< I have to use sheer triangles for *pure* overlap establishment. >

< Circle structure and triangle structure as separate hierarchies. One was originally  called containment hierarchy, while the other was called the inheritance hierarchy. >

< Procedure and object hierarchy regarded separately... >

Members can be grouped by different criteria. Groups can overlap, therefore triangles can overlap. This goes against object oriented programming, because objects can’t overlap.

To establish this:

< P >

The following is done:

< P >

Each interface has a shared part that way.

A and B share an interface by putting a traingular object symbol inside both A and B and connecting them with an object line makes them represent the same object. A and B basically both contain the object. In that sense, containment can overlap. Lines are a way for one object to have multiple containers. Lines are a way for objects to overlap.

You aren’t limited to traingle symbols to make objects overlap. You can also use an overlapping notation for circular objects:

< P >

But let’s take the triangles as an example further.

The overlapping parts are different object symbols in the non overlapping notation. If you access something in the overlapping notation, it is like you access only one border:

< P >

While in the non overlapping notation you access two. For triangles, which merge with their container, this is not a big problem, because triangular borders can be ignored in a lot of situations. With circles you might want to denote in the overlapping notation that you access another border:

< P >

This conforms with both normal border notation and peel notation.

If you use lines only to get an overlapping structure, you probably used triangles to tie the overlapping parts together. There are so called non-object triangles that are used to group members. Non object triangles are objects in the system and have almost same capabilities, but it’s simply ignored that they’re objects. Type interface genericity also doesn’t work on non object triangles. Only when you tag a triangle as being non object, you won’t get double capsules in the overlapping parts.

< P: no double capsules for overlapping parts. >

The overlapping parts are not separate capsules: it represents space in both capsule A and B.

That way you’ve just used the lines between triangles to denote overlapping parts. This is mainly only useful if you’ve used connected triangles for the sheer purpose of grouping members.

With circular symbols it’s quite logical to display double capsules in overlapping parts:

< P: two circles with each a parent circle, both of which are connected. >

< P: its overlapping notation >

A and B both contain C. Therefore C is notated in the overlapping area.

##### Containment for Divergance, Lines for Convergance

This suggests that a line structure can represent part of the containment.

Normal containment is a tree like structure: one thing contains multiple things. Using lines you can make the tree branches convert again: multiple things contain one thing. Convergance can be displayed in the overlapping notation. So the effect of lines can be displayed in an overlapping notation.

In a normal diagram, *containment* is both the divergence structure of the *object structure*, *type structure* and *interface structure*.

< P >

Containment in the diagram is like three hierarchies in one: all three hierarchies are the same. serves all three hierarchies. 

< P: object containment, type containment, interface containment, same pictures >

Each line type creates the convergence structure for a different hierarchy: object lines establish the *convergence* structure for the object structure, type lines establish the convergence structure for the type structure, interface lines establish the convergence structure for the interface structure.

Containment creates the same tree out for all three of the hierarchies. Convergence, so lines, can hef op the branch out:

< P: Two layer tree out. >

< P: Type tree out heffed op. >

That way the three hierarchies can be made independent of eachother. The example above is a perfect way for part of the branch out, that the containment structure imposes, to be lifted, anulled, ignored. In the case above, the type structure ignores the split up in A, B, C, D and E. A, B, C, D and E are still separate objects: the object structure still makes a split up, but the type structure does not make a split up.

The example above, though, does not establish convergence in the type structure. The type structure is as follows:

< Circle in circle >

To completely lift up the branch out you can do the following:

< P: containment notation 1, 2 >

< P: type containment >

The last picture is still called overlapping notation. You can see that the overlapping notation does not show all the details about the lines. It just shows their resulting effect.

##### Triangles for Arbitrary Groupings

In the programming environment, triangles can be used to group members by criteria, without the triangle’s being real objects. The triangles are then just used as marks. In that case there can be overlapping triangles, but the triangles aren’t objects.

< Perhaps I should allows non existant triangles: triangles that aren’t object capsules. I might want the programmer to have control over them. Triangles used for the sheer purpose of creating an overlapping structure can then be made non-object, so that no double capsules need to be displayed in the overlapping parts in the overlapping notation.

##### Procedures can Overlap

Procedures can overlap all the same, because they are much like objects.

< Does this add two more hierarchies? Call and procedures reference hierarchy? >

##### Another Thing

A View Where Lines point to target objects?

### Diagram Metrics

< Those molecular like pullings of line connections >

#### Symbol Placement and Proportion

#### Line Alignment

- 1: Line convergence is...
- 2: Dimensional convergence with only target convergance
- 3: Dimensional convergence with source convergance and target convergence
- 4: Disturbance of convergance:
    - Alignment disturbance
    - Angle disturbance
    - Solutions for disturbance
        - Total solution annuls convergence completely
        - Two metric rules create convergence again:
            - Lines go from center to center
            - Symbols are proportionate.
                - Rules:
                    - To their encapsulation level
                    - To the quantity of contained symbols
                - When proportionality causes a deeper object to be smaller, then it works *with* the convergence. Then proportionality causes a deeper symbol to be bigger, it works against the convergence and can actually show divergence. < However lines still group themselves together >. It’s encapsulation level fighting against quantity of contained symbols.
    - Exact and approximate alignment
        - Simple example allows exact alignment. This situation occurs in many places in a diagram
        - Complexer example shows inaxact alignment:
            - More than two children
            - Both source and target convergence
        - Multiple lines fight.
- Exaggerated convergence
    - Quanta of a distance unit
    - Varying distance unit over line segments
    - Removing dimensions from the line convergence
    - Varying the presence of dimensions over line segments.
    - Varying Quanta of distance unit between two crossings
        - This rule is a part annihilation of the exaggerated convergence.

I have to have a term for the piece of line in between two crossings: line segment.

Do I need to cover proportionality of symbols here. I could. I could upgrade this subject to symbol metrics in general.

__Sometimes symbol proportionality and placement is compromised for the sake of alignment.__

1: Line convergence is the metric phenomenon, that lines converge towards mutual targets. As they travel, they move closer and closer to one another.

2: When multiple borders are crossed. \< a dimensional convergence onstaat \>

3: In the previous example only the target symbols were part of an encapsulation structure (or the souce symbols, if you reverse the direction). When both sources and targets are part of an encapsulation structure, there is both groupage by source as well as targets. Actually there is groupage by any crossing and by eventual source and target symbols>

4: The symbols in the diagrams above were properly aligned to show the convergence of lines best. The symbols were lined up by line target. Not like this:

< P: symbols not aligned, lines crossing a lot >

That is one disturbance of the convergence. It causes lines to cross. It’s called order distrurbance or cross distrurbance. The lack of this disturbance is called source-target alignment. Another disturbance is the following:

< P: aligned more paralel. Convergence angle decreases. >

This disturbance causes the angle of the convergence structure to decrease. This disturbance is called angle disturbance. The below is the extreme example of that.

< P: aligned paralel. Lines melt together. >

To limit the disturbance of line convergence, Symbol should be order by target:

< P: original, neat alignment >

Which is the same as ordering the target symbols by source. Switch the order of either and you ge this effect:

< P: use rainbow colors to denote which order is reversed. Two pictures: in one the sources reversed, in the other the targets. >

The ideal situation would seem to be be if you could always line up symbols by source and target the and put them tegenover elkaar. This is when the row of target symbols and the row of source symbols make no angle and if these rows are perpendicular to the lines’ metric direction.

Exact alignment of sources and targets, however, totally annuls the alignment.

< P: Symbols straight lines, equally spaced >

Lines always go from the center of the source symbol to the center of the target symbol, though. This causes convergence.

< P: previous picture, but lines go to the center >

The reason that lines automatically converge is that they go from center to center. < more pictures explaining that metric fact. Zonneklaar aantonen waar het metrische effect door komt >

The symbol sizes should be more proportionate, though, dependant on their encapsulation level and the amount of symbols it contains.

< P: normal simple convergence picture: proportionate symbols, lines from center to center. >

Making symbols proportionate like that causes more convergence.

##### Old

< >

De binnenkomende lines worden geordend op waar ze vandaan komen en de uitgaande lines worden geordend op waar ze naar toe gaan. Naar welk object ze toegaan.

< Ik moet de uitleg beginnen met een simpele toepassing van line convergence. Ik moet het steeds moeilijker maken en uiteindelijk ermee eindigen dat je kan groeperen op elk mogenlijk criterium. >

< Eigenlijk worden de lines al automatische geordend op waar ze heen gaan en waar ze vandaan komen, met convergence wordt dat nog een zwaarder benadrukt. Ja... dat is zo. Dat is grappig ja. Line convergence is alleen maar een overdrijving van wat al gebeurt. Maybe it’s near a border crossing where convergence is exaggerated. Eigenlijk wordt de convergence niet geëxaggerate. Eigenlijk wordt het ge-deëxaggerate. Je converged ze waar ze eigenlijk divergeren. Convergen doen ze al... zie tekeningen. Als de lijn naar het ene symbol en naar het andere symbol geen grote hoek maken, of zelfs een hoek van 0° dan kan er niet of nauwelijks ‘natuurlijke’ convergence plaats vinden. Stiekum vergroot je de hoek.

Bij overdreven convergence moeten vaste afstanden aangehouden worden.

Worden er nog groeperingen afgestreept onderweg? Nee. Nooit. Er is altijd groepering op alle criteria. Ik bedoel entrances. Op exits wordt niet gegroepeerd, want het is altijd dezelfde die exit < nah, het gaat over meedere lines >. Er is altijd een groepering op entrances en target. Altijd primair op uiteindelijk target, secundair op de parent van de target, ternair op de grandparent van de target, totaan de eerste exit. Shit. Ik ben er nog niet uit.

Een ander voordeel van gedwongen convergence is dat tijdens de rit de afstanden tussen de lines meestal gelijk blijven. Je kunt wel na elke border de convergence steeds wat verder overdrijven.

Convergence gebeurt alleen goed natuurlijk als de children verder uit elkaar staan dan ze wijd zijn... en dat is zonde van de ruimte! Maar over het algemeen, oh en dit maakt alles uit: lines gaan niet naar een symbool toe, maar naar hun middelpunt... behalve als ze naar een child toegaan, want dan wijkt het ag: het gaat niet meer naar het middelpunt. En bij gedwongen convergence wordt er gedaan alsof de children op een rechte lijn liggen, loodrecht op de line direction, zodat de convergence niet over een hoek van 0° verdeeld is... Verder wordt bij gedwongen divergence nauwelijks varierende afstanden tussen lines gebruikt. Of eigenlijk varierende varierende afstanden. Hoe dichter je bij het target komt, hoe minder het varieert of tussen elke twee crossings gaat het minder varieren?

\>

##### Old

< Picture showing line convergence >

Line convergence basically means that you group lines that have similar aspects. The usual aspects you’ll group them by is by what they enter or exit. You can also group lines by source and destination.

It’s usually near a border crossing where line convergence takes place.

Say multiple lines exit a parent. Around the border you can group them by where they’re going. Some lines will enter A, some will enter B, others will exit. On the border you group them.

You can also group lines just before the borders and just after. Say before the border you group them by where they came from and after the border you group them by where they’re going.

You can also express both where they came from and where they’re going with line convergence. So called multidimensional line convergence: groups of lines within groups of lines.

You can regroup borders or add more grouping using multidimensional line convergence.

In the analyses of very complex (usually poorly written, ‘spaghetti’-) programs, line convergence serves very well.

To accompany the grouping you can mention the grouping criterium. Or rather: mention with the grouping where the group of lines is going or came from.

Convergence takes place where lines enter or exit borders.

The grouping between borders can become more precise or more general. You might not care about the source of a line in a higher encapsulation level, so grouping can be generalized and possibly more focused on where the lines are going. Ofcouse, if before a crossing the grouping is about where the lines are going, after the crossing, the same grouping is about where the lines came from. Grouping can be about any crossing. On borders or around borders, regrouping can take place and grouping. Ofcourse any other criterium can be grouped by too, but you usually use crossings as the criteria for for line grouping.

A group of lines can be seen like a buslane for lines with certain sources, targets or any selection of its crossing actually.

Grouping lines by next entrance is quite handy in any case. It even evetually takes place anyway: they converge towards what they enter automatically, because they’re all ending up in the same point... at least in the same symbol.

You could also group lines by line type so that you separate object lines, type lines and interface lines.

<< In line convergence, show that not only is convergence useful when you see the whole diagram, but also when you don’t see the full diagram, you can still distinct line targets and sources >>

< line convergence, or actually, the curvedness of lines also creates clarity where lines cross eachother. When drawing a diagram you should try to make as little lines as possible cross. When you curve lines you can make crossings of lines more haaks. That makes it clearer to see where each line is going >

< Line convergence is very useful in complicated situations where many things call many other things in a rather disoriented matter. *Spaghetti code* this is called sometimes. In Symbol, the actualy spaghetti becomes visible, because the lines look like spaghetti, and the more lines there are and the more they go though<> eaching, the more it looks like spaghetti >

#### Compromise between Symbol Placement and Line Alignment

< different name >

#### Other Metrics

- Access symbols
- Shape peels
- Line peels
- All other diagram elements
- Identifiers
- Text language
- ‘Specifiers’
- Custom language

#### Ambiguity Risks In Symbol Metrics

- Multiple shape peel types may suggest the existance of another symbol.
- Line convergence may suggest line peels
- Line peels may suggest line convergence
- Line peels may suggest the existance of multiple lines.
- Others

...

#### Notation Choice

< - Implicit calls notation >

<
There may be an automatic choice mechanism in the Symbol programming enviroment. This is a rather complex, thing though, but should be regarded part of the language explanation, not just part of the Symbol programming environment.

Maybe this isn’t an alternative notations subject
\>

#### Brainstorm

Do explain that these are standard metrics and that they are not mandatory, obligatory, compulsory, required to obey.

The *start* of an identifier must be closest to the symbol it belongs to. Usually there isn’t enough room for the whole identifier to be closest to the symbol it belongs to.

< I also must find a way to place identifiers there where there’s room... >

### Language Integration

< State can *not* be expressed in diagram code. It can only be expressed in an alternative notation >
< Chemistry language. Flat or 3D>
< controls are an interactive language>
< an interactive language is a language that doesn’t only allow expression of things, but allows at least two parties to exchange information and respond to given information. > 
< Assembly >
< So there must be standard translations and translations for specific symbols.>
< Note that it’s only Symbol to another language here. There is no translation for another language to symbol. Is there? And if there is, there is definitely no editor for it available just like that, without programming it >

#### Too Much Material for an Introduction

Symbol Language embeds techniques that makes you able to integrate any other language into it. Certain and Symbol recognizes uses translation. Symbol text code is actually a language embedded into the Symbol Diagram Language. You can translate parts of a system to text, but you can just as well translate it to a more graphical language. This way you can for instance embed other diagram types into the Symbol Language. The Information Language, part of the J Data technology, is a diagram language designed to define information ( / data ) structures. It is a form of diagram different from Symbol.

There can be defined standard ways to translate, as well as translations specific to certain symbols. Standard translations allow you to translate any part of a system to another language using a standard notation. Translations for specific symbols allow you to define a custom way to translate

The following can be translated to another language, for instance text code:

- Identifiers
- Structure: Encapsulation structure
- Declaration: Procedure declaration
- Operators: Procedure call
- Literals: The state of an object

Symbol text code is established by a set of standard translations for the elements above, and a few special translations for for instance execution control procedures.

To demonstrate how other languages, including graphical ones, can be integrated into Symbol I will show how text code is established. 

Text code is made out of a symbol by giving a reference to a symbol to a translation procedure. The translation procedure will construct a String object that contains the text code. Thus, a tranlation procedure takes a system and translates it to an object that represents the system. If you don’t translate the system to a String, but another type of object, containing shapes and lines, for instance a Shapes object, then you can establish a graphical language.

The symbol diagram language is such a translation to a graphical language... ... yes, unfortunately the diagram language introduced so far is nothing more than a utilization of Symbol. It isn’t symbol itself. A system is retained in a J Data Base. The J Data Base stores the symbols and their relations and also a few standard translation procedures, which are also systems. Some of those standard translation procedures draw out the Symbol diagram language. Another set of those standard translation procedures produce the Symbol text language.

#### Operators

<<
Operators *are* procedures. They are assigned a special notation.

Evaluation order, childhesis, Precedence

Conversion operators
\>>

An example of operators are arithmetic operators:

```
+  –  /
```

An operator is notated like a method. It resembles an operation. The difference in notation is not in the diagram code. An operator’s speciality is that it supports an alternate notation, usually textual, but not necessarily.

\+ and – operations can be represented in plain text. Powers in Basic were represented by the ^ character. I wish to change that. I want the real mathematical notation to integrate with the language. For that I define operators as procedures that have any alternate notation. The power is represented by the exponent being notated in superscript: higher and smaller than the: be

##### Parameters

The textual notations of parameters

Possibly notating parameters on calls differently in the diagram than usual object assignments.

Parameter notations and operators are subjects totally for the Text Code chapter

Operators then too. 

#### Literals

Some types have special notation formats, such as Integer Number, Floating Point Number or Text:

```
415
1.32352e-1
“Hello, I am a text literal”
```

The notation as such describes the state of an object and it’s called a literal. The examples above are textual literals. To assign a literal to an Integer object, the literal is put into a Text object and the conversion procedure for Text to Integer is called. So literals are interpreted by using a conversion procedure with Text as the source type.

A literal can be a Text, but any other type will do, for instance a Picture. If a Picture serves as a literal, then to interpret the literal, the conversion procedure with. < A literal is always of a type of a type. >

There can also be a reverse for a literal interpreter. The Integer to Text conversion produces the textual integer literal.

##### Standard Literal

There’s a standard way to interpret and procedure textual literals of objects. If there is no custom conversion to text and back, you can only control the state of an object by calling its members. Say an object has the following members:

Integer 1
Integer 2
Reset
Object . State = { 

Their state can only be controlled using

Of its data members

Maybe you should be able to define orders in which 

< This concept is much like the operator concept, which can convert *procedures* with arguments to a textual notation and back. 

This conversions isn’t usually?) incorporated into the system procedures of procedure to textually notate, though. There is standard way to produce a textual notation from a procedure call.

The concepts ‘literals’ and ‘operators’ are very very alike, and a single word could be used that encapsulates both...

Standard textual literals and standard textual procedure notation. >

#### Structure

#### Identifiers

There can be graphical identifiers.

#### Declaration

#### What Is...

There is text code notation that I’ve introduced for which language integration techniques are used.

- Calls and parameter assignment
- Procedure declaration
- (Standard literals)
- Access operators
- Execution control statements

##### Access Operators

De access operators in text code

In text code you sort of see the calls to system procedures and you also sort of don’t. Each system procedure has its own access operator

|State Get:|x|
| -: | - |
|State Set:|=|
|||
|Object Access:|. Member|
|Object Copy:|.|
|Object Set:|. =|
|Create:|= New|
|||
|Type Access:|:: Member|
|Type Copy:|::|
|Type Set:|:: =|
|||
|Interface Copy:|:|
|Interface Set:|: =|

<< Maybe I’ll do special operator symbols in text code that represent the object relations. Actually, that’s what I’d like a little. Except member access. I wanna keep that. >>

- Access Operators
    - One for each system procedure and ones that can do for multiple system procedures, depending on the context
    - \- ... :: . , (), []
    - Special operators. Are they operators? If they are then they should be able to be overloaded. Maybe that’s handy too.
        - System procedure arguments
        - Genetivity

#### Real Language

```vb
If X Then A
```

If X is true then A will be executed.

```vb
Select X
    Case 0: A
    Case 1: B
End Select
```

When X = 0, A is executed

When Y = 1 then A is executed

Maybe I should allow the ‘real language’ text to be used as code too. Eventually.

#### Brainstorm

Dit drukt er een stempel op dat alles *binnen* de computer gebeurt. De taal heerst *in* de computer. De taal laat het toe weer gegeven te worden, maar alles gebeurt binnenin de computer. De weergave (in diagrammen) is niet het primaire element van de taal. Het primaire van de taal is de betekenis. De taal zelf is daaraan ondergeschikt.

Text, diagram, algebra, data.

Perhaps this can be part of the same system as explained above

- The parrallel between on one hand
    - strings, fonts, GDI
- and on the other hand:
    - simple shape description, GDI, ways to draw the shapes (anti aliased, not anti aliased ...)

How about ... an alternative notation for an object structure... like a simple tree notation.

How about integrating VB and C++?

Does properties have a place here? Somewhere? A bit?

##### What to Do With These Issues

I think a lot of this needs to be put in the other sections.

Operators, literals *is* a special text code issue. It can be parallelized with language integration, actually. And if it can’t be put in one concept as it is now, then I might need to make a single concept that covers language integration altogehter. There are two ways to express parameters in text code: as a definition or as a procedure call. The declaration of a procedure can be expressed as freely as an operator or literal notation. The general form of a textual procedure call notation is nothing more than a standard operator notation for a procedure.

- Mention that access operators are operator notations of the system procedures.
- Explain what execution control text notation is (is it an operator notation?)

Perhaps the standard procedure call notation, standard literal notation and standard procedure declaration can be put in the other sections, to be able to use them well explained.

As for the other issues:

- Identifiers:
    - Move to the beginning of this book. It’s a basic subject about naming symbols.
- Object structure:
    - Move to Objects chapter.
- Procedure structure:
    - Move to Procedure chapter.
- Execution control:
    - Move to Execution Control section
- Access Operators:
    - Introduce them in the access procedure section. 
- Access Controllers:
    - Move to Access Controllers section.

##### Variable Amount of Arguments

< Might go in Language Integration, Text Code. It may be a language integration feature to be able to invent custom tags for symbols >

In text code parameter assignments before a call are notated something like this:

```
Procedure A ( 0 , 4 )
```

Procedure A is the procedure name, the two numbers between brackets are the two arguments. Text code is covered in detail lateron.

The parameters of a procedure are listed in a fixed order. Even the optional parameters have a place in this fixed list and when you don’t want to fill it in you must leve the position open:

```
Procedure A ( 0 , 4 ,  , 1 )
```

After the fixed parameter list, a procedure can allow a variable amount of parameters to follow. This variable amount of parameters is stored in a single special parameter. This parameter is of type Array, a type defined in the Sigma Data module. To support variable amount of arguments, the procedure must have a public Array object that is assigned to be this special parameter.

```
Procedure A ( 0 , 4 ,  , 1 , 3 , 7 , ... )
```

Variable amount of arguments is a purely textual notation. The diagram notation shows working with the Array object. However, an Array parameter needs to be tagged and in the diagram code this is simply shown by displaying the words ‘Arguments’ with the Array object. < Maybe it has something to do with Language integration. >

#### Text Code

##### Objects

![](images/Symbol%20Language%20(2004).472.png)

Lines are set in the create procedure.

###### Lines Shown in Create Procedure

```
Circle System

    Circle Object A
    Circle Type A
    Circle Interface A

    Circle Type B
        Traingle
    End Circle

    System Procedures
    
        Square Create
            Object A . Type = Type B
            Type B . Triangle . Interface = Interface A
            Type A . Interface = Interface A
            Object A . Create
        End Square

    End System Procedures

End Circle
```

###### Lines Shown at declaration

```
Circle System

    Circle Object A : Type = Type B, Create
    Circle Type A : Interface = Interface A
    Circle Interface A

    Circle Type B
          Traingle : Interface = Interface A
    End Circle

End Circle
```

The calls added to the declaration are executed in the Create procedure, though.

###### No =

```
Circle System

    Circle Object A : Type B, Create
    Circle Type A : Interface A
    Circle Interface A

    Circle Type B
        Traingle : Interface A
    End Circle

End Circle
```

###### No Circle

Circle is rather general, so maybe I ought to be able to leave it out:

```
System

    Object A : Type Type B, Create
    Type A : Interface Interface A
    Interface A

    Type B
        Traingle : Interface A
    End B

End Circle
```

Slechte voorbeeld namen, dan lijkt het erop dat Type, Object en Interface keywords zijn. Dat zijn het ook, maar niet in de identifiers die ik heb gekozen.

###### Variations

__Circle System ó Object System ó Circular Object System__
__Triangle B ó Triangular Object B__
__Square A ó Procedure A__
__End Circle ó End Object__
__End Triangle ó End Object__
__End Square ó End Procedure__

##### Procedures

- Procedure Structure
- Parameter notations
    - Optional
    - Variable
    - Parameter order

###### Parameter Text Notation

There are several ways to notate parameters in text code. First of all, the definition of the procedure in text code must contain a parameter list:

```
Procedure Do Something ( Parameter 1 : Type A, Parameter 2 : Type B, Interface A )
```

Several notations for parameter assignments.

What do I mean several?

Textual:

- Enumerated argument list
- Named arguments
- Reading and writing arguments like the procedure is an object
- In, Out denotion

Ik wil dit er toch tussendoor doen. En na de andere hoofdstukken moet ik het er ook weer even over hebben.

< >

...

- Procedure structure
- Standard call notation
- Standard procedure declaration

###### Parameter Notations

In text code a parameter

In text code there are several notations for parameter definitions and assignments call. The most common one is in a comma separated list.

< I need to explain the difference between the term parameter and argument somewhere before this section >

##### Access Control

###### Textual Notation of Exclusion

```
Object A
    Exclude B . P1, B . C . P2
    Include B . P2_
End Objec
```

Or: 

```
Object A
    Exclude:
        B . P1
        B . C . P2
    End Exclude
    Include:
        B . P2
    End Publish
End Object
```

Or: 

```
Object A

    Exclude B:
        P1
        C . P2
    End Exclude

    Include:
        B . P2
    End Publish

End Object
```

###### Textual Notation of Friendship

```
Object A
    Friends
        ...
    End Friends
    Exclude B:
        P1
        C . P2
    End Exclude
    Include:
        B . P2
    End Publish
End Object
```

< Execution Control? >

#### Other notations

##### Dimensional Table notation

|Object Genericity|
| :- |
||__Object__|
|||Original object|<p>Object determined by no line</p><p>(no object line)</p>|
|||Delegated object|<p>Object determined by a line</p><p>(object line)</p>|
||__Type__|
|||Original type|<p>Type determined by no line</p><p>(object nor type line)</p>|
|||Delegated type|<p>Type determined by a line</p><p>(type or object line)</p>|
|||Explicit type|<p>Type determined by type line</p><p>(limits the possible object to objects of that type)</p>|
|||Generic type|<p>Type determined by object line</p><p>(symbol adopts any type the object might have) </p>|
||__Interface__|
|||Original interface|<p>Interface determined by no line</p><p>(interface, type nor object line)</p>|
|||Delegated interface|<p>Interface determined by a line</p><p>(interface, type or object line)</p>|
|||Explicit interface|<p>Interface determined by interface line</p><p>(one specific interface of the type is used)</p><p>(limits the possible types to ones that support the interface)</p>|
|||Generic interface|<p>Interface determined by type line or object line</p><p>(type’s whole interface used)</p><p>(symbol adopts any interface the type might have)</p>|
|__Procedure Genericity__|
||__Definition__|
|||Original definition|<p>Definition determined by no line</p><p>(no reference line)</p>|
|||Delegated definition|<p>Definition determined by a line</p><p>(a reference line)</p>|
||__Interface__|
|||Original interface|<p>Interface determined by no line</p><p>(interface nor reference line)</p>|
|||Delegated interface|<p>Interface determined by a line</p><p>(interface or reference line)</p>|
|||Explicit interface|<p>Interface determined by interface line</p><p>(limits the possible procedure to procedures with that interface)</p>|
|||Generic interface|<p>Interface determined by reference line</p><p>(symbol adopts any interface the procedure might have)</p>|
|__Interface Doesn’t Determine Type__|
||Interface-type genericity|The fact that the interface never fixes the type|
||Interface-procedure genericity|The fact that the procedure interface never fixes the  procedure.|

##### Tree Notation

You know the kind

But my kind also has convergence... and allows 1/nà1/n distinction or maybe those are other notations yet.

### Analyses

< Abstract symbol is introduced on numerous occasions already. Implicit notations are an example of abstract symbol. Abstract symbol is required. It is impossible to overview a (large) system if you see the exact process all the time, up to machine instructions. >

#### Other Notation Techniques

Coloring, alternative views...

The title of this chapter is dubious, though, because textual code seems another notation technique too.

Abstract symbol is about using symbol code alternatively. It might integrate with this section, because all I’ve mentioned as issues in this section is alternative views and coloring.

It’s about:

- Abstract Symbol
- Coloring
- Alternative views:
    - Overlapping encapsulation
    - Using encapsulation to express the other hierarchies

Then the chapter must get a different name.

- Symbol Usage or
- Using Symbol
- Symbol In Practice
- Alternative Views
- Views

Coloring is een analyse methode en abstract sybmol geeft analyses weer, dus het hoort wel bij elkaar. Hoe kan ik dat bij elkaar noemen. Analysis?

Dan is er nog dat rottige alternative views.

Analysis klopt daar ook wel bij.

#### Abstract Symbol

<
But another odd thing it that even though something is a call, you don’t always notate it, so the square won’t seem to have a line... This may be a subject for Abstract Symbol.
\>

Symbol can be used to describe a system in full, so to program a system. You can also use symbol to describe the rought outline of a system: abstract Symbol code. *This* is also used in programming in order to simplify the view on the system. However, abstract Symbol can also be used for diagrams in documents describing technical designs.

- Assumptions and in the middle latingen

Assumptions about access controllers, for instance:

![](images/Symbol%20Language%20(2004).473.png)

This for some reason implies that it’s ONLY accessible from the inside. Formally, the access symbol denotes that it’s simply accessible and that this access controller is imposed by the square.

#### When Shape Types, When Line Types

< So there’s a call trace and a definition trace. >

< Target call, target definition >

< Misschien mag ik dan al wel verklappen dat de call zo’n beetje het object is en de definition de klasse.

En waarom het dan aparte symbolen zijn en niet verschillende line types. Eigenlijk moet ik dan de keuze voor alle line types en symbolen aangeven.

Je kunt maar 1 reference line hebben. Dat is zo’n beetje de reden. Hè, ik moet het inderdaad goed opschrijven 

Call is een hoedanigheid van het symbool, dat geen line behoeft.

Type is niet een hoedanigheid van een symbool, het is waar een symbool voor *kan* dienen.

Een triangle is gekozen voor interface implementation, omdat een interface implementation ook een hoedanigheid is van het symbool, dat geen line behoeft. 

Eigenlijk is het wel een beetje zo dat: alles wat ik aan mezelf heb moeten uitleggen, moet ik aan de lezer uitleggen.
\>

A definition is a lot like a type of procedure, while an execution is an instance of the procedure. As I state this relation, it may seem strange to you that I picked *separate symbols* to denote a procedure symbol’s execution and definition, while for objects I use different *line types* to separate objects from types. Diamond is actually the extra symbol picked to represent an execution. An execution of a definition is like an object of a type. However, an execution has another special characteristic: it executes. 

When an object symbol has a type line it’s behavior in the container isn’t as much different as

However, object symbols aren’t different to their container if they 

To find the definition you follow the reference line between

Just consider: if a diamond doesn’t have a line it is an executing clause, when a square doesn’t have a line, it’s a non executing clause. In both cases it’s a definition. But the two case differ in that in one case it executes and in the other it doesn’t. If an object symbol has no line, it’s an object. Simply stated, it needs an object line for it not to be a type. A procedure symbol shouldn’t need a line to be an execution.

When a characteristic’s presence shouldn’t be dependent of the presence of a line, it needs to be drawn out with a shape type. If a characteristic is dependent of the presence of a line, it’s the line presence that gives it the characteristic. If I’d want object symbols to serve only as a type and not as an object, then I’d need to reserve a special shape to separate types from objects. Now, to make an objet symbol serve as a type only and not as a type, I make the Object Get Inaccessible? NO. That’s not true. Actually I’d have to not be able to Symbol Get if it’s for the purpose of assigning an object line. 

A square is never an object.

For a procedure symbol to function as a reference and not as an execution is not up to the possibility to have a symbol as an execution target.

Ok, if I wanted it so that an object symbol could only function as a type, but not as an object, I should reserve a separate shape for it. But that doesn’t mean that an object shape can’t serve as a type. An execution shape can serve as the definition too.

It’s important for some procedure symbols not to function as an execution. Otherwize the system would behave complete different. It’s not as important for an object symbol not to function as an object, only as a type. The system isn’t really harmed as severly by that. The same goes for triangles: if a triangle is suddenly a circle, the system behaves completely differently.

I’m still in doubt. I think it’s good that there’s a diamond symbol and that there aren’t separate object, type and interface shapes. I just can’t define *why* yet.

It totally makes sense to use separate type, interface and object shapes, but ... it’s just not that important. Not as important as the function of diamonds, triangles and pentagons. 

Sure it is nice to see in a system that one set of object symbols serve as the types... So it might be an idea to make it possible to give them a different shape type... when you can’t use the symbol as an object target.

The total reason of the diamond and triangle symbols is that the effect of it has greater consequences for the behavior of the system. A diamond symbol makes rules easier to understand: it’s easier to get: “you can’t place a diamond in an object symbol”, than it is to remember “a procedure symbol in an object symbol can’t have a call line”

*“The reason why both call and reference lines need to be followed is because call and reference lines are actually both kind of like reference lines. However, a call line has the side effect that its square will execute if its parent square executes.”*

Dat is zo’n beetje waar het kwartje begon te vallen dat het een shape moest zijn en geen line type.

Een andere shape wordt in basis Symbol alleen gebruikt als het echt nodig is. Als het niet echt nodig was om andere shapes te gebruiken, dan maakte ik het *allemaal* cirkels.

### Programming

< I have explained all possiblities of the language, but there simply are things you’ll use more than others. In my former explanations for instance it seems that using object lines is just as common as using type and interface lines. However, you’ll find, let’s say 20 times more object lines that you will find type lines. You might even write a whole module without any interface lines at all.

So some topics of the language might be complex, but used only incidently.

Exclusion, that is, a container’s exclusion of members of its children, doesn’t need to be used a lot. In fact, other programming languages I know don’t even have this capability at all. 

Etcetera. Symbol will become much easier when you find what’s used most and what things are for incidental use, no matter how complex the topics you’ll use incidently are.

You can write programs in which you have no notice of any system aspect procedure at all. In programs in which you do work with system aspect procedures, you won’t will not notice the presence of all aspect procedures, just some.
\>

< remember that I can only explain how to program structurally using the systems I’ve programmed as an example >

I’ve called this chapter into existance, because I want to write about programming methodologies.

#### Transforming a Procedure to an Object

There’s a method for turning a procedure into a type.

Say a procedure has input objects and output objects. When you call the procedure you set the input objects. After the call you can read the output objects.

To create a type out of the procedure you just take over all of the procedure’s objects. The procedure itself, stripped from objects, becomes a member of the type too.

You can freely read and write the objects. However, the procedure must be occasionally run.

Changing input objects means that the result of the procedure will change.

The method is: when you change an input object, the procedure must be run the next time you read an output object. So the procedure would only be run when output is read after input has changed.

This I call apply methodology. The reason I call it that is because When writing an input object a Boolean is set to __False__ called __Input Applied to Output__. Whenever you read an output object and __Input Applied to Output = False__ then the procedure is run: the procedure that converts input to output. After the procedure is run, all input has been applied to output, thus __Input Applied to Output__ is set to __True__.

The benefits from making a type out of a procedure is that you can dynamically write and write input objects and read output objects, without having to run a procedure all the time.

Sometimes, though, you always want input immediately applied to output when it changes. Then you can choose for immediate apply when writing input. The previous method only applied when reading output. Applying when writing input still has benefits: you can keep reading output objects without running the procedure and the procedure is only run when an input object is assigned a *different* value. When you assign the same value, the procedure isn’t executed either.

< >

I am still in contemplation about this. Perhaps apply methodology can be applied to all procedures and I could make it just a tag of a procedure which apply method is used.

Another thing interesting in these kinds of objects is Changed events. Perhaps this must become something standard too.

In types I always want changed events for the sub objects. The only reason I don’t add them for all sub objects is that it’s more code writing and Visual Basic may make the program heavier. Symbol however, doesn’t put anything unused in the compiled code. Oh, shit, it does when a type with a load of changed events is a public member of the module. Hmmm... perhaps changed events must become a standard thing. That way you can really respond to any change without having to 

Shit, I should also add programming methodology issues in this book. Most of which must be explained at the end.

< >

### Integrating Structure and Symbol

<< Brainstorm >>

You have to look at basics of Symbol. And the basic thing is encapsulation. The encapsulation of a Structure can be derived from the referential structure using a mutual parent rule. This in real life also determines how we feel something encapsulates another thing. You can apply this mutual parent rule to class relations and object relations. All class and object reference are expressed as splines, except the references from parent to child. Objects and procedures are there in both languages and are exchangable. Publicity is also present in both systems. The only thing I don’t know how to express in Symbol is plurality.

Symbol always had a lack of expression in plurality. How. You’d almost want a new shape of symbol. But I’ve sort of run out of shapes. I’d go for a hexagon. It looks like a circle, but has a plurality feeling to it. If you have to, you could choose for octagons.

Ofcouse, one of those, would contain a variable amount of objects, that don’t even have to be of the same type, but will always have the same interface I guess.

That would conclude seem to conclude the parallelization of Symbol and Structure.

But wait a moment. Structure is based on relations between types. How well do I see those relations between types in Symbol.

In Symbol I better see the relations between objects, while you see none of that in Structure.

How well are the relation between types shown in symbol. Well, you see the containment relations better than ever.

But how do the relations between classes show? Each circle or octagon expresses a relation class. Its class target is the class. You can recognize the class of the target by the class name of the relation class symbol. Class splines show the Structure Relations.

Ok, to recap: most things can be mutually exchangable between Symbol and Structure. There are two tacky points though: giving the Symbol code an encapsulation structure and plurality in symbol. An octagon will express that an object is plural. The encapsulation is derived from the reference structure using the mutual parent method. Some advantage symbol adds to Structure then, are encapsulation and also object relations. In structure code, it’s hard to view object relations.

Oh, crap. The expression of the structure is covered that way.

But what about the generated code? The data part may look much like the structure, but what about the user interface. Code for the user interface will add so much diagram to it, that overview over the realy structure will be pushed away. 

Oh, how funny, you program the structure in one diagram, but the object oriented system that comes out is a different structure, that resembes the structure diagram, but is much more extended.

Object relations will only come to light when the generated code is running.

However, you should be able to define static object relations in the structure, or not? Anyway, in the generated code, you should also be able to hide all user interface elements.

- Translate Litterly
    - Most things in the structure and the generated application can be litterly translated to Symbol
- Plurality
    - A plurality symbol was added to Symbol
- Mutual Parent
    - Encapsulation is derived out of the Structure with a Mutual Parent method.
- Hide Things
    - Things in the generated application are hidden, to keep the focus on the structure (but they can be shown if chosen).
- Extra Relation Splines
    - Add special lines to the diagram that expresses the Structure. You 
    won’t see the relations between classes as well in the structure as you do in the generated code, and I do want to see it. The relations between classes should be expressed with relation splines in the Classses collection. And the classes collection’s mutual parent structure should be expressed as the encapsulation structure, right then and there. iagram elements may be added to better see that.
    - Perhaps I should develop a separate way to notate the structure. Perhaps you should draw out the relations as you see them in the generated code and then Structure will figure out what it means.
    - That means you draw classes and you put object in them and that draws out the relation. The object contain the members of the Class class and you can specify it furtherly there.

Nee, forget all that.

Als je Structure in Symbol gaat toepassen, zal je een deel van ‘de gegenereerde code’ zelf programmeren. Dat lijkt in ieder geval zo. Als je een class in de structure will aanmaken, maak je een symbol aan. Als je een relatie tussen twee klassen wilt maken, dan maak je een object reference aan in een klasse die een relatie met de ander heeft. De relatie wordt wel automatisch dual. Als je een attribuut wilt toevoegen aan een class, dan stop je een objectje er gewoon in. Attributen worden trouwens objecten. Veel dingen worden wel op een gewone Structure achtige wijze ingevoerd. Daarvoor heeft een object symbol een Class interface gekregen, waar de structure information in wordt bewerkt. Daarin kun je ook bijvoorbeeld, customizen voor deeper objects. Je ziet ook nog globaal de classes en de relations collecties. Je ziet dus gewoon alle structuur informatie. Je kunt ook alles van de gegenereerde applicatie zien. Zo kun je in het aangemaakte object symbol (dat een Structure class is) de symboliek van de gegenereerde user interface zien. Die symboliek wordt automatisch bijgewerkt als je de Class informatie aanpast. Wijzigingen in de gegenereerde user interface symboliek worden als customization gezien en blijven staan, tenzij ze weer gedefault worden, waardoor de generator weer bepaalt wat het wordt. Je kunt ook een symbol meteen runnen, dus je kunt een control meteen laten zien.

Je ziet gewoon de structuur informatie en de gegenereerde applicatie in één symbol diagram. Dus voor een deel programmeer je in Symbol de Structure alsof je zelf de gegenereerde code aan het programmeren bent en de structure informatie is nog steeds wel beschikbaar. Alles wat je ziet komt ook in de gegenereerde applicatie terecht. Structuur informatie wordt namelijk ook zichtbaar in de gegenereerde applicatie. De uitzondering daarop is dat er kan gekozen worden om structuur informatie achterwege te laten in de generated application, alsmede andere dingen achtewege gelaten, maar die dingen zie je dan wel in de design code.

Je kunt ervoor kiezen om de encapsulatie structuur automatisch aan te laten leggen. Je kunt ook zelf de encapsulatie bepalen.

Er kan veel worden verzonnen om andere structuur eigenschappen zo direct te editen als je bijvoorbeeld klassen en relaties edit. Bijvoorbeeld zou progression ook op expliciete manier geëdit kunnen worden. Wat er allemaal nog meer expliciet geëdit zal kunnen worden, dat zal zichzelf wel wijzen.

Dat zal nog moeilijk te leren zijn, die taal. Ach, tutorials.

### Appendices

#### Summary of Concepts

< Make this a more extensive topic with a full description of the Symbol language >

< The theory of the Symbol language is a soup of concepts. However, in a book you have to start at one point and gradually explain things one by one, without referring to any unexplained material, even though it’s part of the soup. It was hard to find a point at which to start, and the beginning of the book is definitely not the first part of the book I wrote.

This summary, though, doesn’t organize Symbol in the order of explaining it and it doesn’t cover concrete examples either. It just orders the concepts by category and is an overview of the soup of rules that is Symbol. >

<<
‘Static’ is part of Object Structure. So lifetime is part of object structure.

Access and Scope are the same subject.
\>>

##### Rough

- Identifiers
- Objects
- Procedures
- Access

- Generic Code

##### More Detailed

<<
Overloading can only be part of procedures if you either cannot overload an object or you call a procedure to return an object...
\>>

- Identifiers

- Objects

    - Objects, Types and Interfaces

    - Destruction
    - ‘Normal’ Variables

    - Static

    - Object Operators
        - Conversion 
        - Creation
        - Pointer
            - \* Dereference
            - &  Address-of
            - .\* Apply pointer to type member (objects) 
            - –>\*    Dereference pointer to type member
        - Size of object
        - Type name
        - Assigment: =

    - Blocks...

    - Lifetime

- Procedures
    - Procedures
    - Procedure Reference
        - Pointing
        - Calling
- Operation Flow
    - Normal order
    - Selection
    - Iteration 
    - Call and Return
- Parameters
    - In, Out, Thru
    - Optional
    - Variable Amount
    - Return Type
- Operators
    - Operators *are* procedures. They are assigned a special notation.
    - Evaluation order, parenthesis, Precedence
    - Conversion operators
- Object Extension
    - Include
    - Exclude
    - Override
    - Merge
    - Pre-extend
    - Post-extend
    - Overload
- Properties and Events

- Ambiguity
    - Overloading
        - Being able to reference things with the same name
        - The thing being referenced dependent of the referers place...
    - Hiding names: 
        - one name takes precedence over another. 
        - Accessing a hidden name.
    - Real ambiguity

- Recursion and Circularity
- Delegating
- Notations

- Access  << does constant have a place here. Private read, public write... >>
    - Public, Private
    - For different Aspects: 
        - Object
        - Type
        - Interface
        - Creation
        - Genericity change
    - For different Parties: 
        - Me
            - Parent
            - Children
            - N levels up
            - N levels down
            - Interface parent
            - Interface children
            - N interface levels up
            - N interface levels down
            - Up until globality
            - N globalities up
            - Certain types
            - Certain objects
            - Certain globality types
            - Certain globality objects
    - Globalities
        - Delocating members 
            - (‘friend’ sorta transfers things out of a type to the nearest globality. Is all that required? Does Symbol not  have better substitutes for this?)
    - Access Operators
          - Special operators. Are they operators? If they are then they should be able to be overloaded. Maybe that’s handy too.
        - Access globality
        - Access object
        - Access interface
        - Access type
        - System procedure arguments
        - Genetivity

- Generic and Explicit
- Recursion and Circularity
- Constant and Variable
- Assignment
    - Object
    - Reference
        - Creation
        - Conversion
    - Type
    - Interface
    - State
        - Copy
    - Literal

- Generic code
    - Templates
    - Generic code:
        - Code automatically generated real time as interface of a generating component is used.

- Standard Variable Types and Operators are covered in ‘Math’

##### Brainstorm

- Dubious:
    - pointer to any member of a type (ClassName::\*). Genericity like that.
    - (Grouping Symbol?)

- Afleidbare concepts:

    - Variables types:
        - Pointers
        - Structure

    - Namespaces
    - Module
    - Strings 
    - Declarations on first use (in the middle of a statement)
    - Friend access modifier
        - Heeft in C++ een aantal functies:
            - ...
        - Deze hebben allemaal een vervanging in Symbol:

#### Summaries of Other Languages

#### C

*A summary of Msdn Library Visual Studio July 2000: C Language Reference*

- Identifiers
- Constants: floating point, integer, string, enumerator
- Lifetime: when does a variable exist
- Scope: visibility, reuse of names
- Name Spaces
- Variable
- Specifiers
    - Access modifiers: public, private, 
    - Types: void, char, short, int, long, float, double, signed, unsigned, struct-or-union-specifier, enum-specifier, typedef-name; signed, unsigned
    - Type qualifiers: normal, const, volatile
- Declarations
    - Single value variable with fixed size declations
    - Array, string declations
    - Pointer declations
    - Enumeration declations
    - Structure declations
    - Union declations
    - Alignment
    - Typedef declations
    - complex variable declarations
    - initialization: scalar, aggregate and strings
    - Incomplete types (look it up)
- Statements
    - expression (can include assignment)
    - break
    - label, goto
    - while, do-while, for, continue
    - if, switch
    - null statement
    - return
    - try-except, try-finally
- Expressions and assignments
    - L-value and r-value expressions
    - Constant expressions
    - side effects
    - sequence points
    - operators (are functions)
        - Postfix operators
            - One dimensional array
            - Multidimensional array
            - Function call
            - Structure and union
            - increment, decrement
        - Unary operators
            - prefix increment, decrement
            - cast
            - sizeof expression
            - sizeof(type)
            - &, \*, +, -, ~. !: bitwise and, dereference, plus, negate, bitwise complement, not/logical negation
        - Arithmetics (are functions)
            - Multiplative: \*, / and %
            - Additive: +, -, pointer arithmetic
        - Bit shift
            - shift: <<, >>
        - Relational and equality / Comparison: <, >, <=, >=, ==, !=
        - Bitwise:
            - And: &
            - Xor: ^
            - Or: |
        - Boolean / logical operators:
            - And: &&
            - Or: ||
        - Ternary: Conditional expression: ? :
        - Assigment: =, \*=, /=, %=, +=, -=, <<=, >>=, &=, ^=, |=
        - Sequential evaluation: , (doesn’t do much)
    - Operator precedence
    - Type conversions
        - Assignment conversions: value of one type assigned to variable of another type
        - Cast conversions: cast of a value of one type to another type
        - Function call conversions: value of one type passed to a function taking another type
- Functions
    - declaration
    - return statement
    - definition
    - return type
    - parameters
    - arguments
    - variable number of arguments
    - prototypes
    - calls
        - call
        - arguments
        - call with variable number of arguments
        - recursive function

##### C++

*A summary of Msdn Library Visual Studio July 2000: C++ Language Reference*

I reorganized the information into the following main topics:

- Identifiers
- Types
- Expressions
- Statements
- Declarations
- Types
- Scope

More detail:

- Identifiers
- Types
    - Simple
    - Derived
    - Nested types
- Statements
    - Statement types
        - Expressions
        - Declarations
        - Selections
        - Iterations
        - Jumps
        - Exception Handling
    - Blocks
    - Labeled statements
    - Compound statements
- Expressions
    - Primary expressions
    - Operators
        - Access
            - ::  ::  [ ]  ( )  .  –>  ,  =
        - Arithmetic
            - ++  --  ++  --  +  -  \*  /  %  +  –  \*=  /=  %=  +=  –=
        - Creation
            - new  delete  delete[ ]
        - Pointer
            - \*  &  .\*  –>\*
        - Comparative
            - <  >  <=  >=  ==  !=
        - Boolean
            - !  &&  ||
        - Bit
            - ~  <<  >>  &  ^  |  <<=  >>=  &=  |=  ^=
        - Analytic
            - sizeof  sizeof ( )  typeid( )
        - Conversion
            - (type)  const\_cast  dynamic\_cast  reinterpret\_cast  static\_cast
        - Conditional
            - e1?e2:e3
    - Semantics
- Declarations
    - Specifiers
    - Declarators
    - Functions
    - Enumerations
    - Templates
    - Namespaces
- Types
    - Types
    - Unions
    - Derived types
    - Objects
    - Overloading
- Scope

Full summary:

- Identifiers: (the distinction between identifiers and names is probably a flaw in the explanations)
    - Identifier:
        - __Name of__ object, variable, type, structure, enumeration, union, member of type, member of structure, member of union, member of enumeration, function, function, typedef, label, macro, macro parameter
    - Name:
        - identifier, simple type, template, value
- Types:
    - Simple
        - void, unsigned, signed, short, long, int, float, bool, char, double
        - Numerical limits
        - Standard conversions (see doc)
    - Derived:
        - Directly derived types
            - arrays, functions, pointers, object references, constants, type member pointers
        - Composed/aggregate/elaborate types
            - type, structure, union, enum
    - Nested types: derived types declared inside a type

- Statements
    - Statement types
        - Expressions
        - Declarations
        - Selections: if, else, switch, case, default
        - Iterations: for, do, while
        - Jumps: break, continue, return, goto
        - Exception Handling: try, throw, finally, except, catch,
    - Blocks
    - Labeled statements
    - Compound statement: in case of if’s and switches and loops

- Expressions: compute, assign, generate side effects
    - Primary expressions
        - Literals: integer, character, floating point, string
        - Identifier
        - Operator (-function name)
        - Parenthesis
        - this
    - Operators
        - Access
            - ::  ::  [ ]  ( )  .  –>  ,  =
            - Scope resolution, Global, Array subscript, Function call, Member selection (object), Member selection (pointer), Comma, Assignment
            - Comma : argument seperation, multiple statements where one expected (e.g. if specification)
        - Arithmetic
            - ++  --  ++  --  +  -  \*  /  %  +  –  \*=  /=  %=  +=  –=
            - Postfix increment, Postfix decrement, Prefix increment, Prefix decrement, Unary plus, Arithmetic negation - (unary), Multiplication, Division, Remainder (modulus), Addition, Subtraction, Multiplication assignment, Division assignment, Modulus assignment, Addition assignment, Subtraction assignment
        - Creation
            - new  delete  delete[ ] 
            - Allocate object, Deallocate object, Deallocate object
        - Pointer
            - \*  &  .\*  –>\*
            - Dereference, Address-of, Apply pointer to type member (objects), Dereference pointer to type member
        - Comparative
            - <  >  <=  >=  ==  !=
            - Less than, Greater than, Less than or equal to, Greater than or equal to, Equality, Inequality
        - Boolean
            - !  &&  ||
            - Logical NOT, Logical AND, Logical OR
        - Bit
            - ~  <<  >>  &  ^  |  <<=  >>=  &=  |=  ^=
            - Bitwise complement, Left shift, Right shift, Bitwise AND, Bitwise exclusive OR, Bitwise OR, Left-shift assignment, Right-shift assignment, Bitwise AND assignment, Bitwise inclusive OR assignment, Bitwise exclusive OR assignment
        - Analytic
            - sizeof  sizeof ( )  typeid( )
            - Size of object, Size of type, type name
        - Conversion
            - (type)  const\_cast  dynamic\_cast  reinterpret\_cast  static\_cast
        - Conditional
            - e1?e2:e3
    - Semantics
        - Evaluation order and sequence points
        - Declarations on first use (in the middle of a statement)

- Declarations: Introduce names into a program
    - Specifiers: specify mainly type, access, storage. Characteristics of what is declared.
        - All:
            - public, protected, private, static, auto, register, extern, virtual, inline, const, volatile, friend, type, typedef
        - Access:
            - public, protected, private
        - Storage type:
            - static, auto, register; extern (linkage); Ommitted
        - Function:
            - virtual, inline
        - Type qualifiers:
            - const, volatile
        - Friend: a global function overloaded and specified inside a type for access to its protected and private members
            - friend
        - Type:
            - any type
        - typedef specifier:
            - typedef    

    - Declarators: specifies
        - The name and pointering in a declaration (and type names in certain cases). Basically the part of the declaration that the specifiers do not cover.
            - Name
            - Pointers: pointer, reference, array, pointer to any member of a type (ClassName::\*)
            - Type names: in conversions, sizeof, new, function prototypes, typedefs
        - Initialization
            - Pointers to const objects
            - Static members
            - Aggegrates
            - Character arrays
            - References
    - Functions
        - Function declaration
            - Argument declaration list
                - in prototypes
                - in definitions
            - Default arguments
            - Variable argument lists
            - function overloading
            - Return restrictions: Can’t return arrays or functions. They can however return references of pointers to arrays or functions, or arrays inside structures
        - Function definition
            - Distinction of declaration and definition: only in functions (?and maybe types too?)
    - Enumerations: Declaration, Conversions and enumerated types
    - Templates: functions and types: template
        - No arbitrary textual substitution, but only substitution of type, type or constant
            - type placeholders: <type ...>
            - constant placeholder: any type name e.g. <int ...>
            - type placeholder: <typename ...>
        - Specifies a family of types, code generated when it is referenced in code
    - Namespaces
        - Declaration
        - Definition (like type)
        - Members
        - Namespace alias: alternate name for namespace
        - namespace
        - using namespace <namespace>: allows you to ommit the namespace identifier when referencing things in the namespace
        - Accessing the namespace (C++ uses ::)
    - Abstract declarator: identifier omitted
    - const and volatile pointers

- Types
    - Types
        - Defining types
        - Type objects
        - Type name
        - Type members
            - Functions
            - Data
            - Nested types, structs and unions
            - Enums
            - Bit fields
            - Friends
        - this pointer
        - Static data members
    - Unions:
        - Can have functions, can have constructors and destructors, can’t have base types and cannot be used as base types
    - Derived types
        - Multiple base types
        - Virtual functions
        - Virtual base types
        - Overriding (more on that in another summary)
    - Objects: special functions
        - constructor, destructor
        - conversions
        - new operator
        - delete operator
        - assignment operator
    - Overloading
        - argument type differences
        - argument matching to find the right function
        - Overloaded operators: any operator

- Scope
    - Scope rules
    - Scope: local (within block), function scope, file scope, type scope, prototype scope (check what they meant by that)
    - Lifetime, point of initializing objects.
    - Hiding names: one name takes precedence over another. Accessing a hidden name.
    - Name ambiguity

- Other aspects
    - Startup and termination: 
        - exit abort, return
        - Command line
        - atexit function
    - Comments
    - Calling conventions
    - asm

###### Unclassified

Microsoft specific:

```
allocate3 \_\_inline property
\_\_asm1 \_\_int8 selectany
\_\_based2 \_\_int16 \_\_single\_inheritance 
\_\_cdecl \_\_int32 \_\_stdcall 
\_\_declspec \_\_int64 thread
dllexport3 \_\_leave \_\_try 
dllimport3 \_\_multiple\_inheritance uuid
\_\_except naked3 \_\_uuidof 
\_\_fastcall nothrow3 \_\_virtual\_inheritance 
\_\_finally
```

- Keywords:
    - Constants: true, false
    - Don't know: typename, typeid, type\_info, mutable, explicit, bad\_cast, bad\_typeid

- Where did the embedded declarations in a function declaration go?

Other Sigma components replace functionality of Standard libraries, but C programmers should be able to specify functions from them, shouldn’t they. Not gonna mind right now.

Formal arguments are the variables  inside the function as opposed to the values given in the function call.

Concepts

##### Other

I don’t summarize Com, because it doesn’t really add any programming concepts, but mainly only libraries. I don’t summarize Visual Basic, because it doesn’t really add any concepts to... oh, I do need Visual Basic and Com, for the events and stuff... dang. And properties, and all. Many Visual Basic and Com concepts have no place in this programming language, but in other modules.

Com concepts: components, interfaces.

#### Terms

capsule
containment structure
encapsulation (structure)
*ancestors* 
*higher* objects
Deeper objects
*lower* objects
*descendants*
derived 
*inherit* 
*child*
*parent* 
*grandchild*
*grandparent*

*base*
*base* *object*
*base type*
*ancestry*
*level*
*layer*
*deep ancestry*
*Deeper layers*
*bottom layers*
*Higher layers*
*top layers*
*foundation*

*Container*
*the contained*


Object
Type

Base
Derive, derivation
Inheritance

Lower
Deeper
Higher

Child
Parent
Ancestor
Descendant
Grandchild
Grandparent

Reference
Referee

Interface
Implementation

Procedure
Procedure reference
Call
Definition

# Brainstorm

Als je een te supplyen procedure reference (pure virtual function, pure overridable) niet invult, dan heeft hij van zichzelf waarschijnlijk geen inhoud. Als je hem dan aanroept gebeurt er gewoon niks. Eigenlijk zou dan misschien ook bij niet gecreerde objecten moeten gebeuren: je roept hem wel aan maar er gebeurt gewoon niks. Dat voorkomt foutmeldingen, maar het is eigenlijk niet de bedoeling. Of kan je erop bouwen. Misschien is het een keuze die je maakt als programmeur. Nou moet ik zeggen dat ik in mijn code er altijd voor kies dat als er iets 'verkeerds' wordt aangeroepen, dat er dan gewoon NIKS gebeurt. Er gaan niks fout, nee er gebeurt gewoon niks.

Delegation, delegation structure.

< I have to get all of my Symbol scribbles out of the bin and put them in a ... map.

< What I call type members a lot, really aren’t type members. They’re object members. Only static type members are type members. And what I call procedure members aren’t procedure members. They are call members. Only static procedure members are procedure members. So what are Type Static procedure members? They are type members that are only associated with a single procedure. Oh, but they are still procedure members than. And then object members can also be called type members. Hmmm... yes, but I overuse ‘type member’ I think. In a lot of places I can say object member.>

< I need a story about where the code resides and that the code isn’t really part of globality instances, types, objects or procedures. Those entities only complete the code with a copy of data. >

Objects don’t *really* contain data, though, but memory is reserved for every object and linked to the object.

Er moet ergens nog in dat een procedure een interface heeft. En misschien moet een procedure daarom ook een interface line krijgen.

Trouwens: Een multicast event is niet meer dan een object met een dimensie, die meerdere procedure references registreerd. Misschien moet er een speciale notatie zijn zodat je de lines ziet. Je moet van dat object met een dimensie een method aan kunnen roepen, die in een rij alle references aanroept. Daarom moet een dimensionaal object ook niet dimensionale members kunnen hebben, maar ik weet nog niet helemaal hoe dat dan gaat.

- Pointer to member of type
- Pointer to function: can I make obligations about function signature?

*Little disclaimer: I use the word Friend here, but it’s not the same as the Friend access controller. It’s a keyword overused here. However, it’s overused the same way in C++ and I have not yet come up with a decent alternative. The word Friend has been taken over from C++, just like the other access controller keywords. The access controller keywords aren’t super accurate description of their effect, they are just picked because the words are short and you can related their meaning remotely to their effect. I ain’t good at coming up with inaccurate names for something, so I can’t find an alternative now for this second hand use of the keyword Friend. I could go look for more concise words for the access controllers, but those would confuse me, because I’m still used to the old words. And it’s hard enough trying to get the description of this programming language on paper as it is.*

In J Code you could do overloading in which anything of the declaration can differ. If you use

named arguments than you can do same parameter types. You can link to any symbol anyway,

so it would be just a matter of what you see in text code.

I may need to use the terms *object* and *child* everywhere rather than *type* and *ancestor*. An object’s member for instance. I should also talk about *parents* and *children*.

Cover the possible ways to have events.

A possible notation: showing things further away as smaller.

Operators:

J Data Information Language is an alternative notation used inside Symbol code. Does it therefore consist of operator functions? And is that then the first operator that is about a more non textual notation a a more graphical one?

#### Other Things

- Object structure
- Procedures and 
- Operators
- Operation control

I’m going to summarize all programming concepts. I need to shorten the list by only mentioning the general outline concepts. Blah. I’ll use the C and C++ language analyses I made. I need a short summary of com concepts too:

- Interfaces
- Properties and events

Isn’t that basically all? Maybe, but it needs to be incorporated.

The alternative views and colors and other indicators are all a separate subject that shouldn’t be covered at first, but lateron.

Don’t forget to expand inheritance possibilities. Exclude, override, pre extension, post extension. 

<<

- Operation control:
    - Expressions
    - Iterations
        - Do
        - For
    - Jumps
        - If
        - Select / Switch
        - Procedure call and return

- Objects and interfaces

- Operators: are interfaces for functions. Interfaces for functions??

- Variables, Simple data types
- Variables are objects and simple data types are their types. 
- They control data and a variety of operations are allowed on them

- Function arguments, In, Out, Through

- Creation

\>>

J Code Access Controllers and Interfaces.
\------------------------------------------------

I mentioned friend and public here, but access controllers are more complex in J Code due to embedded globalities. There is basically an infinite amount of access controllers. For that they aren't primarily named anymore, they are systemized. You might have an access controller that ensures that. Maybe what I put in a triangle previously, is actually something that just has special access. Maybe the triangle shouldn't be used there then, but just a special access controller. The triangle can then be used as an interfaces mark. The triangle previously marked all symbols inside the triangle as having this special access. If I don't use the  triangle there anymore then I'd have to change each of those symbols' access controllers. For that... You should be able to group symbols inside a special symbol that controls the access for all the directly contained symbols. So to see the triangle as a special access controller and for that not use the triangle for it anymore, but an actual access controller, I'd have to use access controller symbols (line and line 'terminators) for all the containing symbols, which would drastically make the diagram more difficult. An  idea is to make a special symbol to control the access for all the directly contained symbols. What pops into my head now is: since the triangle would then stand for interface, each member with the same access controller could belong to the same interface. Therefore, an interface symbol (triangle) could be used to group these symbols and the interface symbol gets the access controller instead, which applies it to all directly contained symbols.

Groeperingssymbool op basis van wat een client object gebruikt. De interface indeling is op die manier een beetje automatisch. Als je geen interface indeling hebt, dan kun je toch zien 

wat de verschillende clients gebruiken en misschien voor het overzicht toch een interface indeling gebruiken.

|Programming Concepts’ Diagram Elements|
| ------------------------------------ |
|Containment|Shapes contain other shapes|
|Reference|<p>Line between reference and referee, </p><p>    going outward and acces controllers shed light on direction</p>|
|Type|<p>Dotted line from object to type</p><p>    going outward and acces controllers shed light on direction</p>|
|Object reference|Circle|
|Interface|Triangle|
|Procedure|Square|
|Access||
|    Global|All inside a pentagon (There are issues)|
|    Public for reference|Line to just outside to a tangent line.|
|    Private for reference|Line to just outside to a cross|
|    Friend for reference|Line to just outside to a < shape pointed inwards|
|    Public for instancing|Line to just outside to a dotted tangent|
|    Private for instancing|Line to just outside to a dotted cross|
|    Friend for instancing|Line to just outside to a dotted < shape pointed inwards|
|Execution order|Dependent of positioning. Clockwise. Symbols possibly tied together with lines.|
|Changing reference or type|Also include creation and destruction. Special procedures that actually alter the diagram.|
|Array|Special type with special methods changing the count of contained object references.|
|Module|A globality symbol can be compiled|

#### Old

<< you can integrate data logic by being able to choose to display the data logic diagram right inside a symbol, or display the object structure it resolves in. >>

<< you can integrate text code in the very same way >>

#### Introduction

Sigma Core is tightly involved in Symbol Language and are both part of the same project that I call the Core Code project.

Symbol diagram language is accompanied by Symbol text code. Symbol text code is used in captions in the diagram, but sometimes a piece of diagram is easier to view in text code.

So two languages are defined: 

- Symbol diagram language 
- Symbol text code

The translation of Symbol code to a Sigma module is also very important to consider when designing the language. It may require adaptations to Sigma modules.

#### Darn

##### Abstract Concepts

Single concepts about multiple items. For instance: 

- Putting restrictions on a childs methods
- Methods abstract other methods
- Having an event interface
- ...

##### Out of Nowhere

global

Maybe then I can wrap it up to inambiguous. Perhaps I then should combine sections to be about for instance both pointers and object references.

#### Symbol Diagram Language

- Concepts
- Diagram Elements
- Concept à Diagram Element
- Diagram Element à Concept
- Ambiguous Programming Concepts

##### Primary Concepts

- Containment
- Reference
- Type
- Object Reference
- Interface
- Procedure
- Access
- Changing reference or type
- Arrays
- Execution order
- Module

##### Diagram Elements

- Basic elements
    - Shapes
    - Lines
    - Line disectors
- Basic elements more refined
    - Shapes
        - Circles
        - Triangles
        - Squares
        - Pentagons
    - Lines
        - Continguous line
        - Dotted line
    - Line dissector
        - Continguous
            - --|
            - --X
            - --<
        - Dotted
            - --|
            - --X
            - --<
- Element combining
    - Containment
    - Linkage
    - Positioning

##### Concept à Diagram Element

|Programming Concepts’ Diagram Elements|
| :- |
|Containement|Physical containment of shapes|
|Reference|<p>Line between reference and referee, </p><p>    going outward and acces controllers shed light on direction</p>|
|Type|<p>Dotted line from object to type</p><p>    going outward and acces controllers shed light on direction</p>|
|Object reference|Circle|
|Interface|Triangle|
|Procedure|Square|
|Access||
|    Global|All inside a pentagon (There are issues)|
|    Public for reference|Line to just outside to a tangent line.|
|    Private for reference|Line to just outside to a cross|
|    Friend for reference|Line to just outside to a < shape pointed inwards|
|    Public for instancing|Line to just outside to a dotted tangent|
|    Private for instancing|Line to just outside to a dotted cross|
|    Friend for instancing|Line to just outside to a dotted < shape pointed inwards|
|Execution order|Dependent of positioning. Clockwise. Symbols possibly tied together with lines.|
|Changing reference or type|Also include creation and destruction. Special procedures that actually alter the diagram.|
|Array|Special type with special methods changing the count of contained object references.|
|Module|A globality symbol can be compiled|

##### Diagram Element à Concept

|Circle|Object reference|
| - | - |
|Triangle|Interface, inheritance|
|Square|Procedure, procedure call|
|Pentagon|Globality region|
|Continguous line|Points to referee|
|Dotted line|Points to type|
|Continguous dissector ||Public for reference|
|Continguous dissector X|Private for reference|
|Continguous dissector <|Friend for reference|
|Dotted dissector ||Public for instancing|
|Dotted dissector X|Private for instancing|
|Dotted dissector <|Friend for instancing|
|Containment|Logical containment of objects|
|Linkage|Pointing to referee or type|
|Positioning|Arbitrary / execution order|

##### Derived Concepts

Procedure call
Inheritance
Multiple containment
Pointer
Parameters
Arguments
Variables
Storage
Member grouping
Interface implementation
Events / outward interfaces

Overriding

|Procedure call|Procedure reference|
| - | - |
|Inheritance|<p>Interface with the base as the type</p><p>Interface can be created or refer to a shared base object </p><p></p><p>Interface referencing an object or interface</p><p>Referencing an interface makes it interface inheritance only.</p><p>Referencing the object means referencing its total interface in a way too.</p>|
|Multiple containment|Containment and reference|
|Pointer|Reference|
|Object reference|Object, reference|
|Parameters|A procedure’s object reference public as referee|
|Arguments|<p>In:</p><p>    Create parameter and assign or change reference</p><p>Out:</p><p>    Change reference</p><p>In/Out:</p><p>    change reference</p><p></p><p>Change reference of parameter or create parameter </p>|
|Variables|See storage|
|Storage|<p>Are objects with a read and write method</p><p>Yet another shape? It is sort of an objects in that it has a read and write method. Storage is never really physically addressed. It’s always an abtract that gives you</p>|
|Type reference|You can make any object or interface get the type of any other object or interface, which can in turn have a type.|
|Member grouping|<p>Apparent to the referer: a circle around the group</p><p>Not apparent to the referrer: a triangle around the group, but don’t make the triangle public or it will appear as an interface outside.</p>|

##### Details

###### Interface

I said a triangle was an interface. Eigenlijk is de interface een hoop functie referenties die ingevuld moeten worden. Dan zou het zo zijn dat alle members in een driehoek door zouden moeten refereren naar members binnen de cirkel. Eigenlijk moet ik een driehoek zijn eigen syntax laten hebben. Een driehoek krijgt een interface klasse. Deze kan een cirkel zijn of driehoek. De driehoek krijgt de publieke en vriendschappelijke inhoud van de interface klasse, maar niet de prive inhoud, welke de implementatie omvat. Dus de implementatie ontbreekt. Je kunt deze of zelf invullen of je creeert de implementatie door de driehoek te creeeren met een bepaalde implementatie klasse, waardoor je inheritance bewerkstelligt. Je kunt evengoed de verwijzing van de driehoek veranderen om de implementatie te delegeren. De driehoek heeft altijd de holle vorm van zijn interface klasse, maar de klasse en het object van zijn verwijzing. Als je hem creeert dan heeft hij geen verwijzing.

Een interface heeft een interface, implementatie en object. De klasse is de interface, de implementatie zou ook een klasse moeten zijn en het object dan de referentie.

Heeft de driehoek een extra referentie dan? Interface, implementatie en object?

Maar dan heeft een cirkel dat ook, want die representeert... oh, de gezamenlijke interface. De driehoek kan ook zelf de interface klasse zijn en de interface en de implementatie.

###### Reference

####### Direction

Always first goes outward, but that doesn’t mean that outward is the direction. Line disectors

Reference to a procedure is a call and is represented by a square tied to another.

####### Reference to object

Is reference to total interface, that isn’t denoted with a triangle, but is implicitly there.

###### Access

Direct containment grants access for referring

Line disectors can describe indirect containment access

To the outside there is only access to the children of the pentagon the symbol is indirectly in. Friend access controllers of pentagon children  restrict global access and denote what can serve as a type and what can serve as an object reference. You only have access to other things outside through a reference, but that reference resides inside the symbol.

####### Multiple Globality Levels

A globality B inside a globality A is accessible by A. A globality C inside globality B is not accessible by A unless declared public.

globality A outside globality B can not be accessed by B.

What about ‘system wide’ things that can be accessed from anywhere? It can be reached from embedded globalities, which disobeys the rule just defined. If it’s really system wide, then you simply embed a globality by linking to the shared instance of a module.

But what if it’s less system wide? In that case it seems that a deep globality has access to a shallower globality... << I’ll figure out later >>

If a globality is declared public, it becomes a sub module in the Sigma module.

####### Friend for reference

Means access only anywhere within the globality, but not inside embedded globalities.

####### Public for instancing

The symbol serves as a type and can be instantiated outside the globality.

###### Contaiment by Containment and Reference

Reference can be seen in a way as containment.

###### Changing a Reference or Type

Special procedures that can actually alter the diagram.
Objects are always object references or types until the object is created. Create an object for one reference, then the references tied to that reference also point at that object, ofcourse, since the reference tied to the reference are actually references to references.
A creation procedure method is called with a fixed reference to another reference to create an object for. The dectruction method is the same. The creation method kinda turns the references on, while the destruction method turns it off.
The procedure for changing a reference gets the reference as an argument, and another argument that specifies the symbol to reference. The symbol to reference needs to be the same interface ...
A reference has a fixed interface, but can be point to or be of any type as long as you reference the same interface.
For that, changing the type of a reference is permited

Changing the type of a symbol is not permitted, be it that the same interface of 

These procedures ARE J Core function. Only they have a great impact: they change the diagram.

Possible changes in the diagram may be laid out. There may be limits to the possible reference gotten...

###### Execution order

clockwise starting at the top one or 
like reading: left to right, top to bottom or 
tied together, except for the first and last ones
Sometimes it doesn’t matter in which order something takes place, in case of which both symbols get the same execution order ordinal. Symbols are tied together parallelly instead of serially then or positioned ‘parallely’ over the clock’s arrow.

Type reference

###### Procedures Parameters

A procedure can contain variable objects. The public ones are parameters. The friend ones are parameters within the current globality

#### Standard Modules

There are a few standard modules that supply symbols mostly for hard to divide operations. These symbols don’t only translate as usual to text code, but can also be represented by their own syntax. The clearest example is arithmetic operation symbols. They are translated to text code with formulas. There you also have the perfect example of where plain symbol diagrams are not always adequate. Another standard module is the Assembly module. Assembly symbols can be translated as usual, in case of which they look like ‘normal’ code, a better version of Assembly language to my opinion, but they can also translate to the Intel mnemonics like “MOV AX, 1”.

Data structures in J Data may get alternative notations just as well.

Maybe, but I say maybe, I should make a standard way to make an extension to Symbol Text Code. But that would allow everybody to totally fuck up Symbol Text Code. Unless I don’t publish it.

#### Symbol Text Code

There is a standard way of translating symbol diagrams to symbol text code. There are special standard modules that also have a custom way of translating that I will discuss later.

- Identifiers
- Access operators
- Declarations
- Access controllers
- Parameters
- Arithmetic operators

- Assembly

- Standard conventions

##### Identifiers

Identifiers in Symbol can contain any kind of character, including spaces and punctuation. However, if a character combination is reserved for another purpose, then it can not be contained in an identifier with white space around it, but can be present in an identifier when tied to another word without spaces in between.

Wether you like it or not, words in latin script are all formatted to begin with a capital. This is sort of protection of style and forces you to use spaces or suffer the consequences. < this may be a little crude >

This is a valid identifier:

```
Apple Fruit Table
```

\+ is an operator. So this is an invalid identifier

```
Apple + Pear Fruit Table
```

But without surrounding white space, the operator can be used in an identifier:

```
Apple+Pear Fruit Table
```

##### Access Operators

<< (an object’s Type) operator >>

Interface access .
Member access .
Sub member
Sub system access :
Type access ::

Core : Objects . Event Map :: Alignment . Arbitrary

: Subsystem to subsystem
Subsystem to type
Subsystem to interface (interface access means object access)
Subsystem to member
type to interface
type to member
interface to member
member to submember

to subsystem
to type
to interface
to member
to submember

: to subsystem
:: to type
; to interface
. to member
.. to submember

Core : Object :: Event Map ; Aligment .. Arbitrary

Other scheme:

: from subsystem
:: from type
. from interface
. from member to member
to submember

Aligment . 

Standards

I forgot genetive containment, didn’t I. You do supply a capsule, but everything inside the capsule is like it’s inside its parent. That’s actually what the triangle is for. Nevertheless, you’re forced to use the identifier for access. That’s normal for interfaces, except for the whole interface.

I may want it to be an interface, but I want to see it as member access outside.

The thing is... the member of a purely genetive subdivision without programmatic consequences.

Uhhhmmm... yeah... whatever

An example:

- Alignment
    - Arbitrary
    - Record Size
    - Field Start

The properties of Alignment can be reached by the siblings of Alignment. But the siblings of Alignment can also be accessed by the properties of Alignment. So they have access to 

##### Parameters

There are three types of parameters: in, out and thru. In parameters go in, out parameters go out and thru parameters come in and go out.

Procedure 1 (In: Input, Out: Output 1, Output 2, Thru: Increment Me)
End Procedure


Parameters can have a reference access controller that can be public or friend:

Procedure 1

###### Arguments

: named, unnamed.

#### Diagram Editing

#### Sigma Module

A pentagon can be translated to a Sigma module. Only things publically accessible outside the pentagon get a place inside the Sigma module.

Circles and triangles that are public for instancing, become a type in the Sigma module. There can be a multi-layer subdivision in types. These layers are expressed as sub modules in the Sigma module.

Circles and triangles that are public for reference become public children of the Sigma module’s main type. When a module is instantiated, the creation procedure of the pentagon starts, possibly creating the objects public for reference.

All triangles that are public are put in the module’s interface list. <What subdivision exists there?>

#### Brainstorm

I’m having a hard time finding a good way to explain.

Perhaps I should start at basic programming concepts and then move to more and more advanced ones. This has benefits: I usually translate from another programming language to Symbol, so one should at least know how to express usual programming concepts.

That would make me pass things whose implementation in Symbol I haven’t thought through though.

I’d have to present the concept in both diagram language and text language, because there are parts that don’t look better in diagram. You should be able to embed short text language in the diagram.

Perhaps I should explain on any concept, even when it has no presence in the system because its not necessary.


List diagram elements
List programming aspects
Then associate diagram elements with programming aspects and
Programming aspects with diagram elements.

\---

I adopt the visual basic object way: always an object reference. C++ allows you to declare an object not through a pointer variable, so it is instantiated instantly.

Some objects in Symbol may be tagged so they’re always created.

\---

Global is a bad term

\---

I noticed that in writing when I’ve described how it is, I often leave out the why it’s not different. I do that to keep the story from being lengthy. It happens that ask myself the same questions again as I leave out explanations why it’s not like that.

I should consider to keep them in there. But since I want a story that is not lengthy, I should keep them separate, I guess.

<< I have to define a system that returns  every possible 

tie-together of objects. >> I SHOULD REALLY CONSIDER THIS.

#### Buh

Any symbol code translates to Basic, C++ or Symbol text notation as well as the other way around so you can view any piece of diagram as text code and view any piece of text code as a diagram. There is an assembly module that can be used inside the symbol code, which allows full control over the CPU.

#### Old

##### Contents

< I should distinguish between internal symbols and their representing shapes >

##### Introduction

Do not be alarmed if you can not find how to use a For loop or If structure, because these aren’t explained in this book. Basic statements and operations such as For loop or If structure as well as many others are part of standard symbol modules.

This documentation does not explain object oriented programming. Perhaps I should explain object oriented programming in a document some day.

##### Basic Elements

##### Hierarchies

Another way to see the type/object structure is by coloring the symbols. It can be used to graphically fully expose the inheritance structure.

![](images/Symbol%20Language%20(2004).474.png)

The above shows all smaller circles in blue. That means that all three have the same type. The darker blue circle is the type of the lighter blue ones. Color depth can express the depth of the type/object hierarchy, like the depth of encapsulation is expressed by the size and residence of the circles. There is a standard complex way of doing this coloring. I will elaborate on this later. 

###### Extras Compared To Conventional Object Oriented Programming

In conventional object oriented programming a ancestor object always contained maximally only one instance of the base type. This restriction is overcome in Symbol though it may mostly not be useful. In conventional object oriented programming a ancestor object always contains a fresh new object of the base type. This is a restriction that is overcome in Symbol: two objects with a base type can share a single base object.

##### Grammar

Restrictions to edit actions.

???That triangles can be freely used to anywhere to group things.???
Similar ordinals group things too.... What to do? Put a triangle there for more clarity?

##### Alternative Views

###### Diagram Aspects

There are the following aspects to the diagram:

- Encapsulation
- Lines
- Color
- Shape
- Names

###### Standard Notation

What I have described in the previous sections is the standard notation for Symbol diagrams. 

- Encapsulation is used to express the encapsulation structure
- Lines are used to express the delegation structure
- Color is used to express the type/object structure
- Shapes are used to distinguish between inheritance, encapsulation and execution.
- Names are used to indicate what something is called, what something refers to and of which type it is.

As I said: this is the standard way that the diagram elements are used to express a system. To keep things clear I only introduced you to the standard notation or it would have been futile to explain the notation at all. 

###### Customization

Diagram aspects:

- Encapsulation
- Lines
- Color
- Shape
- Names

Diagram aspects can be arbitrarily exchanged between system aspects. The following is not entirely true, but it draws out the idea: any diagram aspect could represent any system aspect.

###### Hierarchical Diagram Aspects

Diagram aspects:

- Encapsulation
- Lines
- Color

The encapsulation, delegation and type/object hierarchies are all tree-like structures. The diagram’s encapsulation, lines and color can each present a single tree structure. Any of these three diagram aspects can be related to any of the three hierarchies. 

Two diagram aspects can be turned off: lines and color. You can stop color from representing a hierarchy and you can stop lines from expressing a hierarchy. You might want to set up two simultanious views in which you assign different diagram aspects to different hierarchies so for instance you don’t use color to express a diagram aspect, yet in the first diagram you use diagram encapsulation and lines to express two of the hierarchies and in the next diagram you use diagram encapsulation to express the hierarchy missing in the first diagram.

The encapsulation, lines and color aspects of the diagram can be distributed over the encapsulation, delegation and type/object strucures, each hierarchical system aspect being represented by one hierarchical diagram aspect.

\-----

Red, green and blue could actually express three hierarchies...

Or tint, blackness en whiteness.

\-----

###### Criterial Diagram Aspects

Diagram aspects:

- Color
- Shape

There is a set of attributes for each symbol in the system:

- Name
- Parent
- Reference
- Type
- Reference Access
- Type Access
- Inherited
- Executable
- Ordinal
- Selected

These attributes are mostly critical to system design so it is important to express them in a way in the diagram. You can also match symbols to an arbitrarily formulated criterium, which could be regarded a complex or composed attribute. These criteria could be a value of a single attribute, a combination of attributes, a range of values of a single attribute or combination of attributes or could be related to hierarchy depth.

\----

__Thought__:

I could have :
shapes and colors
values of attributes
ranges of attributes
an arbitrary number of values and ranges assigned to any shape or color.

*Waar dit criterium:*

Int(EncapsulationDepth / 2) = ChildDepth / 2

*Een (complexe) toepassing van kleur:*

R = 0.3 \* (1 - (EncapsulationDepth / DeepestEncapsulationDepth)) 
G = 0.6 \*  (EncapsulationDepth / DeepestEncapsulationDepth)
B = 0.9 \* (1 - (EncapsulationDepth / DeepestEncapsulationDepth)) 

*Een (complexe) toepassing van vorm:*

N = 3 + 7 \* (1 - (EncapsulationDepth / DeepestEncapsulationDepth))

En bij overlappende eigenschappen kleuren mixen of optellen en dubbele vormen...

Stel dat ik zelfde klassen dezelfde vorm wil toewijzen

Kan ik niet ook namen gebruiken als criterium diagram eigenschappen?

Er is een grotere complexiteit dan ik in eerste instantie dacht.

Wat is de echte rij met kleur, naam en vorm toepassings-mogenlijkeden zonder efficientie van de oplossing in acht te nemen?

\----

You should be able to highlight symbols with certain simple or complex attributes. Color and shapes can take upon themselves this roll in clarification. You can assign different n-gonic shapes or colors to symbols matching certain criteria. You can easily express a wide range of criteria simultaniously with different colors and shapes

You can also use the color: ‘transparent’. It is almost an insult to call transparent a color because its usefulness by far exceeds that of color. I call transparency a color, because transparency can be applied in exactly the same manner as color. Transparency as a color makes it possible to abstract the diagram. It is a very powerful tool. Abstraction is a mechanism more important than the object oriented paradigma. By using transparency you can hide for instance deep encapsulation depths so that they don’t obscure the big picture. Another very important use of transparency is hiding members of a symbol that have the Reference Access attribute set to private, which means the same as hiding the private members of an object.

(the following paragraph is unclear language)

Another thing about criterial diagram aspects is that you can assign a highlight method to be invoked *under certain circumstances only*, which means for instance that you only show members that are Protected for Reference when the symbol is Inherited and, more related to the Symbol Environment then the Symbol language, the symbol’s parent is the current symbol. That means just about the same as you can only visually see the protected members of an descendant when editing the ancestor. << That’s simply an extra criterium added to the complex criterium, dumb ass >>

###### Other

On top of the arbitrary assignments of diagram elements to aspects of the system there are several other customizations of the view.

You can customize a number of things:

\1) You can express the encapsulation and delegation tree structure as a single encapsulation structure in which symbols can overlap:

This may result in unclarity:

The rule of thumb is: a symbol is encapsulated only if its shape is totally encapsulated << That so? >>

In case of equal ordinals the symbols ARE executed but the order of execution is irrelevant. Even when the order of execution is irrelevant the ordinal is the only pure way to control the positioning of the symbols.

#### Glossary

Parent
Child
Reference
Referrer
Object
Type
Sister
Container
Contents
Scope Level
Level Down
Level Up
Circular Reference
Base
Descendant
Ancestor
Inheritance
Delegation
Encapsulation
Property
Event
Method
Procedure
Event Procedure
Variable
... bla bla bla some other time

#### Brainstorm

A number that's always above zero could be a data type too. Or a number that's always between certain bounds. Or whatever.

Boolean and comparison algebra:

Not CurrentRow < Int(TopRow) = CurrentRow >= Int(TopRow)

Not is both a logical and a comparison operator

Not CurrentRow < Int(TopRow) == CurrentRow >= Int(TopRow)
<> (CurrentRow < Int(TopRow)) == CurrentRow >= Int(TopRow)

Moet je niet gewoon symbolen kunnen added in runtime. Anders kun je misschien geen arrays maken.

Je hebt in Vb 6 en 7 in een With clause get 'Anti-With' net zoals de anti-moniker in Com of beter bekend de hogere directory in een bestands systeem '..'

Consider making:
+=, -=, /=, etcetera:
=+, =-

The problem with that is that + and - can't be unary operators unless you put a space between the = and the + or -:
= +
= -

A parent block is sorta like a globality in that way.

Globality and triangle are alike. They 

I might want to switch the square and pentagon symbols.
A square would then become a globality. A pentagon would become an execution point and then execution would look like neurons between which electrons are shot...

And a 'block' as I described, would actually look like a square.
A procedure will probably not get its own symbol anyway. It would just be an object with an execution point.
An arithmetic operation on something as an argument:

" / 2"
" + 3"

That operation can be executed on something

It would be neccesary to include a variable, actually

x + 3

For instance tString = Left(tString, - 3)

It should cut away the last three characters


Variables declared inside a parent block in a procedure are accessible directly by the child blocks. Variables declared inside a child block are inaccessible to a parent block.

You might not want to be able to reference a types full interface, but only the sub interfaces, so it would be more like com. Oh, this actually seems an access control issue.


Accessing public objects is no longer ambiguous if you use access symbols
just outside the border of
the parent


A pentagon's direct children can all reference eachother and can be
referenced by all ancestors (containmentwise ancestors). Globality is
only one function of a pentagon. Actually a pentagon is a lot like
globality, where there are multiple levels of globality and that exists in
today's systems.


Conditional arguments:

not only being capable of assigning single values to a parameter, but also
being able to
specify ranges. For instance  

Parts(aIDFilter => 100)

Should I make special types for this or should this be generally
applicable. Actually, 
the author has to decide what values may be ranges and which may not. But I
think it must be
as common as assignment for simple data types.

In normal programming languages these operators are only used for
comparison. In the case here
you assign a range by specifying comparison values.


You can use colors coloring diagram elements to denote which diagram aspect represents which system aspect.


Generating the stack operations preceding and concluding function calls is called prolog and epilog code in C


In the C documentation a distinction is made between Lexical Grammar and Phrase Structure Grammar. 

- Lexical grammar:
    - Tokens, keywords, identifiers, constants, string literals, operators, punctuation
- Phrase structure grammar:
    - Expressions, declarations, statements, external definitions


Abstract Symbol. How to express overview concepts, like: there are methods that delegate to methods in children, but put restrictions on the methods.

Methods abstract other methods

The grouping of lines by caller, callee, etcetera

Maybe a private access symbol should be inside the capsule somehow.

perhaps change the symbol

de lijnen van aparte public symbols aan elkaar plakken en line naar object naar samengesmolten public symbol doen wijzen

Tree like diagram with convergences should be part of Symbol I guess.
100258621(14:04 PM) : 
Maybe by giving symbol aspects to it, I can refine the tree like diagram language


Incremental compilation
Debugging
Syntax Checking

##### Notation

ZCore and ZCode provide a more flexible code notation than other languages.

You can choose autoformatting.

In identifiers:

- You can choose to have case sensitivity or no case sensitivity
- You can choose wether or not to use Spaces
- You can choose wether or not to use other characters in a single identifier (that you normally wouldn’t in other languages)
- You can choose whether or not there’ll be extra Spaces around member operators and function call operators

Spaces will not serve as white Space if within identifiers. This adds a bit more complexity to parsing than in other languages.

This is my personal favorite notation of a method call:

Return Value = Object . Object’s Method ( Method Argument 1, Method Argument 2 )

I used to be used to Visual Basic notation which would be:

ReturnValue = Object.ObjectMethod(MethodArgument1, MethodArgument2)

I see readability in using Spaces in identifiers, which would make it:

Return Value = Object.Object’s Method(Method Argument 1, Method Argument 2)

Now the member operators and function call operators are not easily spotted, so I add Spaces around those:

Return Value = Object . Object’s Method ( Method Argument 1, Method Argument 2 )

I guess I kept liking the capitals.

###### Specifics

####### Member call

Return Value = Object . Object’s Method ( Method Argument 1, Method Argument 2 )

Return Value 1, Return Value 2 = Object . Object’s Method ( Method Argument 1, Method Argument 2 )

####### Member declaration

With types...

Method Object . Method (Word: Argument 1, Double Word: Argument 2 ) Real 32: Return Value

Or:

Object . Method (Argument 1 As Word, Argument 2 As Double Word) Return Value As Real 32

Or: 

Object . Method (Argument 1 as Word, Argument 2 as Double Word) Return Value as Real 32


Or:

Method Object . Method (Word Argument 1, Double Word Argument 2 ) Real 32 Return Value

Since I’m working with multiple arguments as well as multiple return values, I may as well use a separate argument type that is both an argument as well as a return value (not to be mistaken for a reference argument).

Arguments are then In parameters. Return values are Out parameters. The last type described would be InOut parameters, more nicely called Thru (Through) parameters.

You could also say Read, Write and Read/Write, but this creates ambiguity about who’se reading or writing: the caller or the procedure.

In, Out and Through. Now we need a notation for them

This was the notation with arguments and return values:

(In, In, In) Out Out Out

Now we need a through.

Options:

In: Argument1, Argument2, Thru: Argument3, Argument4, Out: Argument3, Argument4

I’ll stick to that for now..


Thru arguments are not to be confused by reference arguments. The values of Thru arguments are actually put on the stack and read from the stack and written to the stack by the procedure. Reference arguments are usually In paramters and not written. The reference argument is a mere number that points to an object. The object a reference argument points at can be written and read, but this object doesn’t reside on the stack. Reference arguments in other languages were often used as a trick to use multiple return values or to have arguments that are both given to the procedure and then returned to the caller possibly altered: thru arguments.

Reference arguments are still of use, but since J Core supports multiple return values (Out arguments) and thru arguments, they

Reference arguments are actually pointer arguments. 

References in Visual Basis and the Object Variables are pointers.

References in C++ are a mere altered notation of pointers, with a few restrictions (even) put on them.


> Address (__In:__ First Fragment, Fragments, Position, __Thru:__ Current Physical Fragment, Current Logical Fragment, __Out:__ Address)


When only using in and out arguments I could optionally use the ‘normal’ notation:

Function (In1, In2) Out1, Out2



If IsBetween(TheValue , A, B) Then

or

If TheValue IsBetween(A, B) Then

or

If TheValue IsBetween A And B Then

or

If the value is between A and B then

it's more or less like you're making a simple grammar to be able to notate a function call more dynamically.

\----

100258621(03:22 AM) : 
and also, but not. Hmm those kinds of expressions may do for odd boolean operators too... explore
100258621(06:22 AM) :


nouns are objects, verbs are methods and adverbs are properties. Hmmm... the study of language and grammar will extend the symbol language.

Symbol non encapsulative (full referential) notation. Symbol total encapsulative notation (non referentia) (possible overlaps). Symbol obvious encapsulative notation ? level bound?

So there doesn't have to be a difference between reference and encapsulation. You could arbitrarily assign wether to regard it reference and wether to regard it encapsulation?

For childern that refer to the same thing, should or shouldn't the parent be seen as having to refer to it too? Hmmm

)Oh. In overlapping it seems they contain eachother and you can't see who's the parent and who's the child

Seeing everything that's directly or indirectly referring to another thing.

Seeing what's obsolete, so unreferenced.

Seeing everything that's directly or indirectly referenced by something


\-

Symbol has to be revised. It doesn’t distinct types and interfaces well. It doesn’t work well with interfaces. Like how do I pass a pointer one interface of an object to a method?

\-

Giving properties instant changed events.

\-

The scope of a variable defines which parts of your code are aware of its existence.

\-

If there are multiple procedures and variables with the same name, Visual Basic takes the value of the more local variable, which in this case, is the Form1 variable.

\-

References to the name Temp within the procedure would access the local variable; references to Temp outside the procedure would access the public variable. The module-level variable can be accessed from within the procedure by qualifying the variable with the module name
\-
Static Function RunningTotal(num)
\-
Const conReleaseDate = #1/1/95
\-
Public Const conPi = 3.14, conMaxPlanets = 9, \_
conWorldPop = 6E+09
\-
Const conPi2 = conPi \* 2
\-
Constants can be procedure level
\-
Private I As Integer, Amt As Double


Using the ParamArray keyword allows you to specify that a procedure will accept an arbitrary number of arguments. This allows you to write functions like Sum:





Select Case testexpression
[Case expressionlist1
[statementblock-1]]
[Case expressionlist2
[statementblock-2]]
.
.
.
[Case Else
[statementblock-n]]
End Select

Each expressionlist is a list of one or more values.

\-

There can be multiple return out variables. For that one procedure could also be represented by multiple objects, not? When you could separately read the output, I should manage that you can get the output objects at will, but only when the input changes the procedure is reexecuted when you get an output object...

A procedure often returns a single object. Many procedures simply stand for returning a single object. In that case you can use the procedure AS an object and the procedure is notated as an object... I still need to figure out how to notate it, but it will still contain an execution point and at the time the object is referenced for retrieval or assignment, the execution sets off.

A procedure’s representation can alternatively can be its return value or, in case of multiple return values, a group symbol containing the return values.

Je roept eigenlijk aldoor maar procedures aan als je naar een object refereert om een procedure ervan aan te roepen, dan is dat referen eigenlijk het aanroepen van een procedure die een obect referentie terug geeft

#### Old Overview of Lines

###### Dumped Scattered Around Overviews

####### Overview of Lines: Direction: Access Symbols

- An access symbol can totally determine the direction
    - Access symbol at one end
    - Access symbol at the other end
    - Access symbol at both ends
    - Access symbols left out. Possibilities:
        - The direction goes *both ways.*
        - The direction doesn’t matter in this view
        - Other rules determine the direction.

####### Overview of Lines, Direction, Precedence of Direction Rules

- You can leave out access symbols if other rules determine the direction. The precedence of rules is:
    - *Acces Symbols*: *Access symbol determines direction.*
    - *Outwards*: *The direction is outwards by default.*
    - *You Sooner Exit a Procedure than an Object.*
    - You sooner reference an interface than redirect an interface
    - *Exit the Most Borders:* If multiple borders are exited and entered then the line exits the most borders and enters the least borders. This rule is mostly not relied on.
- Without precedence the rules are summarized as:
    - *Access symbol is decisive.*
    - *You sooner to exit than enter.*  
    - *You sooner to exit a procedure than an object.*
    - You sooner reference an interface than redirect an interface

####### Overview of Lines, Direction, Bidirection

- Bidirection:
    - If no rule determines direction then the direction is either not expressed in the diagram or the direction goes both ways.
    - The direction certainly goes both ways if both ends have an access symbol.

####### Overview of Lines: Direction

- Lines have a direction
- An access symbol can totally determine the direction.
    - Access symbol at one end
    - Access symbol at the other end
    - Access symbol at both ends
    - Access symbols left out. Possibilities:
        - The direction goes *both ways.*
        - The direction doesn’t matter in this view.
        - Other rules determine the direction.
- You can leave out access symbols if other rules determine the direction. The precedence of rules is:
    - *Acces Symbols*: *Access symbol determines direction.*
    - *Outwards*: *The direction is outwards by default.*
    - *You Sooner Exit a Procedure than an Object*
    - *Exit the Most Borders:* If multiple borders are exited and entered then the line exits the most borders and enters the least borders. This rule is mostly not relied on.
- Direction both ways:
    - If no rule determines direction then the direction is either not expressed in the diagram or the direction goes both ways.
    - The direction certainly goes both ways if both ends have an access symbol.

####### Overview of Lines, Connection

- Procedures can be tied only to procedures
- Objects can be tied only to objects

- An object symbol can have only one line of each type: an object line, a type line and an interface line
- A procedure symbol can have only one line: a call line *or* a reference line.

- A symbol’s line points *away* from the symbol.
- The other connected lines point *to* the symbol.

####### Overview of Lines: Procedure Calls and References

- A square can ony have a call line if it’s directly inside another square.
- The call line must first exit the containing square.

- If a solid procedure line can't be a call line then it is a reference line
- If it’s a reference line then you use a solid line unless it directly exits a square

- Any square can have a reference line

A procedure symbol can have one of four roles: - definition, - clause, - call, - reference

####### Overview of Redirection

- Object symbol redirection
    - Target symbols
    - Circularity
        - By recurrence
        - By bidirection

- Procedure redirection
    - A call can not be called or refererenced
    - So a *call* line can only be at the beginning of the redirection
    - So you can only redirect procedures with reference lines

####### Overview of Access Symbol Placement

- If a line crosses borders it first exits borders and then enters borders. You can't mix exits and entrances.
- If an access symbol is drawn to denote direction it is by default put in the section between the exits and entrances, so not neccessarily with the eventually entered symbol.
- In other words: the access symbol is usually put in front of the border that is first entered.
- If this access symbol will go out of view then the access symbol can be placed where it’s visible.
- It is placed in front of a border that is gone entered or exited.

####### Overview of Lines: Alternate Notations

- Double lined shapes:

    - The line can be left out in these cases, but doesn’t have to.

    - Double solid line object symbol:
        - It’s an object reference or
        - It’s an object reference to an object in the parent
    - Triple solid line object symbol:
        - It’s an object reference to an object in the grandparent
    - Etcetera

    - Dashed line object symbol:
        - It has an external type or
        - It has a type that’s inside the parent
    - Double dashed line object symbol:
        - It has a type that’s inside the grandparent
    - Etcetera

    - Dotted line object symbol:
        - It has an external interface or
        - It has an interface that’s inside the parent
    - Double dotted line object symbol:
        - It has an interface that’s inside the grandparent
    - Etcetera

    - Double solid line square:
        - It is a call
        - It’s a call to a procedure in the parent
    - Triple solid line square:
        - It’s a call to a procedure in the grandparent
    - Etcetera

    - Dashed square:
        - It’s a procedure reference
        - It’s a procedure reference to a procedure in the parent
    - Double dashed square:
        - It’s a procedure reference to a procedure in the grandparent
    - Etcetera

- Double lines:

    - In these cases, alternate shape borders are usually not used

    - Double line:     line points two capsules outwards
    - Triple line:     line points three capsules outwards

- Line convergence:

    - If there are many lines then they can converge. They can be grouped by how many borders they will exit and by what they will enter.
    - The grouping can be multi dimensional <P>. 
    - And grouping can take place at multiple borders
    - The grouping between borders can become more precise or more general
    - You can name the groups of lines by what they exit or enter. Sort of line a bus lane can be named by its destination.

- Ambiguity in alternate notations:

    - Double shape borders can seem ambiguous to double encapsulation
    - Double lines can seem ambiguous to two separate lines.
    - Line grouping can make ambiguity of double lines even worse.

You can decide on your own what kind of notation you want to use, but the programming environment adopts standard ways to draw a diagram. It automatically uses different notations in different views on the system.

##### Original

- Direction

    - Lines have a direction

    - An access symbol can totally determine the direction
    - Access symbol at one end
    - Access symbol at the other end
    - Access symbol at both ends
    - Access symbols left out. Possibilities:
        - The direction goes *both ways*
        - The direction doesn’t matter in this view
        - Other rules determine the direction

    - You can leave out access symbols if other rules determine the direction. The precedence of rules is:
    - *Acces Symbols*: Access symbol determines direction
    - *Outwards*: The direction is outwards by default
    - *You Sooner Exit a Procedure than an Object*
    - *Exit the Most Borders:* If multiple borders are exited and entered then the line exits the most borders and enters the least borders. This rule is mostly not relied on.
    - Without precedence the rules are summarized as:
    - Access symbol is decisive
    - You sooner to exit than enter
    - You sooner to exit a procedure than an object

    - Bidirection:
    - If no rule determines direction then the direction is either not expressed in the diagram or the direction goes both ways.
    - The direction certainly goes both ways if both ends have an access symbol.

- Connections

    - Procedures can be tied only to procedures
    - Objects can be tied only to objects

    - An object symbol can have only one line of each type: an object line, a type line and an interface line
    - A procedure symbol can have only one line: a call line *or* a reference line.

    - A symbol’s line points *away* from the symbol.
    - The other connected lines point *to* the symbol.

- Procedure Calls and References

    - A square can ony have a call line if it’s directly inside another square.
    - The call line must first exit the containing square.

    - If a solid procedure line can't be a call line then it is a reference line
    - If it’s a reference line then you use a solid line unless it directly exits a square

    - Any square can have a reference line

    - A procedure symbol can have one of four roles: - definition, - clause, - call, - reference

- Redirection

    - Object symbol redirection
    - Target symbols
    - Circularity
        - By recurrence
        - By bidirection

    - Procedure redirection
    - A call can not be called or refererenced
    - So a *call* line can only be at the beginning of the redirection
    - So you can only redirect procedures with reference lines

- Access symbol placement

    - If a line crosses borders it first exits borders and then enters borders. You can't mix exits and entrances.
    - If an access symbol is drawn to denote direction is is by default put in the section between the exits and entrances, so not neccessarily with the eventually entered symbol.
    - In other words: the access symbol is usually put in front of the border that is first entered.
    - If this access symbol will go out of view then the access symbol can be placed where it’s visible.
    - It is placed in front of a border that is gone entered or exited.

- Alternate notations

    - Double shape borders:

        - The line can be left out in these cases, but doesn’t have to.

        - Double solid line object symbol:
        - It’s an object reference or
        - It’s an object reference to an object in the parent
        - Triple solid line object symbol:
        - It’s an object reference to an object in the grandparent
        - Etcetera

        - Dashed line object symbol:
        - It has an external type or
        - It has a type that’s inside the parent
        - Double dashed line object symbol:
        - It has a type that’s inside the grandparent
        - Etcetera

        - Dotted line object symbol:
        - It has an external interface or
        - It has an interface that’s inside the parent
        - Double dotted line object symbol:
        - It has an interface that’s inside the grandparent
        - Etcetera

        - Double solid line square:
        - It is a call
        - It’s a call to a procedure in the parent
        - Triple solid line square:
        - It’s a call to a procedure in the grandparent
        - Etcetera

        - Dashed square:
        - It’s a procedure reference
        - It’s a procedure reference to a procedure in the parent
        - Double dashed square:
        - It’s a procedure reference to a procedure in the grandparent
        - Etcetera

    - Double lines:

        - In these cases, alternate shape borders are usually not used

        - Double line: 
        - Line points two capsules outwards
        - Triple line: 
        - line points three capsules outwards

    - Line convergence:

        - If there are many lines then they can converge. They can be grouped by how many borders they will exit and by what they will enter.
        - The grouping can be multi dimensional <P>. 
        - And grouping can take place at multiple borders
        - The grouping between borders can become more precise or more general
        - You can name the groups of lines by what they exit or enter. Sort of line a bus lane can be named by its destination.

    - Ambiguity in alternate notations:

        - Double shape borders can seem ambiguous to double encapsulation
        - Double lines can seem ambiguous to two separate lines.
        - Line grouping can make ambiguity of double lines even worse.

    - You can decide on your own what kind of notation you want to use, but the programming environment adopts standard ways to draw a diagram. It automatically uses different notations in different views on the system.

##### Original List

- Alternate notation for symbols: dashed squares...

- Lines have a direction
- Direction is usually outward
- If both ends go outward, then there are precedence rules
    - An object symbol's line is sooner to exit a procedure than to exit an object
- If precedence rules can't determine the direction then 
    - An access symbol determines the direction
<< If direction is determined with none of the rules then the direction is either insignificant or the direction goes both ways. An access symbol on both ends expresses that the direction REALLY goes both ways. >>
- The direction goes both way
    - Or
- Access symbols can be at both ends which makes the line go both ways
- An object symbol can have only one line of each type
- A procedure symbol can have only one line. So it can't have a call line AND a reference line
- the other connected lines point to the symbol, not away

- Redirection
- circularity
    - by recurrence
    - by ambiguity
- target symbols

- procedures can be tied only to procedures
- objects can be tied only to objects

- A square can only have a call line directly exiting another square
- A solid procedure line that can't be a call line is treated as a reference line
“If it is a reference line and a solid line can’t be a call line, a solid line is used”>>
- You can't call or reference a call
- So you can only redirect procedures with reference lines
- So a call line can only be at the beginning of the redirection

- If a line crosses borders it first exits borders and then enters borders. You can't mix exits and entrances
- If an access symbol is drawn to denote direction is is by default put in the section between the exits and entrances, so not neccessarily with the eventually entered symbol.
- If this access symbol will go out of view then the
The access symbol is put in front of the border that is entered.

Create default, ready to easily work with, settings for objects. ‘Advanced’ programmers can alter them as they know better. Programmers might want to create their own default that overrides the premade default. Or use no initialization at all. I’ll think about that later.

\-

Arrays and collections are types that contain objects of a variable type, but not generic on each action. In visual basic you can’t create custom forms of such things. In C++ .... In Com you would HAVE to give the type a certain interface for it to have this genericity and it’s not really handy. In Symbol you can easily change a symbol’s type in run time so you can create custom types that have these array capabilities. This makes it possible for an array to be a regular symbol object in a library and not a special built in type.


I must write documentation on how to design applications. Designing that is not user interface centered and why my type of layering is better than user interface centered and other layering of application design.

#### Attempt to Organize Lines Chapter

##### Original Subdivision

- Direction:
    - Access Symbols
    - Rules:
        - Access Symbols
        - Outward
        - You Sooner Exit a PRocedure than an Object
        - You Sooner Reference an Interface than Redirect an Interface
        - Exit the Most Borders
    - Bidirection
- Connection~
    - Procedures to Procedures, Objects to Objects
    - Referencing Descendants
    - Line ownership
        - Object symbol can have object, type and interface line
        - Procedure symbol can have call *or* reference line and an interface line
- Procedure Lines
    - Call only from another square
    - Any solid procedure line that can’t be a call line is a reference line
        - Procedure Symbol Roles
            - Definition
            - Clause
            - Call
            - Reference
            - Can’t be both a reference and a call
            - \* Maybe I should add procedure interface roles
            - \* Maybe I should discuss object symbol roles (lateron)
            - Object reference
            - Object
            - Type
            - Interface
            - Base
        - Reference and Call targets
            - Reference to definition
            - Reference to clause
            - Reference to reference
            - Call to definition
            - Call to clause
            - Call to reference
        - The Object of the Call Target
            - You can’t call upward in the ancestry (is introduced later too)
            - Events” Techniques to communicate to the parent (is introduced later too)
- Redirection
    - Object Symbol Redirection
        - Target Symbols
        - Circularity
        - Tracing Object and Type
    - Procedure Redirection
        - Target Symbols
        - Call can not be called or referenced
        - \* Any tracing?
- Access Symbol Placement
- Accesses
    - Can’t call upward in the ancestry (Basic call forms)
    - An access is where a call line enters an object symbol
    - Accesses
        - Tracing Object and Type
        - Each access requires tracing object and type
        - After accesses, the reference line must be followed
            - Each reference line redirection requires tracing object and type
            - But not every object symbol the reference line crosses
            - \* Why for the call line then?
        - Complex call example
- Ways to Access
    - < Neigbor > Access
    - Child Access
    - Global Access
    - Interface Access
    - Clause Access
    - Globalities, Interface and Clauses
- Implicit Calls
    - Explicit Calls
    - Implicit Calls
    - Implicit Return Value Reference
    - Multiple Out Parameters
- Procedure Interface
- All Object Symbols that are the same Objects have the Same Line Targets
- Genericity
    - Type Genericity
    - Interface Genericity
        - Type Interface Genericity
    - Explicit Isn’t Fixed
- Symbols can Overlap
    - Containment for Divergence, Lines for Convergence
    - Triangles For Arbitrary Grouping <Non-Object Triangles>
    - Procedures can Overlap
- Events
- Peels
    - Shape Peels
    - Line Peels
    - Ambiguity In Peels

##### Forming New Subdivision

###### Mark Main Grouping

- Direction:
    - Access Symbols
    - Rules:
        - Access Symbols
        - Outward
        - You Sooner Exit a Procedure than an Object
        - You Sooner Reference an Interface than Redirect an Interface
        - Exit the Most Borders
    - Bidirection
- Connection~
    - Procedures to Procedures, Objects to Objects
    - Referencing Descendants
    - Line ownership
        - Object symbol can have object, type and interface line
        - Procedure symbol can have call *or* reference line and an interface line
- Procedure Lines
    - Call only from another square
    - Any solid procedure line that can’t be a call line is a reference line
    - Procedure Symbol Roles
        - Definition
        - Clause
        - Call
        - Reference
        - Can’t be both a reference and a call
        - \* Maybe I should add procedure interface roles
        - \* Maybe I should discuss object symbol roles (lateron)
        - Object reference
        - Object
        - Type
        - Interface
        - Base
    - Reference and Call targets
        - Reference to definition
        - Reference to clause
        - Reference to reference
        - Call to definition
        - Call to clause
        - Call to reference
    - The Object of the Call Target
        - You can’t call upward in the ancestry (is introduced later too)
        - Events: Techniques to communicate to the parent (is introduced later too)
- Redirection
    - Object Symbol Redirection
        - Target Symbols
        - Circularity
        - Tracing Object and Type
    - Procedure Redirection
        - Target Symbols
        - Call can not be called or referenced
        - \* Any tracing?
- Access Symbol Placement
- Accesses
    - Can’t call upward in the ancestry (Basic call forms)
    - An access is where a call line enters an object symbol
    - Accesses
        - Tracing Object and Type
        - Each access requires tracing object and type
        - After accesses, the reference line must be followed
            - Each reference line redirection requires tracing object and type
            - But not every object symbol the reference line crosses
            - \* Why not for the call line then?
        - Complex call example
- Ways to Access
    - < Neigbor > Access
    - Child Access
    - Global Access
    - Interface Access
    - Clause Access
    - Globalities, Interface and Clauses
- Implicit Calls
    - Explicit Calls
    - Implicit Calls
    - Implicit Return Value Reference
    - Multiple Out Parameters
- Procedure Interface
- All Object Symbols that are the same Objects have the Same Line Targets
- Genericity
    - Type Genericity
    - Interface Genericity
    - Type Interface Genericity
    - Explicit Isn’t Fixed
- Symbols can Overlap
    - Containment for Divergence, Lines for Convergence
    - Triangles For Arbitrary Grouping <Non-Object Triangles>
    - Procedures can Overlap
- Events
- Peels
    - Shape Peels
    - Line Peels
    - Ambiguity In Peels

###### Group Together and Reorder Groups

- Direction:
    - Access Symbols
    - Rules:
        - Access Symbols
        - Outward
        - You Sooner Exit a Procedure than an Object
        - You Sooner Reference an Interface than Redirect an Interface
        - Exit the Most Borders
    - Bidirection
        - Access Symbol Placement
- Connection~
    - Procedures to Procedures, Objects to Objects
    - Line ownership
        - Object symbol can have object, type and interface line
        - Procedure symbol can have call *or* reference line and an interface line
- Procedure Lines
    - Call only from another square
    - Any solid procedure line that can’t be a call line is a reference line
    - Procedure Symbol Roles
        - Definition
        - Clause
        - Call
        - Reference
        - Can’t be both a reference and a call
        - \* Maybe I should add procedure interface roles
        - \* Maybe I should discuss object symbol roles (lateron)
        - Object reference
        - Object
        - Type
        - Interface
        - Base
    - Reference and Call targets
        - Reference to definition
        - Reference to clause
        - Reference to reference
        - Call to definition
        - Call to clause
        - Call to reference
    - The Object of the Call Target
        - You can’t call upward in the ancestry (is introduced later too)
        - Can’t call upward in the ancestry (Basic call forms)
        - Events: Techniques to communicate to the parent (is introduced later too)
            - Events
- Redirection
    - Object Symbol Redirection
        - Target Symbols
        - Circularity
        - Tracing Object and Type
        - Tracing Object and Type
    - Procedure Redirection
        - Target Symbols
        - Call can not be called or referenced
        - \* Any tracing?
- Accesses
    - An access is where a call line enters an object symbol
    - Accesses
        - Each access requires tracing object and type
        - After accesses, the reference line must be followed
        - Each reference line redirection requires tracing object and type
        - But not every object symbol the reference line crosses
        - \* Why not for the call line then?
    - Complex call example
- Ways to Access
    - < Neigbor > Access
    - Child Access
    - Global Access
    - Interface Access
    - Clause Access
    - Globalities, Interface and Clauses
- Implicit Calls
    - Explicit Calls
    - Implicit Calls
    - Implicit Return Value Reference
    - Multiple Out Parameters
- Genericity
    - Type Genericity
    - Interface Genericity
    - Type Interface Genericity
- Explicit Isn’t Fixed
- < There is a distinction between notation methods and system rules >
- Peels
    - Shape Peels
    - Line Peels
    - Ambiguity In Peels
- Symbols can Overlap
    - Containment for Divergence, Lines for Convergence
    - Triangles For Arbitrary Grouping <Non-Object Triangles>
    - Procedures can Overlap


- Move to other chapters:
- Procedure Interface
- All Object Symbols that are the same Objects have the Same Line Targets
- Referencing Descendants

###### Mark Sub Grouping and Change Some

- Direction:
    - Access Symbols
    - Rules:
        - Access Symbols
        - Outward
        - You Sooner Exit a Procedure than an Object
        - You Sooner Reference an Interface than Redirect an Interface
        - Exit the Most Borders
    - Bidirection
    - Access Symbol Placement

- Line Rules

    - Main topics:
        - The __*ownership*__ of lines
        - The __*restrictions*__ on line targets (and sources)
        - The __*roles*__ that symbols get when connecting them with lines
        - Redirection and __*targets*__ (hmmm... which adds more roles)
        - Events (this important subject is in jeopardy of being swallowed by a tree of super sections
    - Connection~
        - Procedures to Procedures, Objects to Objects
        - Line ownership
            - Object symbol can have object, type and interface line
            - Procedure symbol can have call *or* reference line and an interface line
    - Procedure Lines
        - Call only from another square
        - Any solid procedure line that can’t be a call line is a reference line
            - Procedure Symbol Roles
            - Definition
            - Clause
            - Call
            - Reference
            - Can’t be both a reference and a call
            - \* Maybe I should add procedure interface roles
            - \* Maybe I should discuss object symbol roles (lateron)
            - Object reference
            - Object
            - Type
            - Interface
            - Base
        - Reference and Call targets
            - Reference to definition
            - Reference to clause
            - Reference to reference
            - Call to definition
            - Call to clause
            - Call to reference
        - The Object of the Call Target
            - You can’t call upward in the ancestry (is introduced later too)
            - Can’t call upward in the ancestry (Basic call forms)
            - Events: Techniques to communicate to the parent (is introduced later too)
                - Events
- Redirection
    - Object Symbol Redirection
        - Target Symbols
        - Circularity
        - Tracing Object and Type
        - Tracing Object and Type
    - Procedure Redirection
        - Target Symbols
        - Call can not be called or referenced
        - \* Any tracing?

- Accesses
    - An access is where a call line enters an object symbol
    - Each access requires tracing object and type
    - After accesses, the reference line must be followed
    - Each reference line redirection requires tracing object and type
    - But not every object symbol the reference line crosses
    - \* Why not for the call line then?
    - Complex call example

- Ways to Access
    - < Neigbor > Access
    - Child Access
    - Global Access
    - Interface Access
    - Clause Access
    - Globalities, Interface and Clauses

- Genericity
    - Implicit Calls
        - Explicit Calls
        - Implicit Calls
        - Implicit Return Value Reference
        - Multiple Out Parameters
    - Type Genericity
    - Interface Genericity
    - Type Interface Genericity
    - Explicit Isn’t Fixed
    - Notation Methods versus System Rules
        - Implicit calls are but notation methods, that don’t affect the behavior of the system. Type genericity, interface genericity and type interface genericity are system rules. They affect the behavior of the system.

- Peels
    - Shape Peels
    - Line Peels
    - Ambiguity In Peels

- Symbols can Overlap
    - Containment for Divergence, Lines for Convergence
    - Triangles For Arbitrary Grouping <Non-Object Triangles>
    - Procedures can Overlap

- Move to other chapters:
    - Procedure Interface
    - All Object Symbols that are the same Objects have the Same Line Targets
    - Referencing Descendants

In the next organization I’ve also reorganized Line Rules.

##### New Subdivision

###### Direction

- Access Symbols
- Rules:
    - Access Symbols
    - Outward
    - You Sooner Exit a Procedure than an Object
    - You Sooner Reference an Interface than Redirect an Interface
    - Exit the Most Borders
- Bidirection
- Access Symbol Placement

###### Line Rules

- Line Ownership (The __*ownership*__ of lines)
    - Object symbol can have object, type and interface line
    - Procedure symbol can have an interface line and acall *or* reference line
- Target Symbols (Redirection and __*targets*__ (hmmm... which adds more roles)
- Redirection
    - Object Symbol Redirection
        - Target Symbols
        - Circularity
        - Tracing Object and Type
        - Tracing Object and Type
    - Procedure Redirection
        - Target Symbols
        - Any tracing
- Line Restrictions (The __*restrictions*__ on line targets (and sources)
    - Procedures to Procedures, Objects to Objects
    - You can only call directly from a procedure
        - A call can not be called or referenced
    - You can’t call upward in the ancestry
    - The Object of the Call Target
    - You can’t call upward in the ancestry (is introduced later too)
    - Can’t call upward in the ancestry (Basic call forms)
    - Any solid procedure line that can’t be a call line is a reference line
- Symbol Roles (The __*roles*__ that symbols get when connecting them with lines)
    - Procedure Symbol Roles
    - Definition
    - Clause
    - Call
    - Reference
    - Can’t be both a reference and a call
    - \* Maybe I should add procedure interface roles
    - \* Maybe I should discuss object symbol roles (lateron)
    - Object reference
    - Object
    - Type
    - Interface
    - Base
- Reference and Call targets
    - Reference to definition
    - Reference to clause
    - Reference to reference
    - Call to definition
    - Call to clause
    - Call to reference
- Events
    - Events: Techniques to communicate to the parent (is introduced later too)

###### Accesses

- An access is where a call line enters an object symbol
- Each access requires tracing object and type
- After accesses, the reference line must be followed
    - Each reference line redirection requires tracing object and type
    - But not every object symbol the reference line crosses
    - \* Why not for the call line then?
- Complex call example

###### Ways to Access

- < Neigbor > Access
- Child Access
- Global Access
- Interface Access
- Clause Access
- Globalities, Interface and Clauses

###### Genericity

- Implicit Calls
    - Explicit Calls
    - Implicit Calls
    - Implicit Return Value Reference
    - Multiple Out Parameters
- Type Genericity
- Interface Genericity
- Type Interface Genericity
- Explicit Isn’t Fixed
- Procedure Interaface Genericity
- Notation Methods versus System Rules
    - Implicit calls are but notation methods, that don’t affect the behavior of the system. Type genericity, interface genericity, type interface genericity and procedure interface genericity are system rules. They affect the behavior of the system.

###### Peels

- Shape Peels
- Line Peels
- Ambiguity In Peels

###### Symbols can Overlap

- Containment for Divergence, Lines for Convergence
- Triangles For Arbitrary Grouping <Non-Object Triangles>
- Procedures can Overlap

###### Move to other chapters:

- Procedure Interface
- All Object Symbols that are the same Objects have the Same Line Targets
- Referencing Descendants

#### Symbol Drawing Equipment

It would be very nice to have a little drawing thing that makes it easy for you to draw on paper:

- Dotted lines
- Dashed lines
- Dotted and dashed peels

#### Symbol Sign Language

How to use hand signs to express systematics.

#### Human Classification

< even the title is wrong>

#### Declared Traversions / Constructions

I’ve noticed that with my coding methods in deep structures in Visual Basic 6, I use code like this for instance:

```vb
With aClass
    With .Attributes
        For i = 0 To .Count - 1
            With .Item(i)
                L "Private Const " + tPrefix + .CodeName + "Field As Long = " + CStr(aIndex)
                aIndex = aIndex + 1
            End With
        Next i
    End With
    With .RelatedClasses
        For i = 0 To .Count - 1
            If .ItemUsed(i) Then
                With .Item(i)
                    If .AbstractNumber = One Then
                        If .WhenX.EditMode = ObjectEditValues Then
                            'Recursion
                                AddFieldConstants .Type, aIndex, tQualifier + .CodeNameSingular
                        End If
                    End If
                End With
            End With
        Next i
    End With
End With
```

There are actually two loops in this construction. I frequently need those loops and I then copy those constructions.

It might be an idea to be able to declare those constructions and reuse them by name:

Delcaration of constructions:

```
Construction Type Attributes ( aClass )

    With aClass
        With . Attributes
            For i = 0 To . Count - 1
                With . Item ( i )
                    ...
                End With
            Next i
        End With
    End With

End Construction

Construction Related Types With Edit Values ( aClass )

    With aClass
        With . Related Types
            For i = 0 To . Count - 1
                If . Item Used ( i ) Then
                    With .Item ( i )
                        If . Abstract Number = One Then
                            If . When X . EditMode = Values Then
                                ...
                            End If
                        End If
                    End With
                End With
            Next i
        End With
    End With

End Construction
```

Use of construction:

```
For Type Attributes ( aClass )
    L "Private Const " + tPrefix + . Code Name + "Field As Long = " + aIndex
    aIndex = aIndex + 1
End For

For Related Types With Edit Values ( aClass )
    Add Field Constants ( . Type , aIndex , tQualifier + . Code Name Singular )
End For
```

Looking at this, I see that you could do this easily in Symbol, by making your own execution control procedure.

#### Notational Choice

You can express the final database structure in Symbol code and in information language ‘dialects’. Actually it’s no more than a notational choice. Symbol works as a base for information language. Information Language is sort of Symbol with an arrow notation and without multiple encapsulation levels. Information Language as I (part) defined it, totally flattens out the object structure. It hands ideas about flattening out object structure, though.

Ja, het begint zich een beetje in elkaar te schuiven. Information is niet meer dan een Symbol dialect, met een speciale toepassing. Als je in Symbol een flat object, arrow notatie invoert dan heb je information language al bijna. Hmmm... interessant.

#### UML

- Symbol depicts the technical object oriented organization. I suspect UML does provide some practical points of view, that Symbol does not. Can Symbol somehow serve as an intermediate language which translates to UML and back? Or should something UML-like still be used to express systems in a practical way.


Notes
-----

Maybe I should abolish the word type completely. It’s just the word that is ‘Soort’ in dutch. I think the word Type does much better. A ‘type of object’ is understandable for normal people too, while a ‘type of object’ will make them stop listeningen.

- Use ‘Type’ where you use ‘Type’
- Use ‘Diamond’ where you use ‘Diamond’
- Use ‘Line’ where you use ‘Line’
- Introduce the word variable in the ‘Introduction’ chapter.
- Just as in procedures, you could make certain members of a type required, while others are optional. You have to fill in the required members on creation of the object. This should be there for the same reason as required parameters are there in a procedure: the function of the object just doesn’t make sense unless you write the required members. The programmer is made extra aware of that by making the members required.

You can also let J Data maintain the containment automatically, based on mutual ancestors. I should be able to do that automatically in Symbol too. Should make a note about that in the Symbol documentation.

\-----

Ik moet een soort Symbol shorthand maken, om met pen en papier te gebruiken, zonder dat je het diagram telkens opnieuw moet tekenen of de kluts kwijt raakt.