If the class doesn’t fix the class of a related item, then any type of object can be assigned as the related item.

Also for later:

Funny enough, in this setting, a collection can be set to have multiple classes, which allows items of all those classes to be added to the collection.

####### Class . RelatedClasses**

This collection of **RelationClasses** contains all the classes related to it. If a **Relation** is not **Dual**, then the class unaware of its relation counterpart will not have its counterpart registered in its **RelationClasses**.

You can’t add **RelatedClasses** to this collection. You have to define relations in the **Structure.Relations** collection and they will be *reflected* in the **Class.RelatedClasses** collection.

##### Reflecting Relations in Class.RelatedClasses (not Synchronizing)***

After a long think and sleeping on it, I’ve decided the following.

I’ve decided that you only edit relations through the **Relations** collection and not through the **Class.RelatedClasses** collection. You ***can read*** the relations through the **Class.RelatedClasses** collection, but you can’t edit them there.

This is done because it would be quite complex to let **Class.RelatedClasses** apply to **Relations** and to let **Relations** apply to **RelatedClasses**. Many aspects make it hard. One of them is that the items of **RelatedClasses** are the same objects as those in **Relation.RelationClass()**, so who’s to apply to who?

Altogether it was far easier to only make **Relations** apply to **Class.RelatedClasses**.

**RelationClass** has two methods, **RegisterRelationInClass** and **DeregisterRelationInClass**, which registers or deregisters the relation counterpart in the class. Calling these at the right times ensures correct reflection of **Relations** in **Class.RelatedClasses**.

Relations.Relation.RelationClass(0 to 1).Class Set

`	`The counterpart class is deregistered origal class

And registered in the new class.

If the Relation is not dual then RelationClassB won’t register itself in 
`	`its counterpart

Relations.Add

Has no effect, because the classes are yet to be filled in after addition of the relation.

Relations.Relation.Dual

`   `Registers or deregisters the counterpart in ClassB.

Relations.Remove

Removes 1 or 2 related classes, depending on the relation's

being dual.

Add or remove of RelatedClasses are Friend, so a programmer can’t do that.

If you call RelationClass.Class through Class.RelatedClasses, then that should have the same effect as setting it through relations. I can’t really see the effect it would have, but I think it’s not harmful. Dang, my brain isn’t capable of doing complicated things at the moment

###### Brainstorm**

- Toch wil ik relaties kunnen specifieren binnen een klasse. Zie het instellen van de relaties van Code . Visual Basic . Module met zijn sub objecten.
  Misschien kan ik een eenvoudige oplossing bedenken om het voor een geval als dat makkelijker te maken.

