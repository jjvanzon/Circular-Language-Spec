Encircle Language Spec | Pointers
===============================

From Framework | Circularity
----------------------------

`[ Preliminary documentation ]`

Circularities are in many cases no problem. Sometimes, however, a program is organized in a way, that circularities will make the program hang. Therefore there is standard functionality in Creator to handle circularities. Procedures that handle a circularity sometimes require a lot of steps.  
< 2007-07-15, Creator will handle these steps for you? >

The first thing to understand is how circularities are formed. Object structures can form large constructions of one object referring to another. when following redirections from one object to another, you can end up at the same object again. This means that the redirecting is circular.

Circularities are easily formed. A parent referencing a child and the child referencing the parent again, is a circularity already. They’re practically there all the time. However, some circularities are important to handle or prevent. In the __Structure__ you have to specify for what kind of redirections you will handle circularities. You do that by selecting a subset of relations in which circularities will be handled.

Circularities formed inside this subset of relations will be handled. You specify a circularity handler in the Structure.CircularityHandlers collection. In a CircularityHandler you can specify a subset of relations for which circularities will be checked. You will also specify the way in which circularity is handled.

There are four ways to handle circularities:

- Circularity detecting
- Circularity blocking
- Circularity encountering
- Circularity targeting

The first type of circularity handing is *circularity detecting*. This type of circularity will add a method to all __Items__ and __Lists__ involved in the subset of relations. This method is named __IsCircular__, which returns __True__ when the object is part of a circularity, and __False__ if the object is not part of a circularity. The whole redirecting of the object structure could be followed to find out if a circularity closes itself somewhere. It can be quite a process. Hellish in certain cases, but sometimes it’s quite important to know if something is circular. One __IsCircular__ method delegates to other __IsCircular__ methods in related objects, which again delegate to __IsCircular__ in even deeper objects. Passed along with the __IsCircular__ method is the object to check circularity for. Another thing passed along is the __Parent Stack__, which is the chain of redirections already followed: the current redirecting path. In the __IsCircular__ method, an object first compares itself with the object passed along. If they match, then __IsCircular__ will return __True__ and the whole circularity detection will be wrapped up in a flash. If the objects don’t match, then the object adds itself to the __Parent Stack__, and calls the __IsCircular__ method of the related objects, that participate in the circularity handling. The __IsCircular__ methods of the related objects work exactly the same. At the end of the __IsCircular__ method, the object removes itself from the __Parent Stack__ and returns to the previous caller. Depending on the enormity of the structure, this process can be quite elaborate.

The second type of circularity handling is *circularity blocking*. This methods sees to it that circularities are *never formed*. In that case, you will never have to mind circularities when working with the structure, because circularities will simply never be there. Every time an object inside the subset of relations is __Set__, there is checked if a circularity is in jeopardy of being formed. If it is, then the the object will *not* be set. Every involved item and list will get a __WillBeCircular__ method. This method checks if the object is already present anywhere in the redirecting. If it is, then a *circularity* would be formed by assigning the object. __WillBeCircular__ will then return __True__ and the object will not be assigned.

The third type of circularity handling is *circularity encountering*. In this method the circularity is not prevented, but just detected in the right situations. For instance, in J Sound, you might want to detect circularities on getting an __Operator__’s __Value__ (the output value of an __Operator__). A method will be added to the __Operator__ called __CircularityReached__, which checks if the object itself is already present in a chain of *call parents*. That method will require a collection of previously called parents to be passed along. The object will search for itself in this __Parent Stack__. This requires that the __Parent Stack__ is passed to the every __Value__ property. The __Value__ property will call the __CircularityReached__ method that returns if returns if the object is already on the __Parent Stack__. If it was, then the __Value__ method should return a default value and not work with any other operands. The first thing you do in the __Value__ procedure, is call __Circularity Reached__ and if it’s __True__, you return with a default value. When __Circularity Reached = False__ then you continue the procedure. The first thing to do then is for the object to put itself on the __Parent Stack__. At the end of the __Value__ procedure you will remove the object from the __Parent Stack__. In between you will use the __Operands__’ __Value__ procedures, passing along the __Parent Stack__. This __Value__ procedure is a custom procedure that you write yourself and you should obey to these circularity managing rules.

The fourth way of circularity handling is called circularity targeting. This adds a method to the involved classes, named __CircularityTarget__. When this method is called in an object part of a circularity, then it will return the circularity target. I have to check the Symbol documentation to see how a target symbol is found.

Of course circularities don’t need to be protected, circularities can be made as soon as somewhere in the relational redirection, an already passed object occurs. This section simply laid out the possibilities in Creator to handle circularities to prevent your program from hanging.

### Older Story

To completely prevent circularities from forming, though, this procedure only needs to be executed whenever a circularity could be formed: on changing an object reference. To detect a circularity that’s already there, can require a lot of steps, though.

J Sound __Patches__ are a good example of objects in which you have to manage circularities. You could say that __Operator__ objects may not form circularities. However, just stating what __Classes__ can’t form circularities, doesn’t cover it. You have to do with __RelationClasses__. In J Sound __Patches__, when you follow operand relations, you should not eventually encounter the source object. To check if a structure of __Operands__ forms a circularity, you have to go by all direct and indirect relations to __Operands__ and if you don’t find an object already passed, then no circularity will be formed.

Therefore, you have to give all objects that have to prevent a circularity a method called __WillBeCircular__, which will return __True__ if the object passed as an argument is already inside the structure. For each circularity free system, you have a different __WilBeCircular__ method, which is added to every __Item Class__ or __Lists Class__ involved in the Circularity Free System. When you assign an object within a circularity free system, the __Set__ procedure must check for circularities before assigning the object. If a circularity is in jeopardy of being formed, the object is not assigned. All relations involved in the circularity free system are checked, which can be a very extensive procedure.

You have to specify circularity free systems as a tree structure of __Relation Classes__ that may not form circularities. Each of the __Classes__ involved will get a __WillBeCircular__ method which will call the appropriate __WilBeCircular__ methods of its related objects. Only of the __Relation Classes__ involved in the circularity free system will be checked in the __CheckCircularity__ method. In the case of J Sound, all __Operand Relation Classes__, would be added to the circularity free system. A circularity free system is specified in a __CircularityCheck__ object inside a __CircularityChecks__ collection in the __Structure__.

I’m quite sure, that once I try to program __Circularity Checks__ using J Sound as an example, things will fall in to place on their own.

That described just one type of circularity handing, called a __Circularity Free System__.

There is another way to handle circularities in which the circularity is not prevented, but just detected in the right situations. It’s called a __Circularity Encountering System__. For instance, in J Sound, you might want to detect circularities on getting an __Operator__’s __Value__ (the output value of an __Operator__). A method will be added to the __Operator__ called __CircularityReached__, which checks if the object itself is already present in a chain of *call parents*. That method will require a collection of previously called parents to be passed along. The object will search for itself in this collection. This requires that the __Parent Collection__ is passed to the the __Value__ property. The __Value__ property will use the __CircularityReached__ method that returns if a circularity was just entered. If a circularity was entered, then the __Value__ method shouldn’t work with any other operands, but for instance return a default value instead. The first thing you do in the __Value__ procedure, is call __Circularity Reached__ and if it’s __True__, you return with a default value. When __Circularity Reached = False__ then you continue the procedure. The first thing to do then is for the object to put itself on the __Parent Stack__. At the end of the __Value__ procedure you will remove the object from the __Parent Stack__. In between you will use the __Operands__’ __Value__ procedures, passing along the __Parent Stack__. This __Value__ procedure is a custom procedure that you write yourself and you should obey to these circularity managing rules.

The circularity checking system will be specified the same way as a __Circularity Free System__, only there will be a different kind of method to check circularity. In a Circularity Free System, the __WillBeCircular__ method will check *all relations* involved in the __Circularity Free System__, to detect *an object passed along* to the __WillBeCircular__ method. In a __Circularity Detecting System__, the __Circularity Reached__ method will check a __Parent Stack__, to see if the object itself is contained in it.

Both methods don’t offer a universal method to check for circularities. One is designed to prevent circularities and one is designed to see if you’ve bumped into a circularity in the course of a call stack. You can also supply a universal function to check if an object is part of a circularity: IsCircular. This is also bound to a specific Circularity Free / Circularity Checking system of Relation Classes. That is the Circularity Detecting System.

I also want to be able to return the target symbol of a circularity. That requires you to specify a circularity system again. This may be handy for Symbol, in which multiple relation types can lead to the target Class, Object or Interface for instance. This will create a __CircularityTarget__ method. That is the Circularity Targeting System. Or something…

So there are four types of circularity checking:

- Circularity blocking
- Circularity encountering
- Circularity detecting
- Circularity targeting

I have to think of better names. Preventing and blocking sound too alike.

Of course circularities don’t need to be protected, circularities can be made as soon as somewhere in the relational redirection, an already passed object occurs. This section simply laid out the possibilities in J Data to handle circularities to prevent your program from hanging.

### Loose Ideas

2008-04-26  
I would also want to give procedures running over circular object structures, a maximum number of iterations, so that you can let procedures run circularly to a certain extent.

-----

Circular creation,  
2008-08-15

Special creation behavior for recursive calls, prevents a hazard, that is actually also present in objects: circular creation:

create an object of a class, that creates an new object of the same class, which creates a new object of the same class.

Don't pay too much attention to it now. Make it an article in the circularity topics. Also put there, that in the project, that works out circularity, you have to see if you can merge the concepts of circular creation and creation behavior of sub-commands.

JJ