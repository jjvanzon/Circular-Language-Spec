Circularity
============

*Author: Jan-Joost van Zon*

*Location: Oosterhout, The Netherlands*

*Date: October 15, 2007 - October 15, 2007*

*Copyright: Jan-Joost van Zon*

Circularities are in many cases no problem. Sometimes, however, a program is organized in a way, that circularities will make the program hang. Therefore there is standard functionality in Creator to handle circularities. Procedures that handle a circularity sometimes require a lot of steps.

< 2007-07-15, Creator will handle these steps for you? >

The first thing to understand is how circularities are formed. Object structures can form large constructions of one object refering to another. when following redirections from one object to another, you can end up at the same object again. This means that the redirectioning is circular.

Circularities are easily formed. A parent referencing a child and the child referencing the parent again, is a circularity already. They’re practically there all the time. However, some circularities are important to handle or prevent. In the **Structure** you have to specify for what kind of redirections you will handle circularities. You do that by selecting a subset of relations in which circularities will be handled.

Circularities formed inside this subset of relations will be handled. You specify a circularity handler in the Structure.CircularityHandlers collection. In a CircularityHandler you can specify a subset of relations for which circularities will be checked. You will also specify the way in which circularity is handled.

There are four ways to handle circularities:

- Circularity detecting
- Circularity blocking
- Circularity encountering
- Circularity targeting

The first type of circularity handing is *circularity detecting*. This type of circularity will add a method to all **Items** and **Lists** involved in the subset of relations. This method is named **IsCircular**, which returns **True** when the object is part of a circularity, and **False** if the object is not part of a circularity. The whole redirectioning of the object structure could be followed to find out if a circularity closes itself somewhere. It can be quite a process. Hellish in certain cases, but sometimes it’s quite important to know if something is circular. One **IsCircular** method delegates to other **IsCircular** methods in related objects, which again delegate to **IsCircular** in even deeper objects. Passed along with the **IsCircular** method is the object to check circularity for. Another thing passed along is the **Parent Stack**, which is the chain of redirections already followed: the current redirectioning path. In the **IsCircular** method, an object first compares itself with the object passed along. If they match, then **IsCircular** will return **True** and the whole circularity detection will be wrapped up in a flash. If the objects don’t match, then the object adds itself to the **Parent Stack**, and calls the **IsCircular** method of the related objects, that participate in the circularity handling. The **IsCircular** methods of the related objects work exactly the same. At the end of the **IsCircular** method, the object removes itself from the **Parent Stack** and returns to the previous caller. Depending on the enormity of the structure, this process can be quite elaborate.

The second type of circularity handling is *circularity blocking*. This methods sees to it that circularities are *never formed*. In that case, you will never have to mind circularities when working with the structure, because circularities will simply never be there. Every time an object inside the subset of relations is **Set**, there is checked if a circularity is in jeopardy of being formed. If it is, then the the object will *not* be set. Every involved item and list will get a **WillBeCircular** method. This method checks if the object is already present anywhere in the redirectioning. If it is, then a *circularity* would be formed by assigning the object. **WillBeCircular** will then return **True** and the object will not be assigned.

The third type of circularity handling is *circularity encountering*. In this method the circularity is not prevented, but just detected in the right situations. For instance, in J Sound, you might want to detect circularities on getting an **Operator**’s **Value** (the output value of an **Operator**). A method will be added to the **Operator** called **CircularityReached**, which checks if the object itself is already present in a chain of *call parents*. That method will require a collection of previously called parents to be passed along. The object will search for itself in this **Parent Stack**. This requires that the **Parent Stack** is passed to the every **Value** property. The **Value** property will call the **CircularityReached** method that returns if returns if the object is already on the **Parent Stack**. If it was, then the **Value** method should return a default value and not work with any other operands. The first thing you do in the **Value** procedure, is call **Circularity Reached** and if it’s **True**, you return with a default value. When **Circularity Reached = False** then you continue the procedure. The first thing to do then is for the object to put itself on the **Parent Stack**. At the end of the **Value** procedure you will remove the object from the **Parent Stack**. In between you will use the **Operands**’ **Value** procedures, passing along the **Parent Stack**. This **Value** procedure is a custom procedure that you write yourself and you should obey to these circularity managing rules.

The fourth way of circularity handling is called circularity targeting. This adds a method to the involved classes, named **CircularityTarget**. When this method is called in an object part of a circularity, then it will return the circularity target. I have to check the Symbol documentation to see how a target symbol is found.

Ofcourse circularities don’t need to be protected, circularities can be made as soon as somewhere in the relational redirection, an already passed object occurs. This section simply laid out the possibilities in Creator to handle circularities to prevent your program from hanging.
#### **Older Story**
To completely prevent circularities from forming, though, this procedure only needs to be executed whenever a circularity could be formed: on changing an object reference. To detect a circularity that’s already there, can require a lot of steps, though.

J Sound **Patches** are a good example of objects in which you have to manage circularities. You could say that **Operator** objects may not form circularities. However, just stating what **Classes** can’t form circularities, doesn’t cover it. You have to do with **RelationClasses**. In J Sound **Patches**, when you follow operand relations, you should not eventually encounter the source object. To check if a structure of **Operands** forms a circularity, you have to go by all direct and indirect relations to **Operands** and if you don’t find an object already passed, then no circularity will be formed.

Therefore, you have to give all objects that have to prevent a circularity a method called **WillBeCircular**, which will return **True** if the object passed as an argument is already inside the structure. For each circularity free system, you have a different **WilBeCircular** method, which is added to every **Item Class** or **Lists Class** involved in the Circularity Free System. When you assign an object within a circularity free system, the **Set** procedure must check for circularities before assigning the object. If a circularity is in jeopardy of being formed, the object is not assigned. All relations involved in the circularity free system are checked, which can be a very extensive procedure.

You have to specify circularity free systems as a tree structure of **Relation Classes** that may not form circularities. Each of the **Classes** involved will get a **WillBeCircular** method which will call the appropriate **WilBeCircular** methods of its related objects. Only of the **Relation Classes** involved in the circularity free system will be checked in the **CheckCircularity** method. In the case of J Sound, all **Operand Relation Classes**, would be added to the circularity free system. A circularity free system is specified in a **CircularityCheck** object inside a **CircularityChecks** collection in the **Structure**.

I’m quite sure, that once I try to program **Circularity Checks** using J Sound as an example, things will fall in to place on their own.

That described just one type of circularity handing, called a **Circularity Free System**.

There is another way to handle circularities in which the circularity is not prevented, but just detected in the right situations. It’s called a **Circularity Encountering System**. For instance, in J Sound, you might want to detect circularities on getting an **Operator**’s **Value** (the output value of an **Operator**). A method will be added to the **Operator** called **CircularityReached**, which checks if the object itself is already present in a chain of *call parents*. That method will require a collection of previously called parents to be passed along. The object will search for itself in this collection. This requires that the **Parent Collection** is passed to the the **Value** property. The **Value** property will use the **CircularityReached** method that returns if a circularity was just entered. If a circularity was entered, then the **Value** method shouldn’t work with any other operands, but for instance return a default value instead. The first thing you do in the **Value** procedure, is call **Circularity Reached** and if it’s **True**, you return with a default value. When **Circularity Reached = False** then you continue the procedure. The first thing to do then is for the object to put itself on the **Parent Stack**. At the end of the **Value** procedure you will remove the object from the **Parent Stack**. In between you will use the **Operands**’ **Value** procedures, passing along the **Parent Stack**. This **Value** procedure is a custom procedure that you write yourself and you should obey to these circularity managing rules.

The circularity checking system will be specified the same way as a **Circularity Free System**, only there will be a different kind of method to check circularity. In a Circularity Free System, the **WillBeCircular** method will check *all relations* involved in the **Circularity Free System**, to detect *an object passed along* to the **WillBeCircular** method. In a **Circularity Detecting System**, the **Circularity Reached** method will check a **Parent Stack**, to see if the object itself is contained in it.

Both methods don’t offer a universal method to check for circularities. One is designed to prevent circularities and one is designed to see if you’ve bumped into a circularity in the course of a call stack. You can also supply a universal function to check if an object is part of a circularity: IsCircular. This is also bound to a specific Circularity Free / Circularity Checking system of Relation Classes. That is the Circularity Detecting System.

I also want to be able to return the target symbol of a circularity. That requires you to specify a circularity system again. This may be handy for Symbol, in which multiple relation types can lead to the target Class, Object or Interface for instance. This will create a **CircularityTarget** method. That is the Circularity Targeting System. Or something…

So there are four types of circularity checking:

- Circularity blocking
- Circularity encountering
- Circularity detecting
- Circularity targeting

I have to think of better names. Preventing and blocking sound too alike.

Ofcourse circularities don’t need to be protected, circularities can be made as soon as somewhere in the relational redirection, an already passed object occurs. This section simply laid out the possibilities in J Data to handle circularities to prevent your program from hanging.
## **Ideas**
2008-04-26

I would also want to give procedures running over circular object structures, a maximum number of iterations, so that you can let procedures run circularly to a certain extent.


Circular creation,

2008-08-15

Special creation behavior for recursive calls,

prevents a hazard, that is actually also

present in objects: cicular creation:

create an object of a class,

that creates an new object of the same class,

which creates a new object of the same class.

Don't pay too much attention to it now.

Make it an article in the circularity topics.

Also put there, that in the project,

that works out circularity, you have

to see if you can merge the concepts of

circular creation and creation behavior of sub-commands.

JJ

