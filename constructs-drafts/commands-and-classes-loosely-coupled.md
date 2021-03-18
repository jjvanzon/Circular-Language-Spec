Circle Language | Broader View
==============================

Commands and Classes Loosely Coupled
------------------------------------

`[ Preliminary documentation ]`

### Concept

Objects of the same class might have a similar set of commands.

But one particular idea for commands would be, that they might live as separate entities, not part of a specific class.

The general idea would then be, that a command would automatically be available inside a class, if one of its parameters matches with that class.

In this idea, when a parameter of a command would not be given a class, the command would be available from *any* object.

In this scheme, giving a parameter a specific class might limit the amount of objects that that command would appear in.

### More Commands but Grouped by Source

This idea might also give an object more commands. In an attempt to keep overview, commands might be grouped together inside an object. Each source/module/library/service might add a separate group of commands inside the object. An interface symbol might set the sources apart. If you would not trust a source, you may opt not to use that command.

### Mutual Control

So the control over the commands is not only with a class, as might be classically the case, but the commands also control which classes they are available in. You might see it as: you can always invent new ways to use an object, to do more than what it was initially intended for.

### General Notation

A command might be executed on an object. This would be the suggested notation.:

![](images/Commands%20and%20Classes%20Loosely%20Coupled.001.png)

An attempt to clarify this notation in steps would now follow.

### Example

The following drawing might be considered:

![](images/Commands%20and%20Classes%20Loosely%20Coupled.002.png)

It aims to show a command definition, which would be the larger dashed square at the bottom. It also attempts to show an object without a class: the circle on the left. It also tries to show a second object: the circle on the right. The object on the right would point to a class using a dashed line, connected to the dashed circle in the top-middle part of the picture. The dashed circle in the top-middle part would be a class.

### Parameter without a Class

When a parameter might be added to the command, and that parameter would not have a class, the following might happen:

![](images/Commands%20and%20Classes%20Loosely%20Coupled.003.png)

The command definition at the bottom would be given a circle inside it. That would represent the new parameter. The parameter would have *no class* yet here, so a square command symbol would appear in *each* object and in the class. The small squares all have lines to the large square at the bottom. That would indicate the smaller squares would be the same command definition as the large one at the bottom. 

(That the middle line is dashed, may have been more of a stylistic choice in an attempt to distinguish static structure from object structure by dashed lines versus solid lines. The lines could have been drawn with a solid line. Another choice could be for more symbols to be drawn with dashed lines, for more (intuitive) separation between static structure and object structure. Dashed shapes might not have an exact definition or meaning yet, so there may be freedom of choice there.)

So command symbols would have appeared in each of the objects and in the class as well. With this idea, a command might quickly become very present in the system, where it might be executed on any object.

### Parameter with a Class

When assigning a class to a parameter, then the command might only be available from objects of that class. This may limit the amount of objects the command would be available in:

![](images/Commands%20and%20Classes%20Loosely%20Coupled.004.png)

The image attempts to show some differences compared to the previous image. The small circle in the large square now has a dashed class line pointing to the dashed class circle at the top. What also seems to have happened, is that this made the object circle on the left not have the command anymore. The circle on the left no longer seems to participate, because it does not have the class associated with the command.

### Line Merge

The connections in the center of the image, might seem a bit crowding. These lines might be merged together:

![](images/Commands%20and%20Classes%20Loosely%20Coupled.005.png) 

This might be less visually demanding. It might also express the tighter bond between the command parameter and the class command. The two two directions.

This notation may be a bit ambiguous, because it suggests, that the two symbols are directly connected together, instead of two connections with an inverse relationship. An arguments to perhaps defend the perceived ambiguity, might be that an object symbol and a command symbol might never be tied together directly like that in any other case. It also seems to express the tightness of the bond. They are not independent connections: change one connection and the other one would change too.

### Summary

So this:

![](images/Commands%20and%20Classes%20Loosely%20Coupled.006.png)

When adding a parameter with a class, might turn into this:

![](images/Commands%20and%20Classes%20Loosely%20Coupled.007.png)

What would be visualized here, might be that the system may have been expanded with a connection between a class and a command, which may also have added the command to objects of that class.

### Commands and Classes Loosely Coupled when Object would Define Its own Class?

The concept of *Classes and Commands Loosely Coupled* may run into trouble when thinking of classless as 'defining its own class'. It would imply, that when a parameter would be assigned a class, command would become available in every object of that class. When a parameter would have no class, it might become a problem when thinking of that as a parameter defining its own class. That might only make the command available to objects, that would point out *that parameter* as their class.

![](images/Commands%20and%20Classes%20Loosely%20Coupled.008.png)

A quite particular situation. But it might be solved by regarding situation as that a parameter without a class, would simply *have* *no* class. That may add the command to *any* object. This make *classless* stands for *arbitrariness* again.

![](images/Commands%20and%20Classes%20Loosely%20Coupled.009.png)