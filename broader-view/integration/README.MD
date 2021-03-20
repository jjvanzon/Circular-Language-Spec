Circle Language Broader View | Integration
==========================================

Overview
--------

`[ Preliminary documentation ]`

This folder may contain documentation about integration modules, that might work with *Circle* in order to integrate with the rest of the world of computer technology. *Circle* is not meant to live on its own, but existing resources on the internet should be accessible, when working with the new language. Each integration module will facilitate two goals: accessing other systems using *Circle* and the ability to access *Circle* resources from inside other systems. As such you can access other file systems using *Circle*, and you can also access *Circle* resources as if it was a file system. That example would be called *File System Integration*. As such there will be systems such as *Database Integration*, *SOAP Integration*, *ODBC Integration*, *File Types* and *Module System Integration*. It is considered quite important, that *Circle* in the future will give access to all those resources as well as be accessible by other systems through all kinds of different protocols.

Here are some topics that might be put under this umbrella. Some may have their own article.

- ### [Integration Loose Ideas](https://github.com/jjvanzon/Circle-Language-Spec/blob/master/broader-view/integration/integration-loose-ideas.md)

    - Lesser worked out ideas about integration.

- ### [Text Codes](https://github.com/jjvanzon/Circle-Language-Spec/blob/master/broader-view/integration/text-codes.md)

    - *Text Codes* might encapsulates a large number of sub-modules. It might be about integrating many other text codes.
    
- ### File System Integration

    - You can access other file systems from within *Circle*, and you can also access *Circle* as if it *were* a file system. *File System Integration* also covers any other tools regarding files. In the new software system you would apply those to *objects* instead of files. Some file tools have been developed. The documentation folder only contains loose ideas about file functions.

- ### Database Integration

    - *Database Integration* will allow you to access *Circle* as if it were a relational database, but will also allow you to access relational database systems from within *Circle*. The documentation folder is empty. No software has been developed for this yet.

- ### SOAP Integration

    - *SOAP Integration* will expose *Circle* resources through a SOAP interface, but also allow you to access other SOAP interfaces using *Circle*. The documentation folder is empty. No software has been developed for this yet.

- ### ODBC Integration

    - *ODBC Integration* will make *Circle* support connecting to it through ODBC, but will also allow you to access other relational database resources using ODBC from within Circle. The documentation folder is empty. No software has been developed for this yet.

- ### File Types

    - *File Types* will allow you to export or expose *Circle* resources as different commonly used file types, but also allows you to access files of such types from within *Circle*. The documentation folder is empty. No software has been developed for this yet.

- ### Module System Integration

    - *Module System Integration* means, that you could for instance use ActiveX resources, Java, COM, .NET and other module systems using *Circle*. Also, *Circle* resources could linked to as if they were for instance COM or any other module systems. The documentation folder is empty. No software has been developed for this yet.

- ### [Protocols](https://github.com/jjvanzon/Circle-Language-Spec/blob/master/broader-view/integration/protocols.md)

    - Also, there will be *Protocols*, which will enable several internet protocols, so that you can access resources that are exposed through those protocols. Protocols such as HTTP, SMTP, POP3, FTP, etcetera. *Protocols* will make sure a *Circle* resource is accessible through those protocols. The documentation folder is empty. No software has been developed for this yet.

- ### External API's

    - Furthermore, a lot of software is dependent on API’s. When software is made, and it uses an API, it is dependent on that API. You can not port the software to another system if the same API is not supported. *Module System Integration* might part solve this. You can link to resources from other systems, so you do not necessarily need to port to native *Circle* to integrate with another system. However, you might want to be able to port your system to the new computer language’s native operating system, to make use of new features in it. Porting as such is only possible if the API your program depends on, is either accessible through *Module Systems Integration* or the external API is supported in the new computer language as well. That is the part *External API’s* is responsible for. It is undoable to support all existing API’s inside the new *OS*, but if an API is supported, *External API’s* is the part of the system to put it in. The documentation folder is empty. No software has been developed for this yet.

- ### [Translating From XML (to a J Data Structure)](https://github.com/jjvanzon/Circle-Language-Spec/blob/master/broader-view/integration/translating-from-xml-to-a-j-data-structure.md)

    - This may be a tool to read out XML and show it as a structure in the new computer language. So it is not about saving and loading data as XML, but it is about taking existing XML from another source and showing it inside the new computer language. The idea came out of the design of the relational language *Creator* made in 2007. This idea will probably not be implemented inside the main module *Code*, but inside the main module *Legacy*, to offer access to XML. Nothing like this has been developed in the software yet. The documentation only contains a loose idea about it and is not a full description yet.

- ### [Translating To and From Relational Database](https://github.com/jjvanzon/Circle-Language-Spec/blob/master/broader-view/integration/translating-to-and-from-relational-database.md)

    - This may be a module to convert a relational database to a structure inside the new computer language or to convert a structure in the new computer language to a relational database. The idea came out of the design of the relational language *Creator* made in 2007. The idea was, that this would make using the new language an option more easily picked. This idea will be superseded by *Legacy* modules offering the ability to access the new computer language as if it were relational database and the ability to display relational databases in the syntax of the new computer language. Nothing like this has been developed in the software yet. The documentation only contains a loose idea about it and is not a full description yet.

- ### [UML](https://github.com/jjvanzon/Circle-Language-Spec/blob/master/broader-view/integration/uml.md)

    - This article is not finished. It should contain an evaluation on what are the pros and cons of the new diagram notation compared to UML: what does UML offer, that the new diagram notation does not and what UML-expressible concepts have a better alternative notation inside the new diagram language? How useful is UML anymore if you have the new diagram notation? Or does UML still offer things, that the new diagram notation does not? And if there is something the new diagram notation does not offer: should the diagram notation be changed, so that it could be a substitute for UML? So this article should be a comparison between UML and the diagram notation of the new computer language.

- ### ‘...’

    - Perhaps later other types of systems to integrate with will come to light. That is why this folder is put at the end: as a placeholder for possible future folders.
