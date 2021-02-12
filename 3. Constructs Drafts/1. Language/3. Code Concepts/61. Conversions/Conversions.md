Computer Language Coding Concepts
=================================

Conversions
------------

## **Ideas**

*The texts below are loose ideas, yet to be turned into good documentation.*

##### ***Conversions***

If the State isn’t assigned to the same type then a conversion must take place. The target type for the state assignment must define the conversion and this conversion is bound to the state source type; for each state source type, the state target type must define a conversion. If the conversion isn’t defined then it’s not possible to assign a state of that type.

Conversions can also be cast explicitly rather than being automatically performed on state assignment.

Conversion procedures are considered system procedures as well. One type can define multiple conversion procedures. The parameter of the conversion procedure is the source object. A conversion procedure can also have multiple parameters. That way multiple objects can be converted to a single object, sometimes grouping multiple object of the same type, sometimes grouping a combination of types.


< If you want to convert a number to text then the text object should define the conversion for all this stuff. Hmm… mayve the source object should be able to define the conversion too >

###### **Conversions Aren’t Create Procedures**

This comment is made because in the C++ programming language, conversion procedures *are* alternative create procedures. A conversion does not involve the creation of an object. A conversion is the assignment of new values to an existing object, values that are based on the values of an object from a different type.

##### ***More Ideas***

Conversion,

2009-05-12

Conversions may apply to assigning object references as well, as well as other types of assignment.

But in assignment of an object, that does not have the right class, but it does support the right interface should be allowed and not result in conversion. How the two resolutions relate, has to be covered in this documentation folder as well.

It seems, that when type control does not allow the assignment, a conversion command must be available for implicit invokation, or an error will occur.

Conversion commands are not specific to an object. It links to two objects: the source and the target. Because command parameters and object commands are interchangeable, how do conversion commands look in a diagram?

What if you have multiple possible conversion commands? One has to be selected. This has to be unambiguated in that case, through object resolution or explicit conversion. You do not have to do with all the conversion commands in the world, just the ones out of modules you selected.

JJ


