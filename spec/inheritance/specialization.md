Encircle Language Spec | Inheritance
====================================

Specialization
--------------

`[ Preliminary documentation ]`

There are four groups of specialization techniques that can be identified. Each will be separately explained:

- *Data Replacement*
- *Altering the Member Set*
- *Detouring Members*
- *Altering Command Implementations*

### Specialization & Data Replacement

You do not need any specialization techniques to alter the behavior of a base object.

![](images/2.%20Specialization.001.png)

Anything inside the base object is just data, that can be changed, including the commands, command calls and member sets. This is all just data that you can change.

![](images/2.%20Specialization.002.png)

One condition though is that the data is accessible.

However, data replacement is not what we usually call specialization. What we call specialization are less destructive methods where most of the data stays in tact.

Some specialization techniques actually replace data, rather than just add it, but they are generally considered less destructive than sheer data replacement. *Data replacement* and *specialization* are two different concepts.

### Altering the Member Set

The easiest group of specialization techniques is *altering the members set*. Three techniques can be identified:

- *Member Addition*
- *Member Exclusion*
- *Member Inclusion*

Each technique is explained in a separate article

#### Member Addition

The easiest technique for specialization by altering the member set is *member addition*. Here the concept of class inheritance is displayed:

![](images/2.%20Specialization.003.png)

Member addition means adding a member, that was not there in the base, but will be in the derived object:

![](images/2.%20Specialization.004.png)

#### Member Exclusion

Another technique for specialization by altering the member set is *member exclusion*. This is not possible in most other object oriented languages. What happens is that members from deeper objects that were formerly __Public__, are __Private__ through the derived class.

![](images/2.%20Specialization.005.png)

This also makes it possible to protect some of the members of the sub-objects, and let the parent object be the only one to control them.

![](images/2.%20Specialization.006.png)

Do note that this protection is dependent on the context, so when you can reference the object from another location, you can still access the excluded member:

![](images/2.%20Specialization.007.png)

You can prevent this by making the __Object Get Private__ while __Object Get For Access__ is still __Public__.

![](images/2.%20Specialization.008.png)

(there is no notation yet for the distinction between __Object Get__, __Object Get For Access__ and __Object Get For Copy__)

#### Member Inclusion

Another technique for specialization by altering the member set is *member inclusion*. This is the opposite of member exclusion. Instead of making a formerly __Public__ member __Private__, you make a formerly __Private__ member __Public__. This seems to go against the rules for encapsulation, but in fact it is valid, since only __Friend__ objects can do it.

![](images/2.%20Specialization.009.png)

### Detouring Members

Detouring members is a group of specialization techniques. These techniques allows a derived class to redefine a member from the base class. This can happen in two ways:

- *Shadowing*
- *Overriding*

Each of them is covered in a separate article

#### Disclaimer

Inheritance makes extensive use of the concepts of overriding and shadowing. However, the notations and implementations of overriding and shadowing are not worked out to perfection yet. Preliminary notations are proposed. They will be reconsidered when working out the chapter *Object Resolution*.

#### Shadowing

A derived class can *shadow* a command of the base class. This means that when you call a base command through the derived object, the derived command is run instead.

Below you see a normal base member and a call to it:

![](images/2.%20Specialization.010.png)

Below you see the situation when the base command is shadowed:

![](images/2.%20Specialization.011.png)

You can still call the base command, by qualifying the call so that the interface is addressed directly:

![](images/2.%20Specialization.012.png)

When the base class itself calls the shadowed command, the original base command is called.

![](images/2.%20Specialization.013.png)

This is where the behavior of *shadowing* is different from *overriding*.

What should be mentioned is that you can also shadow objects, just like you can shadow commands.

*Unshadowed:*

![](images/2.%20Specialization.014.png)

*Shadowed:*

![](images/2.%20Specialization.015.png)

*Access to base member through qualifier:*

![](images/2.%20Specialization.016.png)

*Base class calls base member, not derived member:*

![](images/2.%20Specialization.017.png)

#### Overriding

Base classes normally call their own commands:

![](images/2.%20Specialization.018.png)

But derived classes can redefine those commands. When the base class tries to call its own command, the call is detoured to the redefined command. In other words: the original call to the command is detoured to another command.

![](images/2.%20Specialization.019.png)

The base class can not run its original command anymore, but the command is detoured to a command defined in the derived class.

Overriding is accomplished with simple object redirection.

What should be mentioned is that you can also override objects, just like you can override commands:

![](images/2.%20Specialization.020.png)

What should also be mentioned is that overriding is not specific to inheritance. It can also be done in case of regular containment:

![](images/2.%20Specialization.021.png)

##### Calling Base Class’s Version of Overridden Member

Some programming languages offer a way to call the member defined by the base class, even when the base member was overridden. In the new computer language this is not possible by default, because any call to the overridden member will redirect to the overriding member.

![](images/2.%20Specialization.022.png)

However, there is an alternative: define a base command and create an overridable command that is a reference to the base command.

![](images/2.%20Specialization.023.png)

You can replace the overridable command, but you can still call the base command.

![](images/2.%20Specialization.024.png)

##### Overriding Alternative: Event Notation

An alternative notation to overriding is the override event.

![](images/2.%20Specialization.025.png)

An override event is basically unnecessary, because you can already accomplish that by simple object redirection, but the notation is intuitive, and creates an analogy with the notation for pre- and post-extension, which is introduced later. The notation also offers the possibility to easily express overriding *system* commands, also explained later.

The notation does not seem to work for object overriding.

![](images/2.%20Specialization.026.png)

This is because object overriding redirects to an object, and since events are commands, it looks strange.

##### Discarded Intrinsic Overriding Notation

There used to be an intrinsic overriding notation which looked a lot like shadowing:

*Shadowing notation:*

![](images/2.%20Specialization.027.png)

*Intrinsic overriding notation:*

![](images/2.%20Specialization.028.png)

However, the intrinsic overriding notation was discarded, because it is undefendable to have it when the same is possible with simple object redirection.

### Altering Command Implementations

Another way to specialize a derived object is to *alter* the command implementations of the base object (as opposed to replacing a command entirely).

Several separate techniques can be identified and will be explained in individual articles:

- *Command Extension*
- *System Command Extension*
- *System Command Overriding*
- *System Command Shadowing*

Furthermore there are a some of variations on these techniques which also have a separate article:

- *System Command Extension By Shadowing*
- *System Command Extension By Overriding (Questionable)*
- *System Command Overriding By Extension*

#### Command Extension

When a base class defines a command, the derived class can add extra functionality to the existing command. The derived class can pre- or post-extend a command from the base class:

![](images/2.%20Specialization.029.png)

This pre- and post-extension happens by means of the already available system events explained in the *Events* chapter. The events are actually named __Executing__ and __Executed__.

![](images/2.%20Specialization.030.png)

#### System Command Extension

Another way to specialize a derived object is to let it define extra functionality around a *system* command. The previous section was actually a demonstration of how to extend the implementation of the __Execute__ system command. But *other* system commands can be extended as well, such as the __Value Set__ command. Here is an example where the __Value Set__ command is post-extended by implementing the __Value Changed__ event.

![](images/2.%20Specialization.031.png)

So then the derived class defines something that will be run every time the object’s value changes.

#### System Command Overriding

Overriding was already introduced before, but what is separately mentioned here is that you can override any of the system commands. You can for instance override the __Value Set__ command.

A lot of notations were considered but many were complicated or ambiguous. Easier alternatives are adopted here. 

Here are the two alternatives to a notation for overriding system commands:

*The event notation* 

![](images/2.%20Specialization.032.png)

*System interface with object redirection*

![](images/2.%20Specialization.033.png)

#### System Command Shadowing

Shadowing a system command can only be displayed by opening up the system interface:

![](images/2.%20Specialization.034.png)

#### System Command Extension By Shadowing

You can accomplish command extension by employing the shadowing concept. The idea is that you shadow the base command, executing your own procedure and call the base command from your own procedure.

![](images/2.%20Specialization.035.png)

Note that the call to the base command has to be qualified with the base object.

When anyone tries to call __Value Set__, the shadowing command is run instead, unless someone can qualify the call with the base object.

A benefit of system command extension by shadowing compared to normal system command extension is that these extensions only count inside the derived class.

#### System Commands Extension By Overriding (Questionable)

This is a technique that will not work. The idea is that you accomplish command extension by employing the overriding concept. The idea is that you override the base command, executing your own procedure and call the base command from your own procedure.

![](images/2.%20Specialization.036.png)

The problem with this technique however, is that the call to the base command immediately detours to the derived command again, causing an infinite loop.

However, extending system commands by *shadowing* does work.

#### System Command Overriding By Extension

There is an alternative to overriding: you can implement the pre-extension event of a command and cancel the event.

![](images/2.%20Specialization.037.png)

This cancels the execution of the base command.

### Destructive & Non-Destructive Specialization Methods

Most of the specialization methods are extensions. The extensions are commonly *data* that is *added* to the base system. There are two specialization techniques that do not only extend, but also *change* the behavior of the base:

- Overriding
- Pre-extension with cancellation

These could be considered destructive specialization methods, because they change behavior, while *extensions* are mere non-destructive specialization methods.

