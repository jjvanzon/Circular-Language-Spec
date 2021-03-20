Circle Language Broader View | Extensibility Principles
=======================================================

Overview
--------

`[ Preliminary documentation ]`

Perhaps the most important goal of the Circle programming language, is to melt together all computer technology disciplines, providing one clear language, that can express anything, and that everybody can understand. The *Extensibility Principles* may make a lot of promises about the new language.

The *extensibility principles* may cover the techniques that make sure existing software is extensible and make sure, that *Circle language* may integrate with the rest of the world of computer technology. *Circle* resources might be accessible to other systems and existing resources on the internet might be accessible in *Circle*. Not all these articles might be finished yet. More may be added in the future. The *Extensibility* folder may contains the following articles:

### Extensibility

- #### Introduction

    - This folder is empty for now. In the future it should contain a description of what extensibility principles are.

- #### Reflection

    - Reflective data is data that describes the structure of a program. The reflective data of a program for instance contains descriptions of classes. In ordinary programming languages, it is considered something special to be able to access data that describes a program, listing out all the classes and all of its members. In the new computer language the program actually *is* a description of the structure of the program. As you make the program, you are creating this data, and it is actually the program itself, that will just be run inside an engine. Any object simply has a reference to its class. You can access the full description of this class at all times.

    - Having this reflective data at hand at all times, makes it easy to write software that adapts its behavior to this reflective data, rather than being written for a specific data structure. That creates better extensibility.

- #### Module Integration

    - In a newer version of computer language there is simply no distinction between modules anymore. It is like there is only one module running on the computer. Separate modules are simply sub-objects of one single module. An object can have a class out of any of the modules, that run on the computer or even a class out of any module on the internet.

    - Modules are not separate programs. They are just objects living inside the computer or on the internet. When a module contains an object with a class from another module, the object simply refers to the class as if there was not even any distinction between modules: everything is running on the same computer or on the same internet, everything is an object, and the modules are simply a benign grouping of things, that does not really create any barrier between programs.

- #### Concepts As External Modules

    - Concepts are power-enhancements of software, that can be immediately applied to any system without any further programming. A concept is a special programming construct.

    - A *concept* is close to what some programming environments call *aspects*. But concepts are supposed to be a richer, more usable variation on aspects.

    - Concepts allow you to program modules, that adapt themselves to the structure of other modules, automatically extending an existing structure with an extra aspect, such as instantly enabling copy-paste actions inside a system, that originally did not support it, or instantly being able to save object structures to XML, for a system that originally did not have this functionality.

    - Concepts will often make use of a system’s *reflective data*.

    - Turning concepts into external modules instead of polluting all the code of a program with it, makes systems more easily extensible.

    - This article is still just a throw-together of ideas, yet to be turned into good documentation.

- #### Relational As Carbon Base

    - The *Relational As Carbon Base* principle means that when making a program, you should primarily think in terms of relations between classes. The relations and classes are used as a base. They are used by *concepts*, for instance to automatically generate a user interface for the system. Also other concepts like *Undo* and *Copy & Paste* can automatically be applied to the relational structure. The concepts are tied to the relational structure. The relational structure forms the carbon base of the program, onto which other atom groups can be attached.