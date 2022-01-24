Relationships
=============

*JJ van Zon, 2021*

[back](..)

__Contents__

- [Introduction](#introduction)
- [Relationships Between Classes](#relationships-between-classes)
    - [Related Item with a Class](#related-item-with-a-class)
    - [Related Item Without a Class](#related-item-without-a-class)
    - [Related Lists](#related-lists)
    - [Related List Without a Class](#related-list-without-a-class)
    - [Related List with a Class](#related-list-with-a-class)
    - [Related List with Multiple Classes](#related-list-with-multiple-classes)
- [Bidirectional Relationships](#bidirectional-relationships)
    - [Compared to Unidirectional Relationships](#compared-to-unidirectional-relationships)
    - [1 to 1 Relationship](#1-to-1-relationship)
    - [Relational Ring](#relational-ring)
    - [Lists](#lists)
    - [1 to N Relationship](#1-to-n-relationship)
    - [N to 1 Relationship](#n-to-1-relationship)
    - [N to N Relationship](#n-to-n-relationship)
    - [Relationship with Multiple Classes](#relationship-with-multiple-classes)
    - [Class Relating to Itself](#class-relating-to-itself)
    - [Example](#example)
- [Bidirectional Relationships Between Objects](#bidirectional-relationships-between-objects)
    - [Pairs of Related Objects](#pairs-of-related-objects)
    - [Lists](#lists-1)
    - [Object Related to Itself](#object-related-to-itself)
- [Bidirectional Relationship Synchronization](#bidirectional-relationship-synchronization)
    - [Implementation](#implementation)

## Introduction

This topic aims to introduce the idea that the build up of classes might be viewed as a model of relationships between classes. A notation for bidirectional relationships is suggested. An attempt is also made to describe how relations between classes might compare to relations between objects.

## Relationships Between Classes

One object may relate to another object.

![](images/1.%20Relationships.001.png)

But that might not be what the topic of relationships might commonly be about. It might be more about relationships between *classes* than individual objects.

![](images/1.%20Relationships.002.png)

Relations between classes may determine the configuration of how objects are connected to each other, rather than just loosely tying together arbitrary objects.

### Related Item with a Class

A sub-object inside a class could have a class. This might relate these two classes together.

<img src="images/1.%20Relationships.003.png" width="300" />

When class might set the class for a sub-object like that, the sub-object might only be an object of that specific class.

<img src="images/1.%20Relationships.004.png" width="250" />

__Object B__ might point out a class with a dashed line connected to __Related Class B__. Otherwise, __Object B__'s connection with the solid line might not be possible.

Here another example: an attempt to depict an object and its class with two more related classes. 

![](images/1.%20Relationships.005.png)

The __Class__ might contain two sub-objects, each pointing to another class. The __Object__ might get contents similar to the __Class__. To 'see' the relationships between classes, it might be an idea to focus on the dashed lines.

### Related Item Without a Class

The class of a related item might not be set.

![](images/1.%20Relationships.006.png)

Then any type of object might be assigned as a related item. That might not introduce a relationship between classes. 

### Related Lists

A class may also specify related *lists*. That might be expressed in a diagram with a nonagon symbol:

<img src="images/1.%20Relationships.007.png" width="80" />

### Related List Without a Class

A nonagon might be placed inside a class, which could symbolize a class with a list inside of it:

![](images/1.%20Relationships.008.png)

When no class might be assigned to the list, it might imply that the list could contain objects of any class. No relation between classes might be introduced by that.

### Related List with a Class

When a class might be assigned to a list, it may suggest the list might only contain items of this class.

![](images/1.%20Relationships.009.png)

### Related List with Multiple Classes

There is also the idea that a list might be assigned *multiple* classes, which could mean that items of a fixed set of classes could be put in the list.

![](images/1.%20Relationships.010.png)

In that case one related list may create two relationships between classes.

## Bidirectional Relationships

### Compared to Unidirectional Relationships

The relationships described so far might be *unidirectional*: one way only. A unidirectional relationship between one class and another might look like this:

![](images/1.%20Relationships.011.png)

__Class A__ might have a sub-object of __Class B__. This may create a relationship from __Class A__ to __Class B__.

Relationships might also be *bidirectional:* a two-way street. If one class relates to another, then the other class might relate back to the first class again.

### 1 to 1 Relationship

In the image above __Class B__ might not seem to have a relationship back to __Class A__ yet. The picture below might add that relationship back to __Class A__:

![](images/1.%20Relationships.012.png)

In case of a bidirectional relationship if one class gets a sub-object of another class, the other class might also get a sub-object pointing back.

### Relational Ring

Because the class references back and forth seem so closely related, an addition to the notation is proposed here. The two class lines may be joined together with a relational ring:

![](images/1.%20Relationships.013.png)

The picture above might express a __1__ to __1__ relationship between __Class A__ and __Class B__.  (The relational ring's being dashed might just be a stylistic choice.)

### Lists

Other multiplicities might also be used. A multiplicity of __n__ might be expressed with a nonagon:

<img src="images/1.%20Relationships.014.png" width="100" />

A nonagon might represent a list of things.

### 1 to N Relationship

There may be __1__ to __n__ relationships between classes. Instead of letting a __Class A__ contain a single item of __Class B__, it may contain a list of items of __Class B__:


![](images/1.%20Relationships.015.png)

The picture above aims to express a bidirectional __1__ to __n__ relationship between __Class A__ and __Class B__. In that case one class may have a list of items of another class. The other class might have a single item, that connects back to the first class.

### N to 1 Relationship

The picture below aims to display a bidirectional __n__ to __1__ relationship between __Class A__ and __Class B__.

![](images/1.%20Relationships.016a.png)

### N to N Relationship

There may also be bidirectional __n to n__ relationships, where one class might hold a list of items of another class, and the other class might also hold a list of items, that connects back to the first class. The picture below aims to display a bidirectional __n to n__ relationship between __Class A__ and __Class B__.

<img src="images/1.%20Relationships.016b.png" width="300" />

### Relationship with Multiple Classes

There is an idea where one list might contain items from multiple classes. __Class A__ might have an __n__ to __1__ relationship to items of __Class B__ and __Class C__, of which the picture below aims to express a bidirectional version:

![](images/1.%20Relationships.017.png)

### Class Relating to Itself

A class may relate to itself. For instance, a person might relate to a parent, which could also be a person. So then a person might be related to a person, which might relate the person class to itself.

A class with a bidirectional relationship to itself could look as follows in a diagram:

<img src="images/1.%20Relationships.018.png" width="150" />

### Example

Classes and their relationships might define behavior of a system, so it might be relevant to be aware of them, instead of looking at individual objects, tied to other objects. The example below could be a piece of the class-relationship structure of a drawing program. It aims to display the classes __Application__, __Document__, __Point__ and __Line__ and the bidirectional relationships between.

![](images/1.%20Relationships.019.png)

The example attempts to display all the classes, relationships, related items and related lists of the class structure. Here might be an attempt to describe with text the classes and relationships that might be drawn out in the picture. A running __Application__ could hold multiple open __Documents__. So __Application__ could have a __1__ to __n__ relationship with the __Document__ class. Viewed in the opposite direction, this could make a __Document__ reference the single __Application__ it might be opened in. A __Document__ might hold a collection of __Points__ and a collection of __Lines__. That might make __Document__ have a __1__ to __n__ relationship with __Point__ and a __1__ to __n__ relationship with __Line__. Inversely, this might make a __Point__ or __Line__ point out one __Document__ it belongs to. Furthermore, a __Line__ could be composed of two __Points__: __Point A__ and __Point B__. The idea is that __Points__ could be reused in multiple lines. Perhaps a bit creatively, these became collections inside a __Point__ called __As Point A in Lines__ and __As Point B in Lines__. It may be a bit non-obvious that it might be a __1__ to __n__ relationship, involving lists of lines.

## Bidirectional Relationships Between Objects

Relationships between *classes* might set guidelines for how objects could connect to each other. Relationships between *objects* could be the *actual* connections between objects.

### Pairs of Related Objects

One idea about bidirectional relationships between objects might be: for each reference to an object, the other object might contain one reference back. 

Drawing out the separate counterparts of a relationship between two objects might look like this:

<img src="images/1.%20Relationships.020.png" width="270" />

To express the closeness of the relationship between the two objects, a relational ring may be placed around the two lines:

<img src="images/1.%20Relationships.021.png" width="270" />

The bidirectional relationships between objects all seem to be __1__ to __1.__ That might be a bit of a bold statement. And it might be just one way of looking at it. But here the idea is entertained that when one object might refer to another, the other one might refer back to the first one.

### Lists

Bidirectional __1__ to __n__ and __n__ to __n__ relationships between classes might result in multiple __1__ to __1__ relationships between objects.

1 to n:

<img src="images/1.%20Relationships.022.png" width="270" />

A multiplicity of __n__ may create a list inside a class. In objects these lists might contain separate items. Any item in the list references an object and that might give the other object *one* reference back again, in case the relationship is bidirectional.

For __n__ to __n__ relationships it may work similarly:

<img src="images/1.%20Relationships.023.png" width="270" />

### Object Related to Itself

Sometimes an object might relate to itself. For a bidirectional relationships this might look as follows:

<img src="images/1.%20Relationships.024.png" width="110" />

## Bidirectional Relationship Synchronization

In a bidirectional relationship between classes, one class might relate to another, and the other class might relate back to the first class. But that might not be enough.

An object of one class might refer to an arbitrary object of another class, which then might refer back to an arbitrary object of the first class again, but not necessarily the object we started with.

<img src="images/1.%20Relationships.025.png" width="320" />

Two unidirectional relationships might not be synchronized with each other. It might not make the two objects refer to each other. It might just make the two objects refer to an arbitrary object of the other class.

To see to it one object relating to another might make the other object relate back to the first object again, it might be useful for the two counterparts of the relationship to be synchronized.

<img src="images/1.%20Relationships.026.png" width="240" />

The tell-tale sign in a diagram, that a bidirectional relationship might be *synchronized*, could be a relational ring around lines.

When a sub-object's target might then be changed, the other side of the relationship might also be updated.

<img src="images/1.%20Relationships.027.png" width="320" />

*Relationship synchronization* might mean ensuring the integrity between the two counterparts of a relationship. For example, when a __Lid__ might be assigned to a __Jar__, the __Jar__ might also be assigned to the __Lid__.

As such, a bidirectional relationship might have three parts:

- One class has a sub-object of another class.
- The other class has a sub-object of the first class.
- The two unidirectional relationships may be synchronized.

### Implementation

The idea might be that that there might be software libraries that have code that make the relationship synchronization work. Circular Language Spec currently only aims to supply a notation for it. There should be freedom of choice how it might be implemented. The notational choices made here, and implementation details might not always resonate with each other. Variations on notations may be possible. The one described here might just lay a foundation.

The implementation commands for relationship synchronization might be expressed in a diagram, when a *system interface* of a symbol might be displayed.

<img src="images/1.%20Relationships.028.png" width="420" />

System interfaces might be like the inner workings of a symbol. Those inner workings might be tucked away and not always visible. System interfaces may have a chapter on their own. The picture above might just be an impression of what that might look like. There might be more than one way of doing it.

[back](..)