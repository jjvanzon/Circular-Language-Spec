Circle Language Spec | Events
=============================

System Events
-------------

### Introduction

Without even defining any objects or class libraries, there are already a lot of standard events you can use. In most situations these will suffice.

They are events mostly related to changes to the data. Any type of change to the data can be picked up as an event.

More specifically: each system command has an event going off before it is executed and an event going off after it is executed: an __Executing__ event (before) and an __Executed__ event (after).

Derived from this comes the concept of being able to pick up a __Value Set__ command going off. This event is called the __Value Changed__ event. Picking up an event before the value is set also makes you able to cancel that change before it even happened. In case of the __Value__ aspect this is the __Value Changing__ event. So you have the opportunity to cancel a system call altogether.

Any other event of a call to a system command, such as __Add__, __Remove__ and __Execute__ can be picked up, before or after it happened, and could be cancelled.

Below is an overview of all events that derive from this concept. This results in a big list of standard events, varying in aspect, read/write direction and the before and after events. Something to denote is that __Changed__ events are the ones most commonly used.

#### Changed Events

- __Value Changed__
- __Object Changed__
- __Class Changed__
- __Name Changed__
- __Data Changed__
- __Interface Changed__
- __Interface Merged Changed__
- __Clone Written__

#### Changing Events

- __Value Changing__
- __Object Changing__
- __Class Changing__
- __Name Changing__
- __Data Changing__
- __Interface Changing__
- __Interface Merged Changing__
- __Writing Clone__

#### Get Events

- __Getting Reference__
- __Reference Gotten__
- __Getting Object__
- __Object Gotten__
- __Getting Reference-Class__
- __Reference-Class Gotten__
- __Getting Object-Class__
- __Object-Class Gotten__
- __Getting Value__
- __Value Gotten__
- __Cloning__
- __Cloned__
- __Getting Name__
- __Name Gotten__
- __Getting Data__
- __Data Gotten__
- __Getting Reference-Interface__
- __Reference-Interface Gotten__
- __Getting Object-Interface__
- __Object-Interface Gotten__
- __Getting Interface Merged__
- __Interface Merged Gotten__

#### Use Events

- __Reference Used As Object__
- __Using Reference As Object__
- __Using As Class__
- __Used As Class__
- __Using Reference As Class__
- __Reference Used As Class__
- __Using As Interface__
- __Used As Interface__
- __Using Reference As Interface__
- __Reference Used As Interface__

#### List Events

- __Added__ (used more)
- __Adding__ (used less)
- __Removing__ (used more)
- __Removed__ (used less)
- __Storage Count Changed__
- __Storage Count Changing__

#### Execution & Existence Events

- __Executed__
- __Executing__
- __Created__
- __Creating__
- __Annulled__
- __Annulling__

#### Pointer to Pointer Events

Perhaps the different overloads for pointer-to-pointer situations should have separate events as well, but this depends on design choices and this issue will be left open for now.

### System Events in Normal Notation

System can be displayed with the normal event notation, examples of which you will find below.

![](images/2.%20System%20Events.001a.png)

![](images/2.%20System%20Events.001b.png)

### Simplified System Event Notation

System events can also be displayed using a simpler notation that uses line types to denote the aspect, and leaves out the aspect out of the displayed event name.

In the matrix below, reference-bound aspects are displayed with a parent around the event source and object-bound aspects are displayed without a parent around the event source.

![](images/2.%20System%20Events.002.png)

![](images/2.%20System%20Events.003.png)

(It is not sure whether this will adequately disambiguate in practice. Hopefully using the diagram concept of automatic containment it will turn out not to be ambiguous, but that is not sure yet.)

Here follow the simplified notations for all the system events.

__Reference Aspect__

| Getting Reference | Reference Gotten |
|:-----------------:|:----------------:|
| ![](images/2.%20System%20Events.004.png) | ![](images/2.%20System%20Events.005.png) |

__Object Aspect__

| Object Changed | Object Changing | Object Gotten | Getting Object |
|:--------------:|:---------------:|:-------------:|:--------------:|
| ![](images/2.%20System%20Events.006.png) | ![](images/2.%20System%20Events.007.png) | ![](images/2.%20System%20Events.008.png) | ![](images/2.%20System%20Events.009.png) |

| Reference Used As Object | Using Reference As Object |
|:-------------------------:|:------------------------:|
| ![](images/2.%20System%20Events.010.png) | ![](images/2.%20System%20Events.011.png) |

__Class Aspect__

| Class Changed | Class Changing |
|:-------------:|:--------------:|
| ![](images/2.%20System%20Events.012.png) | ![](images/2.%20System%20Events.013.png) |

| Used As Class | Using As Class | Reference Used As Class | Using Reference As Class |
|:-------------:|:--------------:|:-----------------------:|:------------------------:|
| ![](images/2.%20System%20Events.014.png) | ![](images/2.%20System%20Events.015.png) | ![](images/2.%20System%20Events.016.png) | ![](images/2.%20System%20Events.017.png) |

|                     |                      |                  |                  |
|:-------------------:|:--------------------:|:----------------:|:----------------:|
| __Reference-Class__ |     __Getting__      | __Object-Class__ |   __Getting__    |
|      __Gotten__     |  __Reference-Class__ |    __Gotten__    | __Object-Class__ |
| ![](images/2.%20System%20Events.018.png) | ![](images/2.%20System%20Events.019.png) | ![](images/2.%20System%20Events.020a.png) | ![](images/2.%20System%20Events.020b.png)|

__Interface Aspect__

| Interface Changed | Interface Changing |
|:-----------------:|:------------------:|
| ![](images/2.%20System%20Events.021.png) | ![](images/2.%20System%20Events.022.png) |

| Used As Interface | Using As Interface | Reference Used As Interface | Using Reference As Interface |
|:-----------------:|:------------------:|:---------------------------:|:----------------------------:|
| ![](images/2.%20System%20Events.023.png) | ![](images/2.%20System%20Events.024.png) | ![](images/2.%20System%20Events.025.png) | ![](images/2.%20System%20Events.026.png) |

| Reference-Interface Gotten | Getting Reference-Interface | Object-Interface Gotten | Getting Object-Interface |
|:--------------------------:|:---------------------------:|:-----------------------:|:------------------------:|
| ![](images/2.%20System%20Events.027.png) | ![](images/2.%20System%20Events.028.png) | ![](images/2.%20System%20Events.029.png) | ![](images/2.%20System%20Events.030.png)|

__Interface Merged Aspect__

| Interface Merged Changed | Interface Merged Changing | Getting Interface Merged | Interface Merged Gotten |
|:------------------------:|:-------------------------:|:------------------------:|:-----------------------:|
| ![](images/2.%20System%20Events.031.png) | ![](images/2.%20System%20Events.032.png) | ![](images/2.%20System%20Events.033.png) | ![](images/2.%20System%20Events.034.png)|

__Value Aspect__

| Value Changed | Value Changing | Getting Value | Value Gotten |
|:-------------:|:--------------:|:-------------:|:------------:|
| ![](images/2.%20System%20Events.035.png) | ![](images/2.%20System%20Events.036.png) | ![](images/2.%20System%20Events.037.png) | ![](images/2.%20System%20Events.038.png) |

__Clone Aspect__

| Clone Written | Writing Clone | Cloned | Cloning |
|:-------------:|:-------------:|:------:|:-------:|
| ![](images/2.%20System%20Events.039.png) | ![](images/2.%20System%20Events.040.png) | ![](images/2.%20System%20Events.041.png) | ![](images/2.%20System%20Events.042.png) |

__Data Aspect__

| Data Changed | Data Changing | Data Gotten | Getting Data |
|:------------:|:-------------:|:-----------:|:------------:|
| ![](images/2.%20System%20Events.043.png) | ![](images/2.%20System%20Events.044.png) | ![](images/2.%20System%20Events.045.png) | ![](images/2.%20System%20Events.046.png) |

__Name Aspect__

| Name Changed | Name Changing | Getting Name | Name Gotten |
|:------------:|:-------------:|:------------:|:-----------:|
| ![](images/2.%20System%20Events.047.png) | ![](images/2.%20System%20Events.048.png) | ![](images/2.%20System%20Events.049.png) | ![](images/2.%20System%20Events.050.png) |

__List Aspect__

| Added | Adding | Removing | Removed |
|:-----:|:------:|:--------:|:-------:|
| ![](images/2.%20System%20Events.051.png) | ![](images/2.%20System%20Events.052.png) | ![](images/2.%20System%20Events.053.png) | ![](images/2.%20System%20Events.054.png) |

| Storage Count Changed | Storage Count Changing |
|:---------------------:|:----------------------:|
| ![](images/2.%20System%20Events.055.png) | ![](images/2.%20System%20Events.056.png) |

__Execution Aspect__

| Executed | Executing |
|:--------:|:---------:|
| ![](images/2.%20System%20Events.057.png) | ![](images/2.%20System%20Events.058.png) |

__Existence Aspect__

| Created | Creating | Annulled | Annulling |
|:-------:|:--------:|:--------:|:---------:|
| ![](images/2.%20System%20Events.059.png) | ![](images/2.%20System%20Events.060.png) | ![](images/2.%20System%20Events.061a.png) | ![](images/2.%20System%20Events.061b.png) |

Some aspects have no associated line type, so they are not shown with a simplified notation, but with the normal notation. The above are the connectors, but the actual event commands look almost the same, but then without the loose end at the top.

### System Event Parameters

System events have parameters. First of all they have the __This__ parameter, which identifies which object something’s happening to.

![](images/2.%20System%20Events.062.png)

__This__ can be an __Object__, but also for instance a __Related Item__. 

|     ![](images/2.%20System%20Events.063.png)     |  ![](images/2.%20System%20Events.064.png)   |
|:------------------------------------------------:|:-------------------------------------------:|
| *The* __This__ *parameter is a* __Related Item__ | *The* __This__ *parameter is an* __Object__ |

Second of all for systems events that announce something is about to happen, usually have a __Value__ parameter which indicates which value is about to be assigned and also a __Cancel__ __Boolean__ parameter to be able to assign the value __True__ to, to cancel the event. 

![](images/2.%20System%20Events.065.png)

The __List__ and __Existence__ aspects have additional event parameters.

The __Creating__ event have a __Class__ and __Interface__ parameter, which indicate which class or interface the new object will have.

![](images/2.%20System%20Events.066.png)

The __Adding__ event has an __Item__ parameter (an __Object__).

![](images/2.%20System%20Events.067.png)

And the __Added__ event has a __List Item__ parameter (a __Related List Item__).

![](images/2.%20System%20Events.068.png)

The __Clone__ aspect’s events also have a __Depth__ parameter.

![](images/2.%20System%20Events.069.png)

![](images/2.%20System%20Events.070.png)

Possibly a __Changed__ event will also contain the __Previous Value__ parameter.

![](images/2.%20System%20Events.071.png)

In the earlier introduced connector notation, parameters are not shown. But the parameters *are* shown in the event *implementations*.

### System Event Design Choices

The names used for the events might not be the eventual names. For instance a more simplified design might simply let all system commands have a __Executing__ and __Executed__ event, instead of inventing different names for the different events, so that __Value Changed__ is named __Value Set . Executed__. In another design choice you might not call it the __Executing__ and __Executed__ event, but the __Before__ and __After__ event, or the __Happening__ and __Happened__ events, or the __Pre-Extension__ and __Post-Extension__ events.

This does not change the concept. These are all just benign design choices. You could also call it __Value Will Change__ instead of __Value Changing__, this is not really the point. It does not change the concept.

The concept is still derived from the fact that you can pick up the __Executing__ and __Executed__ event from any command, including all system commands.

Other design choices that could be made are that other aspect’s changed events may very well all derive from the __Value Changed__ event. And the __Class__ and __Interface__ aspects’ events might all derive from the __Object Changed__ event.