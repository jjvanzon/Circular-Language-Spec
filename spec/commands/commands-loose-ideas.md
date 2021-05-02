Circular Language Spec | Commands
=================================

Loose Ideas
-----------

`[ Preliminary documentation ]`

__Contents__

- [From the Original Symbol Documentation](#from-the-original-symbol-documentation)
    - [Executions & Parameters](#executions--parameters)
        - [Forming New Subdivision](#forming-new-subdivision)
            - [Old Subdivision](#old-subdivision)
        - [Brainstorm](#brainstorm)
            - [New Brainstorm Texts](#new-brainstorm-texts)
            - [Argument Access Summary](#argument-access-summary)
        - [Commands to Commands, Objects to Object](#commands-to-commands-objects-to-object)
        - [Brainstorm](#brainstorm-1)
    - [Reference and Call Targets](#reference-and-call-targets)

### From the Original Symbol Documentation

#### Executions & Parameters

##### Forming New Subdivision

These seem fragments of an attempt to re-subdivide topics formerly inside the original Symbol documentation from 2004.

###### Old Subdivision

`<< explains other technology >>`

- Differences with Com with returning object references

`<< interpretation >>`

- Inside directly accessible, outside only 'indirectly' accessible (if line set FOR you)
- Seeming randomly referencing diamond members. 

`<< details >>`

- Diamond pointing to another diamond
- Line of connected diamonds change simultaneously

##### Brainstorm

###### New Brainstorm Texts

The problems proposed in this text might have to do with:

`<< details >>`

- Paradox: Parameter assignments involve consults of parameters in prolog of command call, while consults are usually always in epilog.
- Diamond may only represent a single execution per definition call (not regarding unconditional jumps (? The latter is questionable.)

###### Argument Access Summary

`<< details >>`

- Access during execution
    - By owner
    - By child executions (~ is this the proper place for this?)
        - The callees of a diamond can access the caller's members if given references to them

##### Commands to Commands, Objects to Object

`<< already covered >>`

So then object symbols point only to object symbols and command symbols only to command symbols.

However, the picture above is actually again an implicit notation for something else, but I won’t go into detail about that yet.

##### Brainstorm

`<< details >>`

A command might probably not get its own symbol anyway. It might just be an object with an execution point.

A command symbol can define its own command:

![](images/7.%20Commands%20Ideas.064.png)

But if it has a reference line it is regarded no more than a reference or call to a command. The target of the line is considered the command itself or the *definition* of the command.

*A is the reference, B is the definition:*  
![](images/7.%20Commands%20Ideas.065.jpeg)

*A is the command reference, B is the definition:*  
![](images/7.%20Commands%20Ideas.066.jpeg)

| ![](images/7.%20Commands%20Ideas.067.png) | ![](images/Symbol%20Language%20(2004).409b.png) | ![](images/7.%20Commands%20Ideas.068.png) | ![](images/7.%20Commands%20Ideas.069.png) <br> ![](images/7.%20Commands%20Ideas.070.png) | ![](images/7.%20Commands%20Ideas.071.png) |

#### Reference and Call Targets

`<< commands example diagrams >>`

|     |    |
|-----|----|
| ![](images/7.%20Commands%20Ideas.077.jpeg) | __Reference to sibling inactive nested command, in a square.__ <br> Only possible for static command members or exclusive establishment. | 
| ![](images/7.%20Commands%20Ideas.078.jpeg) | __Reference to sibling active nested command, in a square.__ <br> Only possible for static command members or exclusive establishment. | 
| ![](images/7.%20Commands%20Ideas.079.jpeg) | __Call to sibling inactive nested command, in a square.__ <br> This is like a jump to a nested command, that might otherwise not execute. <br> Only possible for static command members or exclusive establishment. |