﻿Construct Drafts | Automatic Containment
========================================

`[ Draft ]`

__Contents__

- [Introduction](#introduction)
- [A slice of referential structure](#a-slice-of-referential-structure)
- [The main solution](#the-main-solution)
- [The closest mutual parent](#the-closest-mutual-parent)
- [Branched out reference lines](#branched-out-reference-lines)
- [Recap](#recap)
- [Zooming in, zooming out and making changes](#zooming-in-zooming-out-and-making-changes)
- [Analogy to the real world](#analogy-to-the-real-world)
- [Ignored concepts](#ignored-concepts)
    - [Physical location](#physical-location)
    - [Caching](#caching)
    - [Pointers](#pointers)
    - [Residence on a site](#residence-on-a-site)
    - [Central registration lists](#central-registration-lists)
    - [Classes, interfaces and methods](#classes-interfaces-and-methods)
    - [Fixed logical residence](#fixed-logical-residence)
    - [Class pointers](#class-pointers)
    - [Duality of relations](#duality-of-relations)
    - [Module](#module)
- [Loose Ideas](#loose-ideas)
    - [Automatic Containment Ideas](#automatic-containment-ideas)
    - [Esthetic reference & real reference replaces imaginary reference](#esthetic-reference--real-reference-replaces-imaginary-reference)
    - [Other](#other)
- [Commands with Fixed Logical Residence](#commands-with-fixed-logical-residence)
- [Ideas From Commands & Classes Loosely coupled](#ideas-from-commands--classes-loosely-coupled)
    - [Automatic containment of independent commands](#automatic-containment-of-independent-commands)
    - [Expressing a call to a command as a call to multiple objects](#expressing-a-call-to-a-command-as-a-call-to-multiple-objects)
    - [Command definition accessing the objects](#command-definition-accessing-the-objects)
    - [Editing a call](#editing-a-call)
- [Ideas From the project Work Out Parameter Articles](#ideas-from-the-project-work-out-parameter-articles)
- [Out of the original Symbol documentation](#out-of-the-original-symbol-documentation)
    - [Overlapping Hierarchies](#overlapping-hierarchies)
        - [Containment for Divergence, Lines for Convergence](#containment-for-divergence-lines-for-convergence)
        - [Triangles for Arbitrary Groupings](#triangles-for-arbitrary-groupings)
        - [Commands can Overlap](#commands-can-overlap)
        - [Another Thing](#another-thing)
    - [Integrating Structure and Symbol](#integrating-structure-and-symbol)
    - [Brainstorm](#brainstorm)
    - [Contaiment by Containment and Reference](#contaiment-by-containment-and-reference)
    - [Other](#other-1)
    - [Object Basics](#object-basics)
        - [Referencing a Parent](#referencing-a-parent)
- [More Ideas](#more-ideas)

## Introduction

The concept of automatic containment is about translating a referential structure to a containment structure.

That might make relations between object more easy to overview.

To be able to work out the idea, some concepts need to be ignored first and reconsidered later (concepts such as module and physical storage location).

I am working out the idea here as I go along. The explanations may need to be redone in the future.

It might be mentioned, that the method of automatic containment described here, applies to unary references, and not to objects referring to each other in a dual relation. The notation for dual relations, and the notation of automatic containment described here, just *do not match* yet, unfortunately. In the future it might be further worked out how to best turn them into a single notation.

## A slice of referential structure

One thing that might make it doable, to convert a referential structure to a containment structure, is that you might never display the complete referential structure: you might always display a slice of the referential structure. The contents of *one* object are shown and it goes but x levels deep. That way you always display a slice of the referential structure: cut off from the top at the parent object and cut off at the bottom x levels deep. The containment structure is worked out only for that slice of referential structure.

## The main solution

The main solution to converting a referential structure to a containment structure is demonstrated with the following example. The following reference structure is considered:

![](images/3.%20Automatic%20Containment.001.png)

The circles are all objects. Object A for instance has two references: one to object B and one to object E. Two objects refer to object D: both object C and object E refer to object D.

In a Circular diagram, the references might look more like this:

![](images/3.%20Automatic%20Containment.002.png)

References are considered things that are contained inside an object, that point to somewhere.

The references are directly converted to a containment structure, by simply displaying one thing inside another thing, instead of one thing referring to another:

![](images/3.%20Automatic%20Containment.003.png)

The diagram above actually displays the same structure as the other diagrams: instead of giving object A references to object B and E, object B and E are simply placed directly inside object A. But there is a problem. There are two parent objects, that have a reference to the same object. In the containment structure this means, that two objects *contain* the same object. The same object is displayed twice in the same diagram. In the diagram you can see, that object D is displayed twice: once contained inside object C and once contained inside object E.

The references have a containment position now, but the *object* didn’t get a fixed position in the containment structure yet.

The main solution to solving the ambiguity of having two symbols represent the same object, is to connect the two symbol that represent the same object with a line:

![](images/3.%20Automatic%20Containment.004.png)

Now both symbols represent the same object.

One symbol is going to be selected to represent the object itself, so that an object gets a fixed containment position, while the other symbols are considered mere references to the object. How a single symbol is selected is explained in the next section.

Regardless of which diagram you find prettier, the containment diagram might display more clearly *what* is part of *what*. For instance: you can see that object B *indirectly* contains object D. That was not that apparent in the referential diagram. But now you have a problem: a single object is not represented by a single symbol anymore.

## The closest mutual parent

Multiple symbols in a diagram can represent the same object. In that aspect, a containment diagram might not explicitly express a single place where the object really is. It might not display where the *object* is, just where the object *references* are. Only one of the symbols should be considered the object itself, and the other symbols mere references.

To determine the containment position of the actual object, you might ask yourself: what might the *real* containment level of the object be? You might go upward in the containment hierarchy, until you find the level at which all the references are contained inside a single symbol. That is the actual containment level of the object:

![](images/3.%20Automatic%20Containment.005.png)

The blue circle is the closest containment level in which both object references are present. It is the larger whole which the object is part of.

The container of the object is also called the *closest mutual parent* of the object references.

The mutual parent connects all the references together. The mutual parent is the containment position of the object itself.

The diagram above might not even display the symbol, that represents the object itself. We have yet to put a new circle in the diagram directly inside the closest mutual parent of the references:

![](images/3.%20Automatic%20Containment.006.png)

It is an *imaginary* reference, directly placed inside the closest mutual parent. It is called imaginary, because its container doesn’t really refer to the object directly.

The other references might connect to the symbol that represents the object itself:

![](images/3.%20Automatic%20Containment.007.png)

This solves the problem, that multiple things contain the same object. This only happens when the same object is referenced from multiple places.

This is a simple example of expressing the location of an object. The situation can get more complex, though.

## Branched out reference lines

Here is a more complex example, in which the lines might branch out into a tree structure. This happens when an object is present in several different branches of the containment structure:

![](images/3.%20Automatic%20Containment.008.png)

Imaginary references might be created at every mutual parent in the structure, that contains multiple references:

![](images/3.%20Automatic%20Containment.009.png)

You might say, that all the references to object D could also have been connected to just a single circle on the highest level of containment, instead of creating *two* extra circles. But by creating an extra imaginary reference, nodes are displayed at all points at which there is a larger whole, that contains multiple references to the same object.

To find the symbol, that represents the actual object, you might follow the reference lines upward in the hierarchy. The reference to D on the highest level represents the object itself:

![](images/3.%20Automatic%20Containment.010.png)

The other symbols of D are mere *references* to the object.

The containment structure splits up the object structure into branches, and the reference lines branch things back to the same object, and point out the residence of the actual object.

From the target symbol’s point of view, you can easily see in what different places the object is used, because it just directs to them in a tree structure.

## Recap

When you display a diagram in pure referential style, a single symbol represents a single object. There are no multiple symbols, representing the same object.

When you display a reference structure as containment, and there are things, that refer to the same object, then all of a sudden the same object is displayed multiple times and in totally different places.

The diagram might not explicitly display individual objects anymore. 

The referential structure is treated directly as a containment structure, but then multiple symbols can represent the same object.

This is solved by connecting the symbols that represent the same object together with lines, to indicate that they are the same object.

But to have a single symbol, that represents the object itself, all symbols of the same object all need to point back to a single symbol. That single symbol represents the object itself. The other symbols are mere references to the object.

But where is this object placed? You might go upward in the containment hierarchy, until you find the level at which all the references are contained inside a single symbol. That is the actual containment level of the object.

![](images/3.%20Automatic%20Containment.011.png)

The symbol representing the actual object is placed in the closest mutual parent of all the references.

The references are connected by tying a deeper reference to a higher reference.

![](images/3.%20Automatic%20Containment.010.png)

The containment structure splits up the object structure into branches, and the reference lines branch things back to the same object.

Inside each symbol, that indirectly contains multiple references to the same object, an new node is created.

That way, a complex referential structure is displayed as a more tangible containment structure, even though it is not pure containment. In that display, multiple symbols represent the same object, but this is elegantly solved, by choosing a clear spot at which to put a single symbol, that represents the object itself, while other symbols are considered mere references to the object. The single symbol is also placed in a spot that is the bigger whole in which multiple object references are contained.

## Zooming in, zooming out and making changes

You can move through the diagram by zooming in on a sub object and zooming out to the parent. But a single object can have multiple parents. So the diagram viewer should remember the path you took before you got to the current object, so that it knows what parent to zoom out to again.

Whenever you change something in the object structure, the containment structure of references is easy to draw out, because it is the same as the referential structure. But the reference lines and imaginary references, that make the object references lead back to a single symbol, just need to be wiped out and recalculated. Which of the symbols is a mutual parent can totally change. The reference lines and imaginary references are recalculated as soon as you move upward in the hierarchy, displaying the contents of the parent of the object you were displaying. The same goes for moving downward in the hierarchy. In all those cases, the reference lines and imaginary references need to be recalculated. Fortunately it is always a limited set of symbols for which you are recalculating this: you are only displaying the contents of a single object, and you display symbols but x levels deep.

< You can establish a reference to an object, by connecting a reference to an imaginary reference to an object. But in reality the reference shall point to the real location of the object. In the diagram, however, the reference points to an imaginary reference. >

## Analogy to the real world

The way diagrams are displayed, has an analogy to the real world.

Let’s say your TV contains an electronic part. But what if you have a stereo set that also contains this electronic part. When you only focus on the TV, it is the only object that contains this electronic part that you need to be concerned with. When you look at the whole room, you see that this type of electronic part is part of two appliances in the room. Imaginarily, the whole room is the container of this kind of electronic part. The whole room is the indirect mutual parent of both electronic parts of this type, because the room contains two appliances, that directly contain this electronic part. This gives the room an imaginary reference to this type of electronic part. The room doesn’t really contain the electronic part. The appliances could be carried out of the room, and then the room loses its imaginary reference to the electronic part, but the appliances still contain it.

What if you have more appliances in your house, in multiple rooms, that also contain that electronic part. In that case, looking at it from the perspective of your whole house, the whole house has an imaginary reference to the electronic part. This type of electronic part belongs to your whole house in that case. That way you could also look at the whole neighborhood. Perhaps multiple houses contain appliances with the same electronic part in it. In that case this type of electronic part is part of the whole neighborhood. But if you’re just looking at the room you are in, you are not considering the whole neighborhood. You are only bothered with your room. If you focus on just your TV, you just don’t pay attention to the fact that your TV is part of a whole house: the electronic part is just part of your TV.

The containment level of this type of electronic part, just depends on the perspective from which you look at it.

And this is what also happens in the diagrams. That way, something can get a different containment level depending on the perspective from which you look at it. From within that perspective, something might get a *unique* containment level.

## Ignored concepts

To easily understand the idea of automatic containment, a few concepts were ignored. In the sections that follow I might consider the concepts that earlier were ingored.

Here is a sum-up of all the concepts that might be considered here.

- Physical location
- Caching
- Pointers
- Residence on a site
- Central registration lists
- Classes, interfaces and methods
- Fixed logical residence
- Class pointers
- Duality of relations
- Module

### Physical location

The most important concept to explain first, is the physical location of an object.

It turns out I was lying a bit, when I suggested that the target object totally depends on the specific perspective displayed by the diagram. That’s not entirely true. The true target object is stored on a physical storage device.

But if all object references might directly point to the physical storage location of the object, things might turn into an unoverviewable bunch of wiring.

The imaginary references, that were automatically put in between are the answer to making things overviewable when the target object is far away. The imaginary references are intermediate target objects. Those turn reference lines into an overviewable tree structure, the root of which is the target object on physical storage.

Even though on a logical level the same object can be logically resident in different parts of a system, the physical location is fixed.

The logical containment levels are important. They make sure, that you see which objects indirectly contain multiple references to the same object. It also always gives you an intermediate target object to look at, when the real target object is way out of sight: in a diagram, displaying a limited part of the system, there is always one symbol that represents the object itself.

Because the physical location of an object might usually be out of sight, the last intermediate target object, that *is* in sight, usually points out of the diagram: a reference line, the end of which you don’t see on screen. You could even display the name of the physical location in the reference line going out of the screen. If you go one containment level up, you might find another intermediate reference there.

The storage location gives the object its ID.

### Caching

Having a single way to clearly express something’s physical location as well as something’s logical location, makes you able to clearly display multiple cache layers inside a diagram, without obscuring the logical picture. An object is permanently stored on the target storage of a caching scheme. The target object may be on a *cached storage*, which uses other storages to eventually store things on the *target storage*. This caching is hidden inside the caching system and is only displayed close to the physical storage (the physical storage is also represented in the diagram). In *logical* locations of an object stored, you don’t see all this caching and physical storage at all, you just see the logic of the objects, not the storage.

### Pointers

The lines connecting to imaginary references are considered imaginary reference lines. In this section I might introduce *real* reference lines, that are set by a programmer, instead of being automatically set by the system.

In the explanations above the lines simply indicate which symbols represent the same object. Imaginary references in mutual parents are used to indicate which symbols contained by the mutual parent represent the same object. The lines connected to imaginary references are also imaginary: they are not really part of the system. The symbols connected to it, don’t really point to it: in reality they point directly to the target object.

There are also references lines that are *real*, instead of imaginary. *Real* reference lines are connected to *real* object references. These reference lines are not automatically set by the system. They are set by a programmer.

An object reference, that is connected to another object reference with a *real* reference line is a reference to a reference, a pointer to a pointer, not a pointer to an object. Whenever the target reference starts pointing to another object, a pointers to the reference starts pointing to the other object too.

You can distinguish references to references from imaginary references, because they are displayed differently. Imaginary references look fainter. Real references look bright.

Imaginary reference lines never connect to real references, and real reference lines never connect to imaginary references.

It is important to mention, that when a mutual parent already contains a real reference, this real reference never replaces the imaginary references that are to be put inside mutual parents. Every mutual parent get an imaginary reference to the object it contains, whether there’s a real reference to the object already present there or not.

Also important to stipulate is that lines connected to imaginary references are not real indirections. They are put in between, but everything connected to it, really points directly to the target object.

Imaginary references and imaginary reference lines can change as soon as you change the structure of the program. But real reference lines and real references do not change volatilily, they are actively set by a programmer, and represent pointers to pointers.

### Residence on a site

In the first story I gave about automatic containment I said, that the target object is represented by an imaginary reference put inside the mutual parent of multiple references to the same object.

Later I said that the imaginary reference is really not the target object: the target object is the physical storage of the object.

The fact that an object *can* have a fixed spot, also makes it possible for an object to reside on a site. When I still suggested that an object didn’t have a fixed location, it was an enigma how I was going to let an object live inside a site, while an object doesn’t have a fixed location at all. Now an object might have a fixed location, it is easy to place it inside a site. A site could host *pointers* to the physical locations, instead of exposing the target object itself, because you might probably not want other sites to point directly to the place an object is stored or directly see the infrastructure of the site: what disks and which computers. The infrastructure of the site can be hidden by access controlling it. A site might only be exposing things that others have access to.

If an object is stored on one site, it may logically be resident in multiple locations, but its physical position is still on that site.

### Central registration lists

One problem I did not want to consider at first, was that a module might contain a registration list of all objects of a certain class. Because that might have given an object an exact location: that might have given an object a fixed place, and all lines might have pointed directly to the central list, which might not make the diagram overviewable.

However, in the method found, I do not think central registration lists might be a problem anymore. A central registration list might have a place in the diagram, but not all lines are not directly pointing to it, and when it is outside the screen, you only see the closest logical location of the object. The display of the diagram is simply dependant on the level of detail now and lines are usually not pointing directly to a fixed location at all: just to an imaginary logical location. Having central registration lists inside a diagram is really not a problem anymore.

### Classes, interfaces and methods

In the stories above only objects were considered. Classes, interfaces and methods were ignored. To cut to the chase: it simply works the same for the display of classes, interfaces and methods.

In Circular the class of an object is actually another object. In Circular, another object simply serves as the prototype for another object, with default values and everything.

When you first display containment, without lines leading back to a single object and everything, you do not see mutuality of classes at all. Just like you don’t see mutuality of objects. To express the mutuality of classes, lines and imaginary references are positioned the same way, as they are for lines leading back to the mutual object, but now it is lines leading back to the mutual class. Class lines are dashed instead of solidly drawn.

In Circular an interface is also simply an object. An object can serve as the prototype for the interface of another object. When you first display containment, without lines leading back to a single object and everything, you do not see mutuality of interfaces at all. To express the mutuality of interfaces, lines and imaginary references are positioned the same way, as they are for lines leading back to a mutual object, but now it is lines leading back to the mutual interface (= object serving as a prototype for the interface). Interface lines are dotted, instead of solid.

For methods it works a bit differently. Methods are not objects. Methods are not displayed as circles. Their default display is a square. So they have different symbols compared to objects. But the way lines lead back to a mutual method, simply works the same as for objects. There is more to the display of methods, but that is not covered here. The main point is: the technique for displaying mutuality of class, interface, and object works for mutuality of methods too.

Imaginary object references are always circles, and not triangles or pentagons or anything, because those alternate shapes might give the object a special function, that can only be chosen by a programmer. Imaginary references are created by the system, which might not give the object symbol any other function than to simply be an imaginary reference, so no alternate shapes are required for its notation. For the same reason imaginary method references are always squares and not diamonds or anything else, because this alternate shape might give the method a special function, that can only be chosen by a programmer. Imaginary references are created by the system, which might not give the method symbol any other function than to simply be an imaginary reference to a method.

### Fixed logical residence

A target object resides on a storage device. That is the residence of the object. However: classes and methods represent structure of a program. The definition of the structure of a program often not only needs a physical target location. The definition of structure of a program often needs to be part of a module: not just as an intermediate target, that then redirects to the storage device, but as the only target. A single logical location can take over the position of the physical target and might become *the* target. That way you can give something a fixed logical location.

This is important for objects that serve as prototypes for other objects (also known as classes) and it is also important for methods to be able to have a fixed logical location. Normal objects can sort of float around and change residence. They don’t need to be part of one module, they just float around.

Classes and methods however, you might want to make part of a single logical unit. That’s why you need to be able to replace the physical target with a logical one, and let the logical target shadow the physical target, and be the only one referencing the physical target.

Interfaces are also structure definitions that you might want to give a fixed logical location.

You can also give normal objects a fixed location, so that they become part of a module, and have a fixed logical target location, that shadows the physical storage location.

### Class pointers

The pointers concept was ignored at first, but now it is clear how to create explicit pointers, instead of just imaginary pointers, you can also imagine how you can keep the class of a sub-object variable, for objects that can manage other objects of a variable class. The sub-objects managed all have class pointers to a mutual symbol, symbolically representing the class. That mutual symbol representing the class can be set to point to any arbitrary other class. Whichever class is assigned to the class symbol, becomes the class of the objects managed.

Such genericity of class can be access controlled: you can control whether the class of an object reference can be changed at all. By default others shouldn’t be changing the class of object references. You made the program and expect the class not to change. Only you can reprogram it. For others the class is fixed. In that sense, using and programming something is only dependent on access control in this software system. There is not really a difference between users and programmers in this system. There is only a difference between what different users can change.

### Duality of relations

The concept of duality of relations was ignored at first. Just like the concept of physical location, this concept might change the nature of the diagrams a little bit.

In the diagrams explained before, only mono-directional relations were considered. An object that referred to another object, did not refer back to the first object.

In relational programming it is common, that if one thing references another thing, the other thing has a reference back to it. But if you display that in the diagram, then one thing contains another thing, the other thing contains the first thing again, which again contains the other thing; you just see too much recursion, and it is confusing.

Because it is unacceptable *not* to see this duality in a diagram, the following rules are followed.

Consider first of all, that if something contains another thing, the reference back to the parent is just as apparent as the parent’s reference to a child: just look a container of the child. So the duality of that relation was already displayed in the diagram.

The rule to follow is: if one direction of the relation is already displayed as going downward in the containment structure, don’t display the other direction of the relation as going downward again, because then you might be displaying the same relation twice.

So when something is already displayed as something’s parent, you don’t display the reference back to the parent as a child anymore. The display of a containment is already considered the display of a bi-directional relation.

Just accept the fact, that the display of a parent, is already the display of the reference back.

- This may stand a little bit in the way of creating a pointer to a reference: if you create a pointer to a parent, are you creating a pointer to the child's pointer to the parent, or are you creating a pointer to the grandparent pointing to the parent? A good solution for this can be found later.

A funny effect of that is, that when you zoom in on a child, the object formerly displayed as the parent, all of a sudden appears as a child again. Something else funny, is that if you zoom in on that child, the child becomes the parent again and you might be seeing the same thing as when you were two zoom levels up! Now, that’s automatic containment!

When one direction of a relation is displayed, the other direction is not displayed anymore. That is the rule.

One flaw in this is, that you don’t easily see the relation type. An n => n relation is displayed as a 1 => n relation. A n => 1 relation is displayed as a 1 => 1 relation. A solution may need to be found for that. When and how the full relation types between classes can be expressed might be covered in another article, discussing the explicit expression of relations in a diagram.

In this section it is important to understand that a backward relation between *objects* is always expressed when automatic containment is applied.

### Module

A module is there to group something into a large whole. Modules and programs are modules. A site is also a module. Anything directly inside the module can be directly referenced from anywhere within the module. That is the basic principle. However, you might not make everything directly inside the module accessible globally. If members of a module are just publicly accessible, they are not globally accessible, they are just accessible as members of an object, and not accessible from anywhere within the module. It is also not entirely true, that everything inside the module can access the global members. You can only access global member, from members, whose fixed logical residence is inside the module. So global things can only be directly accessed from definitions, whose fixed logical residence is inside the module. Things *referenced* inside the module, whose definition are elsewhere, can not access the global members.

A module is an object. However, it is not represented by a circle, but by a pentagon shape.

You could directly connect lines to the global things, but that might make the diagram unoverviewable. But we already had a solution for that: you make imaginary references.

When the module itself is not in sight, but you are zoomed in on *part* of the module, you are going to see an imaginary reference to the module. Imaginary references to module, just like imaginary object references, are positioned in all the mutual parents from which global things are accessed. But unlike imaginary references to objects, nothing has to point to a module, in order for an imaginary reference to the module be displayed. An imaginary reference to the module is always displayed at the highest visible level of containment. You can point to the global things you see inside this imaginary reference. The imaginary references to module are displayed as pentagons, that is how you recognize the global things you can access.

You can reference a module like referencing an object. In that case it behaves like a normal object reference.

You can also reference a module directly from within another module. In that case, one module has a reference to another: one module has a reference to another module. Everything of the referenced module is now globally accessible from anywhere within the other module.

You don’t need to let modules refer to each other, to actually let one module use something from another module: one module can always access anything inside another module, whether it has a reference to it or not. A reference however, makes global things from one module, globally accessible inside another module.

The reason why module was at first ingored when working out automatic containment, is that module gave things a fixed spot. Everything might have been pointing to a fixed spot, which might make the diagrams unoverviewable. That is the same reason why physical location, residence on a site and central registration lists were ignored.

But this is all solved with imaginary references: *the* trick to give something referenced multiple times a single logical position inside the containment structure.


Loose Ideas
-----

*The texts below are loose ideas and texts out of older documentation, that still need to be turned into good documentation and integrated with the rest of the concepts.*

Automatic Containment,  
2009-08-18

‘Analogy to the real world’ unnecessary. It was immediately clear to my brother that it was an ok notation. It falls under the category of ‘trying to __defend__ myself too much’.

JJ

-----

![](images/3.%20Automatic%20Containment.012.png)

Watch out. The diagrams above suggest that lines don’t always go outwards. But the diagrams are not written well enough. The real imaginary residence of an object or a method definition is not inside the modules where their fixed logical residence is. They are one level higher, because mutual usage extends across the module. If that’s right, then the imaginary target object is different from the real target object ... That means that first lines go outward to the imaginary residence, then back inward to the fixed logical residence, and from thereon tot the physical residence. That is weird, however. The lines going inward could from some views be going outward to an imaginary residence. I still need to work this out. Perhaps you just need to see everything as going outward to a certain extent, but the access marks lead to the fixed logical residence.  
It’s best not to make a fixed logical residence any more specific than on a site or inside a module. It might get the appropriate imaginary residences anyway.

-----

< The object symbols and the lines connecting them together together represent the same object. You could draw it out as a solid, making the lines thicker, and you have a single structure that represents the same object. For class lines it’s different: all the symbols in that structure are separate objects, but they are all objects of the same class. The structure represents the same class of object. But one symbol is considered the heart of the structure: the target symbol. >

-----

< I guess you always have a physical target, a logical target and an imaginary target. >

-----

Explicitly connected though parent:

![](images/3.%20Automatic%20Containment.013.png)

The objects of the class are visible in 2 spots, but not connected though an imaginary references inside the mutual parent, because the connection between the logical class definition and the imaginary class definition already explicitly expressed that it is about the same objects references. However, they aren’t even the same object references, they are just the same object references inside a class.  
Formally there are object and methods symbols in the diagram that represent the same method, that should be connected through imaginary references to the method or object inside the mutual parent of the references, but this makes the picture less clear.  
You can see an implicit connection between the symbols through their parents.  
One object may be confused with the other, if implicitly connected like that. You can only recognize them by name, or can possibly by their contents.  
But this implicit connection makes the diagram so much clearer. It makes it so much clearer to leave out any connection already implicitly expressed by a connection between their parents.

-----

< I might make implicit connection a part of automatic containment, because automatic containment defines the imaginary references, that we’re going to leave out by implicit connection through connection between parents. >

-----

When the whole screen just shows you the contents of a symbol, you’re displaying a *related object*, not just an object, but a related object, that has a relation to its parent. That’s how you know what parent to display, when you zoom out. An object can have multiple parents, but a *related object* only has one parent.

-----

2008-08-10

Imaginary references break the restrictions set for command symbols. See the article group *Command, Basic*.

JJ

-----

Are imaginary class symbols drawn with a dashed line? I bet they are. But then the class structure is not emphasized with classes? I’m not sure yet.

-----

Integrate automatic containment into the consecution of small coding principles articles somehow.

-----

Automatic Containment,  
2008-08-04

Automatic Containment geeft in wezen overlap in gebruik van objecten aan.  
Misschien is het mogelijk overlap ook duidelijk als OVERLAP weer te geven.  
Dat zou wel in de trant zijn van most direct depiction of an object 

oriented system zijn:  
overlap noteren als overlap. Het is de vraag of het diagram er dan niet te ingewikkeld uit komt te zien. Maar de regel van Automatic Containment is al, dat je altijd maar een stukje van de referentiele structuur ziet, dus dat zou het weergeven van overlap misschien kunnen vergemakkelijken.

Je krijgt echter wel moeilijkheden, doordat symbolen van object  straks staan voor het object en zijn context. Als je overlap aangeeft en een object in de overlap plaatst, staat 1 symbool niet meer voor een object in een bepaalde context.

JJ

-----

Automatic Containment,  
2008-08-07

Je hebt het voordeel, dat het bij relations, en references in een context, dat er toch een beperking is in onderscheid maken: 1 referentie heeft 1 context. Je moet mutuality of reference aangeven = mutuality of pointer en daarna mutuality of object. Misschien kan je daar toch iets moois van maken.

JJ

-----

Automatic Containment,

If you don't like reuse of real references for imaginary references, you could like let a real reference be possessed by an imaginary reference.

JJ

-----

Automatic Containment for reads and writes,  
2008-07-03

Might automatic containment apply to reads and writes?  
The two counterparts do not represent the same object. They are different objects. How do you draw that out in a diagram.  
I won’t be concerned with it now. Automatic Execution Order is my current subject. Not the notation of it.

JJ

-----

Automatic Containment,

Er zou automatic containment moeten plaatsvinden van de pointer zelf, in plaats van alleen automatic containment van het object. Maar dat terzijde.

JJ

-----

Automatic containment,  
2008-07-30

An object cannot see the outside. It cannot look outside its frames. A parent object can, however, give a sub-object a reference to another object on the outside, but this makes the object reference available *inside* the sub-object.

JJ

-----

Automatic Containment,  
2008-08-10

You might mention, that the other articles may not conform exactly to the notation of automatic containment, but the automatic containment notation is the only one used when programming.

The other articles may have simplified diagrams, that demonstrate a point more clearly, but in practice the notation of automatic containment is the only one used.

JJ

-----

Automatic Containment,  
2008-09-02

Actually, the system could do without automatic containment, manually defining the containment. So you can completely introduce the language, without considering automatic containment, and then, as a surprise, introduce the automatic determination of containment.

JJ

-----

Automatic Containment,  
2008-08-17

If it weren't for object references always being object references, the principle of always being able to pass an object on to another object, might be lost.  
That why everything is always pointers to object, instead of
being directly contained by something.  
If you do want something to be really RESIDENT somewhere,
you just fix its residence.  

Isn't that just making it the default.  
It's still implemented as a pointer,  
because it isn't REALLY resident there either.  
It is only LOGICALLY resident there.  
Physically it could be on any disk in the world.  
It could even physically be moved to another disk,  
while it's still LOGICALLY situated in the same spot.

JJ

-----

Automatic Containment,  
2008-08-17

The fact that attributes are bound to an object, is required, in order to give a parent object full control over the value of an attribute, without volatile influences from the outside.  
Could that have been accomplished in with another method, such as I use to make commands protectors of a class's data?

JJ

-----

Circular,  
2008-08-17

Two layers.  
So fundamentally everything is built up of things two layers deep: objects with sub-symbols.

JJ

-----

Encapsulation is not the right word for the containment relationships I have. Encapsulation is used to denote the black box effect.

### Automatic Containment Ideas

Automatic Containment,  
2008-08

Sub-commands of a command definition are created objects. They have a fixed logical residence inside the command definition, even though their definition is totally elsewhere. 

JJ

-----

AC,  
~ 2008-06-24

At the beginning of the documents AC and Diagram Expression For Classes And Relations, ADMIT that there is a discrepancy between the notation for unary object references, and dual relations between objects.

After that: just let it go for now. It doesn't overthrow the system. It is an unfortunate fact, but there are other things to work on, and it is stressing me out. I give up, for now.

JJ

-----

Problem with references and targets:

Objects usually physically refer directly to their target. In a rare case a pointer redirection is in between.But most redirections are only imaginary redirections, that are show in the diagram.

In Coding Principles it is important to understand the physical part of it, and the imaginary part is ignored.

In Coding Principles in a Diagram the imaginary references are important. Even though they are imaginary redirections, you visually do need to follow them to get to the reference target. For the structured view on the system, they are very important, even though they do not persist to physically storage.

But imaginary redirections aren't even discussed in The Diagram expression articles. They were discussed in automatic containment as a flat & structured interchange concept. I think I'll leave it there, and just direct the reader to it. I'm not going to try and embed it into Diagram expression (yet, if ever).

-----

Circular,

Eigenlijk moet je wel blij zijn met het feit, dat je de notatie langzamerhand helder krijgt, zij het met moeite.  
Er stonden nog issues open aangaande automatic containment.  
implicit connection, esthetic reference en het weergeven van relaties.  
Dus als je dat nu netjes in orde krijgt, met extra moeite in het documenteren van de Classes en Relations Coding Concepts, dan is dat heel fijn.

JJ

-----

Automatic Containment,  
2008-06-19

I just wonder what might be left of the original display of imaginary references, when most references become part of a dual relation, and won’t connect to the same imaginary reference anymore.

JJ

-----

Automatic Containment,  
2008-06-18

A ‘display once’ policy?

JJ

-----

Diagram complexity limitation,

Like implicit reference through parent, there is also implicit contents through reference target. It is about not doubly displaying what's already displayed.

JJ

-----

See: Automatic Containment \ Duality of relations  
The duality of a parent-child containment display:  
One flaw in this is, that you might not easily see the relation type. An n => n relation is displayed as a 1 => n relation. A n => 1 relation is displayed as a 1 => 1 relation. A solution may need to be found for that.
\> I’ve already found a solution for that. See the article *Relations Between Objects in a Diagram*, in the section *Relation counterpart out of sight*.

-----

When the counterpart of the relation is out of sight, a line should point out of the diagram.

-----

Diagram Expression,

The diagram view on an object, should be showing just the object's contents x levels deep. When you focus on an object, the diagram might be showing everything x levels deeper, and y levels higher. That way, you have one object focussed on, of which you can see the contents as well as the surroundings, so you can see its direct context.

JJ

-----

About incorporating automatic containment into the Diagram Expression documentation: I think I should introduce automatic containment only later in the documentation (of Diagram Expression). I should first ignore it, and after explaining enough topics I might have created enough frame of reference, to be able to introduce it

-----

Classes & Relations & Automatic Containment,

If you draw out the two ends of the relations as unary relations, and then do a line merge, the only option seems to be to get this weird line, that goes outside the highest object and then bends around to go back inward again. < but draw that out again, and look at the scribbles on paper. >

-----

I stated that for two counterparts of a dual relation, two references are uniquely connected to each other. What if you give another object a pointer to an object reference inside another object? Then it won't be a pointer to the object reference. The pointer to the object reference is transformed to a pointer to the object itself, and then automatic containment is applied to draw out the diagram; to correct the diagram so to say, and objects' references to each other in a dual relation are tied together uniquely again.

JJ 2008-06-04

-----

Words usable in the explanations about mutual parent:  
*encircle* / *enclose* / *surround*  multiple references to the same object 

### Esthetic reference & real reference replaces imaginary reference

Esthetic reference: 

![](images/3.%20Automatic%20Containment.014.png)

And automatically the lower references might point to the esthetic reference.  
This is actually not true. An imaginary reference is created, that defines mutuality of ...

When you turn a reference structure into a containment structure, you might take away the effect of splitting up methods into sub-methods, that refer to each other.  
But if you want to reestablish that, you might put an extra reference to the method on a higher level, and that might actually become the target definition, so you are back in business regarding the splitting up methods into sub-methods.

You should stereotype an esthetic reference as esthetic. You might draw it brighter than the other symbols. It might be like it is lifted up: it’s a real reference that’s only there for an imaginary reason. I find the imaginary reason so important, that I might make it real. It makes it somehow even more real than a real reference that’s there only for a logical reason.

Imaginary reference not created if single real reference already there. If multiple real references are there, you might create an imaginary one anyway. Because the line to the real reference is imaginary, you can still tell it's an imaginary intermediate target.

Reusing a real reference where you’d otherwise put an imaginary one:  
Now, one problem with automatic containment now, is that no real references point to each other. Real reference only converge into imaginary references.  
So when you already have a real reference on a level that contains multiple of the same objects, an imaginary reference is added anyway to which the deeper reference point, and to which the reference on the same level also points.  
But it usually just looks more clear when the real reference replaces the otherwise created imaginary reference.  
It also turns things more into a tree structure, because a reference to something on the same level doesn’t really look like a tree branch as much.  
And esthetic reference won’t work if a real reference might not replace the imaginary reference.  
But there was a reason why I created an imaginary reference anyway. For instance: when two object references on the same level, refer to the same object, they need to converge to an imaginary reference, or you won’t know what is the target object.  
Do the arguments against reusing a real reference weigh up to the clarity of reusing an real reference?  
I’d might look that up in the article Automatic Containment.

### Other

Imaginary reference in the mutual parent:

Ik zeg altijd: in een mutual parent, en dat dat betekent, dat het in een container, waarin meerdere referenties naar hetzelfde staan moet zijn. Maar dan zou een mutual parent altijd elke container zijn van het niveau van de diepste referentie tot het niveau van de hoogste referentie.

Je moet het echter zo zien:

Altijd een imaginary reference op een container die meer referenties toevoegt.

-----

De uitleg houdt zicht niet genoeg aan Automatic Containment.  
Automatic containment begint pas te spelen bij meer dan 2 niveaus diep, ofzo.  
Misschien moet je gewoon in het oog houden, dat alle referenties in principe als containment eruit zien. Lijnen worden alleen gebruikt als oplossing bij mutuality van een systeemeigenschap van symbolen.  
Ik weet alleen niet zeker of dat voor aanduiding van de class wel zo is. Naar de class moet je volgens mij echt wijzen?  
Nee: objecten met dezelfde class worden verbonden. Het geheel heeft een target class op het laagste niveau waar alle objecten van de class in zitten.  
Als de class maar op 1 plek wordt gebruikt, dan heeft dat symbol een dubbele rand: een ononderbroken lijn en een streepjeslijn.  
\> Kijk naar ideas

-----

This is also, because the stuff inside a pointer is always part of the target. The pointer itself is usable independently from the target, but the stuff displayed inside the pointer is really part of the target, not part of the pointer.

Implicitly connected through parent / implicitly connected through referrer.  
“but the sub-symbols do need to be named in order to unambiguously take over targets specified inside a reference to the symbol.”

Implicit connection through parent kan alleen, als daarbij de namen van de objecten niet veranderen in beide containers.

Connect to sub objects inside the closest imaginary reference.

Each object’s contents should officially also be class-tied to their class. But if there is an implicit connection through parent it might not. If a reference target already class tied the sub-objects, then you might not repeat it in the referrer.

-----

About incorporating automatic containment into the Diagram Expression documentation:

I think I should introduce automatic containment only later in the documentation (of Diagram Expression). I should first ignore it, and after explaining enough topics I might have created enough frame of reference, to be able to introduce it

## Commands with Fixed Logical Residence

(2008-05-18)  
Another way to make a command part of a bigger whole, is to give a command a fixed logical residence. A command already has a fixed *physical* residence, being the place where the command is stored on disk permanently. A command is stored somewhere, just like an object. But a command can also be given a fixed *logical* residence. This fixed logical residence shadows the fixed physical residence and gives a command a fixed logical position. The logical residence is the target of all references to the command. Only the fixed logical residence has access to the physical residence of the command.

It is actually advised to give a command a fixed logical residence. Preferably, you make the command logically part of a module, because modules might bundle together classes and commands to a single logical unit of functionality. Don’t make the command part of a class. This binds a command too much to a class. Give a command the freedom to become part of multiple classes, rather than tying it up to a single class. A class’s granting a command access to its private contents already establishes a tighter bond, and the command might be visible as part of the class anyway, even when the class is not the fixed logical residence of the command. And even when you do give the command a fixed logical residence inside a class, the whole rest of the system is going to ignore that: a command call might still be a call upon multiple objects. Only the definition of the command might then be bound to the class.

A module can get overloaded command names, when all commands are logically tied to a module, but this was already the case in languages such as C++. In C++ all the commands of all classes were already reachable globally. In Circular, commands can even be overloaded having the same signatures, because in the diagram they are different symbols, and can be reached separately regardless of their name or signature.

## Ideas From Commands & Classes Loosely coupled

< 2008-09-22. These sections used to be part of Commands & Classes Loosely Coupled, but are moved to Automatic Containment as a cross out text. Some of the approaches in this section are old. Class commands are no longer imaginary. The questions, that remain at the end of the first section should be solved by automatic containment of relations. The display of a bidirectional relation between a command and an object is not like this anymore. If the explanations might not have a place in Automatic Containment anymore, then they can be deleted, because these texts are not required anywhere else. >

### Automatic containment of independent commands

Commands can be called in arbitrary places, just like objects can be referenced in arbitrary places. In the article about automatic containment, for objects it is extensively discussed, how that makes objects logically part of multiple wholes. However, a single logical residence of the object was appointed, that is the real residence of the object itself, while all the other locations, were mere *references* to the object. Also: from the perspective from which you looked at the object structure, a single logical location *within view* was appointed to represent the object itself, even though the real location of the object was out of sight.

It works the same for commands. A command has a fixed physical location, where the command is physically stored on disk. This physical location is usually shadowed by a fixed logical location, which is the logical target residence of the command. The fixed logical location usually resides directly inside a module. Any pointer to the command directly or indirectly points to the logical target location of the command. However, when the target location of a command is out of sight, a single location is appointed to be the intermediate, imaginary target of the command references.

A reference to a command is either a command invocation, or an inactive pointer to the command. For now only command invocations are considered, also called *command calls*.

In this section, about automatic containment of commands, I might first look at commands as totally independent entities, not tied to a class at all. I might actually explain here how a more structured view on a command call is translated to a flat view on it, because the flat view is how things might be physically stored. In later sections, I might show, how a flat view might translate to a structured view, and explain how a call upon a global command turns into a call upon multiple objects.

A call to a command contains parameters, to which objects need to be assigned. When an object is assigned to a parameter, the parameter is tied to the closest imaginary reference to the object. The command call might simply contain object references pointing outward to imaginary object references.

The command call symbol itself, so not the command parameters, but the command call itself, might point to the closest imaginary reference to the command definition. The command call symbol might be connected to the closest imaginary reference with a class line (a dashed line), because the command symbols might represent the same class of command, not the same instance of the command (a call itself is an instance of a command, but the commands tied together represent the same definition, not the same call).

Now I might explain, how you create a command call in the programming environment. A command *call* can be created inside another command. First you create a command call, with no particular command assigned to it yet.

| ![](images/3.%20Automatic%20Containment.015.png) | `=>` | ![](images/3.%20Automatic%20Containment.016.png) |
|--------------------------------------------------|------|--------------------------------------------------|

Next you tie the command call to a particular command. This command resides usually inside an object. You tie the call to the command inside an object.

![](images/3.%20Automatic%20Containment.017.png)

< 2008-09-22 Note, that object ‘methods’ are not imaginary anymore, but *real* references. >

Command 1 now calls command 2 of the object in the diagram. After you’ve done this, the diagram transforms. You, the programmer, tied the call to a command inside an object. The system under the surface ties the command call to the actual command definition, which could be far out of sight.

![](images/3.%20Automatic%20Containment.018.png)

After that, the command call is imaginarily tied to the command definition through imaginary references, that eventually lead to the command definition.

![](images/3.%20Automatic%20Containment.019.png)

The command call is tied to the imaginary reference to the command, but the imaginary command definition inside the object is also tied to the imaginary reference to the command.

The command call contains pointers to the arguments, which means, that the line, tying the call to a command inside an object:

![](images/3.%20Automatic%20Containment.020.png)

is now replaced by an object reference inside the call that points to the object.

![](images/3.%20Automatic%20Containment.021.png)

The imaginary command reference inside the object with the imaginary command in it isn’t even pointed to anymore. It just sits there, just as an imaginary reference, that nothing is tied to, just to see what actions you can perform on the object and what you can make the object do. The object simply says: “Hello, this is what you can do to me.” The object commands do point to the command definition through imaginary references, but nothing is pointed *to* it anymore. After that, the diagram is transformed even more: the parameter might not point to the object symbol you first called upon anymore: it now points to the closest imaginary reference to the object, which may not be the object symbol you used, to establish the call to the object, at all.

![](images/3.%20Automatic%20Containment.022.png)

So really, this:

![](images/3.%20Automatic%20Containment.023.png)

Turns into this:

![](images/3.%20Automatic%20Containment.022.png)

When you get used to reading the diagrams, you might clearly see that you are calling a command of a module, passing an object on a site to it as a parameter. You also see that nearby there is a reference to the same object, that contains an imaginary reference to the command.

But what you don’t see, is that you are calling a command of an object. That’s what still ‘sucks’ in this notation.

It’s like the call to an object’s command is replaced by a call to a global command, passing the object as a parameter. But you want it the other way around: you want a call to a global command to be displayed as a call to an object’s command. The flat and structured interchange principle commands & classes loosely coupled could also have been called *automatic class commands*, because global commands should be transformed to class commands automatically.

So it should be the other way around: the last picture should automatically turn into the first picture, and that should be the automatic coupling of the object and the command call.

### Expressing a call to a command as a call to multiple objects

The diagrams shown before, is the expression of calling a global command, with its object as a parameter. This turned out to be exactly what I *didn’t* want to express. Displaying a command as part of a class is much more preferred over displaying the class as a parameter of a command.

When you might express, that one command is called upon two objects, you might tie the command call to both objects' command definitions.

So it might be a call to both objects' command. Instead of referencing both objects from the command, the command is tied to both command references inside the objects.

In this section I display calling a remote command with two remote objects as parameters. And then I display the same call as calling a remote command on both those objects. It’s basically the same example as above, but now with *two* parameters.

Call to a global command with two parameters:

![](images/3.%20Automatic%20Containment.024.png)

A call upon two objects:

![](images/3.%20Automatic%20Containment.025.png)

Both pictures express the same physical thing. The first picture displays the objects involved in the command as parameters. The second picture displays the call as a call upon both objects.

This is a better way to express a call to a command, that is part of multiple objects. Looking at the second diagram, you can see that it expresses calling upon multiple objects to execute the same command. It seems a good depiction of calling the same command upon multiple objects. However, there is a flaw.

### Command definition accessing the objects

If you are authoring a command, you need to be able to access the object, the command is called upon. When you display the objects as parameters of the command, you can easily use the objects inside the command.

![](images/3.%20Automatic%20Containment.026.png)

But parameters get replaced by imaginary command definitions inside the classes:

![](images/3.%20Automatic%20Containment.027.png)

This is because this gives a more intuitive view on the process of calling a command upon two object. But then, the references to the objects aren’t accessible inside the command definition anymore.

A solution is to show the objects inside the command anyway. 

![](images/3.%20Automatic%20Containment.028.png)

A call upon two objects makes the two object available inside the implementation of the commands. The object symbols of the parameters are sort of like extra imaginary references to the objects.

But the parameters get totally different names, than the objects assigned to them, so you don’t really see which object was assigned to which parameter. This problem is even worse, when both parameters are have the same class. Then you can really not see which object is assigned to which parameter.

The solution is a hybrid display, which connects a parameter to a command inside an object:

![](images/3.%20Automatic%20Containment.029.png)

It is an implicit notation, because a connection between two symbols usually means both symbols represent the same thing. A command and an object can’t represent the same thing, so an object and a command can’t really be directly connected to each other. However, this notation is the clearest way to express it, and really expresses the *interchangeability* between command parameters, and class commands.

Connecting a *parameter* directly to a *command* definition inside an object is *the* implicit notation for interchangeability between command parameters and class commands, because it is useful for editing and it is unambiguous as to which objects are called / which object are the parameters.

In object oriented all members of the class, that the command is part of, were available directly from within the command, without qualifying them with the object name, in other words: without accessing them through an object. But in commands and classes loosely coupled, the object a command is called upon is like accessing an object inside the command anyway. But perhaps this notation might be changed in the future. Or perhaps not: this may be a concession you need to make.

\> 2008-09-06 Actually, if you make the command parameter object a triangle, then the members of the triangle sort of melt together with the command, making the triangle’s members direct available without any further qualification. To prevent the triangle’s members to be directly accessible through the command object, you can just make the triangle Private. But then you have the problem, that the parameter is Private, which might not make it a parameter of the command anymore, but a Private object. The solution is to add a private triangle to the command, that is a reference to the parameter. < See picture on paper 2008-09-06. >

### Editing a call

First you create a call inside another command.

![](images/3.%20Automatic%20Containment.016.png)

Then you need to assign a command definition to it, to determine which command you are going to call, unless you might be defining the command right then and there, right inside the call. You can assign a command definition in two ways:

- You point the call to an imaginary command reference somewhere or
- you point the call to an imaginary command definition inside an object.

The first way is where you point the call to an imaginary command reference somewhere.

![](images/3.%20Automatic%20Containment.030.png)

After that, the diagram is transformed, to tie the command to the closest imaginary reference, instead of the arbitrary reference you might have pointed to.

![](images/3.%20Automatic%20Containment.031.png)

The other way to assign the command definition to a call, is to point the call to an imaginary command definition inside an object.

![](images/3.%20Automatic%20Containment.032.png)

After that, the diagram is transformed to also tie the command call to the closest imaginary reference of the command. Tying the call to a command definition inside an object also assigns one of the parameters of the call, but this is not considered here yet:

![](images/3.%20Automatic%20Containment.031.png)

Now that you’ve assigned which command to call, the parameters, that are not yet filled in, are displayed inside the command call.

![](images/3.%20Automatic%20Containment.033.png)

There are three ways to assign a parameter:

- You tie the command call to a command definition inside an object,
- you tie the parameter to an object or
- you tie the parameter to a command definition inside an object

The first way is where you tie the command call to a command definition inside an object.

![](images/3.%20Automatic%20Containment.034.png)

After you picked out the object, the line you drew is replaced by a connection between the parameter, and the command of the nearest imaginary reference to the object.

![](images/3.%20Automatic%20Containment.035.png)

The second way to assign an object to the command, is by tying a parameter to an object reference somewhere.

![](images/3.%20Automatic%20Containment.036.png)

After that, the parameter is replaced by connecting the parameter to the imaginary command definition inside the nearest imaginary object reference.

![](images/3.%20Automatic%20Containment.035.png)

That’s the end result of the second way to assign a parameter. It is the same end result as the first way to assign a parameter.

The third way to assign an object to the command, is to tie the parameter to a command definition inside an object:

![](images/3.%20Automatic%20Containment.037.png)

Again, the line is replaced, by connecting the parameter to the imaginary command definition inside the nearest imaginary object reference.

![](images/3.%20Automatic%20Containment.035.png)

So the following three notations are replaced by the same line:

![](images/3.%20Automatic%20Containment.038.png)

![](images/3.%20Automatic%20Containment.039.png)

![](images/3.%20Automatic%20Containment.040.png)

They are all replaced by the following:

![](images/3.%20Automatic%20Containment.035.png)

## Ideas From the project Work Out Parameter Articles

Parameters, class redirections & calls,  
2008-09-16

![](images/3.%20Automatic%20Containment.041.png)

I still do not know what to do with the fact, that the class lines to class B of sub-objects of objects of a class A are unary relations.

![](images/3.%20Automatic%20Containment.042.png)

I also do not know why, when a definition inside an object is called by giving the call a class line to the definition, the class line is unary again, and what might make it so, that this might make the object of which the definition was used as a class, the parameter of the call, giving the object an active command reference back to the call.  
I do not know yet what makes this happen and why so many class lines are unary.  
I expected class relations to be more like object relations and more dual, and I expected relations to automatically cause intuitive behavior of calls and stuff.  
I think I might compare it conceptually to how you look at it in current programming languages.

JJ

-----

Automatic Containment,  
2008-09-20

You might solve a lot of things in automatic containment.  
For instance: display of referenced parameters and reference parameters.

I thought automatic containment implied, that when you point inward to something, it is because something has a fixed logical location inside of something. But you really should not worry about that at this stage.

JJ

-----

Automatic Containment,  
2008-09-20

Actually, when you comply to the idea of automatic containment, then you can always see references as being outward. When something has a fixed logical residence, the references marked with an access mark do lead you to the fixed logical location, but all lines can also be interpreted as going outward, ending up at the imaginary reference.  
If the same object is displayed more than once in the diagram, then its contents are displayed only at the topmost (imaginary) reference to the object.

JJ

-----

Automatic Containment,  
2008-09-21

The beginning of the System Interfaces article group:

“Objects are never directly accessed. They are always floating around somewhere you cannot touch. You are always accessing an object through an *object reference*. You are always dealing with *references* to objects, never with the object directly.”

Objects only contain object references, they never contain objects themselves.  
Referential structure is real. Containment structure is imaginary.  
Automatic containment displays the references as containment, then converges references to the same object back to a single imaginary object location near the top of the structure visible in the diagram. Then that imaginary object location leads back to the logical object location possibly somewhere on another site, even, by following inward references.  
Those inward references could also be interpreted as going outward to the imaginary object location. The logical target location leads even further, to the physical target location, but that’s for another project.

In conceptual explanations you can stick to the referential approach, while automatic containment might convert it to a containment structure.

JJ

-----

Automatic containment,  
2008-09-15

The (second) project of automatic containment should also be about defining the exact position of the referential approach and the containment approach in the system.

JJ

## Out of the original Symbol documentation

### Overlapping Hierarchies

< Triangles can converge types, right? Give a symbol three types? Think about that. >  
< I might use sheer triangles for *pure* overlap establishment. >  
< Circle structure and triangle structure as separate hierarchies. One was originally  called containment hierarchy, while the other was called the inheritance hierarchy. >  
< Command and object hierarchy regarded separately... >

Members can be grouped by different criteria. Groups can overlap, therefore triangles can overlap. This goes against object oriented programming, because objects can’t overlap.

To establish this:

< P >

The following is done:

< P >

Each interface has a shared part that way.

A and B share an interface by putting a triangular object symbol inside both A and B and connecting them with an object line makes them represent the same object. A and B basically both contain the object. In that sense, containment can overlap. Lines are a way for one object to have multiple containers. Lines are a way for objects to overlap.

You aren’t limited to triangle symbols to make objects overlap. You can also use an overlapping notation for circular objects:

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

#### Containment for Divergence, Lines for Convergence

This suggests that a line structure can represent part of the containment.

Normal containment is a tree like structure: one thing contains multiple things. Using lines you can make the tree branches convert again: multiple things contain one thing. Convergence can be displayed in the overlapping notation. So the effect of lines can be displayed in an overlapping notation.

In a normal diagram, *containment* is both the divergence structure of the *object structure*, *type structure* and *interface structure*.

< P >

Containment in the diagram is like three hierarchies in one: all three hierarchies are the same. serves all three hierarchies. 

< P: object containment, type containment, interface containment, same pictures >

Each line type creates the convergence structure for a different hierarchy: object lines establish the *convergence* structure for the object structure, type lines establish the convergence structure for the type structure, interface lines establish the convergence structure for the interface structure.

Containment creates the same tree out for all three of the hierarchies. Convergence, so lines, can hef op the branch out:

< P: Two layer tree out. >

< P: Type tree out heffed op. >

That way the three hierarchies can be made independent of each other. The example above is a perfect way for part of the branch out, that the containment structure imposes, to be lifted, annulled, ignored. In the case above, the type structure ignores the split up in A, B, C, D and E. A, B, C, D and E are still separate objects: the object structure still makes a split up, but the type structure might not make a split up.

The example above, though, might not establish convergence in the type structure. The type structure is as follows:

< Circle in circle >

To completely lift up the branch out you can do the following:

< P: containment notation 1, 2 >

< P: type containment >

The last picture is still called overlapping notation. You can see that the overlapping notation might not show all the details about the lines. It just shows their resulting effect.

#### Triangles for Arbitrary Groupings

In the programming environment, triangles can be used to group members by criteria, without the triangle’s being real objects. The triangles are then just used as marks. In that case there can be overlapping triangles, but the triangles aren’t objects.

< Perhaps I should allow non-existent triangles: triangles that aren’t object capsules. I might want the programmer to have control over them. Triangles used for the sheer purpose of creating an overlapping structure can then be made non-object, so that no double capsules need to be displayed in the overlapping parts in the overlapping notation. >

#### Commands can Overlap

Commands can overlap all the same, because they are much like objects.

< Might this add two more hierarchies? Call and commands reference hierarchy? >

#### Another Thing

A View Where Lines point to target objects?

### Integrating Structure and Symbol

< Brainstorm >

You might look at basics of Symbol. And the basic thing is encapsulation. The encapsulation of a Structure can be derived from the referential structure using a mutual parent rule. This in real life also determines how we feel something encapsulates another thing. You can apply this mutual parent rule to class relations and object relations. All class and object reference are expressed as lines, except the references from parent to child. Objects and commands are there in both languages and are exchangeable. Publicity is also present in both systems. The only thing I don’t know how to express in Symbol is plurality.

Symbol always had a lack of expression in plurality. How. You’d almost want a new shape of symbol. But I’ve sort of run out of shapes. I’d go for a hexagon. It looks like a circle, but has a plurality feeling to it. If you might, you could choose for octagons.

Of course, one of those, might contain a variable amount of objects, that don’t even might be of the same type, but might always have the same interface I guess.

That might conclude seem to conclude the parallelization of Symbol and Structure.

But wait a moment. Structure is based on relations between types. How well do I see those relations between types in Symbol.

In Symbol I better see the relations between objects, while you see none of that in Structure.

How well are the relation between types shown in symbol. Well, you see the containment relations better than ever.

But how do the relations between classes show? Each circle or octagon expresses a relation class. Its class target is the class. You can recognize the class of the target by the class name of the relation class symbol. Class lines show the Structure Relations.

Ok, to recap: most things can be mutually exchangeable between Symbol and Structure. There are two tacky points though: giving the Symbol code an encapsulation structure and plurality in symbol. An octagon might express that an object is plural. The encapsulation is derived from the reference structure using the mutual parent method. Some advantage symbol adds to Structure then, are encapsulation and also object relations. In structure code, it’s hard to view object relations.

Oh, gee. The expression of the structure is covered that way.  
But what about the generated code? The data part may look much like the structure, but what about the user interface. Code for the user interface might add so much diagram to it, that overview over the really structure might be pushed away.  
Oh, how funny, you program the structure in one diagram, but the object oriented system that comes out is a different structure, that resembes the structure diagram, but is much more extended.

Object relations might only come to light when the generated code is running.  
However, you should be able to define static object relations in the structure, or not? Anyway, in the generated code, you should also be able to hide all user interface elements.

- Translate Literally
    - Most things in the structure and the generated application can be literally translated to Symbol
- Plurality
    - A plurality symbol was added to Symbol
- Mutual Parent
    - Encapsulation is derived out of the Structure with a Mutual Parent method.
- Hide Things
    - Things in the generated application are hidden, to keep the focus on the structure (but they can be shown if chosen).
- Extra Relation Lines
    - Add special lines to the diagram that expresses the Structure. You won’t see the relations between classes as well in the structure as you do in the generated code, and I do want to see it. The relations between classes should be expressed with relation lines in the Classes collection. And the classes collection’s mutual parent structure should be expressed as the encapsulation structure, right then and there. Diagram elements may be added to better see that.
    Perhaps I should develop a separate way to notate the structure. Perhaps you should draw out the relations as you see them in the generated code and then Structure might figure out what it means.
    That means you draw classes and you put object in them and that draws out the relation. The object contain the members of the Class class and you can specify it furtherly there.

Nee, forget all that.

Als je Structure in Symbol gaat toepassen, zal je een deel van ‘de gegenereerde code’ zelf programmeren. Dat lijkt in ieder geval zo. Als je een class in de structure might aanmaken, maak je een symbol aan. Als je een relatie tussen twee klassen wilt maken, dan maak je een object reference aan in een klasse die een relatie met de ander heeft. De relatie wordt wel automatisch dual. Als je een attribuut wilt toevoegen aan een class, dan stop je een objectje er gewoon in. Attributen worden trouwens objecten. Veel dingen worden wel op een gewone Structure achtige wijze ingevoerd. Daarvoor heeft een object symbol een Class interface gekregen, waar de structure information in wordt bewerkt. Daarin kun je ook bijvoorbeeld, customizen voor deeper objects. Je ziet ook nog globaal de classes en de relations collecties. Je ziet dus gewoon alle structuur informatie. Je kunt ook alles van de gegenereerde applicatie zien. Zo kun je in het aangemaakte object symbol (dat een Structure class is) de symboliek van de gegenereerde user interface zien. Die symboliek wordt automatisch bijgewerkt als je de Class informatie aanpast. Wijzigingen in de gegenereerde user interface symboliek worden als customization gezien en blijven staan, tenzij ze weer gedefault worden, waardoor de generator weer bepaalt wat het wordt. Je kunt ook een symbol meteen runnen, dus je kunt een control meteen laten zien.

Je ziet gewoon de structuur informatie en de gegenereerde applicatie in één symbol diagram. Dus voor een deel programmeer je in Symbol de Structure alsof je zelf de gegenereerde code aan het programmeren bent en de structure informatie is nog steeds wel beschikbaar. Alles wat je ziet komt ook in de gegenereerde applicatie terecht. Structuur informatie wordt namelijk ook zichtbaar in de gegenereerde applicatie. De uitzondering daarop is dat er kan gekozen worden om structuur informatie achterwege te laten in de generated application, alsmede andere dingen achterwege gelaten, maar die dingen zie je dan wel in de design code.

Je kunt ervoor kiezen om de encapsulatie structuur automatisch aan te laten leggen. Je kunt ook zelf de encapsulatie bepalen.

Er kan veel worden verzonnen om andere structuur eigenschappen zo direct te editen als je bijvoorbeeld klassen en relaties edit. Bijvoorbeeld zou progression ook op expliciete manier geëdit kunnen worden. Wat er allemaal nog meer expliciet geëdit zal kunnen worden, dat zal zichzelf wel wijzen.

Dat zal nog moeilijk te leren zijn, die taal. Ach, tutorials.

### Brainstorm

Multiple containment

### Contaiment by Containment and Reference

Reference can be seen in a way as containment.

### Other

On top of the arbitrary assignments of diagram elements to aspects of the system there are several other customizations of the view.

You can customize a number of things:

1) You can express the encapsulation and delegation tree structure as a single encapsulation structure in which symbols can overlap:

This may result in unclarity:

The rule of thumb is: a symbol is encapsulated only if its shape is totally encapsulated < That so? >

-----

You can’t access anything upward in the hierarchy, only downward, unless given a reference to something upward in the hierarchy, but then it already goes downwards again.

-----

All Object Symbols that are the same Objects have the Same Line Targets

-----

Symbols can Overlap  
Containment for Divergence, Lines for Convergence  
Triangles For Arbitrary Grouping < Non-Object Triangles >  
Commands can Overlap

-----

You can also let J Data maintain the containment automatically, based on mutual ancestors. I should be able to do that automatically in Symbol too. Should make a note about that in the Symbol documentation.

-----

2004,

Symbol non encapsulative (full referential) notation. Symbol total encapsulative notation (non-referential) (possible overlaps). Symbol obvious encapsulative notation ? level bound?

So there might not be a difference between reference and encapsulation. You could arbitrarily assign wether to regard it reference and wether to regard it encapsulation?

For children that refer to the same thing, should or shouldn't the parent be seen as having to refer to it too? Hmmm

Oh. In overlapping it seems they contain each other and you can't see who's the parent and who's the child

JJ

### Object Basics

#### Referencing a Parent

You can also reference a parent or descendant:

![](images/3.%20Automatic%20Containment.043.png "Reference to Ancestor")

I mention this separately here, because you won’t see this notation very often, but it’s possible all the same.

-----

< Might explain how the children inside parents, that are the same object, have the same line targets. Or the children inside diamonds that are the same execution. >

## More Ideas

Automatic Containment,  
2009-04-30

I have a problem with automatic containment: what if you have the logical residence of an object in sight, and you also have objects displayed, that contain references to the object, but the containment level displayed is just not deep enough to show those references to the object. Then, no imaginary references are displayed either... perhaps in the future, the imaginary references are persisted anyway, instead of recalculated, so that they can always be displayed, even when the real references are out of sight.

JJ

-----

Formerly in the Relations chapter,

It `might` be mentioned, that `the*` method of *automatic containment* applies to unidirectional references, and `just` *might `not*` match* yet with `the*` notation for relationships. In `the*` future it `might` be further worked out how to `best` turn them into a single notation.

JJ

-----

Artificial Promotion / Esthetic Reference,

Objects automatically put on a lower level, because of deeper usage, can artificially be promoted to a higher level, by creating a reference to it from a higher object, for esthetic reasons, related to it having great significance on a higher level. (this might not result in an object reference being put on every level in between.)

A compiler could generate a warning about such an unused reference, unless you actively type the reference as being esthetic.

JJ

-----

Artificial Promotion / Esthetic Reference,

Heel algemene dingen komen bij automatische containment in de diepste lagen terecht, terwijl je het misschien wel hoger wil zien. Eigenlijk wil je het dan promoveren naar een hoger niveau. Ik bedenk me nu, dat je dat kan doen door een hoger object een (ongebruikte) referentie te geven naar het algemene object. Dat hoger object zit dan wel 'toevallig', 'vanzelf' hoger op dat moment. Dat is ok.

JJ

-----

Artificial Promotion / Esthetic Reference,

Automatische encapsulatie, zet algemene dingen op het diepste niveau  
Aan de andere kant zijn algemene dingen eigenlijk minder belangrijk, dus mogen ze diep zitten, maar ze kunnen voor het begrip van het systeem wel belangrijk zijn. Logging is bijvoorbeeld eigenlijk deel van de user interface, en de user interface ligt een niveau hoger dan het proces zelf, ondanks dat de functionaliteit van het proces meer over het programma zegt, dan de user interface, die daarop gebouwd is. Het probleem van technische encapsulatie versus functioneel belang versus belang voor het begrip van het systeem, zit me nog niet lekker wat betreft automatische encapsulatie.

Maar gebruikte componenten zitten ook op een dieper niveau, maar het diepere niveau refereert qua class naar hoger, want de component class staat gewoon naast het component dat daarop voortbouwt.

Eigenlijk moet ik autocontainment gewoon in de praktijk zien.

JJ

-----

express mutuality of object separate from expressing relations...
So you have a relation symbol function as the indicator of a relation, and an imaginary reference functioning as the indicator of the object. Too many lines.
It sucks.

Perhaps I need to show the symbol's contents only at the highest containment level, at which the object is referenced. And therefore, have relation symbols also only reside on a high level.

But is there a situation in which you access things on a deeper level? Or is everything happening, elevated to a higher level, by putting imaginary references on a higher level.

It still might not look good

-----

Perhaps the answer lies somewhere in
- Containment implies a relation back to the parent
- Relations are given direction
- Most relations have a main direction,
  the main direction is displayed as a unary relation
  but with a couple of circles around the line,
  indicating a dual relation.

-----

Automatic Containment,  
2008

Brainstorm:

I am wondering if I can stop emphasizing every symbol is a reference, and just save that for specific diagram topics. That might make the story a lot simpler. I can then ignore automatic containment, making an outer stub of a redirection, the object itself. Crap, might that simplify the explanations.


In automatic containment, I create imaginary references, turning all the symbols imaginarily to object references,
which they actually already were. But the outer reference is representing the object itself.

Ignore that for other article groups. Only focus on the current one. But actually, I have already done that in the other articles.

In that case, I should stop calling them pointers to pointers. They are, but I should stop calling them that.

It might so much simplify the usage of the language. If you might consider any symbol a reference, then it might be totally inaccessible to children, for instance.


These contemplations have everything to do with the implications of automatic containment. Every symbol is a reference. But in the original Symbol, the target of all the redirections was the object itself. I might uphold that, for a better understandable language.

JJ

-----

Posessed Imaginary References,

![](images/Posessed%20imaginary%20references.png)

JJ
