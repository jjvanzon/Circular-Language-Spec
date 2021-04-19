Encircle Language Spec | Commands
=================================

Misc Issues
-----------

`[ Preliminary documentation ]`

__Contents__

- [Command Referrers](#command-referrers)
    - [Command Object Referrers](#command-object-referrers)
    - [Command Definition Referrers](#command-definition-referrers)
- [This](#this)
    - [Class . HasThis](#class--hasthis)
    - [Class . This](#class--this)
    - [This](#this-1)

### Command Referrers

`<< referrers >>`

#### Command Object Referrers

The *Referrers* article explained how an object can be made aware of its referrers. The concept of referrers applies direction to command objects as well.

If a command and its references both support the __Referrers__ concept, then every command reference might register itself in the __Referrers__ list of the target command.

Refer to the article *Referrers* for an explanation on how the Referrers concept works.

#### Command Definition Referrers

The *Referrers* article explained how an object can be made aware of its referrers. A command is an object as well and the __Referrers__ concept already provides a command with *command definition referrers* functionality. An inactive command is the only type of command symbol that can be referenced. Am inactive command symbol can implement the __Referrers__ concept to register every call or reference to it.

When a site hosts a command definition, that is widely used all over the world, you might not want the command definition to register its referrers, because it might be a very long list to maintain. You can turn off the Referrers concept for any command definition.

If another site uses this widely used command definition, the using site could add a command reference to the command definition on the other site. A command reference has its own list of referrers. The using site could then redirect calls and references to its own command reference. Then the using site has a registration of anything on its site that uses the external command definition.

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


