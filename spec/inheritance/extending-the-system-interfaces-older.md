Encircle Language Spec | Inheritance
====================================

Extending the System Interfaces
-------------------------------

`[ Preliminary documentation ]`

__Contents__

- [Introduction](#introduction)
- [Main Examples of System Command Extension](#main-examples-of-system-command-extension)
- [Command Extension Possibilities](#command-extension-possibilities)
- [Extend System Interface with More Members](#extend-system-interface-with-more-members)
- [Extension Regardless of Value Change](#extension-regardless-of-value-change)
- [Extension Procedures are Events](#extension-procedures-are-events)
- [Extension Procedures Part of Parent](#extension-procedures-part-of-parent)
- [Obsolete Members: Initialize Item & Terminate Item](#obsolete-members-initialize-item--terminate-item)
- [Extension of System Interfaces in a Diagram](#extension-of-system-interfaces-in-a-diagram)
- [Loose Ideas](#loose-ideas)
    - [Extension (Cross-Out Leftovers from System Interfaces)](#extension-cross-out-leftovers-from-system-interfaces)

### Introduction

In the *System Interfaces* articles it has been repeatedly mentioned, that all the system commands can be extended with extra procedures. First, to demonstrate the concept, this article gives you the main examples of system command extension. After that, all the possible system command extensions will be listed out.

### Main Examples of System Command Extension

By default the __Object  .  Get__ and __Object  .  Set__ commands just return and set the object. But calls to __Object  .  Get__ and __Object  .  Set__ can also be extended with procedures around the assignment and retrieval of the object.

The  __Object  .  Get__  command can be programmed. By default it just returns the target object of the related item or related list item, but you can program it to return any object, resulting from a procedure as complex as you want. One application of this is letting the __Object  .  Get__  return a related item from another parent, so that another parent determines the related item. Functionally, this establishes a pointer to a pointer. From the outside, you don’t see this; the symbol just looks like the target object. (A pointer to pointer is indeed also possible in a more basic form. See the article *Pointer to Pointer* for that.)

The __Object  .  Set__ command can also be programmed. Being able to program the __Object  .  Set__ command is particularly handy. In the  __Object  .  Set__ you can add validation of the assigned object. The newly assigned object may also need to be applied to other objects. The changes to other objects can be immediately applied by a procedure extending the __Object  .  Set__  command.

Actually, the *extension* of the system interface is the most important thing about even being *aware* of the system interface.

Even though a value is stored inside the object *itself*, the system commands of a *related item* or *related list item* allow you to build a procedure around assigning a value to a sub-object.

By default the __Value  .  Get__ and __Value  .  Set__ commands just return and set the value. But calls to __Value  .  Get__ and __Value  .  Set__ can be extended with procedures around the assignment and retrieval of the value.

### Command Extension Possibilities

Only the system *commands* of the system interface are extensible with procedures.

Related items and related list items have the following system commands:

- __Object  .  Get__
- __Object  .  Set__
- __Other Related Item  .  Get__
- __Other Related Item  .  Set__
- __Other Related List Item  .  Get__
- __Other Related List Item  .  Set__
- __Value  .  Get__
- __Value  .  Set__
- __New__
- __Annul__
- __Created  .  Get__
- __Created  .  Set__

Related list items also have the system command:

- __Remove__

A related list has following the system command:

- __Add__

Only the system *commands* are listed out above, not the other system members.

Extension can be done in three different ways:

- Pre-extend
- Post-extend
- Overriding

These types of extension can be applied to each system command. Pre-extension triggers a custom procedure *before* running the system command’s default procedure. Post-extension triggers a custom procedure *after* running the system command’s default procedure. The same system command can be both pre-extended and post-extended at the same time. A system command can also be overridden completely, and the default procedure completely omitted. Inside the overriding procedure you can always decide to call the default procedure anyway. So in theory, you only need overriding, because that gives you the ability to either pre-extend and post-extend. But it’s more intuitive to be able to immediately choose to *extend*, instead of first choosing override and *then* choose to extend.

Extension procedures may be implemented by the system interface as events raised by the system commands. But how to best implement procedure extension can be determined later.

A related item will have the following extension possibilities:

- __Object  .  Get  .  Pre-Extend__
- __Object  .  Get  .  Post-Extend__
- __Object  .  Get  .  Override__
- __Object  .  Set  .  Pre-Extend__
- __Object  .  Set  .  Post-Extend__
- __Object  .  Set  .  Override__
- __Other Related Item  .  Get  .  Pre-Extend__
- __Other Related Item  .  Get  .  Post-Extend__
- __Other Related Item  .  Get  .  Override__
- __Other Related Item  .  Set  .  Pre-Extend__
- __Other Related Item  .  Set  .  Post-Extend__
- __Other Related Item  .  Set  .  Override__
- __Other Related List Item  .  Get  .  Pre-Extend__
- __Other Related List Item  .  Get  .  Post-Extend__
- __Other Related List Item  .  Get  .  Override__
- __Other Related List Item  .  Set  .  Pre-Extend__
- __Other Related List Item  .  Set  .  Post-Extend__
- __Other Related List Item  .  Set  .  Override__
- __Value  .  Get  .  Pre-Extend__
- __Value  .  Get  .  Post-Extend__
- __Value  .  Get  .  Override__
- __Value  .  Set  .  Pre-Extend__
- __Value  .  Set  .  Post-Extend__
- __Value  .  Set  .  Override__
- __New  .  Pre-Extend__
- __New  .  Post-Extend__
- __New  .  Override__
- __Annul  .  Pre-Extend__
- __Annul  .  Post-Extend__
- __Annul  .  Override__
- __Created  .  Get  .  Pre-Extend__
- __Created  .  Get  .  Post-Extend__
- __Created  .  Get  .  Override__
- __Created  .  Set  .  Pre-Extend__
- __Created  .  Set  .  Post-Extend__
- __Created  .  Set  .  Override__

These are the new computer language’s equivalent of __Getters__, __Setters__ and __Property__ procedures.

This adds a lot more possibilities to surround a sub-object’s behavior, than just the one __Getter__ and __Setter__, that other computer programming languages offer. You don’t have to define all of the extension procedures. When you don’t define a __Getter__ or __Setter__, the related item will just have default __Getter__ and __Setter__ behavior.

=>n related *list items* have the same system commands as =>1 related items, but the extension of a related list item’s system commands is the same for every item of the list, so the extension procedures for related list items are defined by the related list. The related list items have a reference to the list they belong to, and also store the position in the list, as well as a __Remove__ command, that removes the item from the list. In the new computer language’s code base, a related list item automatically calls the extension procedures defined in the list, passing the position of the item in the list to the extension procedure as a parameter. Here is a list of all the extension procedures a list can define for a related list’s items:

- __Item Object  .  Get  .  Pre-Extend__
- __Item Object  .  Get  .  Post-Extend__
- __Item Object  .  Get  .  Override__
- __Item Object  .  Set  .  Pre-Extend__
- __Item Object  .  Set  .  Post-Extend__
- __Item Object  .  Set  .  Override__
- __Item Other Related Item  .  Get  .  Pre-Extend__
- __Item Other Related Item  .  Get  .  Post-Extend__
- __Item Other Related Item  .  Get  .  Override__
- __Item Other Related Item  .  Set  .  Pre-Extend__
- __Item Other Related Item  .  Set  .  Post-Extend__
- __Item Other Related Item  .  Set  .  Override__
- __Item Other Related List Item  .  Get  .  Pre-Extend__
- __Item Other Related List Item  .  Get  .  Post-Extend__
- __Item Other Related List Item  .  Get  .  Override__
- __Item Other Related List Item  .  Set  .  Pre-Extend__
- __Item Other Related List Item  .  Set  .  Post-Extend__
- __Item Other Related List Item  .  Set  .  Override__
- __Item Value  .  Get  .  Pre-Extend__
- __Item Value  .  Get  .  Post-Extend__
- __Item Value  .  Get  .  Override__
- __Item Value  .  Set  .  Pre-Extend__
- __Item Value  .  Set  .  Post-Extend__
- __Item Value  .  Set  .  Override__
- __Item New  .  Pre-Extend__
- __Item New  .  Post-Extend__
- __Item New  .  Override__
- __Item Annul  .  Pre-Extend__
- __Item Annul  .  Post-Extend__
- __Item Annul  .  Override__
- __Item Created  .  Get  .  Pre-Extend__
- __Item Created  .  Get  .  Post-Extend__
- __Item Created  .  Get  .  Override__
- __Item Created  .  Set  .  Pre-Extend__
- __Item Created  .  Set  .  Post-Extend__
- __Item Created  .  Set  .  Override__
- __Item Remove  .  Pre-Extend__
- __Item Remove  .  Pre-Extend__
- __Item Remove  .  Override__

References to these extension procedures are stored inside the related list inside the following system objects:

- __Item New__
- __Item Annul__
- __Item Remove__
- __Item Created  .  Get__
- __Item Created  .  Set__
- __Item Object  .  Get__
- __Item Object  .  Set__
- __Item Other Related Item  .  Get__
- __Item Other Related Item  .  Set__
- __Item Other Related List Item  .  Get__
- __Item Other Related List Item  .  Set__
- __Item Value  .  Get__
- __Item Value  .  Set__

So those are all objects, not commands. The objects contain references to the extension procedures for a related list item.

A related list itself only has the following system command:

- __Add__

The list object only has one system command. Its extension procedures are:

- __Add  .  Pre-Extend__
- __Add  .  Post-Extend__
- __Add  .  Override__

The other extension procedures, a related list defines, are extensions for commands of the list *items*, not extensions for commands of the list object itself.

You are most likely to only use the __Add  .  Post-Extend__ to extend the addition of an item and use the __Item Remove  .  Pre-Extend__ to finalize an item ready to be removed. But the other extension possibilities of __Add__ and __Remove__ are there, because this allows you full control over the behavior of related objects, regardless of what would be most logical to do.

Extension of the system interface’s members allows you to control the inner workings of a sub-object.

### Extend System Interface with More Members

Other features of the new computer language can add more items to the system interface, to define the behavior of a related item. The system interface is *extensible*. For instance the concept of *the class* will add more items to the configuration of a related item. So apart from extending a system interface’s existing commands, new commands and objects can be added to the system interface.

The system interface members added by other features will automatically get all the extension possibilities as well.

### Extension Regardless of Value Change

The various __Get__ commands only really execute their procedure when a value is actually *changed*. That is the default behavior of the new computer language. It prevents a lot of unnecessary system activity. By default, pre- and post-extension procedures are only executed for getters, when a *different* value is actually assigned. However, a feature, that may be added to the new computer language could be:

- Pre-extension regardless of value change
- Post-extension regardless of value change

That feature adds two more extension possibilities to every __Get__ command, to execute a procedure extension even when the value does not change.

### Extension Procedures are Events

The implementation of an extension procedure looks the same as the implementation of an event procedure. The concept of *events* has not been covered yet, but it looks the same as the notation used for system command extensions.

The reason why an extension procedure *has to be* an event, is because it is a signal from a sub-object to a parent object. A signal from a sub-object to a parent is always an event.

A system command extension event is a multi-cast event, even though you may only define one extension procedure yourself. Different concepts can automatically add more extensions to system commands, so the same extension has multiple implementations, that are all run when a system command is fired.

The parent object is the only one that can implement the system command extension event. This also counts for concepts too. Concepts just extend the parent object, so it is still only the parent object extending a system command. This is has to be access controlled. Access control is worked out later in the *Access Control* articles.

### Extension Procedures Part of Parent

Although the system objects define the extension events, the *parent object* defines the implementation of the extension procedures. The extension procedures are defined by the parent object. This counts for related item, related lists and related list items. Extension procedures need to be normal commands, not system commands.  
It is just more practical to make the extension procedures part of the parent object. Only a normal computer language object can define commands, that have all the possibilities of computer language. You cannot really change objects like related items or related lists, because they are system objects. Those system objects can only be extended, not changed.

Theoretically it does not matter whether extension procedures are defined by for instance inside a related item or inside the parent object of a related item. A related item is part of the parent object anyway.

### Obsolete Members: Initialize Item & Terminate Item

In an earlier version of the new computer language, version 2.0, a related list also had the extension procedures __Initialize Item__ and __Terminate Item__. In the new version of the new computer language, version 3.0, __Initialize Item__ is replaced by __Add  .  Post-Extend__ and __Terminate Item__ is replaced by __Remove  .  Pre-Extend__.

### Extension of System Interfaces in a Diagram

The concept of extending the system objects is already explained in the article *Extending the System Interfaces*. The current article demonstrates its expression in a diagram.

Not all possible extensions of the system commands will be displayed in this article. Any extension procedure of the system interface commands is displayed the same way. Only a couple of extension procedures will be displayed, to demonstrate the idea.

![](images/5.%20Extending%20System%20Objects%20(Older).001.png)

In the picture above, a __Related Item__ is shown inside a __Parent Object__. The system interface of the related item is opened up. You can see the __Object__ part of the system interface. Inside the __Object__ part of the system interface is displayed the __Object  .  Set__ command. Lines are going out of the __Object  .  Set__ command to the __Pre-Extend__ and __Post-Extend__ procedures, that are implemented by the __Parent Object__.

Extension of system commands of a related list item works a bit differently, because the extension procedures of a related list item are the same for all items in the list, thus the extension procedures are defined by the related list. The related list defines a number of objects, that contain references to the extension procedures. When you open up the system interface of a related list, you can specify the extension procedures.

![](images/5.%20Extending%20System%20Objects%20(Older).002.png)

The examples shows the system interface of a related list, but not all its members. The following system objects are shown: __Item New__, __Item Annul__ and __Item Object__. The rest of the system objects are left out. The system object __Item Object__ contains the __Get__ and __Set__ objects. Objects like __Item Object  .  Get__, that have the same name as a system command of a related list item, define the extension procedures. In the example above, the system object __Item Object  .  Get__ has a pre- extension defined. The extension is displayed as a line going out of __Item Object  .  Get__ to a procedure named __Pre-Extend__, defined inside the parent object. The extension procedure is passed a parameter, namely: the __Related List Item__ for which the extension procedure was called.

### Loose Ideas

*The texts below are loose ideas yet to be turned into good documentation.*

#### Extension (Cross-Out Leftovers from System Interfaces)

Assignment and retrieval of the related item can be decorated with extra procedures.

Decorating assignment and retrieval of a related item with extra procedures will be covered by the article *Extending the System Interface*.

Each item in the list has different data in its system object, but extensions to the procedures around assignment or retrieval of an item in the list are the same for each item. That’s why the extension procedures of related list items are defined inside the related list.  
A related list’s system interface has objects, that define the extension procedures of related list items’ system commands:

- __Item New__
- __Item Annul__
- __Item Created  .  Get__
- __Item Created  .  Set__
- __Item Object  .  Get__
- __Item Object  .  Set__
- __Item Other Related Item  .  Get__
- __Item Other Related Item  .  Set__
- __Item Other Related List Item  .  Get__
- __Item Other Related List Item  .  Set__
- __Item Value  .  Get__
- __Item Value  .  Set__
- __Item Remove__

The complete system interface of the related list system object looks like this:

![](images/5.%20Extending%20System%20Objects%20(Older).003.png)

So most of those are objects, not commands. The objects only contain references to the extension procedures for related list items.

-----

For a related *list item* extension procedures of assignment and retrieval are delegated to the list, because the assignment and retrieval procedure extensions are the same for every item in the list.

At first there was the idea, that a related list item could get the same behavior as a related item. The reason why a related *list item* is not the same as a related *item*, is because a related *list* *item* does not define its own decoration with procedures. The decoration of the assignment and retrieval of the a related list item is delegated to the related list and is the same for all the items in the list.

-----

Actually, system objects would not be an equivalent of __Getters__ and __Setters__ if it weren’t for the *extension* of system commands. A summary of the system objects would not be complete without a list of all possible system commands and all its possible procedure extensions. Below you will find lists of all the extension possibilities of the system objects. For explanations about the extension possibilities, refer to the article *Extending The System Interfaces*. 

Related item extension possibilities:

- __Object  .  Get  .  Pre-Extend__
- __Object  .  Get  .  Post-Extend__
- __Object  .  Get  .  Override__
- __Object  .  Set  .  Pre-Extend__
- __Object  .  Set  .  Post-Extend__
- __Object  .  Set  .  Override__
- __Other Related Item  .  Get  .  Pre-Extend__
- __Other Related Item  .  Get  .  Post-Extend__
- __Other Related Item  .  Get  .  Override__
- __Other Related Item  .  Set  .  Pre-Extend__
- __Other Related Item  .  Set  .  Post-Extend__
- __Other Related Item  .  Set  .  Override__
- __Other Related List Item  .  Get  .  Pre-Extend__
- __Other Related List Item  .  Get  .  Post-Extend__
- __Other Related List Item  .  Get  .  Override__
- __Other Related List Item  .  Set  .  Pre-Extend__
- __Other Related List Item  .  Set  .  Post-Extend__
- __Other Related List Item  .  Set  .  Override__
- __Value  .  Get  .  Pre-Extend__
- __Value  .  Get  .  Post-Extend__
- __Value  .  Get  .  Override__
- __Value  .  Set  .  Pre-Extend__
- __Value  .  Set  .  Post-Extend__
- __Value  .  Set  .  Override__
- __New  .  Pre-Extend__
- __New  .  Post-Extend__
- __New  .  Override__
- __Annul  .  Pre-Extend__
- __Annul  .  Post-Extend__
- __Annul  .  Override__
- __Created  .  Get  .  Pre-Extend__
- __Created  .  Get  .  Post-Extend__
- __Created  .  Get  .  Override__
- __Created  .  Set  .  Pre-Extend__
- __Created  .  Set  .  Post-Extend__
- __Created  .  Set  .  Override__

Related list extension possibilities:

- __Add  .  Pre-Extend__
- __Add  .  Post-Extend__
- __Add  .  Override__

Related list item extension possibilities:

- __Item Object  .  Get  .  Pre-Extend__
- __Item Object  .  Get  .  Post-Extend__
- __Item Object  .  Get  .  Override__
- __Item Object  .  Set  .  Pre-Extend__
- __Item Object  .  Set  .  Post-Extend__
- __Item Object  .  Set  .  Override__
- __Item Other Related Item  .  Get  .  Pre-Extend__
- __Item Other Related Item  .  Get  .  Post-Extend__
- __Item Other Related Item  .  Get  .  Override__
- __Item Other Related Item  .  Set  .  Pre-Extend__
- __Item Other Related Item  .  Set  .  Post-Extend__
- __Item Other Related Item  .  Set  .  Override__
- __Item Other Related List Item  .  Get  .  Pre-Extend__
- __Item Other Related List Item  .  Get  .  Post-Extend__
- __Item Other Related List Item  .  Get  .  Override__
- __Item Other Related List Item  .  Set  .  Pre-Extend__
- __Item Other Related List Item  .  Set  .  Post-Extend__
- __Item Other Related List Item  .  Set  .  Override__
- __Item Value  .  Get  .  Pre-Extend__
- __Item Value  .  Get  .  Post-Extend__
- __Item Value  .  Get  .  Override__
- __Item Value  .  Set  .  Pre-Extend__
- __Item Value  .  Set  .  Post-Extend__
- __Item Value  .  Set  .  Override__
- __Item New  .  Pre-Extend__
- __Item New  .  Post-Extend__
- __Item New  .  Override__
- __Item Annul  .  Pre-Extend__
- __Item Annul  .  Post-Extend__
- __Item Annul  .  Override__
- __Item Created  .  Get  .  Pre-Extend__
- __Item Created  .  Get  .  Post-Extend__
- __Item Created  .  Get  .  Override__
- __Item Created  .  Set  .  Pre-Extend__
- __Item Created  .  Set  .  Post-Extend__
- __Item Created  .  Set  .  Override__
- __Item Remove  .  Pre-Extend__
- __Item Remove  .  Pre-Extend__
- __Item Remove  .  Override__

-----

Usually not all members of a system object are shown, but only the parts that are extended or used. In that case the diagram shows an ellipsis in the spots where the additional members are not displayed:

![](images/5.%20Extending%20System%20Objects%20(Older).004.png)

Each ellipsis can be double clicked or clicked, or something, to show all the other system object members and extension possibilities.  
When you double click the ellipsis inside the __Object__ part of the system interface, all the __Object__ members are shown and their extension possibilities:

![](images/5.%20Extending%20System%20Objects%20(Older).005.png)

If you double click the ellipsis at the bottom of the related item symbol, all system interface members are shown, but not *their* members.

![](images/5.%20Extending%20System%20Objects%20(Older).006.png)

To also display the members and extension possibilities of another part of the system interface, you have to double-click another ellipsis.

-----

A system interface is the new computer language’s equivalent of __Getters__, __Setters__ and __Property__ procedures. But the new computer language offers a lot more to control the behavior of assigning or retrieving a related object compared to other programming languages.

-----

System Objects implementation,  
2008-07-23

- System object implementation and notation are separate things
    - The extension procedures for related list items must become procedure references, part of the system interface of a related list.
        - \> Actually, internally all system command extensions everywhere are procedure extensions, but in the diagram it is just differently expressed. The internal workings of system objects is different from the way it is expressed in a diagram.
        - \> The system interface of a related list must be extended with all system members a related list item has, but then the members are not callable but only extendable.
- Implementing the tie between related list item and related list:
    - \> If a related items, related lists and related list items get a reference to the parent object, then this makes the system command extensions of the parent object accessible. Each of the system objects’ commands has to be tied to a specific command extension, though.
    For related items and related lists, each system command’s extension is individually assignable. But related list items have the special feature, that they are not individually assignable. Therefore, each related list item as a reference to the related list, that then has a binding to a system procedure extension.
    - I stated, that the related item needed a reference to the list to call the extension procedure of the list object.

JJ

-----

Parameters for System Commands,  
2009-08-31

Parameters for System Commands should also belong to extension, but it is currently inside the System Interfaces article group.

JJ
