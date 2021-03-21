Circle Language Construct Drafts | Interfaces
=============================================

Extensive Classification with Interfaces
----------------------------------------

`[ Preliminary documentation ]`

Extensive classification with interfaces might encompass some ideas about how to use interface more where otherwise you might not, so that a more detailed classification of things might emerge. This might be interesting to form some sort of semantic model.

Extensive classification through interfaces is about automatic definition of interfaces, as well as manual definition of interfaces. (Consider the imaginary group-by-source interfaces, which could be suggestions for interfaces to form.).

Perhaps there will be other ways interfaces will be automatically defined.  
Such as mutuality of commands creates mutuality of interfaces.

A grouping symbol based on what a dependent object uses. The interface organization is a little bit automatic that way. If you do not have an interface organization, then you can still see what the various clients are using and perhaps for the overview you may use an interface organization after all.

Perhaps multiple objects have commands that looks similar on the outside. Even without defining an interface yourself, some sort of mechanism or construct might be thought of that might make you able to reference any object that has a command much like it.

Or when multiple objects have a sub-object with the same class, you might reference them as having a mutual type, even when you have not necessarily defined this type yourself.

## Loose Ideas

- Extensive classification through interfaces
    - Each attribute or method can be made an interface 
    - Etcetera.
    - Semantic classification as such.

### Extensive classification through interfaces

You should use interfaces more, to be able to let a new class participate in existing things, such as the ICollection provides.

Then, for instance, you can program classes that can then be used in J Sound as an operator. That's cool.

I never really organized a system as such, but thinking in that way, does lead to extensibility.

Perhaps several object classes could have physically the same attribute, so that an attribute can belong to multiple classes. Perhaps that should be part of inheritance, though. That would be less uncontrolled. (For instance the BackColor attribute can be part of multiple classes. Perhaps BackColor should be something they all centrally relate to.)

### Mutual Commands, Mutual Interfaces

`[ Preliminary documentation ]`

Brainstorm 2010-05-06:

The idea described here might not be what I want in practice. However, perhaps some derived concept could prove its use.

Perhaps you should be able to define some sort of generic interface.  
If you define an interface with a command in it, that has a certain class, perhaps with some sort of mechanism or construct you should be able to reference any object that has a command with that class. You will get in trouble if an object has two commands with the same class, though.

One of the ideas behind this is idea is that objects, that have the same command, because they are both parameters of the command, have a joint interface, to create a relation. But really, they already have a relation, just an indirect relation, which is also a relation.

This idea just does not work. It only works if you assume that a command definition is unchangeable and that class references to the same command actually have to be the same procedure, but it hasn’t. You can have a command referenced twice that has elements to it that can still be redefined.  
When this would not be the case then yes an idea like objects with the same command have a mutual interface could work, but in dynamic circumstances that are possible in the new computer language I just want to forget about it.

#### A command is an interface

If multiple classes can support the same command, then the classes support the same interface: an interface that has only one command. The interface is represented by the command itself. Each command implicitly creates an interface. That is how it is expressed in a diagram too: a command implicitly creates an interface.

![](images/21.%20Mutual%20Commands,%20Mutual%20Interfaces%20(Unfinished).001.png)

You don’t see triangles around the commands inside the circles, that would specify, that it is a separate interface: each command automatically becomes a separate interface. Just like each object also defines an interface; even though there is no triangle directly inside it, it still has an interface.

#### Multiple classes can support the same command

As you could see in the previous section: multiple classes, that support the same command, also support the same interface. Multiple classes supporting the same commands logically seems to create overlap in interface, but it doesn’t look like overlap in the diagram.

![](images/21.%20Mutual%20Commands,%20Mutual%20Interfaces%20(Unfinished).002.png)

There are just multiple imaginary interface definitions (the circles), that each reference a different set of commands.  
So a class referencing multiple commands, referenced by multiple classes, creates a visible interfaces of the class. The visible display of this interface is there, when you display the commands as part of a class, and not when you display the classes as parameters of the commands.