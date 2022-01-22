﻿Circular Language | Archive
===========================

*JJ van Zon, 2008*

Related Classes
---------------

`[ Deprecated documentation ]`

If the class doesn’t fix the class of a related item, then any type of object can be assigned as the related item.

Also for later:  
Funny enough, in this setting, a collection can be set to have multiple classes, which allows items of all those classes to be added to the collection.

### Class . RelatedClasses

This collection of __RelationClasses__ contains all the classes related to it. If a __Relation__ is not __Dual__, then the class unaware of its relation counterpart might not have its counterpart registered in its __RelationClasses__.

You can’t add __RelatedClasses__ to this collection. You might define relations in the __Structure.Relations__ collection and they might be *reflected* in the __Class.RelatedClasses__ collection.

### Reflecting Relations in Class.RelatedClasses (not Synchronizing)

After a long think and sleeping on it, I’ve decided the following.

I’ve decided that you only edit relations through the __Relations__ collection and not through the __Class.RelatedClasses__ collection. You __*can read*__ the relations through the __Class.RelatedClasses__ collection, but you can’t edit them there.

This is done because it might be quite complex to let __Class.RelatedClasses__ apply to __Relations__ and to let __Relations__ apply to __RelatedClasses__. Many aspects make it hard. One of them is that the items of __RelatedClasses__ are the same objects as those in __Relation.RelationClass()__, so who’s to apply to who?  
Altogether it was far easier to only make __Relations__ apply to __Class.RelatedClasses__.

__RelationClass__ has two methods, __RegisterRelationInClass__ and __DeregisterRelationInClass__, which registers or unregisters the relation counterpart in the class. Calling these at the right times ensures correct reflection of __Relations__ in __Class.RelatedClasses__.

- Relations.Relation.RelationClass(0 to 1).Class Set
    - The counterpart class is unregistered original class.
    - And registered in the new class.
    - If the Relation is not dual then RelationClassB won’t register itself in its counterpart.
- Relations.Add
    - Has no effect, because the classes are yet to be filled in after addition of the relation.
- Relations.Relation.Dual
    - Registers or unregisters the counterpart in ClassB.
- Relations.Remove
    - Removes 1 or 2 related classes, depending on the relation's being dual.

Add or remove of RelatedClasses are Friend, so a programmer can’t do that.  
If you call RelationClass.Class through Class.RelatedClasses, then that should have the same effect as setting it through relations. I can’t really see the effect it might have, but I think it’s not harmful. Dang, my brain isn’t capable of doing complicated things at the moment.

### Brainstorm

Toch wil ik relaties kunnen specificeren binnen een klasse. Zie het instellen van de relaties van Code . Visual Basic . Module met zijn sub objecten.  
Misschien kan ik een eenvoudige oplossing bedenken om het voor een geval als dat makkelijker te maken.