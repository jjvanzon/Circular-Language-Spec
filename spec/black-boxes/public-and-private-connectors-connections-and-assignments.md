Black Boxes | Public & Private Connectors, Connections & Assignments
====================================================================

`[ Preliminary documentation ]`

[back](./)

__Contents__

- [Public & Private Connectors](#public--private-connectors)
    - [Object Connectors](#object-connectors)
    - [Class Connectors](#class-connectors)
    - [Value Connectors](#value-connectors)
    - [Data Connectors](#data-connectors)
    - [Clone Connectors](#clone-connectors)
    - [Existence Connectors](#existence-connectors)
    - [Execute Connectors](#execute-connectors)
    - [Add And Remove Connectors ...](#add-and-remove-connectors-)
    - [Remarks](#remarks)
        - [Object-Bound & Reference Bound Connectors](#object-bound--reference-bound-connectors)
        - [Object Class Connectors](#object-class-connectors)
        - [Class Get and Use As Class Connectors](#class-get-and-use-as-class-connectors)
        - [Value Connectors](#value-connectors-1)
        - [Data Connectors](#data-connectors-1)
        - [Clone Connectors](#clone-connectors-1)
        - [Interface Connectors & Other Connectors](#interface-connectors--other-connectors)
        - [Preliminary System Command Notation](#preliminary-system-command-notation)
- [Public & Private Connections](#public--private-connections)
    - [Object Connections](#object-connections)
    - [Class Connections](#class-connections)
    - [Value Connections](#value-connections)
    - [Clone Connections](#clone-connections)
    - [New & Annul Calls](#new--annul-calls)
    - [Execute Connections](#execute-connections)
    - [< Add And Remove Connections ... >](#-add-and-remove-connections--)
    - [Remarks](#remarks-1)
        - [Friend and Private Connections](#friend-and-private-connections)
        - [Object Set Connections](#object-set-connections)
        - [Class Connections](#class-connections-1)
        - [Value Connections](#value-connections-1)
        - [Data Connections](#data-connections)
        - [Clone Connections](#clone-connections-1)
        - [Existence & Execute Connections](#existence--execute-connections)
- [Public & Private Assignment](#public--private-assignment)
    - [Object Assignment](#object-assignment)
    - [Class Assignment](#class-assignment)
    - [Class Get Connection](#class-get-connection)
    - [Remarks](#remarks-2)
        - [Only Object and Class Assignments](#only-object-and-class-assignments)
        - [Connectors & Assignments](#connectors--assignments)

## Public & Private Connectors

The following articles display the various access connectors an object can have.

### Object Connectors

|                       |                        |                       |
|:---------------------:|:----------------------:|:---------------------:|
| __Public Object Get__ | __Private Object Get__ | __Friend Object Get__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.001.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.002.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.003.png) | 
|                       |                        |                       |
| __Public Object Set__ | __Private Object Set__ | __Friend Object Set__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.004.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.005.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.006.png) |

### Class Connectors

|                                    |                                      |                                     |
|:----------------------------------:|:------------------------------------:|:-----------------------------------:|
|      __Public Use As Class__       |       __Private Use As Class__       |       __Friend Use As Class__       |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.007.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.008.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.009.png) | 
|                                    |                                      |                                     |
|       __Public Class Set__         |        __Private Class Set__         |        __Friend Class Set__         |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.010.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.011.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.012.png) | 
|                                    |                                      |                                     |
| __Public Reference <br>Class Get__ | __Private Reference <br> Class Get__ | __Friend Reference <br> Class Get__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.013.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.014.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.015.png) | 
|                                    |                                      |                                     |
|  __Public Object <br> Class Get__  |  __Private Object <br> Class Get__   |  __Friend Object <br> Class Get__   |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.016.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.017.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.018.png) |

### Value Connectors

|                      |                       |                      |
|:--------------------:|:---------------------:|:--------------------:|
| __Public Value Get__ | __Private Value Get__ | __Friend Value Get__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.019.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.020.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.021.png) |
|                      |                       |                      |
| __Public Value Set__ | __Private Value Set__ | __Friend Value Set__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.022.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.023.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.024.png) |

### Data Connectors

|                     |                      |                     |
|:-------------------:|:--------------------:|:-------------------:|
| __Public Data Get__ | __Private Data Get__ | __Friend Data Get__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.025.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.026.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.027.png) |
|                     |                      |                     |
| __Public Data Set__ | __Private Data Set__ | __Friend Data Set__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.028.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.029.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.030.png) |

### Clone Connectors

|                          |                           |                          |
|:------------------------:|:-------------------------:|:------------------------:|
| __Public Clone (2) Get__ | __Private Clone (2) Get__ | __Friend Clone (2) Get__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.031.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.032.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.033.png) |
|                          |                           |                          |
| __Public Clone (2) Set__ | __Private Clone (2) Set__ | __Friend Clone (2) Set__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.034.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.035.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.036.png) |

### Existence Connectors

|                  |                   |                  |
|:----------------:|:-----------------:|:----------------:|
|  __Public New__  |  __Private New__  |  __Friend New__  |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.037.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.038.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.039.png) |
|                  |                   |                  |
| __Public Annul__ | __Private Annul__ | __Friend Annul__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.040.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.041.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.042.png) |

### Execute Connectors

| __Public Execute__ | __Private Execute__ | __Friend Execute__ |
|:------------------:|:-------------------:|:------------------:|
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.043.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.044.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.045.png) |

### Add And Remove Connectors ...

...

### Remarks

#### Object-Bound & Reference Bound Connectors

> In the overviews, object-bound connectors are displayed with a separate shape without a parent, while reference-bound connectors are displayed with the target inside a parent. 

#### Object Class Connectors

> There is no __Object Class Set__ connector, because the object class can not be freely set; it can only be set on object creation.

#### Class Get and Use As Class Connectors

> For the __Class__ aspect, there is a distinction between __Use As Class__ and __Class Get__. They are different. __Use As Class__ makes you use one symbol as the class for another symbol. That is how classes are most commonly used. That might be the result of an __Object Get__ on the source object, followed by a __Class Set__ on the target object. No __Class Get__ is involved in a __Use As Class__ action, which you might expect if you draw a parallel to the __Object__ aspect.
>
> __Class Get__ gets a reference to the class object of an object. Traditionally this might be considered getting an object’s reflective data. You can use the reference to the class to your own discretion. __Class Get__ is far less common. __Use As Class__ gets a fundamental notation, whereas __Class Get__ has to make dues with the ‘system command’ notation.
>
> This is due to the behavior of the __Class__ aspect. This is different behavior compared to the __Object__ aspect. You just might remember, that each aspect has different behavior, because it has a different purpose.
>
> The funny thing about access controlling __Use As Class__, is that you are actually access controlling the __Object Get__ for specific use in a class assignment.

#### Value Connectors

> Note that for the __Value__ aspect the directions of __Get__ and __Set__ are switched compared to the __Object__ aspect
> 
> | __Object Get__ | __Value Get__ |
> |:--------------:|:-------------:|
> | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.001.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.019.png) |
> 
> This is because for the __Object__ aspect, the access mark indicates the direction of the *resultant line*, while for the __Value__ aspect, the access mark indicates the direction of the *assignment*. You might remember, that each aspect has its own unique behavior.

#### Data Connectors

> You can access control sub-objects, to apply some sort of write-protection to the sub-object. But that might not write-protect the sub-objects of the sub-objects. To collectively write-protect any sub-object, you can access control the object’s __Data__ aspect.
>
> ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.025.png)
>
> A preliminary notation for __Data__ access is a *triple wavy line* (‘triple’ expressing multitude, ‘wavy’ expressing values or data).

#### Clone Connectors

> The __Value__ aspect is about copying the direct value of the object. But you can also copy the values of sub-objects up to a certain cloning depth. The could be any number of levels up to which the values of sub-objects are cloned. The diagrams in the overview show access connectors for cloning at a depth of __2__. That is just an example. Any cloning depth other than two can also be separately access controlled.
> 
> Cloning has the exact same notation as the __Value__ aspect, but then with a number near the access mark, to indicate the cloning depth.
> 
> | __Value Get__ | __Clone (2) Get__ |
> |:-------------:|:-----------------:|
> | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.019.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.032.png) |
> 
> __Clone__ is simply that closely related to the __Value__ aspect.

#### Interface Connectors & Other Connectors

> There are also interface connectors, but *interfaces* as a whole might be caught up with in the *Interfaces* article group. Interface connectors work roughly the same as class connectors. In fact, any other aspect that might be introduced in the future might extend the set of possible connectors.

#### Preliminary System Command Notation

> The access connectors using the system command notation have a preliminary notation. The exact notation system commands might get an update in the future.

## Public & Private Connections

This section covers any kind of connection between objects, that are a *result* of accessing system aspects.

### Object Connections

|                                       |                                       |
|:-------------------------------------:|:-------------------------------------:|
| __Public Object Get <br> Connection__ | __Friend Object Get <br> Connection__ | 
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.046.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.047.png) |
|                                       |                                       |
| __Public Object Set <br> Connection__ | __Friend Object Set <br> Connection__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.048.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.049.png) |

### Class Connections

|                                         |                                         |
|:---------------------------------------:|:---------------------------------------:|
| __Public Use As Class <br> Connection__ | __Friend Use As Class <br> Connection__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.050.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.051.png) |
|                                         |                                         |
|  __Public Class Set <br> Connection__   |  __Friend Class Set <br> Connection__   |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.052.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.053.png) |

### Value Connections

|                                      |                                      |
|:------------------------------------:|:------------------------------------:|
| __Public Value Get <br> Connection__ | __Friend Value Get <br> Connection__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.054.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.055.png) |
|                                      |                                      |
| __Public Value Set <br> Connection__ | __Friend Value Set <br> Connection__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.056.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.057.png) |

### Clone Connections

|                                          |                                          |
|:----------------------------------------:|:----------------------------------------:|
| __Public Clone (2) Get <br> Connection__ | __Friend Clone (2) Get <br> Connection__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.058.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.059.png) |
|                                          |                                          |
| __Public Clone (2) Set <br> Connection__ | __Friend Clone (2) Set <br> Connection__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.060.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.061.png) |

### New & Annul Calls

__New__ and __Annul__ connections are *calls* to the __New__ and __Annul__ system commands.

There are the following possible __New__ and __Annul__ calls:

|                       |                       |
|:---------------------:|:---------------------:|
|  __Public New Call__  |  __Friend New Call__  |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.062.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.063.png) |
|                       |                       |
| __Public Annul Call__ | __Friend Annul Call__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.064.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.065.png) |

But the *result* of accessing __New__ and __Annul__ are the reference’s being __Nothing__ or __Something__, which look as follows:

| __Nothing__ | __Something__ |
|:-----------:|:-------------:|
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.066.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.067.png) |

(As with the __Set__ connections of the __Object__ and __Class__ aspects, actually *accessing* the symbol is history and it might not matter anymore if it was __Public__ of __Friend__ access that caused the result, so you do not need to see it in the diagram of __Nothing__ and __Something__ whether it was established through __Public__ access or __Friend__ access.)

The access *connector* notation of __New__ and __Annul__ were preliminary:

![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.068.png)

And here it becomes apparent why. The following diagrams show __New__ and __Annul__ calls and also the access connectors displayed right in the picture:

![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.069.png)
![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.070.png)

An access connector stands for a potential connection and should look like the potential connection. In the pictures above, the connector might not look like the actual connection, so the notation may need to change in the future. A potential connection is usually expressed as a loose end, so the potential system command call should also be expressed as a loose end somehow, so perhaps the following notation for access controlling a system command might be better:

![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.071.png)

For now the notation of system command connectors is open to discussion.

### Execute Connections

< TO DO: You might address the details in *Using Command Symbols* and the preliminariness of the system command notation might eventually be removed. And then you might display just the actual connections (executable references to the command) that are already visible inside the more complex pictures now shown below. >

Access controlling the __Execute__ system command for command objects may seem like access controlling the ability to call a command. But that is not true. You can access control a command’s __Use As Class__ connector to make a command callable or not. You do not need to access control the __Execute__ system command for that.

The essence of it is, that each system aspect can be separately access controlled. They all get their own access connector. The uses and implications of access controlling the __Execute__ command are less important for now. Access controlling commands is covered later separately.

The __Execute__ access connector was introduced as follows:

![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.045.png)

The result of access controlling the __Execute__ command is that the command can only be executed by __Friends__. The command can not be referenced by a diamond shape (an *execution*) unless it is from a __Friend__ object. Access controlling the __Execute__ aspect *disallows* execution of the command.

So this is allowed (see __Execution__ in the diagram):

![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.072.png)

It is allowed, because of the friend declaration on the left.

When you take away the friend declaration, execution is no longer allowed:

![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.073.png)

But *non-executing* references to the command *are* allowed:

![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.074.png)

The notation for access controlling system commands is not final yet. But because an access connector should be a depiction of a potential connection, the access connector for the __Execute__ aspect might eventually might look as follows:

![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.075.png)

With not even the word ‘execute’ in it anymore.

### < Add And Remove Connections ... >

...

### Remarks

#### Friend and Private Connections

> Because there is not distinction between a __Friend__ connection and a __Private__ *connection*, __Friend__ connections:
> 
> ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.047.png)
> 
> are called __Private__ connections as well.

#### Object Set Connections

> The __Public__ and __Friend Object Set__ connections look the same.
> 
> | __Public Object Set <br> Connection__ | __Friend Object Set <br> Connection__ |
> |:-------------------------------------:|:-------------------------------------:|
> | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.048.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.049.png) |
> 
> __Public__ and __Friend__ might not matter for outward connections. __Public__ or __Friend__ access only mattered when *establishing* the outward connection. Outward connections are passive connections: direct connections to the target object. *Inward* connections, though, cause a __Get__ command on each consult of the source symbol, so in that case an actual *access* takes place, and the distinction between __Friend__ or __Public__ access might matter.

#### Class Connections

> __Use As Class__ and __Class Set__ are covered here. __Class Get__ is not covered here, because that is only used in an assignment, and > assignments are addressed in other section: *Assignment of System Aspects*. 

#### Value Connections

> Note that the indication of *direction* for __Get__ and __Set__ is switched for the __Value__ aspect, compared to the __Object__ aspect: __Object Get__ is inward, while __Value Get__ is *outward*.
> 
> __Value__ connections are shown here in the section *Connections to System Aspects*, and not in the section *Assignment of System Aspects*, but Value connections are assignments, but they do not have an ‘assignment notation’.
> 
> What you can also notice is that outward __Value__ connections do have access marks, while outward connections for the __Object__ and __Class__ aspects do *not* show access marks. This is because *outward* __Object__ and __Class__ connections are passive connections and outward __Value__ connections are *active* connections, because an __Value__ connection always requires an active assignment.

#### Data Connections

> A __Data__ connector such as the following:
> 
> __Public Data Get__
> 
> ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.076.png)
> 
> is an abstract connector: it represents any possible __Get__ connection to a sub-sub-object.
> 
> Even though there is a __Data__ *connector*, there are no __Data__ *connections*. Any __Get__ connection to a sub-object is be considered a __Data Get__ connection.

#### Clone Connections

> The diagrams above show access connections for cloning at a depth of __2__. That is just an example. Any cloning depth other than __2__ could be used.
> 
> Cloning has the exact same notation as the __Value__ aspect, but then with a number near the access mark. Cloning is that closely related to the __Value__ concept.

#### Existence & Execute Connections

> The remaining aspects are __Existence__ and __Execute__.
> 
> The essence of it is, that all system commands are separately access controlled. They all get their own access connector. The uses and implications are less important.
> 
> This part of the documentation displays connections that are a result of accessing system aspects. But for the __Value__ aspect that means the display of an assignment.  
And for __Existence__ and __Execute__ that also means something different.
> 
> Here you see again, that all system aspects behave totally differently.

## Public & Private Assignment

This section demonstrates how accessing system aspects looks in assignment notations.

### Object Assignment

|                                          |                                          |
|:----------------------------------------:|:----------------------------------------:|
| __Public Object Get <br> in Assignment__ | __Friend Object Get <br> in Assignment__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.077.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.078.png) |
|                                          |                                          |
| __Public Object Set <br> in Assignment__ | __Friend Object Set <br> in Assignment__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.079.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.080.png) |

### Class Assignment

|                                            |                                            |
|:------------------------------------------:|:------------------------------------------:|
| __Public Use As Class <br> in Assignment__ | __Friend Use As Class <br> in Assignment__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.081.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.082.png) |
|                                            |                                            |
|  __Public Class Set <br> in Assignment__   |   __Friend Class Se <br> in Assignment__   |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.083.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.084.png) |

### Class Get Connection

At first glance you might guess, that __Class Get__ in assignment looks something like this:

![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.085.png)

But that is __Use As Class__. The smaller circle on the left becomes the class of the circle on the right, requiring an __Object Get__, followed by a __Class Set__. __Class Get__ is far less common: it retrieves a reference to the class of an object, and then you can assign the class to another object.

Using __Class Get__ always requires the system command notation, because the more fundamental notation above is used by __Use As Class__.

The system command notation is not yet final, though. The __Class Get__ access connector may look something like this:

![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.013.png)

Yielding over the class from one object to another may look something like this:

![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.086.png)

Even though the eventual notation might not look like assignment, it still involves an assignment to the object on the right, whose aspect is changed.

Yielding over __Class__ aspect:

|                                                |                                                |
|:----------------------------------------------:|:----------------------------------------------:|
| __Public Reference Class Get <br> Connection__ | __Friend Reference Class Get <br> Connection__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.086.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.087.png) |
|                                                |                                                |
|  __Public Object Class Get <br> Connection__   |  __Friend Object Class Get <br> Connection__   |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.088.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.089.png) |

An alternative: assigning __Class__ object to __Object__ aspect of other symbol:

< Change notation. >

|                                                |                                                |
|:----------------------------------------------:|:----------------------------------------------:|
| __Public Reference Class Get <br> Connection__ | __Friend Reference Class Get <br> Connection__ |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.090.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.091.png) |
|              *(source is inward)*              |              *(source is inward)*              |
|                                                |                                                |
|  __Public Object Class Get <br> Connection__   |  __Friend Object Class Get <br> Connection__   |
| ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.092.png) | ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.093.png) |
|             *(source is outward)*              |             *(source is outward)*              |

### Remarks

#### Only Object and Class Assignments

> Only __Object__ and __Class__ assignments are covered here.  
> __Value__ and __Clone__ assignments were covered in *__Connections__ to System Aspects*.  
> The __Execute__ aspect might not involve assignment.  
> The __Data__ aspect might not work with assignment either.  
> The __Existence__ aspect may involve assignment but that is not covered here.  
> So it comes down to __Object__ and __Class__ assignments.

#### Connectors & Assignments

> The following diagram shows __Object Set__ in an assignment, and the __Object Set__ access connector:
> 
> ![](images/2.%20Public%20&%20Private%20Connectors,%20Connections%20&%20Assignments.094.png)
> 
> The access mark in the assignment and the access mark in the connector have opposite directions.
> 
> This is because for the assignment notation it was decided, that an the access mark expresses the direction of the assignment, and the connector expresses the direction of the *potential connection*, so the direction of the result. It was decided, that it might be clearer to express the direction of the *assignment* inside the diagram notation, instead of letting the assignment call express the direction of its *result*.