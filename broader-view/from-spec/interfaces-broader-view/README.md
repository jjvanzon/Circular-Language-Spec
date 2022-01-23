Circular Language Broader View | From Spec | Interfaces | Broader View
======================================================================

`[ Preliminary documentation ]`

Ideas about this topic, perhaps less to the point but more philosophical, might be moved from the spec to here.

- ### [Imaginary Backward Relationships](imaginary-backward-relationships.md)
    
    - Some relationships between objects might be bidirectional. Some might not. Imaginary backward relationships might be an idea, where even when a relationship is not defined as bidirectional, you might derive the backwards relationship on the fly in certain cases, because it might be useful information. Producing the backward relationship may involve scanning part of a system in which an object might be used, perhaps sped up by some sort of caching scheme.

- ### [Interfaces Group By Source](interfaces-group-by-source.md)

    - A specific application of interfaces might be, when your object might get extended with commands programmed by other people, code coming from other sites. To have commands from others available from the object might be handy, and it may create overview if these commands are grouped by source. Also to maybe have grip onto the reliability of a command. This article tries to further get into that and how a diagram notation might look.