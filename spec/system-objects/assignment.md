Encircle Language Spec | System Objects
=====================================

Assignment
----------

Calls to system commands (like __Get Object__, __Set Value__ or __Use As Class__) might not be commonly seen. They might be more likely to be called indirectly. An assignment command might indirectly carry out a __Get__ on one object and a __Set__ on another object, trying to yield over something from one symbol to another.

### Distinguishing Object-Bound and Reference-Bound Aspects

To demonstrate the difference between object-bound aspects and reference-bound aspects this article tries to employ the following notation. When a reference-bound aspect might be __Get__ or __Set__ then a reference might be displayed with a parent around it:

![](images/2.%20Assignment.001.png)

When an object-bound aspect might be __Get__ or __Set__ then a targeted object may be displayed without a parent around it:

![](images/2.%20Assignment.002.png)

### Basic Assignment Types

Different system aspects (such as a value, object or class) might correspond with different types of assignment. Below an attempt to list some of the more common types of assignment.

The overview also tries to illustrate, which __Get__, __Set__ and __Use__ commands might be called while performing the assignment.

Because assignments might occur commonly, an implicit, simplified notation is suggested here.

|                                                                       |
|:---------------------------------------------------------------------:|
|                         __Value Assignment__                          |
|                  ![](images/2.%20Assignment.003.png)                  |
|                __Get Value `=>` <br> Set Value `<=`__                 |
|          *Aims to copy a value from one object to another.*           |
|                        *The result might be:*                         |
|                  ![](images/2.%20Assignment.004.png)                  |
|                                                                       |
|                         __Object Assignment__                         |
|                  ![](images/2.%20Assignment.005.png)                  |
|               __Get Object `=>` <br> Set Object `<=`__                |
| *Tries to let one symbol point to the object indicated by the other.* |
|            *So attempts to yield over the object aspect.*             |
|                        *The result might be:*                         |
|                  ![](images/2.%20Assignment.006.png)                  |
|                                                                       |
|                         __Class Assignment__                          |
|                  ![](images/2.%20Assignment.007.png)                  |
|       __Use As Class (≈ Get Object) `=>` <br> Set Class `<=`__        |
|          *Tries to use one object as the class for another.*          |
|                        *The result might be:*                         |
|                  ![](images/2.%20Assignment.008.png)                  |

In this assignment notation the line type (dashed, wavy) might indicate which aspect would be yielded over.

![](images/2.%20Assignment.009.png)

The access mark (the smaller line crossing the longer line) might indicate direction.

![](images/2.%20Assignment.010.png)

The diamond shape in the middle would symbolize a call to an assignment command.

![](images/2.%20Assignment.011.png)

### Cross-Aspect Assignments

Perhaps a more common way to use the __Class__ aspect in an assignment might be to __Get__ the __Object__ aspect from one reference and assign it to the __Class__ aspect of another reference. But it might also be done the other way around: attempting to get the __Class__ aspect from one reference and assign it as the __Object__ of another reference. That might be called *Class-to-Object* assignment or a *Class-Get assignment* perhaps. Less conventional ways of yielding over aspects like that, might be called *cross-aspect* assignment and they might be used with the notation below.

Also noteworthy might be, that there could be two ways to get a __Class__ aspect: __Get__ the __Class__ aspect of an *object* or __Get__ the __Class__ aspect of a *reference*, since those seem to be distinct.

|                                                         |
|:-------------------------------------------------------:|
|     __Reference-Bound Class to Object Assignment__      |
|           ![](images/2.%20Assignment.012.png)           |
| __Get Reference-Bound Class `=>` <br> Set Object `<=`__ |
|                 *The result might be:*                  |
|           ![](images/2.%20Assignment.013.png)           |
|    *The object reference on the right may now point*    |
|   *to the class of the object reference on the left.*   |
|                                                         |
|       __Object-Bound Class to Object Assignment__       |
|           ![](images/2.%20Assignment.014.png)           |
|  __Get Object-Bound Class `=>` <br> Set Object `<=`__   |
|                 *The result might be:*                  |
|           ![](images/2.%20Assignment.015.png)           |
|    *The object reference on the right may now point*    |
|        *to the class of the object on the left.*        |

### Assignment without an Assignment Notation

There might be special cases of assignment that do not have an assignment notation. Explicit calls to each system command might be of use then:

|            Get Class - Set Class Assignment            |
|:------------------------------------------------------:|
|          ![](images/2.%20Assignment.016.png)           |
| __Get Reference-Bound Class `<=` <br> Set Class `=>`__ |
|                                                        |
|          ![](images/2.%20Assignment.017.png)           |
|  __Get Object-Bound Class `<=` <br> Set Class `=>`__   |

### Ideas about Assignment

There were some ideas let go of in the main description. An attempt is made here to describe them, in case they are still used somewhere or may be reconsidered later.

#### Opposite Direction Indicators?

There used to be an idea to flip the indication of direction in assignment notation.

|   ![](images/2.%20Assignment.018.png)    |
|:----------------------------------------:|
| __Get Object `=>` <br> Set Object `<=`__ |
|          (opposite direction)            |

Access marks seem to indicate direction in this language. It may make sense that the access mark might indicate the assignment direction and that the assignment direction means from source to destination. But what might make less sense is when the result of the assignment would seem to be in the opposite direction of the assignment direction:

*Result of the assignment*  
![](images/2.%20Assignment.019.png)

Perhaps it can be imagined seeing live changes in a diagram, assignment calls be executed live, seeing their effect, it would perhaps not be so intuitive when lines would seem to flip direction so many times.

That is why the suggestion was made to make the assignment look more like the direction of the result:

|   ![](images/2.%20Assignment.020.png)    |
|:----------------------------------------:|
| __Get Object `=>` <br> Set Object `<=`__ |

The idea to put the mark at the opposite end, might have some intuitivity to it, when looking at value assignments.

|  ![](images/2.%20Assignment.021.png)   |
|:--------------------------------------:|
| __Get Value `=>` <br> Set Value `<=`__ |
|         *(opposite direction)*         |

Since this would sort of indicate the direction of the flow of the data. But the price of inconsistency might not be worth that intuitivity, and might actually be less intuitive.

|  ![](images/2.%20Assignment.003.png)   |
|:--------------------------------------:|
| __Get Value `=>` <br> Set Value `<=`__ |

In the main idea the access mark sort of points in the direction of what the value is going to be, rather than where the value will go.

That said, there is a little bit of doubt. That is why this alternative idea is still described here.

#### Leaving Out Diamonds for Value Assignment?

Currently the idea might be to express value *assignment* and value *correspondence differently:*

*Value assignment*  
![](images/2.%20Assignment.022.png)

*Value correspondence*  
![](images/2.%20Assignment.023.png)

In the past there was the idea, that value lines might always mean assignment. So that assignment might not need a diamond shape:

*Value assignment?*  
![](images/2.%20Assignment.024.png)

But this might conflict with wanting to express value assignment and value correspondence distinctly and be consistent with the rest of the language.

Then again: if value correspondence would have a direction (indicated with an access mark), what else could it mean but a value assignment?

*Value assignment?*  
![](images/2.%20Assignment.024.png)

So there still seems to be some doubt around the idea. A choice was made to make a notation leading with less implicit rules and more equal ways of symbolizing things across the language.

A line would mean correspondence:

![](images/2.%20Assignment.025.png)

Line type could indicate the system aspect, like the value, object or class:

![](images/2.%20Assignment.009.png)

Access mark may mean direction:

![](images/2.%20Assignment.010.png)

And a diamond shape might mean a call:

![](images/2.%20Assignment.026.png)

An assignment call in this case:

![](images/2.%20Assignment.027.png)

The only implicitness in the assignment notation that might be left, may be that the assignment call was simplified to just a diamond shape, instead of for instance showing parameters inside it.
