Circle Language | Construct Drafts
==================================

Overview
--------

`[ Preliminary documentation ]`

This documentation may contain drafts of ideas that might not become part of the spec. Or language constructs that are just not as clearly worked out.

- ### [Expression](expression)

    - The idea behind expression in general might be that a program’s systematics might not be described by text code, but text code as well as the diagram notation may be mere *expressions* of systematics, stored in some other way, for instance a binary way as interlinked objects.

    - This part of the documentation may cover remaining topics about diagram expression. This documentation may cover some misc issues that have not become part of the spec. This documentation folder may be a mere throw-together of ideas or pieces of text, that came out of previous descriptions of new computer programming languages.  

- ### [From Spec](from-spec)

    - Topics recognizable from the *spec*, but then maybe lesser worked out ideas about these topic.

- ### [Implementations](implementations)

    - Topics in this folder may have been left out of the spec, because of a decision not to cover *implementations* and applications of the diagram notation. Internal workings may not be that essential for conveying the ideas about this diagram language. You may find topics here like "Optimization" and "Code Editor".

- ### [Input Output](input-output)

    - The concept of input and output may be well-known by computer experts, yet the concept does not seem very present in both object oriented program code or relational database. Something simply seems to ‘become’ input or output, arbitrarily chosen by the programmer, but it might not be explicitly *defined* in program code, what is the input and what is the output: it could be a return value returned by a procedure, a value passed along to another procedure, but it could also be reads, writes deletes and inserts into a database. In Circle language, input and output may get a more prominent position. It may offer opportunities for resolution of concurrency and parallelism as well as improved security perhaps.

- ### [Text Code](text-code)

    - Traditionally systematics of a program might be expressed by means of text code. But in Circle language, systematics might be stored in another way for instance as binary interlinked objects. Text code may be a mere *expression* of those stored objects. A *Text Code* sub-module might translate those systematics to text code. The text code might be adapted, which may result in changes to the stored objects, rather than the text code’s being literally stored.

    - One of the ideas would be that each language element’s textual representation might be considered the language element’s *literal*, that could be read out and assigned. The idea was, that however large the construct, its text code might still just be a literal, be it composed of the literals of its sub-constructs. This is just an idea, but it might be the way to go.

    - Exactly how the textual code might look in Circle, might not have been decided yet, because at one time it was considered more important to work out the language *conceptually* along with a *diagram notation*, than to work out the *textual notation*. Experimental version 2.0 of a new computer language had a text code, but it was still quite basic.

    - The articles might not have been finished. They might be throw-togethers of ideas sort of like cut up leftovers from older documentation.

- ### [Access Control Loose Ideas](access-control-loose-ideas.md)

    - This document may contain loose ideas about access control.

- ### [Ancestry Terms](ancestry-terms.md)

    - Here terms may be described like "parent", "child", "ancestor" and about 50 variations of them or so.
     
    - The topic might not be essential for describing the Circle language and may also be a bit subjective.

- ### [Automatic Containment](automatic-containment.md)

    - The concept of automatic containment would be about automatically translating a referential structure to a containment structure.

    - The idea may have loose ends.

- ### [Circle Language Summary](circle-language-summary.md)

    - In the future, the *Summary* article might contain a summary of all the coding concepts introduced. It is supposed to become a quick-reference card of all the concepts, with perhaps textual and diagram notation next to it, without further explanations. The whole language might be displayed in this overview.
  
    - This summary is not made yet, but might be created when the design of the Circle language might be more complete. It may be decided to leave out such a summary, perhaps if the added value would be questioned.

- ### [Commands & Classes Loosely Coupled](commands-and-classes-loosely-coupled.md)

    - Objects of the same class might have a similar set of commands. But one particular idea for commands would be, that they might live as separate entities, not part of a specific class. The general idea would then be, that a command would automatically be available inside a class, if one of its parameters matches with that class.

    - This idea is let go of for now, because it seemed optional and hard to match with other ideas like encapsulation and containment structure.

- ### [Computer Language Old Ideas](computer-language-old-ideas.md)

    - Possibly unused ideas might be parked here.

- ### [Concepts](concepts.md)

    - Concepts might be power-enhancements of software, that might be immediately applied to any system without any further programming. The hope would be that concepts for instance make you able to program "copy and paste" functionality once, and then automatically apply it to any system, without any additional code. A *concept* might be close to what some programming environments call *aspects*. But the hope would be that concept might become a richer, more usable variation on aspects. Concepts may be the result of a transition from code generators to generic modules, that might adapt themselves to a structure description, that you might feed to it. In the code generator version of the new computer language (version 0.9), a certain aspect of the code (such as logging, copy and paste or XML serialization) may be isolated into a single module, so that the concept might not be spread out all over the *generator’s* code. In the *generated* code, however, the concept *could* be spread out all over the code. The idea was, that any aspect / concept you could generate code for, might be replaced by a *concept* module, that might embed all the generic code. The concept might be automatically applied to any object or system by just specifying, that the system would support the concept. The idea may not be fully worked out yet, but the functional requirement might be, simply stated: everything you might do with a concept in the experimental code generator version of the computer language, should be (easily) definable as a separate module, that would replace it. The idea might not have been worked out in software yet.

- ### [Concurrency](concurrency.md)

    - Concurrency might occur when several running processes or users would access the same data at the same time. This may result in several problems. There might be several candidate mechanisms to help with concurrency problems. Which is the best, might not be clear. This article may contain quite some ideas about it, but they might still be under construction. The article *Internet As A Single Computer* might shed light on the problem better. The *Input Output* concept might at one point also offer a method to resolve concurrency issues.

- ### [Construct Drafts Loose Ideas](construct-drafts-loose-ideas.md)

    - Uncategorized ideas.

- ### [Conversions](conversions.md)

    - When an object’s state is assigned, and the state comes from an object with perhaps a different class, the assigned data may need to be converted. The conversion might be performed by a conversion command. Conversion commands might be considered system commands. New conversion commands might be introduced into the system. When objects would not match on assignment, implicit conversion may take place. The right conversion command might be found by means of *Object Resolution* (see *Object Resolution).* Conversion commands might also be called *explicitly*. The Conversions article might only contain a brief description of the idea. The details might be worked out later.

- ### [Errors & Warnings Loose Ideas](errors-and-warnings-loose-ideas.md)

    - If a system tries to do something, that is not in accordance to the rules of a system, an error might be raised. A lot of rules might cause errors to be raised. Letting a program just ignore errors might not be the way to go. Error message might not be bad things. Error messages may be our friends. When a program might make an error, you might want to be notified of it. Programs might not be supposed to make errors. When they do, something might be going on, and a safe choice may be to stop. There may be several types of errors. There may also warnings: sort of like errors, but perhaps more regarding style, indicating a possible weak point in a program. You might only want to ignore a warning, when you know exactly what the warning means. There may be different ideas about what a program is supposed to do when an error occurs. You may want the program to pause or terminate or perhaps the code should be rolled back entirely.

    - The complexities behind error handling may once be covered in this documentation, but it is not entirely worked out yet.

- ### [Locking](locking.md)

    - Concurrency resolution ideas about locking mechanisms might be put here. The idea might not be part of the spec as of yet.

- ### [Multiple Language Layers](multiple-language-layers.md)

    - Multiple language layers may be the idea that programming language could be built up of layers, first starting perhaps with *arithmetic* algebra and numbers (`+ - * /`). Arithmetic expressions may be input of *comparative* algebra (`< > =`). Then building up to *logical* operations (`and` / `or` / `not`). Then may follow *execution flow* (`if` / `else` / `then`). Constructs consisting of all of those operations may be organized into *procedures*. Those may be grouped into *objects*. Objects may have *relations* with each other. And what layer follows above that? *Aspects?* *Generated* code? From this idea might once follow a nice story. The document may just contain some loose ideas for now.
    
- ### [Object Storage](object-storage.md)

    - Object Storage may turn lists on storage devices into a landscape of digital objects. It might be the binding force between basic data structures on storage devices and the object logic of this computer language. It may be about how basic data structures are used to store objects. Not all of these principles might be original, because other systems might use them, but they were isolated here in a single place as a single group of concepts that may be used to turn storage into objects.
    
    - Perhaps trying to find one way to manage memory allocation, database-like storage and file systems might be a bit ambitious.
     
    - The documentation might not be finished. An attempt was made to sum up the required concepts trying to turn basic data structures into digital objects.

- ### [Peels](peels.md)

    - This article seems to be about a concept, that may have later been rejected. The article seems to contain texts out of an older design of the diagram language, that would be about a notational concept that seemed later be rejected: using extra lines around a shape to try and reveal information about the target of a line.

- ### [Special Access](special-access.md)

    - Tries to discuss differences between concepts like child access, global access, interface access and access to/from code blocks. The rules seem to be different between those. This text attempted to distinguish those rules. It did not seem the diagram notation depended very much on describing these concepts separately, so this was left out of the spec.

- ### [Summaries of the C and C++ Languages](summaries-of-the-c-and-cpp-languages.md)

    - Attempts to summarize other programming languages, like C and C++, in the form of bulleted lists. They seem to be made around the year 2004 during an analysis of the grammar of C and C++ to perhaps compare it to this Circle programming language.

- ### [Symbol Language (2004)](symbol-language-2004.md)

    - Previous version of an attempt to describe this programming language.

- ### [Transactions](transactions.md)

    - Concurrency resolution ideas about *transactions* might be put here. The ideas currently might not belong in the spec.

- ### Libraries

    - Might not have its own article.

    - The idea might be that base libraries might provide basic types and operations for *math* operations: arithmetic, comparative, logical, Boolean, bit operations for instance. Numbers and math operation might be objects, that link together (perhaps to be called *Math Objects*).

    - Another library might provide individual *assembly* instructions (machine instructions) as commands or perhaps substitutes of such basic operations.
     
    - Even __If__ statements and loops might be helped by a base library to provide the syntax. *Events* perhaps as well.