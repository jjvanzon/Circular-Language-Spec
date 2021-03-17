Circle Language | Construct Drafts
==================================

Coding Concepts
---------------

This documentation folder explains how basic coding concepts are implemented inside the new computer programming language: concepts such as input output, conversions and identifiers. Each concept might be explained in the form of a story as well as a diagram notation. About 50% of the concepts are quite well-described. Most of those made it into the Circle Language Spec. They draw out a good picture of what the language looks like and how the diagram notation is applied. About 50% of the concepts is not adequately described yet or did not make it into the Circle Language Spec. Those are put here in Circle Construct Drafts.

The documentation folder contains the following sub-folders. Each folder covers a main concept.

- ### Identifiers

    - Identifiers are names for objects, collections, attributes, sites, programs, modules or any other element of a system. Any element of a system can get an identifier. This documentation folder describes how such names are used inside the new computer language. The documentation folder consists of five articles. The two most basic ones are finished. The three less fundamental ones are not finished.

- ### Conversions

    - When you assign an object’s state, and the state comes from an object with a different class, the assigned data may need to be converted. The conversion is performed by a conversion command. Conversion commands are system commands. New conversion commands can be freely introduced into the system. When objects do not match on assignment, implicit conversion takes place. The right conversion command is found by means of *Object Resolution* (see *Object Resolution).* Conversion commands can also be called *explicitly*. The documentation folder only contains a brief description of the idea. The details are to be worked out later.

- ### Errors

    - If a system tries to do something, that is not in accordance to the rules set by the system, an error is raised. A lot of rules will cause errors to be raised. Letting a program just ignore errors is not the way to go. Error message are not bad things. Error messages are our friends. When a program makes an error, you want to be notified about it. Programs are *not* supposed to make errors. When they do, something is going on, and it has to stop. There are several types of errors. There are also warnings: sort of like errors regarding style, that indicate a possible weakness in a program. You should only ignore a warning, when you know exactly what the warning means. There are different ideas about what a program is supposed to do when an error occurs. You may want the program to pause or terminate or perhaps the code should be rolled back entirely. The complexities behind error handling should be covered in this documentation folder, but it is not entirely worked out yet. It needs to be better worked out in the future.

- ### Concepts

    - Concepts are power-enhancements of software, that can be immediately applied to any system without any further programming. Concepts for instance makes you able to program ‘copy and paste’ functionality once, and then be able to automatically apply it to any system, without any additional code. A concept is a special programming construct. It is quite similar to what is also called an *aspect* in aspect oriented programming environments, only concepts are supposed to be a richer, more usable variation on aspects. Concepts are a result of the transition from code generators to generic modules, that adapt themselves to a structure description. In the code generator version of the new computer language (version 0.9), a certain aspect of the code (such as logging, copy and paste or XML serialization) was isolated into a single module, so that the concept is not spread out all over the generator’s code. In the *generated* code, however, the concept *was* spread out all over the code. The idea is, that any aspect / concept you could generate code for, should be replaced by a *concept* module, that embeds all the generic code. The concept can be automatically applied to any object or system by just specifying, that the system supports the concept. The idea is yet to be fully worked out, but the functional requirement is, simply stated: everything you can do with a concept in the code generator version of the new computer language, should be easily definable as a separate module, that replaces it. The idea is also yet to be worked out in software.

- ### Uncategorized

    - This folder contains all the articles, for which a proper place was not found yet. There are not many articles inside this documentation folder.

- ### Summary

    - In the future, the *Summary* documentation folder should contain a summary of all the coding concepts introduced. It is supposed to be a quick-reference card of all the concepts, with the textual and diagram notation next to it, without any further explanation. The whole language will be displayed in this overview. The summary is not made yet, and will be created when the design of the new computer language is more complete.