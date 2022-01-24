Circular Language Broader View | Extensibility | Module Integration
===================================================================

`[ Draft ]`

In an earlier version of Circular it was a problem to load multiple modules, and have one module use objects of a class of another module.

But in a newer version of Circular there is simply no distinction between modules. It’s like there is only one module running on the computer. The separate modules are simply sub-objects inside the single module. An object can have a class out of any of the modules, that run on the computer.  
The modules are not separate programs. They are just objects living inside the computer.  
When a module contains an object with a class from another module, the object simply refers to the class as if there wasn’t even any distinction between modules: everything is running on the same computer, everything is an object, and the modules are simply a benign grouping of things, that doesn’t really create any barrier between programs.

One program doesn’t might define a reference to another module, to use anything out of the module. A program can simply reach anything running on the computer. In fact, a program can simply reach anything running on the internet, that is publicly accessible.

A module isn’t even loaded or unloaded into memory or anything like that. When a computer is running, all the modules are just there. Whether it is physically stored on disk or loaded into memory depends on a caching scheme. If a module isn’t used for a while, it might be removed from memory and just reside on disk. If a module is used frequently, the parts frequently used might be put in RAM. This is managed by a caching, not by loading or unloading modules.

It all seems so common, it’s not even worth explaining anymore. The topic isn’t really module integration. The topic is: there is no distinction between modules anymore.