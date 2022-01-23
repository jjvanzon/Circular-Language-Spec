Parameters | Imported Parameter Concepts
========================================

`[ Preliminary documentation ]`

[back](./)

__Contents__

- [Introduction](#introduction)
- [Required & Optional](#required--optional)
    - [Concept](#concept)
    - [Required & Optional in a Diagram](#required--optional-in-a-diagram)
    - [Ideas about Required and Optional](#ideas-about-required-and-optional)
- [Variable Amount of Arguments](#variable-amount-of-arguments)
    - [Concept](#concept-1)
    - [Variable amount of Parameters in a Diagram](#variable-amount-of-parameters-in-a-diagram)
    - [Ideas about Variable Amount of Parameters](#ideas-about-variable-amount-of-parameters)
- [Return Values](#return-values)
    - [Concept](#concept-2)
    - [Diagram](#diagram)
    - [Return Values Idea](#return-values-idea)
- [Parameter Order](#parameter-order)
    - [Concept](#concept-3)
    - [Diagram](#diagram-1)

## Introduction

The following articles might explain some concepts from other programming languages and the how they are implemented in Circular.

- *Required & Optional*
- *Variable Amount of Arguments*
- *Return Values*
- *Parameter Order*

## Required & Optional

### Concept

Some programming languages have a thing called required and optional parameters. In other programming languages basically all parameters are required, unless they are typed optional. In Circular it is the other way around: any parameter is optional unless it is typed required. This is because in Circular commands are the same as objects, that just happen to be executable, and the parameters inside a command are analogous to sub-objects inside another object, whose filling-in is also totally arbitrary.

Some parameters can be made required, so you *might* fill them in as input. In Circular, this means that reading and writing any accessible aspect of a parameter can be separately made required or optional. When output is required, it means you might use the output. You might be unable to execute the command without picking up the return value or returned object.

Basically each system command can be made required or optional. Usually you make access from the *outside* required. When you make access from the *inside* required, this can give the user of the command guarantees about the parameter’s usage.

### Required & Optional in a Diagram

*Optional* is the default behavior. *Required* is an extra rule imposed. Required is expressed by drawing half a shape at the end of a connector. It should be half of what has to be connected to it. Most of the times it might be half a circle:

![](images/2.%20Imported%20Parameter%20Concepts.001.png)

For command objects it is half a square:

![](images/2.%20Imported%20Parameter%20Concepts.002.png)

And when a command needs to be executed it is about 5/8th of a diamond:

![](images/2.%20Imported%20Parameter%20Concepts.003.png)

It is not half a diamond because that already symbolizes the Protected access modifier, which is half a cross:

![](images/2.%20Imported%20Parameter%20Concepts.004.png)

For system commands that require the command call connector notation, also the 5/8th of a diamond is shown when a call is required:

![](images/2.%20Imported%20Parameter%20Concepts.005.png)

The ‘half a shape’ might also get a line type adapted to the role the required object might get. If the connector specifies that it gets a class role, the half-shape might be drawn with a dashed line.

![](images/2.%20Imported%20Parameter%20Concepts.006.png)

Below you might find examples of *required* connectors. Not every possible connector is shown, but enough to cover the notation.

| ![](images/2.%20Imported%20Parameter%20Concepts.007.png) | ![](images/2.%20Imported%20Parameter%20Concepts.008.png) | ![](images/2.%20Imported%20Parameter%20Concepts.009.png) |
|:------------------:|:------------------:|:-----------------:|
|  __Public Required <br> Object Set__   | __Protected Required <br> Object Set__ |  __Public Required <br> Object Get__  |
|                                        |                                        |                                       |
| ![](images/2.%20Imported%20Parameter%20Concepts.010.png) | ![](images/2.%20Imported%20Parameter%20Concepts.011.png) | ![](images/2.%20Imported%20Parameter%20Concepts.012.png) | 
|  __Private Required <br> Object Set__  |  __Friend Required <br> Object Set__   | __Private Required <br> Object Get__  |
|                                        |                                        |                                       |
| ![](images/2.%20Imported%20Parameter%20Concepts.013.png) | ![](images/2.%20Imported%20Parameter%20Concepts.014.png) | ![](images/2.%20Imported%20Parameter%20Concepts.015.png) |
| __Protected Required <br> Object Get__ |  __Friend Required <br> Object Get__   |  __Public Required <br> Class Set__   |
|                                        |                                        |                                       |
| ![](images/2.%20Imported%20Parameter%20Concepts.016.png) | ![](images/2.%20Imported%20Parameter%20Concepts.017.png) | ![](images/2.%20Imported%20Parameter%20Concepts.018.png) |
| __Public Required <br> Use As Class__  |  __Private Required <br> Class Set__   |  __Friend Required <br> Value Set__   |
|                                        |                                        |                                       |
| ![](images/2.%20Imported%20Parameter%20Concepts.019.png) | ![](images/2.%20Imported%20Parameter%20Concepts.005.png) | ![](images/2.%20Imported%20Parameter%20Concepts.020.png) |
| __Public Required <br> Clone (2) Get__ |      __Public Required <br> New__      | *(as opposed to)* <br> __Public New__ |
|                                        |                                        |                                       |
| ![](images/2.%20Imported%20Parameter%20Concepts.021.png) | ![](images/2.%20Imported%20Parameter%20Concepts.022.png) | ![](images/2.%20Imported%20Parameter%20Concepts.023.png) |
|    __Friend Required <br> Execute__    |  __Public Required <br> Object Get__   | __Public Required <br> Use As Class__ |
|                                        |                                        |                                       |
| ![](images/2.%20Imported%20Parameter%20Concepts.024.png) |                      |                                       | 
| __Public Required <br> Use As Class__  |                                        |                                       |
| (might be a better notation,<br>since it is more likely to be <br>used for plain command calls) | | |

### Ideas about Required and Optional

(Out of the original Symbol documentation)

Just as in commands, you could make certain members of a type required, while others are optional. You might fill in the required members on creation of the object. This should be there for the same reason as required parameters are there in a command: the function of the object just doesn’t make sense unless you write the required members. The programmer is made extra aware of that by making the members required.

-----

Required and Optional Parameters,

As a command is like a type it may seem that you have full freedom regarding which objects you write and which you don’t. However, many parameters of commands are *required* parameters. This means that you *might* write something to it before the call. Optional parameters are ones that do not necessarily need to be written before the call. Required parameters are there to on one hand ensure a parameter holds a right value. That however, could have been done by the command’s initializing the value itself. The main point of required parameters is that a lot of times the function of a command just doesn’t make sense unless you write the parameters. The programmer is made extra aware of that by making the parameter required.

In diagram code, optional parameters are denoted by displaying the word __Optional__ near the optional parameter. The other parameters are required.

## Variable Amount of Arguments

### Concept

Other programming languages have a concept called variable amount of arguments. This means, that a command’s parameter list might not have a fixed amount of parameters. The last parameters can be any amount of parameters. This is specified as the last parameter’s being an *array* of parameters.

In Circular, any parameter can be an array. In other programming languages, parameters could also be arrays, but for the array, that represented the variable amount of arguments, each item of the array was separately listed out at the end of the command call, as opposed to other parameters, that were arrays, which were just references to arrays, that were initialized elsewhere, not inside the command call.

In Circular, for backwards compatibility purposes, and textual representation purposes, a parameter may be typed as the array that might represent the variable amount of arguments. In other programming languages, variable amount of arguments was also just for textual representation.

Perhaps in the future, it can be applied, that multiple array parameters are considered the variable amount of arguments. But how the notation might be kept unambiguous then is not clear yet.

Important to remember, is that parameters are not always single items, but a parameter can also be an array.

### Variable amount of Parameters in a Diagram

The array parameter, that represents the variable amount of arguments, might not have a special display in the diagram (yet). What is important to remember about the concept of variable amount of arguments is that: parameters can be arrays.

![](images/2.%20Imported%20Parameter%20Concepts.025.png)

### Ideas about Variable Amount of Parameters

(Out of the original Symbol documentation)

In text code, parameter assignments before a call are notated something like this:

    Command A ( 0 , 4 )

Command A is the command name, the two numbers between brackets are the two arguments. Text code is covered in detail lateron.

The parameters of a command are listed in a fixed order. Even the optional parameters have a place in this fixed list and when you don’t want to fill it in you might leave the position open:

    Command A ( 0 , 4 ,  , 1 )

After the fixed parameter list, a command can allow a variable amount of parameters to follow. This variable amount of parameters is stored in a single special parameter. This parameter is of type Array, a type defined in the Sigma Data module. To support variable amount of arguments, the command might have a public Array object that is assigned to be this special parameter.

    Command A ( 0 , 4 ,  , 1 , 3 , 7 , __…__ )

Variable amount of arguments is a purely textual notation. The diagram notation shows working with the Array object. However, an Array parameter needs to be tagged and in the diagram code this is simply shown by displaying the words ‘Arguments’ with the Array object.

## Return Values

### Concept

Other programming language used to have only *one* return value. Circular can have *any* amount of output values or output objects, and no single parameter is selected to be *the* return value. I guess the concept of one return value dates from when a command was meant to be like a mathematical formula. I do not think, that limiting the amount of return values of a command to one, has a place in a more modern programming language anymore, because we might realize, that programming is not mathematics.

### Diagram

As discussed in the article *Return Values*, Circular might not limit the amount of output objects. Any object readable from the outside, may be an output object.

![](images/2.%20Imported%20Parameter%20Concepts.026.png)

The correct usage of the term output might be discussed only later, in the *Advanced Command Topics*.

### Return Values Idea

![](images/7.%20Commands%20Ideas.062.jpeg)

The above might be a valid notation. It might denote the object being a pointer to the *return value* of the command. It may be an *implicit* notation, that might  standard for something else:

![](images/7.%20Commands%20Ideas.063.jpeg)

## Parameter Order

### Concept

Other programming languages were textual. The parameters were put in a certain order. In Circular parameters are more free in order, just like sub-objects inside another object usually have no particular order. The parameters are not really a list of objects anymore. A command call is an object, that has a set of object references in it, that are individually set, and do not have a particular order.

Even though all parameters can be individually accessed by pointing to its symbol or by using its name, you *can* still give the parameters an order of display. The articles, that follow, might elaborate on the diagrammatic and textual expression of parameter order.

### Diagram

The article *Parameter Order* introduced the concept of an ordered list of parameters. The diagramatic display of parameter order is still not final.

In a diagram the order of the parameters could be expressed just like the order of consecutive commands are ordered by next-command references. See *Execution Flow, Normal Execution Order*. This display is yielded over to ordering objects, and ordering parameters as well.

![](images/2.%20Imported%20Parameter%20Concepts.027.png)

Perhaps the first item might also be denoted like this:

![](images/2.%20Imported%20Parameter%20Concepts.028.png)

The eventual display is all up to the implementation of *Sequence Order*. That might determine the ways sorted objects are displayed. The ideas introduced here are preliminary. Eventually parameter order might comply to sequence order.

The objects may also be displayed clockwise:

![](images/2.%20Imported%20Parameter%20Concepts.029.png)

And possibly, when there are a lot of items in the collection, you may need scroll through them, because they can’t all be individually displayed:

![](images/2.%20Imported%20Parameter%20Concepts.030.png)
