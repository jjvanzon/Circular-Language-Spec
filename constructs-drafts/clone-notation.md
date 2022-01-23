Construct Drafts | Clone Notation
=================================

`[ Preliminary documentation ]`

__Contents__

- [Introduction](#introduction)
- [Structs](#structs)
- [Parameter Passing and the Clone Notation](#parameter-passing-and-the-clone-notation)
    - [By Value Parameter Passing and the Clone Notation](#by-value-parameter-passing-and-the-clone-notation)
    - [By Value Parameter Passing in a Diagram with the Clone Notation](#by-value-parameter-passing-in-a-diagram-with-the-clone-notation)
    - [Value In Parameters and the Clone Notation](#value-in-parameters-and-the-clone-notation)
    - [Value In Parameters in a Diagram with the Clone Notation](#value-in-parameters-in-a-diagram-with-the-clone-notation)
    - [Value Out Parameters and the Clone Notation](#value-out-parameters-and-the-clone-notation)
    - [Value Out Parameters in a Diagram with the Clone Notation](#value-out-parameters-in-a-diagram-with-the-clone-notation)
    - [Value Thru Parameters and the Clone Notation](#value-thru-parameters-and-the-clone-notation)
    - [Value Thru Parameters in a Diagram with the Clone Notation](#value-thru-parameters-in-a-diagram-with-the-clone-notation)
    - [Parameters of Calls Directly Tied Together with the Clone Notation](#parameters-of-calls-directly-tied-together-with-the-clone-notation)
    - [Loose Ideas about Parameter Passing and the Clone Notation](#loose-ideas-about-parameter-passing-and-the-clone-notation)

## Introduction

The __Clone__ aspect might be a system aspect like the __Value__ aspect, or the __Object__ aspect of a symbol. This might be an alternative notation for it.

__Clone__ notation could perhaps be an implicit notation for something that might not be used very often. It may already be adequately expressed, using other constructs from the spec. The idea might be set aside in this document in *Construct Drafts*, because the language may be able to live without it.

## Structs

One construct in particular where a cloning depth of 2 might be common, could be the __struct__ construct that might be found in other languages.

A __struct__ might be a value type that might have multiple distict fields / values. The idea that the object itself + its values might be transferred as a whole in case of value assignment for instance.

## Parameter Passing and the Clone Notation

### By Value Parameter Passing and the Clone Notation

By Value parameters might mean to clone the values of an object up until a certain depth.

More complex objects passed by value might be cloned up until a certain cloning depth.

A single-value transfer might be the equivalent of a cloning operation with a depth of __1__.

### By Value Parameter Passing in a Diagram with the Clone Notation

The notation of a __By Value__ cloning operation may look as follows:

![](images/Input%20Output%20Parameter%20Passings.004.png)

The number __2__ may stand for the cloning depth.

A single-value transfer might be the same as a cloning depth of __1__, but the number __1__ might not be shown then.

### Value In Parameters and the Clone Notation

__Value In__ parameters might also work for more complex objects. Those might then be cloned up until a certain depth.

### Value In Parameters in a Diagram with the Clone Notation

A __Value In__ parameter can also have an indication of a cloning depth, which may be displayed as follows:

![](images/Input%20Output%20Parameter%20Passings.008.png)

Or for an unfilled-in __Value In__ parameter:

![](images/Input%20Output%20Parameter%20Passings.009.png)

The pictures above might display a cloning depth of __2__, but any cloning depth might be used.

Here might be the expression of cloning depth for __Value In__ parameters of *inactive* commands, which is basically the same notation as for active commands:

![](images/Input%20Output%20Parameter%20Passings.012.png)

![](images/Input%20Output%20Parameter%20Passings.013.png)

### Value Out Parameters and the Clone Notation

A parameter might be either a copy of a single value, or a clone up to a certain depth.

### Value Out Parameters in a Diagram with the Clone Notation

A __Value Out__ parameter may also have an indication of a cloning depth, which might be displayed as follows:

![](images/Input%20Output%20Parameter%20Passings.016.png)

Or with the target of the output filled in:

![](images/Input%20Output%20Parameter%20Passings.017.png)

The pictures might above display a cloning depth of __2__, but any cloning depth can be used.

This may be the expression of cloning depth for __Value Out__ parameters of *inactive* commands, which is the same notation as for active commands:

![](images/Input%20Output%20Parameter%20Passings.020.png)

![](images/Input%20Output%20Parameter%20Passings.021.png)

### Value Thru Parameters and the Clone Notation

A __By Value__ parameter might be either a copy of a single value, but also a clone to a certain depth.

### Value Thru Parameters in a Diagram with the Clone Notation

A __Value Thru__ parameter might also have an indication of a cloning depth, which may be displayed as follows:

![](images/Input%20Output%20Parameter%20Passings.024.png)

Or for an unfilled-in __Value Thru__ parameter:

![](images/Input%20Output%20Parameter%20Passings.025.png)

The pictures above may display a cloning depth of __2__, but other cloning depths can be used.

Here might be the expression of cloning depth for __Value Thru__ parameters of *inactive* commands, which is a similar notation as for active commands:

![](images/Input%20Output%20Parameter%20Passings.028.png)

![](images/Input%20Output%20Parameter%20Passings.029.png)

### Parameters of Calls Directly Tied Together with the Clone Notation

When directly tying together value parameters, cloning depth might be intermixed:

![](images/Input%20Output%20Parameter%20Passings.056.png)

![](images/Input%20Output%20Parameter%20Passings.057.png)

Effectively, it might be the lowest cloning depth that would be transferred to the input parameter on the right. When the __Value In__ and __Value Out__ parameters have the same cloning depth, it may be drawn out as follows:

![](images/Input%20Output%20Parameter%20Passings.058.png)

### Loose Ideas about Parameter Passing and the Clone Notation

Passing input parameter by value might guarantee, that the operations inside a command might not affect the original object. 

`<< interpretation issues >>`

For that reason, when a value parameter is cloned up until a certain depth, no references to original objects might be taken over by the clone. __By Value__ clones might not have references to existing objects, but always contain entirely new objects or object references that are __Nothing__.