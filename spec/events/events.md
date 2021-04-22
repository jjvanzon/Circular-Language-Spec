Circular Language Spec
======================

Events
------

`[ Preliminary documentation ]`

__Contents__

- [Introduction](#introduction)
- [Prime Event Example: Button Clicked](#prime-event-example-button-clicked)
- [Main Concepts](#main-concepts)
    - [Main Notation of Event](#main-notation-of-event)
    - [Event Connector](#event-connector)
    - [Event Raising](#event-raising)
    - [Call to a Parent](#call-to-a-parent)
    - [Event Implementation & Connector](#event-implementation--connector)
- [Event Situations](#event-situations)
    - [Multi-Cast Events](#multi-cast-events)
    - [Multi-Cast in Same Parent](#multi-cast-in-same-parent)
    - [Event with Parameters](#event-with-parameters)
    - [Event From Deeper Object](#event-from-deeper-object)
- [Explicit Implementation of Event Object](#explicit-implementation-of-event-object)
- [Explicit Interface of Event Object](#explicit-interface-of-event-object)
- [Event Interface Reference](#event-interface-reference)
- [Interaction Events](#interaction-events)
- [Black Boxed Events](#black-boxed-events)
- [Event Alternatives](#event-alternatives)

### Introduction

Events are notification calls. Call receivers subscribe to an event. The call sender might call the receivers whenever it feels like it. Another name for events that the world adopts, is *‘the observer pattern’*. The caller decides what the message looks like. The receiver has to supply a command, that has an interface, specified by the caller.

The concept of events is nothing more than a combination of constructs: an array of command references, a command interface and supporting the command interface, registering the command inside the array of command references and then calling all the commands in the array at specific times.

Even though it is just a combination of some other constructs, it is such an important concept, that Circular explicitly defines it as a sepate construct, following the footsteps of other programming environments, that did this as well.

The documentation might also show how events look in the diagram notation of Circular.

### Prime Event Example: Button Clicked

The key example that explains the purpose of events is a button click. A programmer defines the command to run when the user presses a button. The button click is implemented using the __Events__ construct, so that a programmer can easily stick a procedure under a __Button Clicked__ event without having to worry how the procedure really got invoked.

The notation of that is as follows.

![](images/1.%20Events.001.png)

### Main Concepts

#### Main Notation of Event

The main notation of an event is as follows:

![](images/1.%20Events.002.png)

It shows an object with an event procedure / event command / event implementation associated with it.

#### Event Connector

When an event procedure is not filled in, you might only see the event as a connector:

![](images/1.%20Events.003.png)

The reason for displaying it like this is that connectors usually look like the result of the system call, but then as a loose end.

#### Event Raising

The object can raise the event. If you only see the interface of the object you might usually not see this, but if you can see the implementation of the object, its raising the event might look as follows:

![](images/1.%20Events.004.png)

#### Call to a Parent

An event is a way for an object to call its parent. So this is what that looks like:

![](images/1.%20Events.005.png)

This is the reason why events are displayed like this in the diagram: it is like a child calling a parent.

#### Event Implementation & Connector

When an event procedure is present, the connector to the event procedure is still available so that other procedures can be tied to the event:

![](images/1.%20Events.006.png)

### Event Situations

Several situations are possible in case of events. Events are *multi-cast*, meaning that multiple commands in multiple objects can run in response to the event. Also, a child object is not the only object you can pick up events from. You can also pick up events from deeper objects.

#### Multi-Cast Events

An event can be picked up by multiple parent objects when they both have a reference to the event-casting object and they both define an event command:

![](images/1.%20Events.007.png)

#### Multi-Cast in Same Parent

Multiple commands can be bound to an event, even when they both are defined inside the same parent object:

![](images/1.%20Events.008.png)

#### Event with Parameters

Events can have parameters. Here is an example of an event with a parameter.

![](images/1.%20Events.009.png)

#### Event From Deeper Object

A child object is not the only object you can pick up events from. You can just as easily pick up events from a deeper object.

![](images/1.%20Events.010.png)

### Explicit Implementation of Event Object

The concept of events is nothing more than a combination of constructs: an array of command references, a command interface and supporting the command interface, registering the command inside the array of command references and then calling all the commands in the array at specific times.

Explicitly drawing out the event concept using constructs mentioned above, the picture might look like this:

![](images/1.%20Events.011.png)

That is the way __Event__ objects are internally implemented.

What you see is the registered event implementation (at the top), the collection of event receivers, the event interface, the __Raise__ command and its implementation that loops through the event receiver commands and calls each of them.

Note that even though the concept is that parents can pick up messages from children, it is not the *parents* that are registered, but the *event procedures* that are registered.

Even though the event concept is just a combination of other constructs, it is such an important concept, that Circular explicitly defines it as a sepate construct with its own notation.

### Explicit Interface of Event Object

The previous article showed how the implementation of an event object explicitly looks. The interface of an __Event__ object, so the part that other objects interact with, looks as follows:

![](images/1.%20Events.012.png)

The connectors at the top of the picture are the members that the event *receiver* might interact with: it might *register* its command as a __Receiver__ and it might *implement* the command __Interface__.

The connectors at the bottom of the picture are the members that the event *sender* might interact with: it might *call* the __Raise__ command of the event and it might also define the *data* that might form the command __Interface__ of the event.

### Event Interface Reference

An event command might always implement an interface specified by the __Event__ object. But if you want to express a command’s implementing the event interface without actually being tied to the event, it might look like this:

![](images/1.%20Events.013.png)

So the event connector is there and the command’s interface reference is tied to the event connector.

### Interaction Events

Apart to system events, the next most commonly used group of events may very well be the *interaction events*.

Interaction events are events that occur when a user for instance clicks a button, or double clicks or presses a keyboard key.

This type of event is more of a *controls aspect* than a coding aspect, but they are mentioned here anyway, because they are such a common use of events

Below you might find a simplified overview of the most common interaction events.

|                                 |                                 |                                 |
|:-------------------------------:|:-------------------------------:|:-------------------------------:|
| ![](images/1.%20Events.014.png) | ![](images/1.%20Events.015.png) |                                 |
| ![](images/1.%20Events.016.png) | ![](images/1.%20Events.017.png) | ![](images/1.%20Events.018.png) |
| ![](images/1.%20Events.019.png) | ![](images/1.%20Events.020.png) |                                 |

### Black Boxed Events

Details about black boxes are covered in the chapter *Black Boxes*.

However, two situations are explicitly denoted here:

- Making events __Private__
- Accessing the __Private__ contents of an event parameter

Just like any other member of an object, events can also be made __Private__. In that case only __Friend__ objects can pick up this event. Below you might find the involved notations. Details are not covered. More information about black boxing can be found in the *Black Boxing* chapter.

|                                  |                                  |                                  |
|:--------------------------------:|:--------------------------------:|:--------------------------------:|
| __Public Event <br> Connector__  | __Friend Event <br> Connector__  | __Private Event <br> Connector__ |
| ![](images/1.%20Events.021.png)  | ![](images/1.%20Events.022.png)  | ![](images/1.%20Events.023.png)  |
|                                  |                                  |                                  |
| __Public Event <br> Connection__ | __Friend Event <br> Connection__ |                                  |
| ![](images/1.%20Events.024.png)  | ![](images/1.%20Events.025.png)  |                                  |

There are two reasons why the __Public__ event connector might not get an access mark: __Public__ is sort of the default, and the event connection is outward so it might not need an access symbol. The others do need an access mark, because it is the only way to express the access modification.

The second black boxing situation to be explicitly mentioned is accessing the __Private__ contents of an event parameter. By default you only get to access the __Public__ members of an event parameter. This is what makes it the black box principle.

![](images/1.%20Events.026.png)

To be able to access the __Private__ members of the event parameter, the event procedure might be declared __Friend__ of the event parameter.

![](images/1.%20Events.027.png)

Then the event procedure can access the __Private__ members of the event parameter:

![](images/1.%20Events.028.png)

The __Friend__ declaration is an agreement between the event sender and the class of the event parameter. The __Friend__ declaration is part of the event interface, defined by the event sender. So the event receiver can not just declare itself __Friend__ of the event parameter whenever it feels like it.

### Event Alternatives

An event is a means for a child to call the parent. The Events concept works well for this. But there are alternatives for a child to call a parent. A simple command reference might do as well, only this might not allow multi-cast events.

Another alternative is that the child defines an interface, that the parent might support, the parent implements the interface, and the child calls upon the interface of the parent. If you want this to work in a multi-cast situation, you might program the multi-cast functionality yourself pretty much the same way as an event object implements it (see *Explicit Implementation of Event Object*). Just using standard events might be an easier solution.