Circle Language | Construct Drafts
==================================

Text Code
---------

`[ Preliminary documentation ]`

Traditionally the systematics of a program are expressed by means of text code. But in the new language, systematics are stored as binary interlinked objects. Text code is a mere *expression* of those binary interlinked objects. The *Text Code* sub-module makes sure, that systematics are translated to text code. The text code can be adapted, resulting in changes to the stored binary objects, rather than the text code’s being literally stored.

The general idea is that each language element’s textual representation is considered the language element’s *literal*, that can be read out and assigned. However large the construct, its text code is still just a literal, be it composed of the literals of its sub-constructs.

The exact way the textual code is going to look inside the new language is not yet determined, because it is more important to work out the language *conceptually* along with its *diagram notation*, than it is to work out the *textual notation*. Version 2.0 of the new computer language had a text code, but it was still very basic.

None of the articles are finished. They are throw-togethers of ideas. The first topic, *Literals*, is what text code really is about. The other sub-folders were just dumped here. They are like leftovers from old documentation. The ideas at the bottom of this article also contain a lot of old material, that might be used inside new documentation in the future.

This folder contains the following sub-folders:

### Literals

The main article in this folder only contains an explanation of the traditional meaning of literals, and also some loose ideas about the topic of literals. There are the following sub-folders:

- #### Object Literals

    - This folder is empty, but should contain the explanation how objects can get literals. Simple objects, like numbers and dates, should be covered, but also how a literal can be assigned to an object to initialize the object’s members.

- #### Command Literals

    - The text code of command definitions and command calls are also considered literals. This article is not finished yet, but it should contain a description of how command definitions and command calls are translated to literals.

- #### Concept Literals

    - This article is not finished, but it should describe how the *concept* programming construct should be able to define new literal notations. Some programming constructs are programmed using the new computer language itself. So as you do that, you also should include a textual notation of those new constructs. So you should be able to custom-define textual notations for newly introduced constructs.

- #### Collection Operation Literals

    - Notations for *collections* should also have literals: from simple array access, to a notation to execute a command on all the items inside a collection at once.

### Access Operators

- This article is just a throw-together of ideas. Traditional text codes have access operators to access an object, a class, a procedure, arrays, pointers or values. Because other languages have access operators, the documentation about this new language also has a separate *Access Operators* article, in which it is to be figured out what place access operators has in the new language. Originally, it was hard to place access operators inside the new language. In C++ documentation access operators are introduced like they have an analogy to mathematic operators:  

````
    ::   Scope resolution  
    ::   Global  
    [ ]  Array subscript  
    ( )  Function call  
    .    Member selection (object)  
    –>   Member selection (pointer)  
    ,    Comma (parameter separation)  
    =    Assignment
````

- Access operators are hard to place inside a mathematical system. It is hard to find an analogy between mathematical operators and such access literals. However, it is clear what place access operators have inside the new computer language. Access operators are abstract character representations of system commands, such as __Object Get, Class Get, Item Get, Value Get__ and __Value Set__. All these system commands are explained in the *System Objects* chapter of the *Code* documentation folder. In the new computer language, access operators are just a textual expression of calls to those system commands. What has yet to be decided inside this unfinished article is how the access operators will textually look inside the new computer language.

### Declaration on first use

- Some programmer’s guide text books say you should declare variables of procedures at the beginning of procedures, to keep an overview of all the variables used inside the procedure. But maybe that rule is just for beginners, that do not make overviewable procedures. Another rule you could adopt instead, is to declare a variable right before you use it. This actually requires less CPU-power, than declaring all the variables at the beginning of the procedure, because if a code block is not executed, the variables used exclusively inside that code block are never allocated.

- When translating binary object systematics to text code, this rule can be applied, that a variable is declared in the text code right before it is used. This also means, that if a variable is used in several deeper blocks of code, the variable needs to be declared inside the *closest mutual parent* of those deeper blocks.

- The concept of *‘closest mutual parent’* is also applied in the diagram notation: the variable, reference or object is displayed inside the *mutual parent* of all the objects inside of which the variable, reference or object is used. (covered in the article *Automatic Containment*.)

### Half-case-sensitive identifiers

- When you type in an identifier to identify an element of the system, it needs to be *recognized*. Other programming languages recognize names either *case-sensitive* or *case-insensitive*. In the new computer language the recognition of identifiers is *half*-case-sensitive: the recognition does not pay attention to upper case or lower case letters, unless it has to. Only when two identifiers with the same name are within scope with different case usage, a case *sensitive* match needs to be made. This gives you the best of both worlds. It leaves out the problems that come with case-sensitive name matching, and reintroduces it only when required.

- This sub-folder does not contain an article yet, but the issue has been explained in the documentation folder *Identifiers* in the *Code* documentation folder.

### Macro Keywords

- Macro keywords is an idea, that came from an older design of the diagram notation. Access modifier literals were considered macro keywords. Some of the access modifiers, like __Public Read-Only__ would mean: __Get Public__ and __Set Private__. So the literals __Get Public__ and __Set Private__ would be replaced by the ‘macro keyword’ __Public Read-Only__. So there would be one keyword replacing a string of other keywords. That was the original concept of macro keywords. What place it still has in the new design is not clear yet. It will probably be part of the subject of concept literals, with which you can introduce new textual notations.

### Pointer Operators

- Hardly anything is documented inside this article yet.

- The language C++ has two pointer operators:

  Dereference / value of ( `*` )  
  Address of ( `&` )

- The dereference operator gets the value of an object reference. The address-of operator retrieves the memory address of a value. It has to be figured out what place this has in the new computer language.

- These pointer operators, just like access operators, will probably turn out to be just calls to system commands, such as __Object Get, Class Get, Item Get, Value Get__ and __Value Set__. All these system commands are explained inside the *System Objects* chapter of the *Code* documentation folder. There is full availability of everything you would want to do with pointers inside the new computer language. Which system commands will substitute dereference and address-of operators in C++ has to be figured out. *And* whether or not *more* pointer operations may be necessary in the new language.