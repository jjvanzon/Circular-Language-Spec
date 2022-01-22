Circular Language | Broader View
================================

Integration
-----------

`[ Preliminary documentation ]`

This folder may contain documentation about integration modules, that might work with *Circular* in order to integrate with the rest of the world of computer technology. *Circular* may not be meant to live on its own, but existing resources on the internet might be made accessible, when working with the Circular language. Each integration module might facilitate two goals: accessing other systems using *Circular* and the ability to access *Circular* resources from inside another system. As such you might access a file systems using *Circular*, and you might also access *Circular* resources as if it was a file system. That example might be called *File System Integration*. As such there might be systems such as *Database Integration*, *SOAP Integration*, *ODBC Integration*, *File Types* and *Module System Integration*. It might be a relevant aim that *Circular* in the future may give access to all those resources as well as be accessible by other systems through all these kinds of different protocols.

Here are some topics that might be put under this umbrella. Some may have their own article:

- ### [Integration Loose Ideas](integration-loose-ideas.md)

    - Lesser worked out ideas about integration.

- ### [Text Codes](text-codes.md)

    - *Text Codes* might encapsulates a larger number of sub-modules. It might be about integrating many other text codes.

- ### XML Integration

    - This may be a tool to read out XML and show it as a structure in the Circular language. So it is not about saving and loading data as XML, but it is about taking existing XML from another source and showing it inside Circular.

- ### [UML](uml.md)

    - This article is not finished. It might once become an evaluation on what are the pros and cons of the Circular diagram notation compared to UML: what might UML offer, that the Circular diagram notation might not and what UML-expressible concepts might have an alternative notation inside the Circular diagram language? Might UML still offer things, that the Circular diagram notation might not? And if there is something the Circular diagram notation might not offer: should the diagram notation be changed, so that it could be a substitute for UML? So this article might become a comparison between UML and the diagram notation of Circular.

- ### File System Integration

    - You might access other file systems from within *Circular*, and you might also access *Circular* as if it *were* a file system. *File System Integration* also may cover any other tools regarding files. In a Circular system you might apply those to *objects* instead of files.

- ### Database Integration

    - *Database Integration* may allow you to access *Circular* as if it were a relational database, but might also allow you to access relational database systems from within *Circular*.

- ### SOAP Integration

    - *SOAP Integration* might expose *Circular* resources through a SOAP interface, but also might allow you to access other SOAP interfaces using *Circular*.

- ### ODBC Integration

    - *ODBC Integration* might make *Circular* support connecting to it through ODBC, but may also allow you to access other relational database resources using ODBC from within Circular.

- ### File Types

    - *File Types* might allow you to export or expose *Circular* resources as different commonly used file types, but also allows you to access files of such types from within *Circular*.

- ### Module System Integration

    - *Module System Integration* is the idea, that you might for instance use ActiveX resources, Java, COM, .NET and other module systems using *Circular*. Also, *Circular* resources might be linked to as if they were for instance COM or any other module systems.

- ### Protocols

    - *Protocols* might enable several internet protocols, so that you might access resources that are exposed through those protocols. Protocols such as HTTP, SMTP, POP3, FTP, etcetera. *Protocols* might make sure a *Circular* resource is accessible through those protocols.

- ### External API's

    - Furthermore, a lot of software may be dependent on API’s. When software is made, and it uses an API, it may be *dependent* on that API. You might not port the software to another system if the same API is not supported. *Module System Integration* might part solve this. You might link to resources from other systems, so you might not necessarily need to port to native *Circular* to integrate with another system. However, you might want to be able to port your system to a native Circular system, to make use of features in it. Porting as such may be possible if the API your program depends on, is either accessible through *Module Systems Integration* or the API is supported inside a Circular system as well. That is the part *External API’s* might be responsible for. It may be undoable to support all existing API’s inside a Circular system, but if an API is supported intrinsically, *External API’s* might be the part of the system to put it in.

- ### ...

    - Perhaps later other types of systems to integrate with might come to light. That is what this placeholder at the end is for.