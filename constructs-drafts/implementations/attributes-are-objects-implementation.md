Encircle Language Construct Drafts | Implementations
====================================================

Attributes Are Objects Implementation
-------------------------------------

`[ Preliminary documentation ]`

__Contents__

- [Implementation in Creator](#implementation-in-creator)
- [J Math Objects](#j-math-objects)
- [Implementing Attributes as Separate Construct](#implementing-attributes-as-separate-construct)
- [Create Objects / Ensure Objects = Default Values / Not Null ?](#create-objects--ensure-objects--default-values--not-null-)

### Implementation in Creator

You might still be able to see a __Relation Class__ as an __Attribute__. An __IsAttribute Boolean__ in the __Relation Class__ may do. Also, an automatic filter index might be maintained named __Attributes__, which might give the class an __Attributes__ collection.

__Attributes__ might still very much be an application design concept. The only technical remainder in J Data will be that there is a __Class Preset__ called __Attribute__, which gives the __Class__ settings as they are generally expected in an __Attribute__. For more information, see the *Presets* section. The __Attributes__ filter index can also be automatically created by setting the __Class__’s __HasAttributes__ property.

You should also be able to add things to the __Attributes__ collection of the __Class__, or you’d have to define everything in the __Structure.Relation__ collection. Heck, I want to be able to add relations to the __Class.RelatedClasses__ anyway. I could just make __Class.RelatedClasses.Add__ create a __Relation__ in the Structure.Relations collection and return the __Other Relation Class__. When adding to the __Attributes__ collection, I should do the same, but give the added __Relation Class__ the __Attribute Preset__.

To be able to use value filters, you have to be able to filter by an object’s literal value. That should be considered in the *Filters, Sorts, Searches, Joins and Indexes* section too.

It still must be possible to give attributes parameters. That implies that =>1 related objects can get parameters.

### J Math Objects

Simple data types could be replaced by J Math objects. In that case some of the rules for mimicking attributes, will get ignored. The worst one that is ignored is that J Math objects can have relations to other classes. In that case, the binary contents of the object isn’t just the value of the variable anymore, it also contains all sorts of stuff for the related classes, such as __IDs__ for instance.

Attributes might be considered are outermost nodes of the relational structure, the other nodes are intermediate nodes. This phrase is true most of the times, but attributes aren’t bound that tightly to the rules I’ve set out above anymore. You can better say: objects with no relations to other objects are the outermost nodes of the relational structure. Actually: pieces of binary data (target data, not pointers) are outer nodes.

### Implementing Attributes as Separate Construct

`[Dutch]`

Eerder dacht ik ook aan om misschien meteen Attributes Become Classes toe te passen. Maar laat dat nog maar even. Het inrichten van attributen is heel erg gelijk aan het inrichten van related items. Je zou de item class ook 1 string waarde kunnen geven, 1 integer waarde, etcetera. Daarmee kan de item class ook een enkele string of integer representeren.

Toen ik dit probeerde te implementeren in de eerste opzet van Creator 2.0, kreeg ik problemen met de verschillen tussen een object referentie en een uniek object, enzo. Het was in ieder geval erg lastig om het meteen te implementeren, dus ik heb gewoon Attributes apart gedaan.

### Create Objects / Ensure Objects = Default Values / Not Null ?

Comparing Attributes and Objects:

The concept Create Objects might be seen as sort of similar to the Default Value concept (though the two concepts could probably only merge if Attributes are Classes).

The Ensure Objects concept can also be seen as similar to the Not Null concept.