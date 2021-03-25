Encircle Language | Broader View
================================

Extensibility
-------------

`[ Preliminary documentation ]`

Perhaps a central goal of the Encircle programming language could be, to melt together computer technology disciplines, aiming to provide one clear language, that might express anything, and that everybody might understand. The *Extensibility Principles* may shape these hopes for the language.

The *extensibility principles* may cover techniques that might make existing software extensible and make sure, that *Encircle language* may integrate with the rest of the world of computer technology. *Encircle* resources might be accessible to other systems and existing resources on the internet might be accessible in *Encircle*. Not all these articles might be finished yet. More may be added in the future. The *Extensibility* folder may contains the following articles:

- ### [Concepts As External Modules](concepts-as-external-modules.md)

    - Concepts might be power-enhancements of software, that might be immediately applied to any system without any further programming. A concept may become a special programming construct.

    - A *concept* might be close to what some programming environments call *aspects*. But the hope would be that concept might become a richer, more usable variation on aspects.

    - Concepts may allow you to program modules, that adapt themselves to the structure of other modules, automatically extending an existing structure with an extra aspect, such as instantly enabling copy-paste actions inside a system, that originally did not support it, or instantly being able to save object structures to XML, for a system that originally did not have this functionality.

    - Concepts might often make use of a system’s *reflective data*.

    - Turning concepts into external modules instead of polluting all the code of a program with it, might makes systems more easily extensible.

    - Perhaps this might only work for systems that have a way to integrate with Encircle.

    - This article may still consist of just loose ideas.

- ### [Extensibility Loose Ideas](extensibility-loose-Ideas.md)
  
    - Unrefined ideas about the topics.

- ### [Module Integration](module-Integration.md)

    - In a newer version of computer language there might simply be no distinction between modules anymore. It might be like there is only one module running on the computer. Separate modules might simply sub-objects of one single super-module. An object might have a class out of any of the modules, that run on the computer or even a class out of any module on the internet.

    - Modules are not separate programs. They are just objects living inside the computer or on the internet. When a module contains an object with a class from another module, the object simply refers to the class as if there was not even any distinction between modules: everything is running on the same computer or on the same internet, everything is an object, and the modules are simply a benign grouping of things, that does not really create any barrier between programs.

- ### [Reflection](reflection.md)

    - Reflective data is data that describes the structure of a program. The reflective data of a program for instance contains descriptions of classes. In other programming languages, it might be considered something special to be able to access data that describes a program, listing out all the classes and all of its members. In the new computer language the program actually *is* a description of the structure of the program. As you make the program, you are creating this data, and it is actually the program itself, that will just be run inside an engine. Any object simply has a reference to its class. You can access the full description of this class at all times.

    - Having this reflective data at hand at all times, makes it easy to write software that adapts its behavior to this reflective data, rather than being written for a specific data structure. That may create better extensibility.

- ### [Relational As Carbon Base](relational-as-carbon-base.md)

    - The *Relational As Carbon Base* principle means that when making a program, you should primarily think in terms of relations between classes. The relations and classes are used as a base. They are used by *concepts*, for instance to automatically generate a user interface for the system. Also other concepts like *Undo* and *Copy & Paste* can automatically be applied to the relational structure. The concepts are tied to the relational structure. The relational structure forms the carbon base of the program, onto which other atom groups can be attached. It might not look like that exactly in the diagrams, but conceptually there might look like there is a parallel. In the Encircle diagrams, things might tend to be placed inside each other, rather than being plugged in on the outside.