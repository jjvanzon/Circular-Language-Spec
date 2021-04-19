Encircle Language Spec | Commands
=================================

Misc Issues
-----------

`[ Preliminary documentation ]`

__Contents__

- [This](#this)
    - [Class . HasThis](#class--hasthis)
    - [Class . This](#class--this)
    - [This](#this-1)

### This

`<< parameters >>` ?

#### Class . HasThis

`<< implementation >>`

This __Boolean__ expresses if the __Item Class__ might have a __This__ property. For more information see the *This* section. 

#### Class . This

`<< implementation >>`

The __This__ member returns the object itself.

#### This

`<< implementation >>`

If you set the __Class.HasThis__ property to __True__, then the class might get a __This__ property, which might return the object itself.

`<< ? >>`

This is particularly handy in __With__ blocks in which you wish to set another variable to the __With__ block object. __Class.HasThis__ is __True__ by default.

- Using class procedures with the THIS argument

Don’t know if I should cover here:

- Using type procedures with the THIS argument (need a good name for the section)


