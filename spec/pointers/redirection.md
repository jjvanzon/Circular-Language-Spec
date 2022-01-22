Circular Language Spec | Pointers
=================================

[back](./)

Redirection
-----------

`[ Preliminary documentation ]`

__Contents__

- [Target Symbols](#target-symbols)
    - [Line Targets](#line-targets)
    - [Terms](#terms)
        - [Target Symbol](#target-symbol)
        - [Source](#source)
        - [‘Target’](#target)
        - [Redirection and Trace](#redirection-and-trace)
        - [Interface Definition](#interface-definition)
        - [Object Definition](#object-definition)
        - [Object Delegation](#object-delegation)
        - [Command Definition Trace](#command-definition-trace)

### Target Symbols

(Out of the original Symbol documentation from 2004.)

#### Line Targets

Lines redirect a *system aspect* of a symbol to another symbol.

For instance: an object symbol can serve as its own object:

![](images/Redirection.001.png)

But if it has an object line, it is no more than a pointer to an object, rather than the object itself, while te target of the line is regarded the real object. 

![](images/Redirection.002.png)

*A is a pointer, B is the object.*

The object symbol *redirects* its *object* system aspect to another symbol. Lines *are* redirection.

#### Terms

There’s a lot to be said about the terminology around target symbols. I’ve put all this in this section. I kept these discussions out of the original text of "Target Symbols", because it might obscure the main point.

##### Target Symbol

The target of a line, the *line target*, is also called a *target symbol*, while the line owner is can also be called the *source symbol* or, less commonly: the *line source*.

##### Source

Be careful with the term *source* in this context, though. You can speak of the source of a line:

![](images/Redirection.003.jpeg)

__A__ is considered the line’s source. __B__ is the opposite party: the *target*. *Source* in this context expresses a party of a line. 

When you use the term *source* to denote a *relation between symbols*, it actually means *the same* as the term target. The terms are not opposites, they’re equivalents.

![](images/Redirection.004.jpeg)

__Type__ can be considered __Object__’s type target, because __Object__’s type line points to it. __Type__ can also be considered __Object__’s type source, because __Type__ serves as the type of __Object__.

##### ‘Target’

The term *target* is used for both intermediate targets and the final target symbols. To be more exact about what target you’re talking about you can use the terms *direct*, *intermediate* and *final*. The *direct object* of __A__ in the picture < there is no picture... > above, for instance, is __B__, while the *final object* is __C__. __B__ is also regarded an *intermediate object target*, or *intermediate object*, because it’s not the final target, nor the line source. The unaugmented terms *target object*, *target type*, *target interface* and *target command* are by rule reserved for final targets. If you want to denote an intermediate object target, for instance use the term *object target*, instead of *target object*, or say *intermediate target object*, but don’t use the unaugmented term *target object* for an intermediate symbol. Many times out of the context it can be understood whether there is talked about a direct, intermediate or a final target, so it’s not always extra denoted. The term target *symbol* can be about any redirection step or be about any the final target of any aspect.

*Object target* is not the same as *target object*. *Object target* denotes the direct target of an object line. *Target object* denotes the symbol that is regarded to *really* represent the object.

The terms *object*, *type* and *interface* can denote the line target of an object line, type line or interface line. The terms *object*, *type* and *interface* are used for *final* targets as well as *direct* targets. The context may illustrate what I’m talking about or I’ll use a more specific term.

##### Redirection and Trace

Each *step* in a trace is called a *redirection*, because following a line is called a redirection. The whole tracing process can also be referred to as *the redirection*, even though it’s also called a *trace*.

##### Interface Definition

The final target interface is also called the *interface definition*.

##### Object Definition

The type of an object symbol is sometimes called the definition of the object, because the type of the object determines the object’s systematics for a great part. Just like the definition of a call determines the systematics of a command. The term *definition of object* could also mean the target object, though, so it’s easy to say something ambiguous.

##### Object Delegation

Delegating the object aspect is the main type of object redirection. Because it is the main one, it can also be called *the* delegation or *object delegation*.

##### Command Definition Trace

The command definition trace can also be called the *command trace* or the *definition trace*.