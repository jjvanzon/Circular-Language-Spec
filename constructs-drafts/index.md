Circle Language | Construct Drafts
==================================

Index
-----

`[ Preliminary documentation ]`

This index page may contain descriptions of topics now spread elsewhere or some topics might still be found in this section of the documentation.

### Coding Concepts Index

This documentation folder explains how basic coding concepts are implemented inside the new computer programming language: concepts such as input output, conversions and identifiers. Each concept might be explained in the form of a story as well as a diagram notation. About 50% of the concepts are quite well-described. Most of those made it into the Circle Language Spec. They draw out a good picture of what the language looks like and how the diagram notation is applied. About 50% of the concepts is not adequately described yet or did not make it into the Circle Language Spec. Those are put here in Circle Construct Drafts.

The documentation folder contains the following sub-folders. Each folder covers a main concept.

- #### Identifiers

    - Identifiers are names for objects, collections, attributes, sites, programs, modules or any other element of a system. Any element of a system can get an identifier. This documentation folder describes how such names are used inside the new computer language. The documentation folder consists of five articles. The two most basic ones are finished. The three less fundamental ones are not finished.

- #### Conversions

    - When you assign an object’s state, and the state comes from an object with a different class, the assigned data may need to be converted. The conversion is performed by a conversion command. Conversion commands are system commands. New conversion commands can be freely introduced into the system. When objects do not match on assignment, implicit conversion takes place. The right conversion command is found by means of *Object Resolution* (see *Object Resolution).* Conversion commands can also be called *explicitly*. The documentation folder only contains a brief description of the idea. The details are to be worked out later.

- #### Errors

    - If a system tries to do something, that is not in accordance to the rules set by the system, an error is raised. A lot of rules will cause errors to be raised. Letting a program just ignore errors is not the way to go. Error message are not bad things. Error messages are our friends. When a program makes an error, you want to be notified about it. Programs are *not* supposed to make errors. When they do, something is going on, and it has to stop. There are several types of errors. There are also warnings: sort of like errors regarding style, that indicate a possible weakness in a program. You should only ignore a warning, when you know exactly what the warning means. There are different ideas about what a program is supposed to do when an error occurs. You may want the program to pause or terminate or perhaps the code should be rolled back entirely. The complexities behind error handling should be covered in this documentation folder, but it is not entirely worked out yet. It needs to be better worked out in the future.

- #### Concepts

    - Concepts are power-enhancements of software, that can be immediately applied to any system without any further programming. Concepts for instance makes you able to program ‘copy and paste’ functionality once, and then be able to automatically apply it to any system, without any additional code. A concept is a special programming construct. It is quite similar to what is also called an *aspect* in aspect oriented programming environments, only concepts are supposed to be a richer, more usable variation on aspects. Concepts are a result of the transition from code generators to generic modules, that adapt themselves to a structure description. In the code generator version of the new computer language (version 0.9), a certain aspect of the code (such as logging, copy and paste or XML serialization) was isolated into a single module, so that the concept is not spread out all over the generator’s code. In the *generated* code, however, the concept *was* spread out all over the code. The idea is, that any aspect / concept you could generate code for, should be replaced by a *concept* module, that embeds all the generic code. The concept can be automatically applied to any object or system by just specifying, that the system supports the concept. The idea is yet to be fully worked out, but the functional requirement is, simply stated: everything you can do with a concept in the code generator version of the new computer language, should be easily definable as a separate module, that replaces it. The idea is also yet to be worked out in software.

- #### Uncategorized

    - This folder contains all the articles, for which a proper place was not found yet. There are not many articles inside this documentation folder.

- #### Summary

    - In the future, the *Summary* documentation folder should contain a summary of all the coding concepts introduced. It is supposed to be a quick-reference card of all the concepts, with the textual and diagram notation next to it, without any further explanation. The whole language will be displayed in this overview. The summary is not made yet, and will be created when the design of the new computer language is more complete.

### Concurrency Index

- #### Input Output

    - The concept of input and output is well-known by computer experts, yet the concept is not very present in both object oriented program code or relational database. Something simply ‘becomes’ input or output, arbitrarily chosen by the programmer, but it is ever explicitly *defined* in program code, what is the input and what is the output: it could be a return value returned by a procedure, a value passed along to another procedure, but it could also be reads, writes deletes and inserts into a database. Those things are spread out all over the procedures and you do not really see where something is input and where something is output. Yet, input and output are fundamental in computer programming. We talk about it all the time. In the new computer language, input and output will get a more prominent position.

    - This documentation is not finished up yet. It contains a lot of unfinished texts but also some amazing ideas, but it is all not worked out yet. The concept of input and output will be taken further than ever before. What should be worked out, is an exact definition of what input and output is and what different forms of input and output there are. In the end, every command will have an input / output definition, that consists of for instance reads, writes, additions and removals of data. This does not define *exactly* what the command does, but it does define what data is affected and what data is used. Users can always see what the input and output of a program or command is and this offers better security, because the user can see the input / output effect of what they are about to run. You can further secure the system by allowing a command to only access data, that it says it needs to access, so nothing funky can be run inside a program. This definition of input and output of a command will be called the *Command IO*.

    - When two commands affect the same data, they could be in each other’s way. The definition of that overlapping usage and alteration is called *Compared IO*. The idea is, that when you have defined what data is mutually used, you have defined the input-output dependency of commands.

    - The hope is, that the input-output dependency, or *outcome dependency*, will offer a mechanism for better managing the execution order of commands. Perhaps the right execution order of commands can be automatically determined without intervention of a programmer: *automatic execution order*. It is not fully worked out yet, but the hope is, that this can be translated into a new method for resolving concurrent access of data *(concurrency resolution)* and automatically determining whether things have to run serially or things can be processed in parallel, offering an automatic way to resolve *parallelism*. When working out this documentation, the exact definition of the concepts above will be worked out and hopefully it can be carefully explained how just by giving the concept of input and output a more prominent position in computer language and comparing different command IO definitions, there will be complete resolution of concurrency and parallelism as well as better security.

- #### Concurrency

    - Concurrency occurs when several running processes or users access the same data at the same time. This can result in several problems. There are several candidate mechanisms to solve concurrency problems. Which is the best one is yet to be determined. In this documentation folder you will find a lot of ideas about it, but the documentation is under construction. Look inside the article *Internet As A Single Computer* for a better description of the problem. The *Input Output* concept may offer a method to resolve concurrency issues in the future as well.

### Construct Drafts Index

This is the first group of products for the new computer language. This group of products is currently being developed. This product will have great use in software development today.

This folder only contains the part that would fall under the category of framework components related to Circle language.

The new language is actually a new way to operate computers. Using the language you can connect to several systems. The main aim now is for it to become usable within .NET.

It is subdivided into the following three parts:

- #### Language

    - This is the most important part of the documentation. It covers everything about coding concepts, including a diagram notation for visualizing program code and the fundamental principles of a new computer programming language. It contains explanations on how coding concepts are implemented in the new computer programming language: coding concepts such as objects, classes, relations, interfaces, input output, commands and parameters. Several experimental versions of a new computer programming language have been developed, but not yet the final one.

- #### Integration

    - This folder does not contain a lot of documentation. It is the bone-structure for future documentation. Also, hardly any integration software has been developed yet. This folder will contain any documentation about integration modules, that *Circle* has to offer in order to integrate with the rest of the world of computer technology. *Circle* is not meant to live on its own, but existing resources on the internet should be accessible, when working with the new language. Each integration module will facilitate two goals: accessing other systems using *Circle* and the ability to access *Circle* resources from inside other systems. As such you can access other file systems using *Circle*, and you can also access *Circle* resources as if it was a file system. That example would be called *File System Integration*. As such there will be systems such as *Database Integration*, *SOAP Integration*, *ODBC Integration*, *File Types* and *Module System Integration*. *Database Integration* will allow you to access *Circle* as if it were relational database, but will also allow you to access relational database systems using *Circle*. *SOAP Integration* will expose *Circle* resources through a SOAP interface, but also allow you to access other SOAP interfaces using *Circle*. *ODBC Integration* will make *Circle* support connecting to it through ODBC, but will also allow you to access relational database resources using ODBC inside *Circle*. *File Types* will allow you to export or expose *Circle* resources as different commonly used file types, but also allows you to access files of such types from within *Circle*. *Module System Integration* means, that you could for instance use ActiveX resources, Java, COM, .NET and other module systems using *Circle*. Also, *Circle* resources could be linked to as if they were for instance COM or any other module systems. Also, there will be *Protocols*, which will enable several internet protocols, so that you can access resources that are exposed through those protocols using Circle. Protocols such as HTTP, SMTP, POP3, FTP, etcetera. It is considered quite important, that *Circle* in the future will give access to all those resources as well as be accessible by other systems through all kinds of different protocols.

- #### Libraries

    - This folder is to contain documentation about some basic libraries needed for the new computer language to run more or less autonomously. It should cover libraries for basic math operations and assembly language, or machine instructions.

    - Most documentation is not written yet. The development version of the *Basic Math* documentation is fairly readable and covers implementations of basic math, which are *object*-systems in which numbers and math operation are objects, that link together (called *Math Objects*). *Math Objects* versions were programmed using version 0.9 and 2.0 of the new computer programming language.

These things are enough to make the *Circle* language useful for accessing many computer systems. 

### Expression Construct Drafts

A program’s systematics are not described by text code, but text code as well as the diagram notation are a mere *expression* of systematics, stored in a binary way as interlinked objects. This folder covers the different kinds of ways you can express systematics.

The basic ideas about a diagram notation were already covered earlier at the beginning of the new computer language documentation, because it was important to quickly introduce those.

Much of the documentation in this folder is a mere throw-together of ideas or pieces of text, that came out of previous descriptions of new computer programming languages.

The *Expression* folder contains the following articles:

- #### Diagrams

    - *Expression* includes a *diagram notation* for visualizing the program code. The diagrams are also a mere expression of binary interlinked objects. Systematics, stored in a binary way as interlinked objects, can be translated to a diagram. The diagram should be fully automatically drawn out. The metrics and positioning of the shapes and lines is automatically determined. The diagram can be edited, resulting in changes to the stored binary objects.

    - The basics of the diagram notation were already covered at the beginning of the new computer language documentation. How *each concept* is expressed in a diagram is already covered in the documentation *of that* concept. This documentation folder explains everything *else* about diagram the diagram notation, such as how the shape positions of the diagram are automatically determined and how the diagram can be *colored*, to make the systematics even more clear. 

    - The articles in the *Diagrams* documentation folder are not finished. They consist mostly of texts coming out of an earlier unfinished design of the diagram notation language. The diagram notation has not been realized in software yet.

- #### Text Code

    - Traditionally, the systematics of a program are expressed by means of text code. But in the new language systematics are stored as binary interlinked objects. Text code is a mere *expression* of those binary interlinked objects. The *Text Code* sub-module makes sure, that systematics are translated to text code. The text code can be adapted, resulting in changes to the stored binary objects, rather than that the text code is literally stored.

    - The articles in the *Text Code* documentation folder are not finished. They are mostly a throw-together of ideas. The exact way the textual code is going to look is not yet determined, because it was more important to work out the language conceptually along with its diagram notation, than it was to work out the textual notation. The general idea, though, is that each language element’s textual representation is considered its *literal*, that can be read out and assigned. However large the construct, the text code that represents it is still just a literal, be it composed of the literals of its sub-constructs. This is just an idea, but it might be the way to go.

    - The working version 2.0 of the new computer language has a text code, but is very basic, for version 2.0 was kept very basic: it was just a proof of concept.

### Language Index 

This documentation folder describes the new computer programming language. This is the most important part of the documentation.

It includes explanations of a diagram notation for visualizing program code and the fundamental principles of a new computer programming language. It contains explanations of how coding concepts are implemented inside the new computer programming language: coding concepts such as objects, classes, relations, interfaces, input output, commands and parameters. Several experimental versions of a new computer programming language have been developed, but not yet the final one.

This documentation folder contains the following sub-folders:

- #### Code Concepts

    - This documentation folder explains how basic coding concepts are implemented inside the new computer programming language: concepts such as objects, classes, relations, interfaces, input output, commands and parameters. Each concept is explained both conceptually as well as in the form of a diagram notation. About 70% of the concepts are well-described. Those are put at the beginning of the documentation. They draw out a good picture of what the language looks like and how the diagram notation is applied. 30% percent of the concepts is not adequately described yet. Those are put at the end of this documentation folder.

- #### Expression

    - This folder covers the different kinds of ways you can express systematics. The basic ideas about a diagram notation were already covered at the beginning of the new computer language documentation, because it was important to quickly introduce those. The diagram expression is also explained throughout the code concepts documentation. This part of the documentation will cover the remaining topics about the diagram expression.  
    The idea behind expression in general is that a program’s systematics are not described by text code, but text code as well as the diagram notation are a mere expression of systematics, stored in a binary way as interlinked objects. Much of this documentation folder is a mere throw-together of ideas or pieces of text, that came out of previous descriptions of new computer programming languages.  
    Text code and diagram expression can be complemented by any other form of expression. Displaying data in tabular form is another form of expression. Expressing data and commands in a graphical windows user interface is also an alternative form of expression of systematics. Furthermore, certain objects have specialized expressions. For instance a sound object may be expressed by playing its sound, but not all objects can be expressed by playing it as sound. All expressions are considered alternative expressions of systematics, just like text code and diagram code.

- #### Other Topics

    - This folder contains topics regarding the new computer language, that are either boring, trivial or just too advanced and go too far for now. All in all: topics, that are not important enough to cover yet.

### Libraries Index

This folder is to contain documentation about some basic libraries needed for the new computer language to run more or less autonomously. It should cover libraries for basic math operations and assembly language, or machine instructions.

Most documentation is not written yet.

- #### Math

    - The development version of the *Basic Math* documentation is fairly readable and covers implementations of basic math, which are *object*-systems in which numbers and math operation are objects, that link together (called *Math Objects*). *Math Objects* versions were programmed using version 0.9 and 2.0 of the new computer programming language.

- #### Assembly

    - ...

### Other Topics Index

This folder contains topics regarding the new computer language, that are either boring, trivial or just too advanced and go too far for now. All in all: topics, that are not important enough to cover yet. These topics may become sub-modules in the future.

The *Computer Language Other Topics* documentation has the following sub-folders:

- #### Utilities

    - Can cover all sorts of utilities for the new computer language, such as debugging or a macro recorder or code editors. Some conceptual utilities are described, some are just named, and for some of them just a few loose ideas are given. None of the utilities were implemented in software yet.

- #### Optimization

    - Covers any kind of optimization algorithm, that might be integrated into the new computer language. For now it is not considered important to think about this.

- #### Old or Boring

    - As the name suggests, the material in this folder is considered either old or boring. As such, it might not be worth mentioning what they cover. However old or boring it is, it is still about 80 pages of material, apparently not worth reading, but apparently hard to throw away as well.

### Utilities Index

This documentation folder can cover all sorts of utilities for the new computer language, such as debugging or a macro recorder or code editors. More tools may be added in the future. Some utilities are described conceptual, some are just named, and for some of them just a few loose ideas are given. None of the utilities were implemented in software yet.

The *Utilities* documentation folder has the following sub-folders:

- #### Code Editor

    - This folder is empty. On top of text code being constructed and parsed, text code also separately requires a code editor for use in the programming environment. Nothing like this has been developed yet in the software.

- #### Debugging

    - The new computer language is described, but how to go through code step by step or debug it has not been covered yet. This documentation may cover how debugging is implemented inside the environment of the new computer language. For now it only contains loose ideas about it. Nothing like this has been developed yet.

- #### Translating From XML

    - This may be a tool to read out XML and show it as a structure in the new computer language. So it is not about saving and loading data as XML, but it is about taking existing XML from another source and showing it inside the new computer language. The idea came out of the design of the relational language *Creator* made in 2007. This idea will probably not be implemented inside the main module *Code*, but inside the main module *Legacy*, to offer access to XML. Nothing like this has been developed in the software yet. The documentation only contains a loose idea about it and is not a full description yet.

- #### Translating To and From Relational Database

    - This may be a module to convert a relational database to a structure inside the new computer language or to convert a structure in the new computer language to a relational database. The idea came out of the design of the relational language *Creator* made in 2007. The idea was, that this would make using the new language an option more easily picked. This idea will be superseded by *Legacy* modules offering the ability to access the new computer language as if it were relational database and the ability to display relational databases in the syntax of the new computer language. Nothing like this has been developed in the software yet. The documentation only contains a loose idea about it and is not a full description yet.

- #### Web Applications

    - This folder is empty. This idea came out of the design of the relational language *Creator* made in 2007. That version of the new computer language offered a generated user interface. The idea was, to also let it offer generated web applications, so that you can access a Creator application through the internet.  
    This idea will be superseded, by the fact, that the new design of the new computer language will be one, in which there is always in interaction with the internet, and that web user interfaces will be offered as a legacy module. Nothing like this has been developed in the software yet. The documentation only contains a loose idea about it and is not a full description yet.

- #### Derive Relation Counterpart

    - When one class of object registers its related objects, but the related objects do not register the relation back, then you might need a tool to add that backward relation. To do that, a query needs to be done, to find the related objects, that were originally not registered inside the other object. The *Derive Relation Counterpart* tool is to cover this. This folder is empty. No such tool was implemented yet in the software.

- #### Normalization

    - Some data is not normalized. Normalization is concept in relational database, to prevent repetition of data, by replacing the same data with a reference to a central point at which you store the data only once. Normalization may also be applied to code as such, to prevent repeated code. The concept is not worked out here yet. It may become a tool in a programming environment in the future.

- #### Text Classing

    - This concept would allow you to quickly select pieces of text out of a text document and call it an object and assign a class typing to it, so that you turn the text document into objects with classes, references to each other and a containment structure. That way you can turn a text document into a relational structure in no time. The documentation only describes the basic idea. No software has been written for it yet.

- #### Macro Recorder

    - The new computer language should have this button to press, that records all user actions, that are undertaken. Then, when you stop recording, the user actions are recorded as a procedure, that can be called as a command to be executed in one blow instead of performing all the actions manually. You can also edit the command code, to fine-tune the behavior of the command. This makes it easy to turn manual work into automatic procedures and it also makes it easier to program new commands. Other programs have this sort of macro recording, and the new computer language should also have such functionality in the futures. Macro recording has not been implemented inside existing versions of the new computer language yet.

- #### Text Statistics

    - This should be a tool to automatically create word statistics for a text document: how many times is a word in there? How many different words are used? How many times is each word used? This can form a base for a document index. But words used too much, such as ‘and’ an ‘a’, should be left out. Text statistics could be a very useful utility. No such utility has been implemented in the software yet.

Ideas
-----

*The material below are loose ideas, yet to be turned into good documentation.*

Computer Language, Utilities,

Ik heb geen tool voor performance monitoring en tuning vermeld in de documentatie.

JJ

-----

Monitoring,

"Regulator"

JJ

-----

Software System,

I think I have too little management of the physical devices yet.

JJ

-----

Monitoring

Where I thought a tuning utility would be an option, I should think more that it is a requirement.

JJ

-----

2004,

- Incremental compilation
- Debugging
- Syntax Checking

JJ 

-----

2004,

Create default, ready to easily work with, settings for objects. ‘Advanced’ programmers can alter them as they know better. Programmers might want to create their own default that overrides the premade default. Or use no initialization at all. I’ll think about that later.

JJ