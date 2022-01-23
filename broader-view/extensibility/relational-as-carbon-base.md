﻿Circular Language Broader View | Extensibility | Relational As Carbon Base
==========================================================================

`[ Preliminary documentation ]`

The Relational As Carbon Base principle means that when making a program, you should primarily think in terms of relations between classes. The relations and classes are used as a base.  
They are used by *concepts*, for instance to automatically generate a user interface for the system. Also the concepts Undo and Copy & Paste can automatically be applied to the relational structure. The concepts are tied to the relational structure. The relational structure forms the carbon base of the program, onto which other atom groups can be attached.

Basically, the relational structure is the carbon base... concepts can extend the carbon base with extra code, that isn’t the core of the system.

## Doubts Looking At Diagrams

I have doubts you’ll be thinking in terms of classes and relations and attaching concepts to them as much as I thought.  
In diagrams you don’t really see relational as carbon base. In the diagrams you basically see an object oriented approach. First and foremost you see objects connecting to other objects. However, if you highlight the target classes, and the target classes of the related objects they contain, you have the relational structure. But in the symbol diagram that doesn’t look like the carbon base at all.

When you edit the diagram, you’re not really busy with defining relations between classes. You’re defining relations between objects out of which a relational structure derives.

Actually, you should see it like this: if you’re defining objects and object lines, you are defining data within your program; when you’re defining classes and class lines, you’re defining the structure of your program.

It’s hard... at all times in the diagram the target classes and the class lines between them should be highlit, because it SHOULD be on the foreground of your software development, and it should count as the bone structure of your program. Therefore the bone-structure might be highlit, because everything is attached to this, and it is the relational structure, which should be the base of what you think about when defining your program.

## Loose Ideas

Men moet gewoon de klasse-relatie structuur zo veel mogelijk als basis nemen, en niets ernaast bouwen, maar commando's in de structuur INbouwen. de klasse-relatie structuur is zeg maar de koolstof basis en daar kan vanalles aanhangen.

-----

Methods are now separate entities. They are flat functions as they used to be very long ago, before C++, but because of the Flat & Structured Interchange concepts, a method becomes part of the class of each of its parameters.  
So if you create a set of functions that processes a recursive structure, and you’re wise and you create a method for each type of element in the recursive structure, and the element in the recursive structure, becomes a parameter of the method, then the functions might automatically become part of the class they process. If the class can not be extended with methods, because the author has locked it, the whole class structure might be inherited from and the derived classes might get the new methods included.

-----

Komt het carbon-based idee ook zichtbaar terug in een diagram? Volgens mij zie je niet een moleculair iets. De uitbreidingen zitten er niet aan vast, maar zitten geëmbed.

-----

Ik zet relationeel bovenaan, en vertaalt zicht direct naar object georiënteerd. Vervolgens kunnen object georienteerde principes worden ingevoerd binnen het relationele model. Dus het raamwerk is relationeel, in plaats van OO. Relationeel is niet een aparte benadering, maar juist het geraamte, waar alle denkbare functionaliteit aan vastgeknoopt wordt als koolstofbasis.

-----

Het nemen van relationeel als geraamte, is misschien origineel.  
In caché denk je nog veel te veel vanuit het individuele object, en wat dat individu nodig heeft, en waar dat individu naar refereert. J Code kijkt meer naar het collective. Mooi verkooppunt: less individuality, more collectivity.