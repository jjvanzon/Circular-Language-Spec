﻿Construct Drafts | Conversions
==============================

`[ Preliminary documentation ]`

## Loose Ideas

*The texts below are loose ideas, yet to be turned into good documentation.*

### Brainstorm

If the State isn’t assigned to the same type then a conversion might take place. The target type for the state assignment might define the conversion and this conversion is bound to the state source type; for each state source type, the state target type might define a conversion. If the conversion isn’t defined then it’s not possible to assign a state of that type.

Conversions can also be cast explicitly rather than being automatically performed on state assignment.

Conversion commands are considered system commands as well. One type can define multiple conversion commands. The parameter of the conversion command is the source object. A conversion command can also have multiple parameters. That way multiple objects can be converted to a single object, sometimes grouping multiple object of the same type, sometimes grouping a combination of types.

-----

< If you want to convert a number to text then the text object should define the conversion for all this stuff. Hmm… maybe the source object should be able to define the conversion too. >

### Conversions Aren’t Create Commands

This comment is made because in the C++ programming language, conversion commands *are* alternative create commands. A conversion might not involve the creation of an object. A conversion is the assignment of new values to an existing object, values that are based on the values of an object from a different type.

### More Ideas

Conversion,  
2009-05-12

Conversions may apply to assigning object references as well, as well as other types of assignment.  
But in assignment of an object, that might not have the right class, but it might support the right interface should be allowed and not result in conversion. How the two resolutions relate, has to be covered in this documentation folder as well.

It seems, that when type control might not allow the assignment, a conversion command might be available for implicit invocation, or an error might occur.

Conversion commands are not specific to an object. It links to two objects: the source and the target. Because command parameters and object commands are interchangeable, how do conversion commands look in a diagram?

What if you have multiple possible conversion commands? One has to be selected. This has to be disambiguated in that case, through object resolution or explicit conversion. You might not have to do with all the conversion commands in the world, just the ones out of modules you selected.

JJ