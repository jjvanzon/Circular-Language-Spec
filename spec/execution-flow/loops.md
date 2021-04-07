Encircle Language Spec | Execution Flow
=======================================

Loops
-----

`[ Preliminary documentation ]`

### Contents

- [Concept](#concept)
- [In a Diagram](#in-a-diagram)
- [For](#for)
    - [Concept](#concept-1)
    - [Diagram](#diagram)
- [For (range)](#for-range)
    - [Concept](#concept-2)
    - [Diagram](#diagram-1)
- [For (conditional)](#for-conditional)
    - [Concept](#concept-3)
    - [Diagram](#diagram-2)
- [For Each](#for-each)
    - [Concept](#concept-4)
    - [Diagram](#diagram-3)
- [While](#while)
    - [Concept](#concept-5)
    - [Diagram](#diagram-4)
- [Until](#until)
    - [Concept](#concept-6)
    - [Diagram](#diagram-5)

### Concept

A loop is a form of control over *execution flow*. Execution flow is explained in the article *Execution Flow*.

Loops, or repetition, are a main form of execution flow, where the same code is repeated a number of times. The __For__ loop is the most common form of repetition. On each repetition, data is changed, which gives the next repetition a different order of execution or makes it operate on different data.

A loop can go through a range of values, in case of which it is called a *range* loop. A loop can also stop repeating when a certain condition is met. In that case it is called a *conditional* loop.

The following forms of repetition are supported:

- __For__ (range)
- __For__ (conditional)
- __For Each__
- __While__
- __Until__

Each form is explained in a separate article.

### In a Diagram

Loops are a form of execution flow explained in the article *Loops*. The articles that follow only explain their expression in a diagram.

There are four forms of repetition:

- __For__ (range)
- __For__ (conditional)
- __For Each__
- __While__

Each form is explained in a separate article. See the articles *For (range) in a Diagram*, *For (conditional) in a Diagram* and *For Each in a Diagram* and While in a Diagram.

### For

#### Concept

The __For__ statement is a form of repetition. Repetition, more commonly known as *loops*, is a kind of execution flow statement, explained by the article *Loops*.

In a __For__ statement usually a range of values is gone through. The same code is executed for each of the values.

There are three kinds of __For__ loop:

- __For__ (range)
    - goes through a contiguous range of values
- __For__ (conditional)
    - originally intended for going through a contiguous range of values, but more flexible than that.
- __For Each__
    - goes through the items of a collection

The three forms will be explained in separate articles.

#### Diagram

Each type of __For__ loop has a slight variation in diagram notation. There are three definitions of __For__ commands. They will be covered in the articles *For (range) in a Diagram*, *For (conditional) in a Diagram* and *For Each in a Diagram*.

### For (range)

#### Concept

There are three forms of __For__ loop, as mentioned in the article *For*. This article explains the form of __For__ loop where a contiguous range of values is gone through.

A contiguous range of values, usually numbers, starts at one value and ends at another value. On every loop, the value is increased by one or by a step smaller or larger than that. You can also go through for instance floating point numbers or dates.

The __For__ command takes an initial value (__From__) as an argument, a last value (__Till__) and optionally the __Step__ to take on loop. The step is __1__ by default, but can also be a smaller step, like __0.5__ or a larger step, like __2__. The step can also be a negative, like __-1__, going through numbers in a reversed order.

The __For__ command will also hold a read only parameter __Variable__, which is the current value of the numbers gone through.

The most important parameter, though, is a command reference to the actual command to loop. This is the __Loop__ parameter, which is a command reference.

There is also a local object, called the __Variable__. The variable will hold the current value of the loop. The __Variable__ will be passed to the __Loop__ procedure as a parameter.

The implementation of this kind of __For__ command uses machine instructions to increment the __Variable__ and a conditional jump command to jump back to start another loop and call and return instructions to call the command to loop (or whatever other appropriate instructions forgotten about).

#### Diagram

Below is an example of the diagrammatic expression of a __For__ statement, that goes through a contiguous range of numbers.

![](images/3.%20Loops.001.png)

The diamond is a call to the __For__ command. The __For__ loop will go through a range of numbers. The first of the range of numbers is passed to the __For__ command as the __From__ parameter, which is visible inside the diamond as the circle named __From__. In the example above, the literal value of __0__ is filled into the __From__ parameter. This will be the first value of the range. The last value in the range is passed to the __For__ command as the __Till__ parameter. In the example above, the __Till__ parameter is visible inside the diamond as the circle named __Till__. The __Till__ parameter is a pointer to something defined outside the call to the __For__ command. The __Till__ parameter is pointing to a variable defined outside the call, displayed in the diagram above outside of the diamond, as the circle named __For End__. The __For__ loop will go through the values __0__ till the value indicated by the variable __For End__. The __For__ loop will increment the current value by __1__ on each loop, because the __Step__ argument of the __For__ command is set to the literal value of __1__, visible inside the diamond as the circle named __Step__. The diamond contains another circle, named __Variable__, which will hold the current value of the range. This current value is passed to the __Loop__, that will be run multiple times. The __Loop__ procedure is displayed inside the diamond, as the square named __Loop__. The the __Loop__ procedure is *defined* outside the diamond. The __Loop__ parameter, visible as a square named __Loop__ inside the diamond, points out of the diamond to the larger square just below the diamond, with the ellipsis in it. The ellipsis stands for whatever you fill into it. The larger square below the diamond defines the command that will run multiple times, once for each value in the range. The circle inside the large square is the __Variable__ passed to the __Loop__ procedure. That circle is not tied to the __Variable__ parameter inside the __For__ call, but it is implicitly connected to it, because of the connection between the squares that contain the circles, and the name __Variable__ repeated for each of the circles. (This is due to the rule of *implicit connection through parent.* See the article *Automatic Containment*.)

The __Loop__ parameter is placed inside a nonagon purely for esthetic reasons. It is a single reference to a command, and the nonagon will never contain multiple references to commands, but it is obvious the command in it will be run multiple times. The nonagon stands for multiple, so it is put around the __Loop__ parameter, but it will always contain a single item and you cannot add any more items to it.

In the example above, two of the circles got literal values filled in. One of the circles is tied to something defined outside the diamond. But any of the three __From__, __Till__ and __Step__ parameters could have had a literal value filled in or could have been pointing to something outside the diamond. The diagram above is just an example. The __Loop__ procedure reference in our example, pointed out of the diamond as well. The loop procedure may as well have been defined right inside the diamond. The __Variable__ of the loop can’t be given a literal value or be set to point to something outside the diamond, because the __Variable__ of the loop is controlled by the __For__ command definition, and can only read.

The *definition* of the __For__ execution flow command is part of a system module for execution flow commands. The public elements of the definition look like this:

![](images/3.%20Loops.002.png)

Nothing is filled in yet as the __From__ , __Till__ , __Step__ or __Loop__. The __Variable__ will be controlled by the __For__ command. It is referenced from the __Loop__ procedure.

### For (conditional)

#### Concept

There are three forms of __For__ loop, as mentioned in the article *For*.  
This article explains the form of __For__ loop originally intended for going through a range of values, but more flexible than that. Unlike the *range* For this kind of __For__ is a *conditional* loop.

The initial value of the range is replaced by an initialization procedure, which could do anything, but usually it assigns an initial value to a loop variable.
The last value of the range is replaced by a condition, which   could be any condition, but usually it is the condition of the loop variable staying below or equal to the last value of the range.  
The step to take going through the range of numbers is replaced by an action, which can be *any command*, but it usually is a procedure, that increments the loop variable with __1__.

The __For__ command takes a command reference to the __Initialization__ procedure, which is called once, at the beginning of the loop. It also takes a command reference to the __Action__, which is a command called at the end of each repetition of the loop. The __For__ command also takes a reference to another command, which is called the __Loop__ command reference, which is the actual loop to repeat. The __For__ command also takes a __Boolean Condition__, that has to stay __True__ for the loop to keep repeating. 

The __Condition__ is usually passed to the __For__ command as a reference to a reference to a __Boolean__. It needs to be a reference to a reference, because the condition needs to be recalculated every time it is consulted. Why making it a reference to a reference solves that problem is explained in the second last paragraph of the article *Execution Flow*, part of which I repeat here:

In a conditional *loop*, the condition must be re-evaluated on every repetition of the loop. Recalculation of the condition, every time the condition is consulted, can be established by making the condition a reference to a reference to a __Boolean__, rather than a reference to a specific __Boolean__ object.  
So the condition argument refers to a *reference*.  
The reference, that is referred to, can perform a calculation before it returns the __Boolean__. It performs the calculation every time the reference is consulted. How a reference can recalculate the value of an object whenever it is retrieved, is explained by the article *System Interface*.

The implementation of this kind of __For__ command uses a machine instruction to jump back in code to call the __Loop__ again. For the rest it just calls the __Loop__ and the __Action__ command references and evaluates the __Condition__ to determine whether to run the loop again.

#### Diagram

Below is an example of the diagrammatic expression of a conditional __For__ statement.

![](images/3.%20Loops.003.png)

The diamond is a call to the __For__ command. The __For__ command will first call the __Initialization__ procedure reference, displayed inside the diamond as a square called __Initialization__. The __For__ command will then evaluate the __Condition__, displayed in the diamond as a circle named __Condition__. The __Condition__ is a __Boolean__. When the __Condition__ evaluates to __True__, the procedure reference __Loop__ will be called, which is displayed inside the diamond as the square named __Loop__, but this square is tied to a bigger square outside the diamond, delegating the definition of the loop to outside the diamond. After execution of a loop, the __Action__ is executed, which is visible in the diamond as a square named __Action__. The __Action__ usually increments a loop variable. The loop variable is not defined in the statement. It has to be defined somewhere outside the statement. Then the __Condition__ is evaluated again. If it is __True__, then the __Loop__ procedure reference is called again. After that the __Action__ is executed again, and the __Condition__ is evaluated again and if it is __True__, the __Loop__ procedure reference is called again. This happens over and over again, until the __Condition__ will evaluate to __False__. Then the loop will stop repeating.

The __Loop__ parameter is placed inside a nonagon purely for esthetic reasons. It is a single reference to a command, and the nonagon will never contain multiple references to commands, but it is obvious the command in it will be run multiple times. The nonagon stands for multiple, so it is put around the __Loop__ parameter, but it will always contain a single item and you cannot add any more items to it.

In the example above, the __Loop__ procedure reference was pointing to something outside the diamond, and the other command references were not. The other command references may as well have pointed to a command definition outside of the diamond and the __Loop__ procedure may have been defined right inside the diamond all the same. The diagram above is just an example. The __Condition__ could also have pointed to something outside the diamond.

The *definition* of the __For__ execution flow command is part of a system module for execution flow commands. The public elements of the definition look like this:

![](images/3.%20Loops.004.png)

Nothing is filled in yet as the __Initialization__ , __Action__ , __Condition__ or __Loop__ .

### For Each

#### Concept

There are three forms of __For__ loop, as mentioned in the article *For*. This article explains the __For Each__ loop, which goes through the items of a collection. the __For Each__ statement is considered a *range* loop (see *Loops*).

The collection is passed as an argument to the __For__ command. The __For__ command will also be passed a command reference that will be called once for every item in the collection. The command reference parameter is called __Loop__. The current item of the collection is stored as the __Item__ parameter, that is read only, and controlled by the __For__ command. The __Item__ parameter is passed to the __Loop__ procedure, each time it is called.

The implementation of the __For Each__ loop does not only use plain machine instructions, because it it will be accessing a collection with a more object oriented approach. The looping itself can be controlled with machine instructions, though jumping back to the same call to the __Loop__ procedure for each of the items of the collection.

#### Diagram

Below is an example of the diagrammatic expression of a __For Each__ statement.

![](images/3.%20Loops.005.png)

The diamond is a call to the __For Each__ command. There is a nonagon called __In__ visible inside the diamond. The __In__ parameter can point to any collection to loop through.

The diamond contains a circle, named __Item__, which will hold the current item of the collection. The current item is passed to the __Loop__ procedure, that will be run multiple times. The __Loop__ procedure is displayed inside the diamond, as a square named __Loop__. The __Loop__ procedure is *defined* outside the diamond. The __Loop__ parameter inside the diamond, points out of the diamond to the larger square just below the diamond, with the ellipsis in it. The ellipsis stands for whatever you fill into it. The larger square below the diamond defines the command that will run multiple times, once for each item in the collection. The circle inside the large square is the __Item__ passed to the __Loop__ procedure. That circle is not tied to the __Item__ parameter inside the __For__ call, but it is implicitly connected to it, because of the connection between the squares that contain the circles.  
(This is due to the rule of *implicit connection through parent.* See the article *Automatic Containment*.) Officially, the two smaller circles explicitly have to be named __Item__ as well, to not confuse the circles with any other possible circles, that might be defined in the __Loop__.

In other loops, the __Loop__ parameter was surrounded by an esthetic nonagon, but because the __In__ parameter is already a nonagon, it is already obvious, that the command handles a collection, so a nonagon is not also placed around the __Loop__ parameter.

In the example above, the __In__ collection and the __Loop__ procedure reference were defined outside the diamond. They may as well have been defined right inside the diamond. The diagram above is just an example

The *definition* of the __For Each__ execution flow command is part of a system module for execution flow commands. The public elements of the definition look like this:

![](images/3.%20Loops.006.png)

Nothing is filled in yet as the __In__ collection or the __Loop__ procedure reference. The __Item__ parameter will be controlled by the __For__ command. It is referenced from the __Loop__ procedure.

### While

#### Concept

The __While__ loop is a form of execution flow. Loops are briefly explained in the article *Loops*. This article explains the While loop.

The __While__ loop keeps repeating the same code as long as a __Condition__ is __True__.

The __Condition__ is usually passed to the __While__ command as a reference to a reference to a __Boolean__. It needs to be a reference to a reference, because the condition needs to be recalculated every time it is consulted. Why making it a reference to a reference solves that problem is explained in the second last paragraph of the article *Execution Flow*, part of which I repeat here:

In a conditional *loop*, the condition must be re-evaluated on every repetition of the loop. Recalculation of the condition, every time the condition is consulted, can be established by making the condition a reference to a reference to a __Boolean__, rather than a reference to a specific __Boolean__ object.  
So the condition argument refers to a *reference*.  
The reference, that is referred to, can perform a calculation before it returns the __Boolean__. It performs the calculation every time the reference is consulted. How a reference can recalculate the value of an object whenever it is retrieved, is explained by the article *System Interface*.

It needs to be said, that you are not obliged to pass a reference to a reference to a __Boolean__. It’s just that, in order to have a formula be reevaluated on every consult of the __Boolean__ it must be a reference to a reference. The __Boolean__ can also be just a reference to a __Boolean__. Then the __Boolean__ has to change by some external force. You can also make it a fixed __Boolean__ value, but then the loop will either not start at all or not end unless you explicitly call __Exit Loop__, based on some other condition (see *Exit Loop*).

Next to the __Condition__, the __While__ loop is passed a reference to a command as a parameter. The parameter is called __Loop__. This command is called repeatedly as long as the __Condition__ returns __True__. 

The implementation of the __While__ loop incorporates an object oriented call to the reference to the reference to the __Boolean Condition__, and a call to a machine instruction to jump back to the call to the __Loop__ procedure when the __Condition__ returns __True__.

#### Diagram

Below is an example of the diagrammatic expression of a __While__ loop.

![](images/3.%20Loops.007.png)

The diamond is a call to the __While__ command. There is a circle inside the diamond, that represents the __Boolean Condition__. The name __Condition__ is not shown with the circle, because it is the only circle there and it looks so obvious that it is the condition. The circle inside the diamond points to another circle outside the diamond, indicating that the __Boolean__ is defined outside the call to the __While__ statement. The diamond also contains a square called __Loop__, which is the reference to a command, that will be run as long as the condition is __True__. The __Loop__ procedure reference points out of the diamond to a command defined outside the call to the __While__ statement.

The __Loop__ parameter is placed inside a nonagon purely for esthetic reasons. It is a single reference to a command, and the nonagon will never contain multiple references to commands, but it is obvious the command in it will be run multiple times. The nonagon stands for multiple, so it is put around the __Loop__ parameter, but it will always contain a single item and you cannot add any more items to it.

In the example above, the __Condition__ and the __Loop__ procedure reference were defined outside the diamond. They may as well have been defined right inside the diamond. The diagram above is just an example.

The *definition* of the __While__ execution flow command is part of a system module for execution flow commands. The public elements of the definition look like this:

![](images/3.%20Loops.008.png)

Nothing is filled in yet as the __Condition__ or the __Loop__ procedure reference.

### Until

#### Concept

The __Until__ loop is closely related to the __While__ loop. It works exactly the same as the __While__ loop, except that the while loop keeps repeating the same code as long as a condition equals __True__, and an __Until__ loop keeps repeating the same code as long as a condition equals __False__. As soon as the condition becomes __True__ the loop will stop.

For the rest of the inner workings of the __Until__ loop, refer to the article __While__.

#### Diagram

Below is an example of the diagrammatic expression of a __Until__ loop.

![](images/3.%20Loops.009.png)

The diamond is a call to the __Until__ command. There is a circle inside the diamond, that represents the __Boolean Condition__. The name __Condition__ is not shown with the circle, because it is the only circle there and it looks so obvious that it is the condition. The circle inside the diamond points to another circle outside the diamond, indicating that the __Boolean__ is defined outside the call to the __Until__ statement. The diamond also contains a square called __Loop__, which is a reference to the command, that will be run as long as the condition is __False__. The __Loop__ command reference points out of the diamond to a command defined outside the call to the __While__ statement.

The __Loop__ parameter is placed inside a nonagon purely for esthetic reasons. It is a single reference to a command, and the nonagon will never contain multiple references to commands, but it is obvious the command in it will be run multiple times. The nonagon stands for multiple, so it is put around the __Loop__ parameter, but it will always contain a single item and you cannot add any more items to it.

In the example above, the __Condition__ and the __Loop__ procedure reference were defined outside the diamond. They may as well have been defined right inside the diamond. The diagram above is just an example.

The *definition* of the __Until__ execution flow command is part of a system module for execution flow commands. The public elements of the definition look like this:

![](images/3.%20Loops.010.png)

Nothing is filled in yet as the __Condition__ or the __Loop__ procedure reference.

