Computer Language
=================

New Computer Language Summary
-----------------------------

Computer Language,
2008-08-06

In the end, you are going to have to summarize the coding concepts and diagram syntax.

How about you only give the diagram syntax, if the coding concept actually has its own syntax, not when the diagram expression just functions a clarification of the concept. Then you have all the syntaxes in a list, and you can distinguish derived concepts and uses of a concept from the main concepts, that actually introduce syntax rules.

JJ

## Out of the original Symbol documentation

#### Summary of Concepts

< Make this a more extensive topic with a full description of the Symbol language >

< The theory of the Symbol language is a soup of concepts. However, in a book you have to start at one point and gradually explain things one by one, without referring to any unexplained material, even though it’s part of the soup. It was hard to find a point at which to start, and the beginning of the book is definitely not the first part of the book I wrote.

This summary, though, doesn’t organize Symbol in the order of explaining it and it doesn’t cover concrete examples either. It just orders the concepts by category and is an overview of the soup of rules that is Symbol.

< ‘Static’ is part of Object Structure. So lifetime is part of object structure.
Access and Scope are the same subject. >

##### Rough

- Identifiers
- Objects
- Procedures
- Access

- Generic Code

##### More Detailed

< Overloading can only be part of procedures if you either cannot overload an object or you call a procedure to return an object... >

- Identifiers
- Objects
    - Objects, Types and Interfaces
   
    - Destruction
    - ‘Normal’ Variables
    
    - Static
    
    - Object Operators
- Conversion 
- Creation
- Pointer
    - \*   Dereference
    - &    Address-of
    - .\*  Apply pointer to type member (objects) 
    - –>\* Dereference pointer to type member
- Size of object
- Type name
- Assigment: =
    - Blocks...
    - Lifetime

- Procedures
    - Procedures
    - Procedure Reference
        - Pointing
        - Calling
    - Operation Flow
        - Normal order
        - Selection
        - Iteration 
        - Call and Return
    - Parameters
        - In, Out, Thru
        - Optional
        - Variable Amount
        - Return Type
    - Operators
        - Operators *are* procedures. They are assigned a special notation.
        - Evaluation order, parenthesis, Precedence
        - Conversion operators
            - Object Extension
    - Include
    - Exclude
    - Override
    - Merge
    - Pre-extend
    - Post-extend
    - Overload
    - Properties and Events

- Ambiguity
    - Overloading
        - Being able to reference things with the same name
    - The thing being referenced dependent of the referers place...
    - Hiding names: 
        - one name takes precedence over another. 
        - Accessing a hidden name.
    - Real ambiguity

- Recursion and Circularity
- Delegating
- Notations


- Access
    - < does constant have a place here. Private read, public write... >
    - Public, Private
        - For different Aspects: 
            - Object
            - Type
            - Interface
            - Creation
            - Genericity change
        - For different Parties: 
            - Me
            - Parent
            - Children
            - N levels up
            - N levels down
            - Interface parent
            - Interface children
            - N interface levels up
            - N interface levels down
            - Up until globality
            - N globalities up
            - Certain types
            - Certain objects
            - Certain globality types
            - Certain globality objects
    - Globalities
    - Delocating members 
        - (‘friend’ sorta transfers things out of a type to the nearest globality. Is all that required? Does Symbol not  have better substitutes for this?)
    - Access Operators
        - Special operators. Are they operators? If they are then they should be able to be overloaded. Maybe that’s handy too.
        - Access globality
        - Access object
        - Access interface
        - Access type
        - System procedure arguments
        - Genetivity

    - Generic and Explicit
    - Recursion and Circularity
    - Constant and Variable
    - Assignment
        - Object
        - Reference
        - Creation
        - Conversion
        - Type
        - Interface
        - State
            - Copy
            - Literal

- Generic code
    - Templates
    - Generic code:
        - Code automatically generated real time as interface of a generating component is used.


Standard Variable Types and Operators are covered in ‘Math’

##### Brainstorm

- Dubious:
    - pointer to any member of a type (ClassName::\*). Genericity like that.
    - (Grouping Symbol?)

- Afleidbare concepts:

    - Variables types:
        - Pointers
        - Structure

    - Namespaces
    - Module
    - Strings 
    - Declarations on first use (in the middle of a statement)
    - Friend access modifier
        - Heeft in C++ een aantal functies:
            - ...
        - Deze hebben allemaal een vervanging in Symbol: