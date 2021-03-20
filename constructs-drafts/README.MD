Circle Language | Construct Drafts
==================================

Overview
--------

`[ Preliminary documentation ]`

This documentation may contain drafts of ideas that might not become part of the spec. Or language constructs that are just not as clearly worked out yet.

- ### Black Boxes Construct Drafts

    - Lesser worked out ideas about this topic may be moved here from the spec.

- ### Expression

    - This part of the documentation may cover remaining topics about diagram expression.  
     
    - The idea behind expression in general is that a program’s systematics might not be described by text code, but text code as well as the diagram notation may be mere *expressions* of systematics, stored in some other way, for instance a binary way as interlinked objects.

    - This documentation may cover some misc issues that have not become part of the spec.

    - This documentation folder may be a mere throw-together of ideas or pieces of text, that came out of previous descriptions of new computer programming languages.  

- ### Implementations 

    - Topics in this folder may have been left out of the spec, because of a decision not to cover *implementations* and applications of the diagram notation. Internal workings may not be that essential for conveying the ideas about this diagram language.

    - Here might be some of the topics that could  be found here:

    - __Code Editor__

        - This document may not have been written yet. On top of text code being constructed and parsed, text code may also separately require a code editor for use in the programming environment.

    - __Optimization__

        - Covers any kind of optimization algorithm, that might be integrated into the new computer language. For now this is considered not too important to think about.

- ### Input Output

    - The concept of input and output may be well-known by computer experts, yet the concept does not seem very present in both object oriented program code or relational database. Something simply ‘becomes’ input or output, arbitrarily chosen by the programmer, but it might not explicitly *defined* in program code, what is the input and what is the output: it could be a return value returned by a procedure, a value passed along to another procedure, but it could also be reads, writes deletes and inserts into a database. Those things are spread out all over the procedures and you do not really see where something is input and where something is output. Yet, input and output seem a fundamental idea in computer programming. It seems we talk about it all the time. In the new computer language, input and output may get a more prominent position.

    - This documentation is not finished up yet. It contains a lot of unfinished texts but also some ideas that are perhaps nice, but it is all not worked out yet. The concept of input and output may be taken further. What might be worked out, is a definition of what input and output is and what different forms of input and output there might be. In the end, every command may have an input / output definition, that could consist of for instance reads, writes, additions and removals of data. This might not define *exactly* what the command does, but it does define what data is affected and what data is used. Users can always see what the input and output of a program or command is and this offers better security, because the user can see the input / output effect of what they are about to run. You can further secure the system by allowing a command to only access data, that it says it needs to access, so nothing funky can be run inside a program. This definition of input and output of a command will be called the *Command IO*.

    - When two commands affect the same data, they could be in each other’s way. The definition of that overlapping usage and alteration is called *Compared IO*. The idea is, that when you have defined what data is mutually used, you have defined the input-output dependency of commands.

    - The hope is, that the input-output dependency, or *outcome dependency*, will offer a mechanism for better managing the execution order of commands. Perhaps the right execution order of commands can be automatically determined without intervention of a programmer: *automatic execution order*. It is not fully worked out yet, but the hope is, that this can be translated into a new method for resolving concurrent access of data *(concurrency resolution)* and automatically determining whether things have to run serially or things can be processed in parallel, offering an automatic way to resolve *parallelism*. When working out this documentation, the exact definition of the concepts above will be worked out and hopefully it can be carefully explained how just by giving the concept of input and output a more prominent position in computer language and comparing different command IO definitions, there will be complete resolution of concurrency and parallelism as well as better security.

- ### Interfaces Construct Drafts

    - Lesser worked out ideas about this topic may be moved here from the spec.

- ### Text Code

    - Traditionally, the systematics of a program are expressed by means of text code. But in the new language systematics are stored as binary interlinked objects. Text code is a mere *expression* of those binary interlinked objects. The *Text Code* sub-module makes sure, that systematics are translated to text code. The text code can be adapted, resulting in changes to the stored binary objects, rather than that the text code is literally stored.

    - The articles in the *Text Code* documentation folder are not finished. They are mostly a throw-together of ideas. The exact way the textual code is going to look is not yet determined, because it was more important to work out the language conceptually along with its diagram notation, than it was to work out the textual notation. The general idea, though, is that each language element’s textual representation is considered its *literal*, that can be read out and assigned. However large the construct, the text code that represents it is still just a literal, be it composed of the literals of its sub-constructs. This is just an idea, but it might be the way to go.

    - The following sub-topic might be found here:

    - __Identifiers__

        - Identifiers are names for objects, collections, attributes, sites, programs, modules or any other element of a system. Any element of a system can get an identifier. This documentation folder describes how such names are used inside the new computer language. The documentation folder consists of five articles. The two most basic ones are finished. The three less fundamental ones are not finished.

- ### Automatic Containment

    - The concept of automatic containment would be about automatically translating a referential structure to a containment structure.

    - The idea may have loose ends.

- ### Access Control Loose Ideas

    - This document has loose ideas about access control.

- ### Ancestry Terms

    - Here terms may be described like "parent", "child", "ancestor" and about 50 variations of them or so.
     
    - The topic might not be essential for describing the Circle language and may also be a bit subjective.

- ### Basic Diagram Elements Construct Drafts

    - Lesser worked out ideas about this topic may be moved here from the spec.

- ### Circle Language Summary

    - In the future, the *Summary* documentation folder might contain a summary of all the coding concepts introduced. It is supposed to be a quick-reference card of all the concepts, with perhaps textual and diagram notation next to it, without  further explanations. The whole language might be displayed in this overview.
  
    - This summary is not made yet, might be created when the design of the new computer language is more complete. It may be decided to leave out such a summary, perhaps if the added value is questioned.

- ### Commands & Classes Loosely Coupled

    - Objects of the same class might have a similar set of commands.

    - But one particular idea for commands would be, that they might live as separate entities, not part of a specific class.

    - The general idea would then be, that a command would automatically be available inside a class, if one of its parameters matches with that class.

    - This idea is let go of for now, because it seemed optional and hard to match with other ideas like encapsulation and containment structure.

- ### Computer Language Old Ideas

    - Possibly unused ideas parked here.

- ### Concepts

    - Concepts are power-enhancements of software, that can be immediately applied to any system without any further programming. Concepts for instance makes you able to program ‘copy and paste’ functionality once, and then be able to automatically apply it to any system, without any additional code. A concept is a special programming construct. It is quite similar to what is also called an *aspect* in aspect oriented programming environments, only concepts are supposed to be a richer, more usable variation on aspects. Concepts are a result of the transition from code generators to generic modules, that adapt themselves to a structure description. In the code generator version of the new computer language (version 0.9), a certain aspect of the code (such as logging, copy and paste or XML serialization) was isolated into a single module, so that the concept is not spread out all over the generator’s code. In the *generated* code, however, the concept *was* spread out all over the code. The idea is, that any aspect / concept you could generate code for, should be replaced by a *concept* module, that embeds all the generic code. The concept can be automatically applied to any object or system by just specifying, that the system supports the concept. The idea is yet to be fully worked out, but the functional requirement is, simply stated: everything you can do with a concept in the code generator version of the new computer language, should be easily definable as a separate module, that replaces it. The idea is also yet to be worked out in software.

- ### Concurrency

    - Concurrency occurs when several running processes or users access the same data at the same time. This can result in several problems. There are several candidate mechanisms to solve concurrency problems. Which is the best one is yet to be determined. In this documentation folder you will find a lot of ideas about it, but the documentation is under construction. Look inside the article *Internet As A Single Computer* for a better description of the problem. The *Input Output* concept may offer a method to resolve concurrency issues in the future as well.

- ### Construct Drafts Loose Ideas

    - Uncategorized ideas.

- ### Conversions

    - When you assign an object’s state, and the state comes from an object with a different class, the assigned data may need to be converted. The conversion is performed by a conversion command. Conversion commands are system commands. New conversion commands can be freely introduced into the system. When objects do not match on assignment, implicit conversion takes place. The right conversion command is found by means of *Object Resolution* (see *Object Resolution).* Conversion commands can also be called *explicitly*. The documentation folder only contains a brief description of the idea. The details are to be worked out later.

- ### Errors & Warnings Loose Ideas

    - If a system tries to do something, that is not in accordance to the rules set by the system, an error is raised. A lot of rules will cause errors to be raised. Letting a program just ignore errors is not the way to go. Error message are not bad things. Error messages are our friends. When a program makes an error, you want to be notified about it. Programs are *not* supposed to make errors. When they do, something is going on, and it has to stop. There are several types of errors. There are also warnings: sort of like errors regarding style, that indicate a possible weakness in a program. You should only ignore a warning, when you know exactly what the warning means. There are different ideas about what a program is supposed to do when an error occurs. You may want the program to pause or terminate or perhaps the code should be rolled back entirely.

    - The complexities behind error handling may once be covered in this documentation, but it is not entirely worked out yet.

- ### Locking

    - Concurrency resolution ideas about locking mechanisms might be put here. The idea is not part of the spec as of yet.

- ### Multiple Language Layer

    - Multiple language layers may be the idea that programming language might be built up in layers, first starting perhaps with *arithmetic* algebra and numbers (`+ - * /`). Arithmetic expressions may be input of *comparative* algebra (`< > =`). Then building up to *logical* operations (`and or not`). Then may follow *execution flow* (`if else then`). Constructs consisting of all of those operations may be organized into *procedures*. Those may be grouped into *objects*. Objects may have *relations* with each other. And what layer follows above that. *Aspects*? *Generated* code? From this idea might once follow a nice story. The document may just contain a few loose ideas for now.
    
- ### Object Storage

    - Object Storage basically turns lists on storage devices into a landscape of digital objects. It is the binding force between basic data structures on storage devices and the object logic of the new computer language. It is about how basic data structures are used to store objects. Not all of these principles are original, because many other systems use them, but they were isolated here in a single folder as a single group of concepts required to turn storage into objects.
     
    - The documentation is not finished. It is the bone-structure of documentation yet to be finished. It does sum up the required concepts to turn basic data structures into digital objects. Some of the concepts, though, should be moved elsewhere to another Storage documentation section. Into this bone-structure, loose ideas are dropped as well as (unfinished) texts out of the documentation of the new computer language version 0.9, as well as texts made during the development of the new computer language version 2.0. Software has been developed using object storage concepts, because both those versions of the new computer language had to do with object storage in order to turn basic data structures into digital objects.

- ### Peels

    - This article is about a concept, that was later rejected. The article contains texts out of an old design of the diagram notation, that are about a notational concept that was later rejected: using extra lines around the shape to reveal information about the target of a line. It should not be gone into too much.

- ### Relationships Construct Drafts

    - Lesser worked out ideas about this topic may be moved here from the spec.

- ### Special Access

    - Tries to discuss differences between concepts like child access, global access, interface access to/from code blocks. The rules seem to be different. This text attempted to distinguish those rules. It did not seem the diagram notation depended very much on describing these concepts separately, so this was left out of the spec.

- ### Summaries of the C and C++ Languages

    - Attempts to summarize other programming languages, like C and C++, in the form of bulleted lists. They were made around the year 2004 during an analysis of the grammar of C and C++ to compare it to this Circle programming language.

- ### Symbol Language (2004)

    - Previous version of an attempt to describe this programming language.

- ### System Command Call Notations Construct Drafts

    - There might be several notations for calling a system command, like __Get__, __Set__ and __Use__ commands. The ideas here in construct drafts were deprecated notation proposals.

- ### Transactions

    - Concurrency resolution ideas about *transactions* might be put here. The ideas are currently not part of the spec.

- ### Libraries

    - The idea might be that base libraries might provide basic types and operations for *math* operations: arithmetic, comparative, logical, Boolean, bit operations for instance. Numbers and math operation might be objects, that link together (perhaps to be called *Math Objects*).

    - Another library might provide individual *assembly* instructions (machine instructions) as commands or perhaps substitutes of such basic operations.
     
    - Even __If__ statements and loops might be helped by a base library to provide the syntax.

    - *Events* perhaps as well.

    - This document may not be written yet.