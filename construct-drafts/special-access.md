Construct Drafts | Special Access
=================================

`[ Draft ]`

__Contents__

- [Introduction](#introduction)
- [Neighbor Access](#neighbor-access)
- [Child Access](#child-access)
- [Nested Command Access](#nested-command-access)
    - [Brainstorm](#brainstorm)
- [Global Access](#global-access)
- [Pentagons not Exchangeable with Triangles and Circles](#pentagons-not-exchangeable-with-triangles-and-circles)
- [Extra Indication](#extra-indication)
- [Interface Access](#interface-access)
- [Modules, Interfaces and Nested Commands](#modules-interfaces-and-nested-commands)
- [Brainstorm](#brainstorm-1)

## Introduction 

(From the original Symbol documentation)

< Do neighbor access and child access protect the independence of types? As a substitute for the old, false rule: ‘Can’t call upward in the ancestry’? >

There’s several ways to access a command. The most common way is for commands of the same object to call upon each other. The second most common way is for a parent to access a child’s commands. A global object is accessible from anywhere within the module and there are more ways. I might discuss these different ways of access one by one in this section.

## Neighbor Access

< Discuss commands within the same object accessing each other. >

## Child Access

The normal way of accessing an object is *child access*: an object can only access its what’s inside of it: its ancestors.

![](images/0.%20Special%20Access.001.png)

< Darn. This is not right, I need to make a call from a command. The line above is a reference line. >

An access always takes place in a command call. In this picture Parent is accessing Child.

You can’t all anything higher in the encapsulation hierarchy, so an object can’t access anything outside the object. If it is to access anything outside the object, it needs to contain a reference to something outside the object.

![](images/0.%20Special%20Access.002.png)

The object is then accessing this *reference*, which is inside the object. The reference just happens to resolve in something outside the object, but the parent is still accessing something inside itself.

-----

<  
2002 +/-:
Variables declared inside a parent block in a command are accessible directly by the child blocks. Variables declared inside a child block are inaccessible to a parent block.  
/>

## Nested Command Access

Or: 'access from nested commands'.

< Nice sentence:  
A command makes all direct children accessible to all blocks.  
Only is that true? >

In a diagram nested commands might be squares contained in other squares that have no lines pointing away from them.

![](images/0.%20Special%20Access.016.png)

Nested commands might have access to the contents of all their ancestor blocks and the command definition they’re in. This means that a nested command might  directly access its containing definition’s members:

![](images/0.%20Special%20Access.017.png)

and all its encapsulating nested commands:

![](images/0.%20Special%20Access.018.png)

But a nested command might not have access to a nested command that doesn’t encapsulate it.

![](images/0.%20Special%20Access.019.png)

So its like the borders of nested commands can be ignored in outward access.

### Brainstorm

Nested commands may have special access privileges compared to delegated command symbols.

![](images/7.%20Commands%20Ideas.049.jpeg)

< Bad explanation following >  
Nested commands may freely access anything of its parent block and the parent block’s parent block, etcetera. If going up the command ancestry a command symbol is encountered with a reference line, the nested command can access this ancestor freely, but not any higher in the command ancestry.

In the picture above, the top two lines could have been set by A itself. The first resides in A’s parent nested command. The second resides in the *execution* that parents A, so still accessible to A. The last line, crossed out, can’t be set by A itself, because it resides outside A’s containing call. It can be set only by a symbol higher than A’s containing call, for instance B.

## Global Access

< Nice sentence:  
Module makes all direct children accessible to all ancestors >

There’s also a way to make objects accessible not only to parents, but accessible from anywhere. This makes the accessed objects global.

A special symbol is used: a pentagon.

![](images/0.%20Special%20Access.003.png)

Anything directly inside the pentagon is accessible from *anywhere*. So the (public) direct children of the pentagon are global:

![](images/0.%20Special%20Access.004.png)

*The blue symbols are accessible from anywhere inside the pentagon.*

A pentagon and all its contents are also called a *module*.

It’s like any object inside a module has a reference to the module object:

![](images/0.%20Special%20Access.005.png)

These references don’t really exist, though. Everything global is just reachable inside every object inside a module.

![](images/0.%20Special%20Access.006.png)

In this the solid line *can* be a call, because it’s a reference to something global.

A module can also be viewed as being a module, or software component. It is a way to order code into components. Modules can be embedded just like as objects:

![](images/0.%20Special%20Access.007.png)

In fact, a module symbol is an object symbol too. It works as a triangle: you can access things in the module directly, but also by qualifying it with the module identifier, but it has the special side effect that anything it directly contains can be directly accessed from anywhere.

-----

When you want one module to use another, you make a reference to the other module:

![](images/0.%20Special%20Access.008.png)

The child module can then be accessed like a circle or a triangle, but refers to an existing instance of the module (software component). Since the module is a direct child of another module, anything in the contained module is just as global as anything in the parent module. However, if you make the child module private, it’s not accessible outside the parent module. It is accessible as global inside the parent module, though.

In other languages, modules usually contain a large amount of code, because it’s not easy to handle many modules. In symbol it’s easier to manage modules and whenever you need the effect of having a small, local, module (or software component), you can easily use a module.

This is also an invitation to making a more refined division in software components. You can not only easily work with a division in more components. You can also embed software components. And you can finely control referencing existing instances of software components.

The child module in the picture above can only access things global inside itself. It can not access the global things of its parent module.

## Pentagons not Exchangeable with Triangles and Circles

A pentagon is not exchangeable with triangles and circles as much as triangles and circles are exchangeable. Global has the side effect that things become accessible where otherwise inaccessible. If you suddenly replace the pentagon with a circle or triangle it might mean that things formerly global are no longer global and all sorts of accesses in the module object are suddenly invalid. For that a pentagon stays a pentagon and a reference to it can only be a pentagon itself.

## Extra Indication

There are two common ways to extra denote that you’re referencing something global.

Put a multiply peeled pentagon around the call:

![](images/0.%20Special%20Access.009.png)

This pentagon reference doesn’t really exist, though.

-----

You can also put a multiply peeled pentagon in the direct parent object and reference this multiply peeled pentagon, rather than the global symbol directly:

![](images/0.%20Special%20Access.010.png)

This multiply peeled pentagon doesn’t exist either.

## Interface Access

The separate interfaces of an object:

![](images/0.%20Special%20Access.011.png)

can be accessed through a reference to the triangle, just like you might access a circle:

![](images/0.%20Special%20Access.012.png)

The special thing about a triangle, though is that its members are also directly accessible through its parent. When referencing the circle, you can access the triangle’s members as if the triangle capsules weren’t even there.

You can’t see in the picture above if the called square is referenced through the circle or through the triangle. If you want to indicate that it’s accessed through the circle, you can put an access symbol with the circle. If you want to indicate that it’s accessed through the triangle, you put an access symbol with the triangle, or with both the circle and the triangle.

| ![](images/0.%20Special%20Access.013.png) | ![](images/0.%20Special%20Access.014.png) | ![](images/0.%20Special%20Access.015.png) |
|:---:|:---:|:---:|
| *Accessed through the Circle:* | *Accessed through the Circle and the Triangle:* | *Also accessed through the Circle and the Triangle:* |
| __*Circle . Command*__ | __*Circle . Triangle . Command*__ | __*Circle . Triangle . Command*__ |

In text code you can see the difference all the more. I’ve put the text code under the diagrams above.

So its like the borders of triangles can be ignored in inward access. You might not access the triangle in order to access its members.

< This concept could have a place in Genericity. >

## Modules, Interfaces and Nested Commands

So usually only parents can access their descendant’s things.

Modules, interface implementations and nested commands make exceptions on those rules.

The public descendants of a module are accessible from anywhere within the module, the borders of triangles can be ignored and a nested command can directly access anything in its ancestor nested commands its command definition.

## Brainstorm

Nested command members can access the members of its ancestor command symbols. 

-----

Module and triangle are alike. They change the way you can access their members.

A parent block is sorta like a module in that way.

Child Access  
is the normal type of access