Circular Language Broader View | From Spec | Parameters Broader View | Relations Between Commands & Objects
===========================================================================================================

`[ Preliminary documentation ]`

__Contents__

- [Concept](#concept)
    - [Object Relations](#object-relations)
    - [Class Relations](#class-relations)
- [Diagram](#diagram)
    - [Object Relations](#object-relations-1)
    - [Class Relations](#class-relations-1)
- [Use This](#use-this)
    - [Out of Commands & Classes Loosely Coupled](#out-of-commands--classes-loosely-coupled)
        - [Inactive Command References](#inactive-command-references)
        - [Local Variables](#local-variables)

## Concept

A command can contain a set of related objects. Those are the parameters of the command. A command might use objects to do its work.

A parameter is an object related to a command.

The relation is bidirectional. When an object is a parameter, then the object also contains a reference back to the command.

There is complete exchangeability between a command’s parameter and an object’s command.

Commands are special objects, that just happen to be executable. That is why the concept of relations applied to commands and objects, result in the concept of parameters.

You can view a system as being a flat set of commands, that take objects as parameters. You can also view a system as being a set of objects, that have a set of commands inside of them them. Procedural and object oriented are completely interchangeable in this system.

Multiple commands can have the same object filled in as a parameter.  
Then the object might contain all of those commands.  
These two perspectives on it are completely interchangeable.

A command can contain multiple objects.  
Then the command becomes part of all of those objects.  
These two perspectives on it are completely interchangeable.

In other programming languages, an executed command is considered part of *one* object, while in Circular the same execution of a command may as well be part of multiple objects. A command might be part of any object, that is an argument of the command. 

### Object Relations

So when you’ve passed an object to a command, the command automatically becomes visible inside the object as a runnable command.

### Class Relations

But in case of a command definition, a parameter is usually not filled in yet, but the class of the parameter *is* filled in. It is a relation between classes, instead of a relation between objects. This automatically makes the command definition available from the parameter’s class. There is complete exchangeability between the class of a parameter and a command of a class.

## Diagram

A parameter is an object related to a command.

![](images/1.%20Relations%20Between%20Commands%20&%20Objects.001.png)

The relation is bidirectional. When an object is a parameter, then the object also contains a reference back to the command.

![](images/1.%20Relations%20Between%20Commands%20&%20Objects.002.png)

There is complete exchangeability between a command’s parameter and an object’s command.

![](images/1.%20Relations%20Between%20Commands%20&%20Objects.001.png)
![](images/1.%20Relations%20Between%20Commands%20&%20Objects.003.png)

Commands are special objects, that just happen to be executable. That is why the concept of relations applied to commands and objects, result in the concept of parameters.

![](images/1.%20Relations%20Between%20Commands%20&%20Objects.004.png)

You can view a system as being a flat set of commands, that take objects as parameters.

![](images/1.%20Relations%20Between%20Commands%20&%20Objects.005.png)

You can also view a system as being a set of objects, that have a set of commands inside of them them.

![](images/1.%20Relations%20Between%20Commands%20&%20Objects.006.png)

Procedural and object oriented are completely interchangeable in this system.

Multiple commands can have the same object as a parameter.

![](images/1.%20Relations%20Between%20Commands%20&%20Objects.007.png)

Then the object might contain all of those commands.

![](images/1.%20Relations%20Between%20Commands%20&%20Objects.008.png)

These two perspectives on it are completely interchangeable.

![](images/1.%20Relations%20Between%20Commands%20&%20Objects.009.png)

A command can contain multiple objects.

![](images/1.%20Relations%20Between%20Commands%20&%20Objects.010.png)

Then the command becomes part of all of those objects.

![](images/1.%20Relations%20Between%20Commands%20&%20Objects.011.png)

These two perspectives on it are completely interchangeable.

![](images/1.%20Relations%20Between%20Commands%20&%20Objects.012.png)

In Circular both points of view, commands being part of objects, and commands being independent entities with parameters, are equally visible in the language. 

### Object Relations

So when you’ve passed an object to a command, the command automatically becomes visible inside the object as a runnable command.

### Class Relations

But in case of a command definition, a parameter is usually not filled in yet.

![](images/1.%20Relations%20Between%20Commands%20&%20Objects.013.png)

But the class of the parameter is determined.

![](images/1.%20Relations%20Between%20Commands%20&%20Objects.014.png)

It is a relation between classes, instead of a relation between objects. This automatically makes the command definition available from the parameter’s class. 

![](images/1.%20Relations%20Between%20Commands%20&%20Objects.015.png)

There is complete exchangeability between the class of a parameter and a command of a class.

## Use This

When you program a command, that might something, the action is immediately available in the context of any type of object, that has anything to do with that command.

This makes it so that the very same command can be part of several classes. This makes commands independent entities, that are not tied to a class.

-----

A command can be called on each object, whose class is a parameter of the command.

When you call a command on an object, the call points to the command of an object, but the object is also visible as a parameter of the call.

### Out of Commands & Classes Loosely Coupled

#### Inactive Command References

In the explanations above only command calls were considered, not inactive command references. Inactive command references don’t work the same as calls.

Calls have parameters filled in. Inactive command references don't have parameters filled in. So they also don’t call upon objects. Only as a command reference gets called again, objects assigned to the call’s parameters.

The object of the parameter is not determined yet in an inactive command reference. However, the class of the parameter may be determined after all. Therefore, the parameters in an inactive command references may be tied to a command inside class with a class line.

#### Local Variables

Local variables, as they are called in contemporary programming languages, are a lot like parameters. Unlike parameters, they are private to the command, rather than publicly written or read. Local variables are private contents of a command. Since they can not be publicly set, and you can not determine what object the private variable might hold, the command also can not become part of any arbitrary object of the class of the local variable.  
So the command might not become part of each object of the class of that local variable, because the object of that local variable can not be freely appointed.

The local variable *might* make the command part of the class anyway, but then as a static command, that can be called on the class, but not on any arbitrary object.

- \> 2008-09-06 Not true. Just wait what it might look like relations between objects and commands.
