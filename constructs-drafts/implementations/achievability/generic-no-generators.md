Encircle Language Construct Drafts | Implementations
====================================================

Achievability | Generic, No Generators
--------------------------------------

`[ Out of Scope ]`

__Contents__

- [Introduction](#introduction)
- [Attributes](#attributes)
- [Related Items](#related-items)
- [Related Lists](#related-lists)
- [User Interface](#user-interface)
- [In Experiment 2.0: All Concepts Can Become Generic, Except For One: Methods](#in-experiment-20-all-concepts-can-become-generic-except-for-one-methods)

### Introduction

Experiment 0.9 was a code generator. This code generator was quite hard to make, even after implementing several good ideas for organizing its code. It still happened frequently, that *something* in the generated code was missing, or some situation was not accounted for. And it made the code generator produce uncompilable code. You could argue that the code generator was just not well written, but it is still a fact that the code generator was simply very hard to make.

Then, for experiment 2.0 I decided to implement things in a different way. I made it a goal to make Encircle run on generic modules. Instead of regenerating the whole program every time, Encircle might become an engine, that simply takes a program description and adapts itself to it.

I proposed the following axiom:

*Any code generator can be replaced by a generic program, that takes the same settings and configuration, and produces the same result.*

So the generic program might become an engine that can load programs and have them run inside of it.

I had foreseen, that programs running in it might be slower than programs that were totally generated and might run stand-alone. In experiment 2.0 it turned out that the speed loss is really not that bad. And I was still identifying things by name there, not even by number; that might have made it even faster.

The programming interface of a *generated* modules used to look very slick in the generated code. Using the programming interface of the *generic* modules might not make the code look nice. However, you won’t be using it directly in C++ anymore. You’ll be using a custom text code, which *might*  look totally slick again. So it really doesn’t matter, that the code might not that good in C++.

Below I give a description of the implementation of some basic coding principles, and how they could be implemented by a generic module, rather than have code generator generate the code for it. It is a simplified implementation, just to make it clear how it is possible.

### Attributes

In both the code generator version of Encircle, as well as the generic engine version of Encircle, there are objects that hold a description of a class. This class description consists among other things of a description of which attributes the class holds.  
The code generator used to use this class description to generate the code of the class.  
In a generic version of Encircle, there are generic objects, to which a class can be assigned. The generic object then adapts itself to the class description. The object contains an arbitrary array of attributes. When the object adapts itself to the class description, all the attributes of the class description are traversed. For each attribute of the class, an item is added to the attribute array of the object. Each attribute is configured according to the class description. Each of the attributes gets the appropriate amount of memory space reserved to store the attribute. The name of the attributes is also stored inside the generic object.  
Then the object holds all attributes that are specified in the class description, with the names of the attributes included.  
You can let the object perform a basic search by name, and let it return the right attribute.

You could optimize things by not storing the attribute names inside every object, but only using the names stored in the class. But that’s for later.  
In a more optimized situation, the attributes might hardly even *be*  accessed by name anyway, but mostly by number, so you won’t even need the names then, but this is an issue for later.

### Related Items

It is pretty much the same issue for related items. The generic object contains an array of attributes. As such it also contains an array of related items. An element of the array of related items contains the related item’s name, as well as a reference to the actual related object, which is also just a generic object again. When a class is assigned to the generic object, all the related items specified inside the class description are traversed. For each related item in the class description, a related item is added to the array of related items in the generic object.

### Related Lists

For related lists you can do the same things. A related list is merely a lists of generic objects. There is a generic class, called List, that simply holds an array of generic objects. An object contains an array of Lists. Each related list has an item in this array of Lists.
The difference between related items and related lists, is that a related list might not contain any objects at first: objects might be added to it later. When adding an object to the related list, the related list is aware of the class of object, that the list should contain, and assigns the class of the object to it whenever an object is added to it.

### User Interface

Now seeing how easily a generic version of an object could adapt itself to a class description, you can also imagine creating a generic user interface, that adapts itself to a class description. An generic user interface, that displays the attributes of a single object for instance. When assigning a class to the generic user interface, for every String attribute that the class contains, it could add a Text Box to an array of text boxes it contains.

### In Experiment 2.0: All Concepts Can Become Generic, Except For One: Methods

All concepts of Encircle might become purely generic.

In the first generic version (experiment 2.0) all the basic concepts could easily be implemented as a generic version, except for one: methods.  
It was harder to let custom methods run inside the engine. A preliminary solution was found, by letting the engine link to external DLLs, but explaining this is outside the scope of this article. See: *Preliminary Methods*.
