Encircle Language Spec
======================

Black Boxes
-----------

`[ Preliminary documentation ]`

__Contents__

- [Introduction](#introduction)
- [Main Concepts](#main-concepts)
    - [The Black Box Principle](#the-black-box-principle)
    - [Private & Public](#private--public)
    - [Friends](#friends)
    - [Friend Relations](#friend-relations)
    - [Accessible & Inaccessible](#accessible--inaccessible)
    - [Access Controlling System Aspects](#access-controlling-system-aspects)
    - [Summarized](#summarized)
- [Public & Private](#public--private)
    - [Public Set / Access Connectors](#public-set--access-connectors)
    - [Public Get](#public-get)
    - [Private Set](#private-set)
    - [Private Get](#private-get)
- [Friend Declaration](#friend-declaration)
    - [Friend Declaration, in a Unidirectional Relation](#friend-declaration-in-a-unidirectional-relation)
    - [Friend Declaration, in a Bidirectional Relation](#friend-declaration-in-a-bidirectional-relation)
    - [Friend Declaration, Container is Friend](#friend-declaration-container-is-friend)
    - [Friend Declaration, the Contained is Friend](#friend-declaration-the-contained-is-friend)
    - [Mutual Friendship Referential Notation](#mutual-friendship-referential-notation)
    - [Mutual Friendship Containment Notation](#mutual-friendship-containment-notation)
- [Notations of Private](#notations-of-private)
    - [Private in a Definition](#private-in-a-definition)
    - [Private in a Friend Reference](#private-in-a-friend-reference)
    - [Private in a Normal Reference](#private-in-a-normal-reference)
- [Friend Declarations in Instances](#friend-declarations-in-instances)
    - [In a Unidirectional Relation](#in-a-unidirectional-relation)
    - [In a Bidirectional Relation](#in-a-bidirectional-relation)
    - [Container is Friend](#container-is-friend)
    - [The Contained is Friend](#the-contained-is-friend)
    - [Loose Ideas](#loose-ideas)
        - [Objects Take Over Class Access Control](#objects-take-over-class-access-control)
- [Public & Friend Connections](#public--friend-connections)
    - [Public Get Connection](#public-get-connection)
    - [Public Set Connection](#public-set-connection)
    - [Friend Connection](#friend-connection)
    - [Friend Declaration, Connector and Connection](#friend-declaration-connector-and-connection)
    - [Friend Get Connection](#friend-get-connection)
    - [Friend Set Connection](#friend-set-connection)
    - [Loose Ideas about Public & Friend Connections](#loose-ideas-about-public--friend-connections)
- [Access Controlling Aspects](#access-controlling-aspects)
- [Object-Bound, Reference-Bound & Access Control](#object-bound-reference-bound--access-control)
    - [Key Example: Value Get](#key-example-value-get)
    - [Another Example: Use As Class](#another-example-use-as-class)
    - [Object-Bound Access Control](#object-bound-access-control)
    - [Reference can Access Control Object-Bound](#reference-can-access-control-object-bound)
    - [Object has Access to its Privates](#object-has-access-to-its-privates)
- [Assignment between Friend Members](#assignment-between-friend-members)
- [Friend = Wavy Line](#friend--wavy-line)

### Introduction

The concept of *Black Box* is also known as the concept of *Public and Private*. *Private* makes something only accessible inside the object. *Public* makes something accessible outside the object. That way, the inner workings of an object are hidden away and you only work with the input and output.

The code generator version of Encircle (version 0.9) simply borrowed the public and private concept of the target programming language for which code was generated. The *generic module* version of Encircle (version 2.0) did not have any black boxing yet at all. The black box implementation of the version to come is worked out in this documentation folder.

The main articles about black boxing are finished, but you will also find a lot of unfinished material at the end of the documentation, which might be worked out later. Nevertheless, the main idea is worked out completely, and it is clearly denoted which material is not finished.

The idea for the future is that *user* access control and *black boxing* access control will become a single concept of ‘what has access to what’, but that will not immediately be done at first. A simpler black box method is worked out first: one much like what you see in contemporary programming languages. However, this method is adapted to Encircle, because Encircle has a different view on objects and commands. Which commands get access to the private contents of which objects is less obvious, because a command is not part of a specific object or class. In fact, no command gets access to the private contents of an object, unless that command is a *friend* of the object. This creates a tighter bond between the command and the object. Another thing, that is different in Encircle, is that commands are no more than objects. They are the same thing. This really impacts the way you think about black boxing.

### Main Concepts

#### The Black Box Principle

Most computer programming languages make it possible to apply the *black box* principle. Using the black box principle allows you to hide and protect the inner workings of an object. You only get to see some properties, parameters and a selection of commands through which you can control the object while the inner workings are hidden away and protected.

There are two key purposes of the black box principle: data protection and complexity hiding.

Complexity hiding can also be called abstraction.

#### Private & Public

The inner workings of an object or command are its *private* members. You only get to work with an object or command’s *public* members.

So the privates of an object are protected and hidden away, while the public contents can freely be used.

#### Friends

There is no point to private content if it is not used by anything. Even though private contents are protected, *something* needs to access and protect that data.

An object’s public contents can be accessed by anything that has a reference to the object. Private contents can only be used by *friends*. Friends are objects that have access to the private contents of another object.

What other programming languages call class methods, Encircle calls friend commands of a class object.

The object with private contents declares which other objects are its friends.  
The friendship does not automatically go both ways: the *befriended* has access to the privates of the friend, but the friend does not have access to the privates of the befriended. For that you would have to establish a mutual friendship.

#### Friend Relations

A befriended object declares which object is its friend. The friend object needs to be able to access the befriended’s privates. Therefore the friend needs a reference back. So a friend connection requires a mutual relationship.

It is not like one class gets access to the privates of another class. It is more specific than that. A friendship is a relation between specific objects. A friendship between objects applies to only one specific relation. One object gets access to the privates of another object through one specific reference.

Friendship can also be applied to related lists instead of just related items.  
An item or list in a specific relation is typed as friend.

#### Accessible & Inaccessible

Black boxing is based on two simple concepts: *accessible* and *inaccessible*. You can express those concepts as follows:

| ![](images/1.%20Black%20Boxes.001.png) | ![](images/1.%20Black%20Boxes.002.png) |
|----------------------------------------|----------------------------------------|
|               Accessible               |              Inaccessible              |

The concepts are not literally used inside the language, but all the other black boxing concepts are based on it.

The notation of __Accessible__ and __Inaccessible__ *can* be used in abstract diagram expression, though, which does not have to be syntactically correct, but is only used to make a point.

#### Access Controlling System Aspects

Each aspect of a symbol can be separately access controlled. Those are aspects such as:

- __Object__
- __Class__
- __Value__

Each aspect’s __Get__ and __Set__ are separately access controlled, for instance:

- __Object Get__
- __Object Set__
- __Class Get__
- __Class Set__
- __Value Get__
- __Value Set__

So when __Object Get__ is __Public__, you can reference the sub-object.  
When __Value Set__ is __Public__, you can assign a value to the object.  
When __Value Set__ is __Private__, you can not assign a value to the object except through Friend objects.

Only *system procedures* get access controllers. Objects do not get access controllers directly. Access to an *object* is controlled by access controlling the __Object Get__ procedure.

There is not just one kind of __Private__ or __Public__. There is a separate __Private__ and __Public__ for every __Get__ and __Set__ of every system aspect.

#### Summarized

- System aspects of sub-objects are access controlled by their parent object.
- You access control system aspects, making their __Get__ or __Set__, __Private__ or __Public__.
- A normal reference only offers access to the __Public__ content of an object.
- You can type an item or list in a specific relation as __Friend__.
- When a __Friend__ has a reference to an object, all its sub-objects are accessible, even when they are __Private__.
- The full access that __Friends__ get, applies to accessing the direct sub-objects, not deeper sub-objects.

### Public & Private

#### Public Set / Access Connectors

The general notation of an access connector is as follows:

![](images/1.%20Black%20Boxes.003.png)

The sub-object is access controlled by the parent object. The line with the stick at the end is the access connector.

It is also the general notation of a __*Public*__ access connector.  
More specifically: it is a __*Public Set*__ access connector, because it denotes, that you can make it point to something.

#### Public Get

The notation of the __Public *Get*__ access connector is:

![](images/1.%20Black%20Boxes.004.png)

Because this denotes, that you can point *to* it.

#### Private Set

The general notation of __Private__ is:

![](images/1.%20Black%20Boxes.005.png)

The cross expresses ‘inaccessible’ or better said ‘restricted’. Access is restricted to only a limited group of objects: the *friends*.

More specifically: it is a __Private *Set*__ connector, because it denotes that making it point to something else is restricted.

#### Private Get

The notation of the __Private *Get*__ access connector is:

![](images/1.%20Black%20Boxes.006.png)

Because this denotes, that pointing *to* it is restricted.

### Friend Declaration

This article covers friend declaration in several situations.

#### Friend Declaration, in a Unidirectional Relation

The following is a unidirectional relation:

![](images/1.%20Black%20Boxes.007.png)

In the following picture object __A__ is declared *friend* of object __B__:

![](images/1.%20Black%20Boxes.008.png)

Object __A__ can now access anything private of object __B__ through the reference contained inside object __A__.

It is object __B__ who declares itself __Friend__, so object __B__ gives access to its private members.  
But the friend declaration is part of __A__’s reference to __B__, because it makes the reference *special*, using the friend access symbol.

#### Friend Declaration, in a Bidirectional Relation

The following picture expresses a bidirectional relation:

![](images/1.%20Black%20Boxes.009.png)

In the following picture __B__ is declared friend of __A__:

![](images/1.%20Black%20Boxes.010.png)

__A__ can access everything of __B__, even the __Private__ stuff. It does not go both ways: __B__ can only access the __Public__ contents of __A__.

#### Friend Declaration, Container is Friend

In the following picture, a related object is only displayed as contained inside another object:

![](images/1.%20Black%20Boxes.011.png)

To declare __A__ as friend of __B__ you can use the following notation:

![](images/1.%20Black%20Boxes.012.png)

Now __B__ can access everything of __A__.

#### Friend Declaration, the Contained is Friend

In the following picture a related object is only displayed as the container of another object:

![](images/1.%20Black%20Boxes.011.png)

To declare __B__ as friend of __A__ you can use the following notation:

![](images/1.%20Black%20Boxes.013.png)

__A__ can access anything of __B__.

There is no line to place the friendship declaration on. The relation is implied by the fact that something is contained inside something else.

#### Mutual Friendship Referential Notation

Mutual friendship can be expressed as follows in a referential notation:

![](images/1.%20Black%20Boxes.014.png)

#### Mutual Friendship Containment Notation

Mutual friendship in a containment notation would look as follows:

![](images/1.%20Black%20Boxes.015.png)

### Notations of Private

Private access connectors get a different notation in different situations.

#### Private in a Definition

In a definition the private access connector is a cross:

![](images/1.%20Black%20Boxes.016.png)

This is because access is restricted.

__Private Set__ in definition:

![](images/1.%20Black%20Boxes.016.png)

__Private Get__ in definition:

![](images/1.%20Black%20Boxes.006.png)

#### Private in a Friend Reference

Inside a friend reference, a __Private__ member becomes accessible, so the access connector it is displayed using a wavy line:

![](images/1.%20Black%20Boxes.017.png)

Which expresses *accessible*, but only to a select group of objects.

The following diagram expresses a member with __Private Set__ accessible from within the befriended:

![](images/1.%20Black%20Boxes.018.png)

The circle on the right is the definition, so the its member is displayed with a private access connector there (a cross). The access connector within the __Friend__ is different. It is drawn with a wavy line, expressing ‘access conditionally’. In that situation the __Private__ access connector is also called a __Friend__ access connector.

The following diagram expresses a member with __Private *Get*__ accessible from within the befriended:

![](images/1.%20Black%20Boxes.019.png)

You can differentiate the __Friend__ *access connector* from __Friend__ *declarations* because an access connector has nothing at the end of its line.

#### Private in a Normal Reference

In normal references, private members are *not shown at all*.

The following diagram shows a member with __Private Set__ not accessible or visible from in a normal object:

![](images/1.%20Black%20Boxes.020.png)

And that is where the complexity *hiding* kicks in. The circle on the right is still the definition, so it does show the __Private__ member while the normal reference on the left does not show the __Private__ members of its related object.

The following diagram shows a member with __Private *Get*__ not accessible or visible from within a normal reference:

![](images/1.%20Black%20Boxes.021.png)

### Friend Declarations in Instances

The points made in the section *Notations of Private* are demonstrated here again in a different situation, where objects have external definitions. To summarize the rules:

- Privates visible in definitions
- Privates invisible in normal references
- Privates visible in friend references

In this section of the documentation it is demostrated how this looks if objects have an external class, as opposed to defining their own contents and behavior.

The main thing clarified here is: “when do you show privates and when do you not”. The same rules apply here as in traditional text code, but now they are demonstrated in a diagram.

#### In a Unidirectional Relation

![](images/1.%20Black%20Boxes.022.png)

The classes show privates, but the objects do not, unless they are __Friend__.

The effect that you see, is that wavy access connectors stay there in the objects, while cross connectors disappear in the objects. So the main rule is: crosses disappear, wavy lines stay visible.

#### In a Bidirectional Relation

The main point to the diagram below is that the classes show privates, but the objects do not, unless they are Friend. It shows the situation in case of a bidirectional relation.

![](images/1.%20Black%20Boxes.023.png)

The effect that you see, is that wavy access connectors stay there in the objects, while cross connectors disappear in the objects.

#### Container is Friend

The main point to the diagram below is that the classes show privates, but the objects do not, unless they are __Friend__. It shows the situation where the *container* is __Friend__.

![](images/1.%20Black%20Boxes.024.png)

The effect that you see, is that wavy connectors stay there in the objects, while cross connectors disappear in the objects.

#### The Contained is Friend

The main point to the diagram below is that the classes show privates, but the objects do not, unless they are __Friend__. It shows the situation where the *contained* is __Friend__.

![](images/1.%20Black%20Boxes.025.png)

Here something different is going on in the notation. Earlier it was stated that: crosses disappear, wavy lines stay visible. But the picture above contains no crosses at all.

In the classes on the right, something unusual is going on.  
The problem is, that __*A*__ is both a definition and a reference at the same time.

__A__ is:

- a definition

and also:

- __B__'s (__Friend__) reference to __A__.

In a definition it should be a cross. In a __Friend__ reference it should be a wavy line.  
To express the member’s accessibility, the choice was made to display it with a wavy line and not with a cross.

This is simply a side-effect of the notation where *the contained is __Friend__*.

#### Loose Ideas

##### Objects Take Over Class Access Control

Objects take over the access control properties of their class.

< And references take over object-access control. >

... is objects taking over friend relations from classes as straightforward as you’d think?

When it is classes, the friendship counts for all the objects derived from that class.  
Usually, access to procedures is controlled in a *class* and each of its objects adopts those same access settings.

### Public & Friend Connections

An actual connection does not replace the access *connector:* an access connector is always displayed, because others can still connect to the object as well:

![](images/1.%20Black%20Boxes.026.png)

The line at the top is an actual connection.  
The line at the bottom is the access connector.

#### Public Get Connection

A connection to an object, that required a __Public Get__ access, looks like this:

![](images/1.%20Black%20Boxes.026.png)

The access connector stays visible, so that others can also connect to the object using __Public Get__.

#### Public Set Connection

A connection to an object, that required a __Public Set__ access, looks like this:

![](images/1.%20Black%20Boxes.027.png)

The access connector stays visible, so that others can also call __Public Set__ and change the connection of the object.

#### Friend Connection

The general notation of a __Friend__ connection is as follows:

![](images/1.%20Black%20Boxes.028.png)

But remember that the *connector* always stays visible:

![](images/1.%20Black%20Boxes.029.png)

#### Friend Declaration, Connector and Connection

Here the difference is demonstrated between the notations of __Friend__ declarations, __Friend__ connectors and __Friend__ connections. It will also become apparent how their notations disambiguate.

![](images/1.%20Black%20Boxes.030.png)

The friend *declaration* is always shown directly *near* the befriended (the situation at the top).  
The friend access *connector* is always a loose end (the situation in the middle): one end of it is not connected yet. It is a placeholder for possible connections. A friend *connection* (the situation at the bottom) *is* connected at both ends. But the access symbol is placed in front the parent of the target symbol. This is because you always access an object through the parent symbol. The parent symbol can impose access restrictions onto its child objects.

If the friend connection would be an outward connection, no friend access mark would be displayed at all:

![](images/1.%20Black%20Boxes.031.png)

The friend connection shown there is not really a *friend* connection either. It is just a *connection*, an outward *connection*, a *passive* connection. What a releaf that a passive connection does not require an access symbol at all, or it would have conflicted with our friend declaration notation, which looks a bit like an outward connection with an access mark displayed in it, but it is not an access mark; it is a friend declaration.

#### Friend Get Connection

The picture below shows a __Friend__ connection to __Private Get__:

![](images/1.%20Black%20Boxes.032.png)

#### Friend Set Connection

The picture below shows a __Friend__ connection, that required to __Private Set__ access:

![](images/1.%20Black%20Boxes.033.png)

#### Loose Ideas about Public & Friend Connections

< Remembering, that the access connector stays visible has to be addressed in a single section and these explanations should not be bothered with that. >

### Access Controlling Aspects

The diagrams in the previous articles explained the concept of accessing __Public__ or __Private__ members. Those were all demonstrated using the __Object__ aspect. But there are more aspects you can access, such as the __Value__ aspect and the __Class__ aspect. Those can also be made __Public__ or __Private__.

The following sections lay out the workings and the notation of access controlling any of the system aspects. Connectors and connections of the following aspects are covered:

- __Object__
- __Class__
- __Value__
- __Data__
- __Clone__
- __Execute__
- __Existence__
- __Add & Remove__

Each aspect has its own unique behavior.

The __Interface__ aspect is not covered here, because it is covered by the *Interfaces* article group.

### Object-Bound, Reference-Bound & Access Control

For the basics: see *Object-Bound & Reference-Bound* in the *System Interfaces* articles.

#### Key Example: Value Get

If the Value aspect were reference-bound and made read-only by a reference and you could still __Get__ the __Object__, you could assign the __Object__ to another reference and write the __Value__ there. Read-only protecting the __Value__ aspect would be non-waterproof and more like a *suggested* access control, rather than *real* access control. By realizing that the __Value__ aspect is object-bound, you can not make a read-only __Value__ aspect all of a sudden writable through another reference.

Reference-related aspects only count for a single reference and not for the whole object, and can be freely overridden by another reference. Object-bound aspects count for all references and can not be overridden by another reference.

By binding some aspects to the object and some aspects to a reference, each aspect can be safely access controlled without any loop-holes through other references.

#### Another Example: Use As Class

__Use As Class__ is basically an __Object Get__, access-controlled for the specific purpose of using the object as a class. By making __Use As Class__ object-bound it is possible to design the system so that it indeed is not possible to use the object as the source in a class assignment. So things like __Use As Class__ can also be made safe now they are object-bound. When __Object Get__ is __Public__, __Use As Class__ can still be __Private__.

#### Object-Bound Access Control

Object-bound access control is visible through each reference and can be controlled through each reference, but object-bound aspects always apply to the whole object.

Object-bound aspects and reference bound-aspects do not require two separate friend declarations. With one friend declaration the Friend can access the object-bound aspects of the object, and access the reference-bound aspects of its sub-objects. It is like a combo-deal.

#### Reference can Access Control Object-Bound

Even though object-bound aspects are primarily access-controlled by the object, a reference can impose additional access control over them. So object-bound aspects can be access controlled by a parent to further protect what the object can already protect. But that is part of the *Deeper Exclusion* concept, explained elsewhere.

#### Object has Access to its Privates

The parent object automatically has friend access to its own object-bound aspects and to the reference-bound aspects of its sub-objects. That is logical: the object automatically has access to its own privates. The access connectors express potential connections that can be made by other objects and are displayed on the outside of the object.  
(But compared to the traditional approach: when an object has a command (a method), the command must be made friend in order to access the privates of the object.)

### Assignment between Friend Members

A connection or assignment always involves two objects. In a connection or assignment that involves a friend object, the access mark is a wavy line. It is only clear which of the objects are friend-accessed from the friend access *connectors*.

![](images/1.%20Black%20Boxes.034.png)

In the example above both members involved in the connection are friend. It is only clear which objects in the access are friend from the presence or absence of a friend access *connector*.

In the following example, one of the members is public while the other one is private.

![](images/1.%20Black%20Boxes.035.png)

Member m of reference __b__ is __Get__-public. The access mark of the connection is changed to a __Public__ access mark, because the __Get__-access is public, and an access mark expresses the __Get__-access. To see which member involved in a connection or assignment is friend, you should look at the *access connectors* and not necessarily at the access mark on the connection or assignment call.

### Friend = Wavy Line

But why the wavy line? The wavy line is already used within the language to express ‘value’, ‘data’, or ‘content’. Now it is also used to express *friendship*.

Compared to the other line types:

![](images/1.%20Black%20Boxes.036.png)  ![](images/1.%20Black%20Boxes.037.png)  ![](images/1.%20Black%20Boxes.038.png)

The wavy line expresses something special. Wavy is also like the symbol ~, which means approximate or ‘under certain conditions’. And under certain conditions you can access __Private__ members, which are then denoted with a wavy access connector. So it looks *like* a straight access connector (meaning __Accessible__), but then under certain conditions, so the line is wavy. A wavy line expresses *special access*, *conditional access*.

Wavy lines already expressed *value*, *data* and *content*. Using wavy lines in the friend notation lets you access the __Private__ *value, data and content*. So there is a vague parallel there.