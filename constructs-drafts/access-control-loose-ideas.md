﻿Construct Drafts | Access Control Loose Ideas
=============================================

`[ Draft ]`

__Contents__

- [Loose Ideas](#loose-ideas)
- [Access Control](#access-control)
    - [Read Only](#read-only)
    - [Authorization](#authorization)
    - [Public Creatable Classes](#public-creatable-classes)
- [Attribute . HasGet](#attribute--hasget)
- [Attribute . HasSet](#attribute--hasset)
- [Attribute . WriteAccess](#attribute--writeaccess)
    - [Class . PublicCreatable](#class--publiccreatable)
    - [Class . Name Properties](#class--name-properties)
- [Loose Ideas](#loose-ideas-1)
    - [Access Control](#access-control-1)
- [Automatic Containment And Access Control](#automatic-containment-and-access-control)
    - [Excluding Add, Remove or Clear from Programming Interface](#excluding-add-remove-or-clear-from-programming-interface)
- [More Ideas](#more-ideas)
- [From the original Symbol documentation](#from-the-original-symbol-documentation)
- [More Ideas](#more-ideas-1)
    - [Brainstorm](#brainstorm)
- [Loose Ideas](#loose-ideas-2)
    - [Security & Safety](#security--safety)

## Loose Ideas

(Access Control used to be intrinsic principle.)

- Encryption
- Object = User, User = Object
- Access Literals
- Over System Methods
- From certain object oriented perspectives
    - Parent
    - Interface Parent
    - Etcetera
- Global
- Certain levels up

-----

Access Control,  
2008

A lot of things about the system interface could be access controlled. Access control might only be worked out in the future. You might however mention it in the documentation in multiple places, where access control could be applied. Maybe refer to the access control documentation, but also maybe mention the access control’s physical effect.

An idea for access control documentation, might be that you could consider the ability to access control disparate little aspects of the system interface.

JJ

-----

Access Control, Public & Private,  
2008-06-08

Public and private are actually part of access control.  
Access control determines what objects can see what content of another object.  
Content of an object, that can only be seen by the object itself is called private content of the object. Public content of the object is what can be seen from the outside by any other object.  
But if one object decides things are visible to any other object, a parent object can decide to put more restrictions on the access, so that not all other objects can access the public contents of another object.

I’ve often brainstormed about this. About making public and private not part of access control, because access control might be user bound and public and private might just be there to turn something into a black box. But if you approach users as objects with certain access privileges, you can make an analogy. Content accessible only to the object itself are private contents of an object. Content accessible to other objects are public content, but access to this content can be further restricted by a parent object.

Private and public do have more of a function as complexity-hiding.  
But that is just another point to access control. Access control is not only there to make certain people not able to do certain things. It is also there for complexity-hiding, to make it easier on people, making sure they don’t see irrelevant details that obscure the picture.

However, this complexity hiding is very welcome in the diagrams, because it hides the complexity of a command, so you only see a name of a command and some parameters.  
However, before access control is implemented, you might just see the private contents of a command wherever you can call it. Tough.

JJ

## Access Control

Access Control in Creator currently means the following things:

- Certain commands in the code Creator generates, can be access controlled by the author of the structure. 
- On top of that, the *existence* of Property Get and Property Set can be controlled for attributes.
- Also certain things can be made read-only or inaccessible to the *user*.

Access controlling commands means that you can give commands one of the following access modifiers:

- Private
- Friend
- Public

The commands that can be access controlled are:

- __JAttribute.WriteAccess__ : 
    - Sets the attribute’s Property Set command acces modifier
- __JAttribute.ChangeByUser__ : 
    - Controls if the user can change the attribute
- __When1.ReadAccess__ : 
    - Access controls the =>1 related object’s Property Set command
- __When1.WriteAccess__ : 
    - Access controls the =>1 related object’s Property Set command
- __WhenN.ReadAccess__ :
    - Access controls List.Item.Get. So if items in a =>n relation can be read.
- __WhenN.WriteAccess__ :
    - Access controls List.Item.Set. So if items in a =>n relation can be set to another object.
- __WhenN.AddAccess__ : 
    - Access controls a Lists’s Add method
- __WhenN.RemoveAccess__ :
    - Access controls a Lists’s Remove method
- __WhenX.ReadAccess__ :
    - Access controls the =>x related List’s Item.Get command. So if items in a =>x relation can be read.
- __WhenX.WriteAccess__ : 
    - Access controls the =>x related List’s Item.Set command. So if items in a =>x relation can be set to another object

And then there’s __JAttribute.HasGet__ and __JAttribute.HasSet__, which control the presence altogether of a __Property Get__ and __Property Set__ for an attribute.

Furthermore, you can separately control access by the user for two things:

- JAttribute.ChangeByUser
    - Controls whether a user can change the value of an attribute or not.
- WhenN.AddAndRemoveByUser
    - Controls whether a user can Add and Remove items in a related list.

It is the intention for the programmer to be able to access control most commands that might otherwise be __Public__ and also separately control access from the user interface to those commands. Also, the programmer might be more able to leave out certain commands altogether, like you can with the attribute __Get__ and __Set__. For instance, the __Add__, __Remove__ and __Clear__ methods in a =>n related list, should become separately access controllable as well as separately excluded.

### Read Only

- Commands
- By User

### Authorization

Nothing has been thought of to control access for different users. That’s quite important, I think. This subject should be thought about. It might probably might get a place in Access Control, for it *is* Access Control, but on a much different level than Public, Friend and Private.

### Public Creatable Classes

A common way of accessing an object structure is by accessing it through one or more global objects and access all other objects from there. You can also allow an application to create object of classes and access a portion of the object structure from there. Internal in the software module that contains a class, the class can already be created. You can’t put a plug in that. Whether or not a class can be created by another software module, you might specify for each class. Make the __Class.PublicCreatable = True__ and the class might be publicly creatable. By default classes are not public creatable.

## Attribute . HasGet

This Boolean property sets or returns whether the attribute might get a __Property Get__ command at all in the generated programming interface. If __HasGet = False__, then the attribute is also completely write-only anywhere else in the system, including the user interface. It might also be write-only within the class itself, so can not be read at all.

For more information, see the *Access Control* section.

## Attribute . HasSet

This Boolean property sets or returns whether the attribute might get a __Property Set__ (or __Let__) command at all in the generated programming interface. If __HasSet = False__, then the attribute is also completely read-only anywhere else in the system, including the user interface. It might also be read-only within the class itself, so can not be written at all.

For more information, see the *Access Control* section.

## Attribute . WriteAccess

This property sets the write access to the attribute property in the programming interface generated by J Data. Setting it to __PublicAccess__, __PrivateAccess__ or __FriendAccess__ changes the access modifier of the __Property Set__ command in the programming interface.

For more information, see the *Access Control* section.

### Class . PublicCreatable

Setting __Class.PublicCreatable__ might see to it that the __Item Class__ might be creatable outside the generated system.

For more information see then *Public Creatable Classes* section.

### Class . Name Properties

__Class__ contains a lot of properties to specify the name of the class and to specify for instance the name of the __Item Control__, the __Item Class,__ the __Item Window__ and file names for the Visual Basic code modules.

Class contains the following name properties:

- Name
- NamePlural
- NameIsolated
- DisplayName
- DisplayNamePlural
- ItemClassName
- ItemClassDisplayName
- ItemClassFileName
- ItemControlClassName
- ItemControlClassDisplayName
- ItemControlClassFileName
- ItemWindowClassName
- ItemWindowClassDisplayName
- ItemWindowClassFileName
- ItemMdiChildWindowClassName
- ItemMdiChildWindowClassDisplayName
- ItemMdiChildWindowClassFileName
- DefaultItemControlObjectName
- DefaultItemObjectName
- DefaultListName
- DefaultListDisplayName
- ItemControlBaseObjectName

When you don’t separately specify names for the `Item Control` or `Item Window` for instance, these names are derived from more general names, like `Class.Name` and `Class.NamePlural`.

For more information see the *Names* section.

## Loose Ideas

### Access Control

Misschien moet elke access modifier / access control specifier wel altijd per object een eigen interface creëren. Je kunt interfaces toch laten overlappen. 

-----

JCode: being able to see the source code, but not change it. That's handy for supplied components.

-----

Function failure due to security restrictions are things on which a function can fail without there actually being an error in any code or logic. I’m sure that a methodology can be devised that might make error handling in these cases unnecessary, though.

-----

Public for sub components, but private for super components.

-----

The problem is, that the idea was to implement it as an aspect, but it’s important to make the access control not easily breached, and I’m not sure how I might do that.

## Automatic Containment And Access Control

Automatic encapsulation structure might impose a problem in Access Control. An access modifier is related to the position in the encapsulation. The base of the system has only a referential structure. Everything is basically accessible at any level. Anything is potentially global. But when you convert it to an encapsulation structure, not everything is global.  
When you see the encapsulation structure, you can impose an access restriction based on the position in the encapsulation structure, but if you change the underlying referential structure, the symbol gets a different position in the hierarchy, perhaps a higher one, making it all of a sudden accessible on a higher level. On one hand this is required: higher objects make use of the object. But that means everything is basically public, because you can use anything. As soon as you want to use it, it is placed on a higher level in the hierarchy. There are no restrictions there. What you might be able to do in Access Control is actually fix the relative encapsulation position, so it can’t be made any higher, and then impose an access modifier based on hierarchical position.  
But access modifiers are for later, but anyway, that was a good idea about it.

-----

With access control you make an object accessible only:
- *through* a certain other object or
- *to* certain other objects or users

-----

Classes giving methods access to their private contents should be a form of access control.

### Excluding Add, Remove or Clear from Programming Interface

You can exclude the __Add__, __Remove__ and __Clear__ methods with the __HasAdd__, __HasRemove__ and __HasClear__ structure settings. You can also merely access control the __Add__, __Remove__ and __Clear__ methods. That way you can disallow calls to the commands from outside your library or application, so only your application can __Add__, __Remove__ or __Clear__, but any program, that links to your application, can’t. That might be the situation when you give a method __Friend__ access. You can also make the method __Private__, in case of which only commands within the list class itself can access the method. See the *Access Control* section for more on this subject.

Consider access control of the system interface members.
Perhaps you just might talk about access control in the implementation articles of Coding Aspects and all.

-----

A command extension event is not a multi-cast event, like most events. There can be only one implementation of a command extension event.  
The parent object is the only one that can implement the system command extension event. This is has to be access controlled.  
Access control is worked out later in the *Access Control* articles.

-----

Access Control

A lot of things about the system interface needs to be access controlled. Access control might only be worked out in the future. You do however might mention it in the documentation everywhere, where access control has to be applied. Refer to the access control documentation, but also immediately mention the needed access control’s physical effect.  
Do put in the preliminary access control documentation, that you need to consider everything about access control in the system interface.

-----

Access Control,  
2008-08-18

The private contents of a call are only visible to users, that are declared friends of the command definition. But that’s a topic for the Access Control articles.

JJ

-----

Access Control,

Restrictions on how large a bulk over data may be transmitted in one blow, or how much data per how much time.

JJ

-----

Access Control,  
2008-06-16

Usage quota's are essential in security now, because otherwise a user programming something could bring a remote module down.

JJ

-----

Security,  
2008-08-06

Macro beveiliging:
- Alleen lees-acties toestaan
- Ook verzend (e-mail, HTTP) acties toestaan
- Schrijfacties toestaan  
  (= access control want je geeft schrijf toegang tot een bron)

JJ

-----

Access Control,

Even though logging into the internet gives you automatic access to certain sites, with your access cards or tickets displayed at the bottom-right corner of the screen, you might also choose to click it in order to actually access the site. This sort of gives you the idea of actively entering something. Perhaps you want to see yourself as the user of a module, and only sometimes, when you click your access card, you get to be an author of it, and see more of its internal structure and the comments.

JJ

-----

But for security it is always important to consider: who's supervising the supervisors of the supervisors? who might manipulate the supervisor. Who might try to go around the supervisor? But further security issues are for later.

-----

Command IO,  
Security & Privacy,  
2008-07-14

Sometimes an executable object might not need to be open about what it reads or writes. It should be able to apply privacy to data, owned by the site, or the user. This to protect the design of the data model. You might not expose your data model.

However, when it is the user or site's OWN data, you might be completely open about what a command might read or change.

Then the data model stores data, that is the user's OWN data, the data model should be completely open, as far as reporting command IO to the user.

You could say: an authoring company might not expose the data model of its programs, even when it is the user's own data. But strong security with a user choice based on command IO requires the data model to be open.

You might look at the belangen of the user and the author of the software: It is the software author's data model, but it is the user's own data, so why should a software author not be completely open about what it might with the user's data.

It is like a user has to have access to the data of its own file. Compare it to  medical data, and an employee's file. The employee or patient has the right to look into this data.

The software author should not have too much of a choice about what data models it might protect. If it's the user's own data, the software needs to be completely open about a command's IO.

If a software author can keep any data undisclosed, it takes away the security aspect. Open Command IO shields malicious software, spyware, adware and viruses.

It remains to be exactly determined how the system can even see whether it is a user's own data or for instance another company's private data.

All this is for later. It is security and privacy. It won't be further elaborated in the project Command As An Aspect.

JJ

-----

Access Control,

< This issue is replaced by access control. >

The following is unclear. A View is something with which you view something, but can also be an editor. To distinguish view and editor you use the terms view and editor. Now... these terms are about the user interface. You can also have one programming interface be read only, while in another programming interface you can also edit the data. How should I call those? How should I call the editable one?

I can't call it editor, because that suggests that it is a user interface...

JJ

## More Ideas

Access Control,  
2008-09-09

In a capsule, everything that goes in and comes out goes through an encryption, so that everything in it looks fuzzy on the outside, when you do not have the key. You could literally display the fuzziness, so the aspect of encryption is visualized.

JJ

-----

Access Control,  
With Conditions,  
2008-09-06

No dual relations allowed WITH objects with type command.

JJ

## From the original Symbol documentation

Assumptions about access controllers, for instance:

![](images/Access%20Control%20Ideas.001.png)

This for some reason implies that it’s ONLY accessible from the inside. Formally, the access symbol denotes that it’s simply accessible and that this access controller is imposed by the square.

-----

< 2008-10-09  The idea back in 2004 of the expression of access controllers in a diagram was, that the controller was placed in front of the symbol, that *imposed* the access control. I really should not consider this for basic black boxing, but I should consider this, when I work out the more generally applicable access control. >

-----

2004,

Accessing public objects is no longer ambiguous if you use access symbols just outside the border of the parent.

JJ

-----

2004,

Maybe a private access symbol should be inside the capsule somehow.

Perhaps change the symbol.

De lijnen van aparte public symbols aan elkaar plakken en line naar object naar samengesmolten public symbol doen wijzen.

JJ

## More Ideas

Security may be an extension to Symbol access control. But then with users. I guess a specific symbol that the user owns gets friend privileges...

### Brainstorm

Bij een absolute integratie van programmatische access modifiers en user access control, moet je een user-under-user principe toepassen, waarbij elke sub-user de access verder kan beperkt. Elke class en command is daarbij ook een user. De access kan ingesteld worden voor alle users (object/gebruiker) (public, private) en users met bepaalde eigenschappen of verhoudingen tot deze 'user' (friend, protected). Dus toegang wordt daarbij verleend voor bepaalde users tot bepaalde users. Een gebruiker wordt daardoor ook een object. Dit user object heeft dus bepaalde eigenschappen, waardoor hij tot bepaalde andere users/objecten wel of geen toegang krijgt. De rights van een user worden nooit door hemzelf bepaald. De toegang tot zijn eigen dingen wordt wel bepaald door hemzelf, en door containers of referrers, maar dan alleen de toegang tot deze objecten via de container. Alle andere toegangswegen zijn open, tenzij ze dus weer door een hoger object worden geblokt. Dus als je toegang regelt op het object boven het hoogst containende object, dan is het afgeblokt. Het hoogst containende object is eigenlijk altijd de owner.

De administrator heeft alle rechten. Dat wil niet zeggen, dat hij zijn eigen privileges kan bepalen. Niemand bepaald de privileges van de administrator: die liggen vast.

Verder moet zo'n access systeem niet alleen mooi georganiseerd zijn, maar ook nog eens werkelijk veilig, en liever niet kraakbaar.

-----

Security & users:  
Why on earth you might login everywhere, why can’t you be a single user on the internet, and you’ve got access rights. The access rights to a certain site are just added to your rights.

## Loose Ideas

Security & Safety,

There's no way in windows something is going to check what an executable actually performs. Whether is contains instructions to delete files or anything. You CAN build that into the Software System as a security feature.

JJ

### Security & Safety

Security is now present at the heart of the system. It is intrinsically part of the Code. It is not a module of Code, but it is very present in it. The access modifiers Public and Private are actually a security feature now. There is no distinction between user access control and programmatic access modifiers. They are both about who can access what out of what position.

The Aspect Literals feature of code makes it possible to integrate security keywords into the programming language.

-----

Access Control,  
2008-06-10

A user is also an object, that has private content, that it can make public.

Every form of grant to access is given to an object in the form of a virtual access card or ticket. Tickets expire sooner than access cards. The tickets and access cards form the access control descriptor for what is accessible to an object.

An object describes what kind of options you might have on your card or ticket in order to get access.

Objects have their own security relations. A user-object is an object with certain access, but sees the objects' restrictions to each other. What's that about? How might that work?

JJ