Encircle Language Broader View | Exchangeability
================================================

Attributes Are Objects
----------------------

`[ Preliminary documentation ]`

__Attributes__ may very well become __Classes__ in the future. __Classes__ might eventually be capable of being configured to behave just like simple variables.

A __Class__ might look like a simple data type when it has the following configuration:

- Exclusive =>1 relation with the parent
- Containment relation with the parent
- Literal
- Never a pointer, always the object itself
- Always created
- No relations to other objects
- Binary data can be written and read from anywhere

A __Class__ may generally no longer be considered an __Attribute__ type when:

- No exclusive =>1 relation with the parent
- No containment relation with the parent
- It has relations to other objects

If the other aspects are missing, then it might still be generally considered an __Attribute__.

__Attributes__ may stop being separately specified, and might become __Classes__. The __Class__ they are an __Attribute__ of, might have an exclusive 1=>1 relation with the __Attribute__, the __Attribute__ might always be created and never assigned another object reference, but its members can be called and a literal value can be assigned and returned, and (most of the times) the binary contents might be used. And there might even be no attribute types anymore.

C++ might allow an object to perfectly mimic a variable, so that’s really nice.