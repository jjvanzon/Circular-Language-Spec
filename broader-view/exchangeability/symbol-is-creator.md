Circular Language Broader View | Exchangeability | Symbol = Creator
===================================================================

`[ Preliminary documentation ]`

*Symbol* refers to an object oriented programming language I began to construct around the year 2001. It is a programming language, that fully expresses a program in a diagram.

*Creator* refers to a programming language I began working on around 2006. The basic principle of it is, that you start off defining classes and relations, and an application is generated out of it.

The principle of *Symbol = Creator* is about turning these two languages into a single programming language. This is hard, because Creator is based on defining relations, and Symbol was object oriented and did not even have a way to express a relation in a diagram.

A few important objectives of Symbol were:

- The diagrams can fully express any piece of code. 
- A diagram is an as direct as possible depiction of an object oriented system.

The most primitive expression of something is in circles and lines connecting them.  
The most primitive way to express something, should be reserved for the most fundamental of principles. In the original version of Symbol, this was: circles for objects and lines to reference objects. However, in Creator relations may be a more important principle than referencing an object...

The most important trick in turning the two languages into a single language is by separating the abstract principles from the way they are expressed. Independant from the expression, the principles don’t have any mismatches with each other. Lateron I might determine how to express these abstract principles in diagrams. The most basic principle should have the most basic expression in the diagram. At this moment it is not clear to me yet how the Symbol-like diagrams might look now, because when I designed Symbol, it was *the object* which was the most primitive of all principles. In Creator *classes and relations* seem to be the most primitive of all principles.  
Now that I want to integrate the relational base of Creator in Symbol, and make it one language, the only right solution seems to be to have a variation of Symbol that is an as direct as possible depiction of Creator’s relational paradigm.

Below I sum up the main problems in trying to unify the two programming languages. The solutions are briefly mentioned too.

- Problem area: relations / no relations
- Symbol: no expression of relations
- Creator: relations are fundamental
- Solution: think of a way to give relations a fundamental expression in Symbol diagrams
-----
- Problem area: containment
- Creator: no containment, only a referential structure, a flat list of classes
- Symbol: has containment structure and referential structure with classes defined at an arbitrary containment depth
- Solution: automatically generate containment structure out of the referential structure; something is declared on the highest level it is used.
- < This isn’t right anymore... >
- < The lowest level of mutual usage, which is above or at the same level of all the locations it is used in. >
-----
- Problem area: multiplicity
- Symbol: no expression of multiplicity
- Creator: multiplicity an important principle
- Solution: a new symbol, that represents a collection of objects, rather than a single object
----- 
- Problem area: creation
- Symbol: creation not made important enough
- Creator: creation a normal principle
- Solution: yet to be found, but try to give creation a more fundamental way to express in a diagram
----- 
- Problem area: separation between objects, classes and interfaces
- Symbol: object, class or interface same symbol
- Creator: classes defined as classes, objects defined by relations
- Not a solution: a separate part of the diagram contains the classes
- Solution: with automatic containment the class is specified on the highest level it is used. A single symbol’s being able to have three possible functions might sustain.

The specification of how Symbol and Creator might become one language might be covered in the explanations in the spec. It might just be the principles and the expression from now on. No more Creator and Symbol.