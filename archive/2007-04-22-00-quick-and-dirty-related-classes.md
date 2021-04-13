Encircle Language | Archive
===========================

Quick & Dirty Related Classes
-----------------------------

`[ Deprecated documentation ]`

*Perhaps reading it slowly might help.*

For cItem to adapt itself to a cClass, it among other things traverses the cClass’s Related Classes. C Creator automatically maintains cClass . Related Classes as G Creator specifies its Relations.

*The Related Classes collections that live in the C layer are a reflection of the structure of the __G layer__, not a reflection of the structure of the __C layer__. It is kind of part of the structure description of the G layer, but the C layer maintains it automatically.*

For cItem to adapt itself to a *gClass*  (as opposed to a cClass), gClass also needs a Related Classes collection, but gCreator is unable to maintain Class . Related Classes collections automatically as ggCreator specifies Relations with it, because I can’t use Custom Code yet, required to extend the assignment of for instance  gRelation . Relation Class A .  
So G is unable to maintain the gClass . Related Classes that reflect ggCreator’s  Relations. Therefore, after GG has specified all its relations, it reflects those relations, by adding them to gClass . Related Classes manually.

In GG I insert the Related Classes data *into* the G layer, that *reflects* the data specified in the GG layer.  
So in one layer I fill the Related Classes data *into* the previous layer, but this data reflects the structure specified in the *first* layer.  
In G this is not required, because C automatically maintains its Related Classes as G adds Relations to it.  
In GG you have to insert its Related Classes into G manually, because G is unable to automatically maintain its Related Classes collection as GG adds Relations to it.  
(G might specify a Relation for GG to put the Related Classes into.)  
In GGG you insert its Related Classes into GG manually, in the same way as in the previous layer.  
So in one layer I insert the Related Classes data about the current layer into the previous layer.  
That means in Creator Text Code I have to insert the Related Classes data into the previous layer: GGG, but this data reflects the structure specified in the Creator Text Code.  
Filling in the Related Classes data into the previous layer is called a Quick & Dirty solution, because officially the deeper layer should do that automatically.  
So officially GGG should fill the Related Classes of the Creator Text Code automatically, but because it can't (yet), Creator In Creator Text Code has to do it.  
What might work is, that in parsing a Relation, I automatically add the Related Class to GGG layer. That might take care of it.  
Then a Creator Text Code Creator might result in the same thing as the current gggCreator.