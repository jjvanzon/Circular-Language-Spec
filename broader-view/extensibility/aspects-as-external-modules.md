Encircle Language Broader View | Extensibility
==============================================

Aspects As External Modules
----------------------------

`[ Preliminary documentation ]`

__Contents__

- [Introduction](#introduction)
- [Brainstorm](#brainstorm)
    - [Generic, Not Generated](#generic-not-generated)
    - [System Structure Elements](#system-structure-elements)
    - [Which Attr- [Introduction](#introduction)
- [Brainstorm](#brainstorm)
    - [Generic, Not Generated](#generic-not-generated)
    - [System Structure Elements](#system-structure-elements)
        - [Which Attributes Exist?](#which-attributes-exist)
        - [How Many Are There?](#how-many-are-there)
        - [How Are They Automatically Added and Removed?](#how-are-they-automatically-added-and-removed)
        - [When Are They Added and Removed](#when-are-they-added-and-removed)
        - [Attribute Roles](#attribute-roles)
            - [No Control Over Retaining the System Attribute](#no-control-over-retaining-the-system-attribute)
        - [N `<=>` N](#n--n)
    - [Loose Ideas](#loose-ideas)
        - [Aspects As External Modules](#aspects-as-external-modules)ibutes Exist?](#which-attributes-exist)
    - [How Many Are There?](#how-many-are-there)
    - [How Are They Automatically Added and Removed?](#how-are-they-automatically-added-and-removed)
    - [When Are They Added and Removed](#when-are-they-added-and-removed)
    - [Attribute Roles](#attribute-roles)
        - [No Control Over Retaining the System Attribute](#no-control-over-retaining-the-system-attribute)
    - [N `<=>` N](#n--n)
    - [Loose Ideas](#loose-ideas)
    - [Aspects As External Modules](#aspects-as-external-modules-1)

### Introduction

Aspects might add something to every class that supports the aspect. The class doesn’t get polluted directly. An aspect might add a sub object operating on the class’s members in a generic way.

What might be desired from Encircle, might be to offer a way to describe any of the aspects that were implemented in experiment 0.9 in text code, and how do I let each class decide which aspect to support. How do I set a default as to which aspects classes should support?

The main part of the text code description of an aspect is the code as generated before, but now with template placeholders in it.  
Shouldn’t be hard. In the code generator version of Encircle, every module decided which aspects to support

< I need to incorporate a story from Software System.doc about aspects about dependencies. >

### Brainstorm

In experiment 0.9 every aspect (for instance Copy-Paste, Default Values and Enums) used to have its own part of the code generator. In a generic version of Encircle, this might translate to every aspect being its own generic part of the engine. It is perhaps easier to program the aspects as part of an engine, rather than part of a code generator, but something might make it even more handy. The aspects might no longer be part of the engine either. They might become external modules, written in perhaps custom code, that might be loaded by the engine and run inside of it.

#### Generic, Not Generated

Instead of generating code for each aspect, each basic aspect gets its own module in the Creator ‘engine’ so to say.

Ik bekijk nu de basale aspecten, en kijk hoe die van gegenereerd, naar generiek kunnen gaan.

#### System Structure Elements

< 2007-10-04 Applies to Extensible Aspects >  
There are several attributes that J Data adds automatically, that aren’t defined by the one building the Structure. There are also other structure elements added by J Data automatically.

In this section I might give an overview of all system structure elements, give information on how they are managed, how they are customized and what you should be aware of.

Everything I mention below about system attributes, also counts for system enums.

System attributes are automatically added and removed from the regular attribute list of a class. That way, system attributes recur everywhere normal attributes occur. By adding them to the normal attributes, a programmer can also freely customize the names of the system attributes.

Being able to appoint an existing attribute to be the system attribute doesn’t have to be possible to me.

##### Which Attributes Exist?

- Name
- Selected
- JType
- Reference Count
    - One for every Reference Counted List the class is in.
- Ids in Lists:
    - To X Lists
    - To N Lists
    - All Lists
    - Shared Lists
    - Selected Lists
    - Registration Lists
    - Reference Counted Lists
- Original IDs in Lists

Currently there is one kind of enum:
- Derived Class Enum
    - One for every inheriting class. It has one element for each derived class.

##### How Many Are There?

There are no limits to the amount of IDs and Reference Counts. For every *relation class* that is N or X, a *class* gets an ID attribute and if it’s a reference counted list, also a __Reference Count__. But you can only have one __Name__ and __Selected__ attribute. __Name__ and __Selected__ are either present or not.

##### How Are They Automatically Added and Removed?

The attributes are automatically added and removed by J Data Structure. A reference to the system attribute is stored in the place the system attribute is created. De attribute stores its position in the attribute list. That way, you can remove the respective attribute from the attribute list again.

##### When Are They Added and Removed

The need for IDs and Reference Counts is pretty clear: it changes with:

- RelationClass.AbstractNumber
- RelationClass.ListType
- RelationClass.OtherRelationClass Existence

Everywhere these variables change, an Apply procedure is called that either adds or removes the ID or Reference Count. The changes of to the dependencies take place in __RelationClass__, but the Attribute is *added* to __*Class*__. This creates no futher complications.

__JType__ is added inside the class when __BaseClassAwareOfDerivedClasses__ and __DerivedClasses > 0__.

The need for the Selected attribute is when a class in a RelationClass is selectable. As soon as the class is selectable in the RelationClass, the class gets a Selected attribute. A count is maintained that says in many RelationClasses the class is Selectable. If it becomes one, then the Selected attribute is created. If it becomes 0 then the Selected attribute is removed.

The Name attribute is important in name linkage. The presence of this property is dependent of LinkByName in a RelationClass. The same mechanism as for the Selected attribute is used.

Currently __OriginalID__ is added whenever __HasOriginalId__ is changed. HasOriginalId can’t be set to False when the ShouldHaveOriginalId  function returns True. __HasOriginalId__ is changed automatically when __RelationClassesThatRegisterInMe__ or __RelationClassesThatSelectFromMe__ change from __0__ to __1__ or __1__ to __0__. See other sections for more information, such as: *Original ID*, *Registration Lists* or *Selection*.

##### Attribute Roles

For every kind of system attribute there is a special attribute role. That gives us a neat Role property for an attribute that identifies what the attribute is for. The role is set to Normal, Name, Selected, Reference Count, Id or OriginalId. That way I can clearly see when something is an ID, even when I’ve changed the name to ‘Pietje’.

###### No Control Over Retaining the System Attribute

A programmer can’t control retaining the system attribute. They are added and removed from the system without an excuse. When a system attribute is removed, you loose the customization of it (when you’ve for instance changed the name of the system attribute). Whether or not that is unhandy for the programmer, all alternatives I can come up with are unhandy in other areas.

##### N `<=>` N

For n`<=>`n, x`<=>`n and n`<=>`x relaties you can’t give the relation classes 1 id. In A 1`<=>`n B, B has an ID in its A. In A n`<=>`n B, B has an ID in every A it exists in.  At the moment I don’t make the IDs system attributes in this case, but I structurelessly generate the dimensional IDs into the code modules.

#### Loose Ideas

##### Aspects As External Modules

Moeten er aspecten bibliotheek bestaan?  
Of: moet een module naast classes en data ook aspecten kunnen definiëren, die vervolgens op gelijk welke gegevensstructuur kan worden toegepast? Moet een aspect een synchrone toepassing kunnen hebben, dus zichzelf opbouwen vanaf dat er nog geen gegevens zijn.

-----

Dit extensible aspects model is een erg aantrekkelijk vlak voor mij. Dit loopt in 1 lijn met *Programming Language Programmed Within Itself* en *Generic not Generated*. In wezen breid je misschien de programmeer taal uit door aspecten toe te voegen. Maar niet alle objecten op de hele wereld implementeren alle aspecten. Dus hoe gaat dat werken?

-----

Kan gegevens als module worden gezien, waarvan de structuur mogelijk uit een andere module komt? Daardoor wordt zowel code als data als module gezien.

-----

De onvoorwaardelijke 'reflectiviteit' van Creator, is het middel voor uitbreiding met aspecten.

-----

You have to note that when something is a coding aspect, and not a coding principle, it doesn’t mean it’s less important for the programming language. It just means that it can be expressed using more basic coding principles using reflective data.  
That might mean that Attributes could become an aspect, and perhaps even that relations could too. Funny. Perhaps I can strip the core even further down.  
Funny. Perhaps object oriented can be defined as an aspect too.  
Deep. Cool stuff.  
Aspect literals is a great help in this as well.

-----

Software System

Het voordeel van dat bepaalde eerst intrinsiek aan de taal zijnde dingen nu als aparte modules implementeer, is dat de complexiteit van het systeem af lijkt te nemen, omdat er een overzichtelijkere groepering en layering is, in plaats van 1 platte laag. En daardoor kun je nog meer features toevoegen en het nog meer uitbreiden, zonder het overzicht te verliezen.

JJ