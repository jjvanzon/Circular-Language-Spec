Circular Language Spec | Parameters
===================================

Loose Ideas
-----------

`[ Preliminary documentation ]`

__Contents__

- [Parameter and Argument](#parameter-and-argument)
    - [Brainstorm](#brainstorm)
        - [Other](#other)
- [Public Inactive Clause `=` Command `Out` Parameter](#public-inactive-clause--command-out-parameter)
- [Reading & Writing Parameters](#reading--writing-parameters)
- [This](#this)
    - [Class . HasThis](#class--hasthis)
    - [Class . This](#class--this)
    - [This](#this-1)
- [Other Ideas](#other-ideas)

### Parameter and Argument

*(From the original Symbol documentation)*

Parameters and arguments are the *public* members of a procedure. In a square they’re called parameters. In a diamond they’re called arguments.

![](images/1.%20Relations%20Between%20Commands%20&%20Objects.017.png)

A parameter is never created. An argument is an object that exists when the diamond executes. Therefore, an argument is a real created object, while a parameter is only a blue-print for it.

A parameter is a public member of a definition.
An argument is a public member of a diamond in execution.

-----

- Definitions of the terms parameter and argument

#### Brainstorm

##### Other

Creation and state read and write only apply to object parameters, not to parameters that are procedures.

### Public Inactive Clause `=` Command `Out` Parameter

`<< parameters >>`
But *inactive* clauses might be referenced and made public. If `you make` an inactive clause public, `you might` make it an __Object Out__ parameter: an object `produced or determined` by `the` command. A public inactive clause `might` be a command definition `produced` by another command.

### Reading & Writing Parameters

Before a command `is` run `you can mess about` with `the` parameters `all you want`.

During `the` execution of a command `you can not` read or write `anything`.

After a command `has` executed, `you can not` change `the` parameters, `just out of practical reasons`, because it `is more practical` for `the` parameters to `keep` visualizing `the` state they `were` in after `the` command `was` run.

- Before execution `you can` read and write.
- During execution `you can not` read or write.
- After execution `you can` only read.

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

### Other Ideas

Commands,  
± 2008

The idea of multi-methods and exchangeability between class methods and method parameters is the expressed in textual pseudo-code below:

![](images/1.%20Relations%20Between%20Commands%20&%20Objects.016.png)

JJ

-----

Nice phrase? "how to link objects to a command."

-----

Clauses might have parameters, `just like` command definitions:

![](images/1.%20Commands%20Main%20Concepts.032.png)

-----

Whether a parameter of a command `can` be read or written `at all is` access-controlled. This access control `determines` whether a parameter `is` for instance input or output.

-----

Clauses `are` like command definitions, `therefore` they `can` have parameters `just like` command definitions.

-----

If `you make` an inactive clause public, `you might` make it an __Object `Out`__ parameter: an object `produced or determined` by `the` command. It `might` be an __Object `Out`__ parameter, that `is` an executable object. That `might` work `just fine`.

