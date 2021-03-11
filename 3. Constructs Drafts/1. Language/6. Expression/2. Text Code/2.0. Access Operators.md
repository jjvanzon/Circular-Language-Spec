Circle Language Construct Drafts | Text Code
============================================

Access Operators
----------------

- Access Globality Operator
- Access Object Operator
- Access Interface Operator
- Access Class Operator
- Access System Method Operator
- Access Genitivity Operator
- Access Module Operator

### Brainstorm

Different types of operator:

- Interface access .
- Member access .
- Sub member
- Sub system access :
- Type access ::
- an operator to enter an object’s type
- < more as such >

An example of a code line containing multiple access operators:

```
Core : Objects . Event Map :: Alignment . Arbitrary
```

- : Subsystem to subsystem
- Subsystem to type
- Subsystem to interface (interface access means object access)
- Subsystem to member
- type to interface
- type to member
- interface to member
- member to submember
-----
- to subsystem
- to type
- to interface
- to member
- to submember
-----
- : to subsystem
- :: to type
- ; to interface
- . to member
- .. to submember

```
Core : Object :: Event Map ; Alignment .. Arbitrary
```

Other scheme:

- : from subsystem
- :: from type
- . from interface
- . from member to member
- to submember

Alignment . 

-----

Standards

I forgot genitive containment, didn’t I. You do supply a capsule, but everything inside the capsule is like it’s inside its parent. That’s actually what the triangle is for. Nevertheless, you’re forced to use the identifier for access. That’s normal for interfaces, except for the whole interface.

I may want it to be an interface, but I want to see it as member access outside.

The thing is… the member of a purely genitive subdivision without programmatic consequences. Uhmmm… yeah… whatever

An example:

Alignment
- Arbitrary
- Record Size
- Field Start

The properties of Alignment can be reached by the siblings of Alignment. But the siblings of Alignment can also be accessed by the properties of Alignment. So they have access to ...