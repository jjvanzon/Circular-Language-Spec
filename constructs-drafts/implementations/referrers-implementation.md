Circle Language Construct Drafts | Implementations
==================================================

Relationships | Referrers Implementation
-----------------------------------------

`[ Out of Scope ]`

*Referrers* is a coding concept. A concept is something programmed inside the new computer language itself, which can extend any object, because it operates using the reflective data of an object, which makes it adaptable to any object.

The __Referrers__ coding concept extends the system interface of any related object with an attribute __Referrer ID in Object. The Object  .  Set__ will be pre-extended with removing itself from the original target object’s list of referrers, using the previously stored __Referrer ID in Object__ attribute. The __Object  .  Set__ also gets post-extended with adding itself to the new target object’s list of referrers. After that the position in this list is assigned as the __Referrer ID in Object__.

The __Referrers__ coding concept also adds a __Referrers__ list to every object. An *object* stores the list of referrers, but a *symbol* can also store its own list of referrers if it is a pointer *pointed to*. Th  __Referrer__ list’s __Add__ method will return the added item’s position in the list, so it can be recorded by the __Referrer__ as a sub-object’s __Referrer ID in Object__.

If an object does not support the concept of __Referrers__, then it will not have a __Referrers__ list.

An object, that does not support the concept of __Referrers__, also will not register itself as a referrer in objects that it references. So that will make the object sort of stealthy, and not known to the objects that it references.

### Diagrams

As explained in the article *Referrers*, the implementation of referrers as a concept requires extension of related item’s  __Object  .  Set__ procedure, so that a referrer is added to the other object’s __Referrers__ list and the __Referrer ID In Object__ is recorded.

The adapted system interface would look something like this in a diagram:

![](images/2.%20Referrers%20Implementation.001.png)

It is just a demonstration of extension of the system interface. Not all the details are shown above. By showing the system interface you can see exactly see how the __Referrers__ list is updated. Fortunately you can hide the system interface, so that it looks simple again:

![](images/2.%20Referrers%20Implementation.002.png)

Showing the system interface gives you a view on the inner workings of the __Referrers__ concept. Further details won’t be discussed here. It is just an example of a concept extending of the system interface.