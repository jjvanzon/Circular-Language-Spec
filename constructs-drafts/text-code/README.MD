Circle Language | Construct Drafts
==================================

Text Code
---------

`[ Deprecated documentation ]`

Traditionally systematics of a program might be expressed by means of text code. But in Circle language, systematics might be stored in another way for instance as binary interlinked objects. Text code may be a mere *expression* of those stored objects. A *Text Code* sub-module might translate those systematics to text code. The text code might be adapted, which may result in changes to the stored  objects, rather than the text code’s being literally stored.

How exactly the textual code might look in Circle might not yet be determined, because at one time it was considered more important to work out the language *conceptually* along with a *diagram notation*, than to work out the *textual notation*. Experimental version 2.0 of a new computer language had a text code, but it was still quite basic.

The articles might not be finished. They might be throw-togethers of ideas sort of like cut up leftovers from older documentation.

You might find the following content here:

- ### [Identifiers](identifiers)

    - Identifiers may be names for objects, collections, attributes, sites, programs, modules or other elements of a system. 

- ### [Literals](literals)

    - The idea here would be that each language element’s textual representation might be considered the language element’s *literal*, that could be read out and assigned. The idea was that however large the construct, its text code might still just be a literal, be it composed of the literals of its sub-constructs.

- ### [Parameters in Text Code](parameters-in-text-code)

    - Here might be found several specific topics about parameters notation in text code.

- ### [Access Operators](access-operators.md)

    - This article might just be a throw-together of ideas. Traditional text codes may have access operators to access an object, a class, a procedure, arrays, pointers or values. Because other languages may have access operators, the documentation about Circle might also has a separate *Access Operators* article, which may make an attempt to figure out what place access operators might have in this Circle language. Originally, it may have been hard to give access operators a place inside this Circle language. In C++ documentation access operators seem to be introduced like they have an analogy to mathematic operators:  

    ````
        .    Member selection (object)
        –>   Member selection (pointer)
        [ ]  Array subscript
        ( )  Function call
        ,    Comma (parameter separation)
        =    Assignment
        ::   Scope resolution
        ::   Global
    ````

    - Access operators seem hard to place inside a mathematical system. It may be difficult to find an analogy between mathematical operators and such access literals. However, a clearer view on what place access operators might have inside Circle language. Access operators seem to be abstract character representations of system commands, such as __Object Get, Class Get, Item Get, Value Get__ and __Value Set__. All these system commands seem already explained in the *System Objects* chapter of the *Spec*. Inside Circle language, access operators might just be a textual expression of calls to those system commands. What might not yet be clarified inside in this unfinished article is how the access operators might textually look inside the new computer language.

- ### [Assignment in Text Code](assignment-in-text-code.md)

    - A specific text notation might be suggested for assignment so that it might distinguish value, object, class and interface assignment and pointer-related assignments, for instance: `c=` and `o=->`.

- ### Declaration on First Use

    - Some programmer’s text books might say you should declare variables of procedures at the beginning of procedures, to keep an overview of all the variables used inside the procedure. It might be a bit suggestive if that is necessarily the best thing to do. A suggestion here is declare a variable right before you use it might be a way to go. This may give a hint about parts of a procedure depend on which variable and which parts of a procedure do not use that variable. Perhaps declaring a variable upon first use requires slightly less CPU-power, than declaring all the variables at the beginning of the procedure, because if a code block is not executed, the variables used exclusively inside that code block might not get assigned.

    - If (binary) stored object systematics might be translated to text code, this rule might be applied, that a variable is declared in the text code right before it is used. This also might mean, that if a variable is used in several deeper blocks of code, the variable may need to be declared inside the *closest mutual parent* of those deeper blocks.

    - The concept of *‘closest mutual parent’* seems similar as a diagram notation idea that might be called *automatic containment*. There a variable, reference or object would be displayed inside the *closest mutual parent* of all the objects inside of which the variable, reference or object might be used.

- ### Half-Case-Sensitive Identifiers

    - When typing in an identifier to identify an element of the system, it might need to be *recognized* by the system. Other programming languages may recognize names either *case-sensitive* or *case-insensitive*. For the Circle language the recognition of identifiers might become *half*-case-sensitive: the recognition does might only pay attention to upper case or lower case letters, if it has to. Only when two identifiers with the same name may be within scope with different case usage, a case *sensitive* match might need to be made. This may combine two concepts into one. It might relieve possible confusion that that may arise from case-sensitive name matching, and might reintroduce it only when required.

    - This topic might not have its own article, but the issue may also have been explained in a documentation folder that might be called *Identifiers*.

- ### Macro Keywords

    - Macro keywords would be an idea, that may have come from an older design of the diagram notation. Access modifier literals might have been considered macro keywords. Some of the access modifiers, like __Public Read-Only__ could mean: __Get Public__ and __Set Private__. So the literals __Get Public__ and __Set Private__ may be replaced by the ‘macro keyword’ __Public Read-Only__. So there would be one keyword replacing a string of other keywords. That might have been the original concept of macro keywords. What place it may still has in the a newer design of the language might not be that clear. It might become part of the subject of concept literals, with which you might introduce new textual notations.

- ### Pointer Operators

    - The language C++ seems to have two pointer operators:

      Dereference / value of ( `*` )  
      Address of ( `&` )

    - The dereference operator seem to get the target of a reference. The address-of operator seems to retrieve the memory address of a value. It might be considered what place this has in Circle.

    - These pointer operators, like access operators, might turn out to be calls to system commands as well, such as __Object Get, Class Get, Item Get, Value Get__ and __Value Set__. All these system commands may be explained inside the *System Objects* part of the *Spec*, not necessarily here. It might be an idea to try and have full availability of everything you might want to do with pointers inside Circle language. Which system commands might substitute dereference and address-of operators in C++ might be figured out. And whether or not more pointer operations may be welcome in the Circle language.

- ### [Qualified Event Names](qualified-event-names.md)

    - Tries to describe how it might look in text code to pick up an event from an object more than one layer deeper in the containment structure of the objects.

- ### [Text Code Loose Ideas](text-code-loose-ideas.md)
  
    - Contains older material, that might once be used inside newer documentation.