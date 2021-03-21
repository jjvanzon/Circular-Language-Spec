Circle Language | Construct Drafts
==================================

Text Code
---------

`[ Preliminary documentation ]`

Traditionally the systematics of a program might be expressed by means of text code. But in the new language, systematics might be stored in another way like binary interlinked objects. Text code may be a mere *expression* of those stored objects. The *Text Code* sub-module might make sure, that systematics are translated to text code. The text code might be adapted, resulting in changes to the stored  objects, rather than the text code’s being literally stored.

The exact way the textual code is going to look inside the new language is not yet determined, because it was considered more important to work out the language *conceptually* along with its *diagram notation*, than to work out the *textual notation*. Version 2.0 of the new computer language had a text code, but it was still quite basic.

The articles might not be finished. They might be throw-togethers of ideas and cut up leftovers from older documentation.

You might find the following content here:

- ### [Identifiers](identifiers)

    - ...

- ### [Literals](literals)

    - ...

- ### [Parameters in Text Code](parameters-in-text-code)

    - ...

- ### [Access Operators](access-operators.md)

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

- ### [Assignment in Text Code](assignment-in-text-code.md)

    - ...

- ### [Declaration on first use](declaration-on-first-use.md)

    - Some programmer’s guide text books say you should declare variables of procedures at the beginning of procedures, to keep an overview of all the variables used inside the procedure. But maybe that rule is just for beginners, that do not make overviewable procedures. Another rule you could adopt instead, is to declare a variable right before you use it. This actually requires less CPU-power, than declaring all the variables at the beginning of the procedure, because if a code block is not executed, the variables used exclusively inside that code block are never allocated.

    - When translating binary object systematics to text code, this rule can be applied, that a variable is declared in the text code right before it is used. This also means, that if a variable is used in several deeper blocks of code, the variable needs to be declared inside the *closest mutual parent* of those deeper blocks.

    - The concept of *‘closest mutual parent’* is also applied in the diagram notation: the variable, reference or object is displayed inside the *mutual parent* of all the objects inside of which the variable, reference or object is used. (covered in the article *Automatic Containment*.)

- ### Half-Case-Sensitive Identifiers

    - When you type in an identifier to identify an element of the system, it needs to be *recognized*. Other programming languages recognize names either *case-sensitive* or *case-insensitive*. In the new computer language the recognition of identifiers is *half*-case-sensitive: the recognition does not pay attention to upper case or lower case letters, unless it has to. Only when two identifiers with the same name are within scope with different case usage, a case *sensitive* match needs to be made. This gives you the best of both worlds. It leaves out the problems that come with case-sensitive name matching, and reintroduces it only when required.

    - This topic might not have its own article, but the issue has may be explained in the documentation folder *Identifiers*.

- ### Macro Keywords

    - Macro keywords is an idea, that came from an older design of the diagram notation. Access modifier literals were considered macro keywords. Some of the access modifiers, like __Public Read-Only__ would mean: __Get Public__ and __Set Private__. So the literals __Get Public__ and __Set Private__ would be replaced by the ‘macro keyword’ __Public Read-Only__. So there would be one keyword replacing a string of other keywords. That was the original concept of macro keywords. What place it still has in the new design is not clear yet. It will probably be part of the subject of concept literals, with which you can introduce new textual notations.

- ### [Pointer Operators](pointer-operators.md)

    - Hardly anything is documented inside this article yet.

    - The language C++ has two pointer operators:

      Dereference / value of ( `*` )  
      Address of ( `&` )

    - The dereference operator gets the value of an object reference. The address-of operator retrieves the memory address of a value. It has to be figured out what place this has in the new computer language.

    - These pointer operators, just like access operators, will probably turn out to be just calls to system commands, such as __Object Get, Class Get, Item Get, Value Get__ and __Value Set__. All these system commands are explained inside the *System Objects* chapter of the *Code* documentation folder. There is full availability of everything you would want to do with pointers inside the new computer language. Which system commands will substitute dereference and address-of operators in C++ has to be figured out. *And* whether or not *more* pointer operations may be necessary in the new language.

- ### [Qualified Event Names](qualified-event-names.md)

    - ...

- ### [Text Code | Loose Ideas](text-code-loose-ideas.md)
  
    - Contains a lot of older material, that might be used inside new documentation in the future.