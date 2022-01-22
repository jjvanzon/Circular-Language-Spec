﻿Circular Language Construct Drafts | Text Code
==============================================

`[ Deprecated documentation ]`

Literals Loose Ideas
--------------------

One thing that makes a simple data type different from an object is that a simple data type can be expressed by a literal. The literal expresses the state of the simple data type variable. You can express the state on screen as a literal, or you can assign a literal to the variable, which alters the variable’s state. 

I’ve created the same capability for objects.

A literal is no more than a textual representation of the state of a variable. If you say a variable holds the value 145, the variable isn’t really holding 145. The variable is holding a series of bits. ‘145’ is just a textual expression of those bits. __String__ literals aren’t even the exact text, that the __String__ contains either. The text:

```
I " love " to " use " double " quotes
```

Has a literal that looks like this:

```
"I "" love "" to "" use "" double "" quotes"
```

So this proves that a literal is a *textual representation* of the state of the object, not the actual state of the object. When you assign a literal, then the text is parsed and the state of the object is changed for instance by deriving a binary coding out of the text.

To give objects the ability to be expressed in a literal just like a simple data type, one attribute of the object is reserved as the __Literal Attribute__. This attribute is always of type __String__. A literal expression can be assigned to the attribute and the attribute returns the literal when it’s retrieved. To actually make the literal assignment change the state of the object or make the literal retrieval return a __String__ that represents the state of the object, you might write your own custom code.

So what’s the value for J Data of making one attribute the literal attribute, while you might specify your own custom code for it anyway? Well, J Data might use the literal attribute in the user interface. An object can be changed by assigning a literal value instead of changing individual properties of the object or calling methods. The object can also be textually expressed instead of by a list of separate properties. That way, the object looks just like an attribute, and can be shown as a column in a __List Control__.

You are not obliged to make the literal assignable. You can also just make it return a summary of the state of the object and not be able to assign the literal. This can be very handy to quickly view a summary of the state of the object.

## Loose Ideas

J Code

Literal recognition.  
If you type text you may refer to things that can be considered objects. You might want to link to them, but it's too much work to turn them into hyperlinks. You can do a Microsoft smart-tag like approach, but them recognizing literals of any object, and link to them automatically.

JJ

-----

J Code

'Smarttaging' in document:  
contextgebonden maken, net zoals classes.  
Markeer een deel van het document als een aparte context (apart object / class ) Je kunt een object betrekken in de context (analyserapport). Dat wordt dan een literal, die herkend wordt binnen de context.

JJ

-----

Literals, Values,  
2008-09-05

If an object only holds a simple value or maybe is a complex object, but also stores a value directly, and there is no literal notation for this value, I want to see in the diagram anyway, that it holds a simple value, so you easily see you are dealing with a simple object.

JJ

-----

Literals,  
2008-09-03

The handy thing about literals, is that they can easily be cut and pasted, and typed in in one blow.

The dowside is, that you might know the exact syntax, to be able to type it in. Interpreting a literal happens more intuitive, though, and
you do not necessarily need to know the exact syntax for that.

But next to literals you might need buttons and options and stuff, in order to be able to use all options without knowing any syntax through a graphical user interface.

Literals can be whole scripts as well.  
Literals also make exchange of objects through text easier.  
So you can send somebody some text and he can let a system interpret the literal and then have a copy of the object, or configure an object using a literal.

Commands in a command prompt are also literals.  
Literals seem more primitive than a graphical user interface, but next to downsides, they also still have upsides compared to more modern user interfaces.  
Upsides, like easy exchange through text (You can send that through e-mail. You might always keep writing e-mails, and e-mail might never be fully replaced by the exchange of actual digital objects. Exchange of text might not be entirely replaced by another language.) And when you do know the syntax, just typing can be a fast way to configure an object.
Also you can get an easy to read summary of something's state when you see a literal.

JJ

-----

Assembly symbols can be translated as usual, in case of which they look like ‘normal’ code, a better version of Assembly language to my opinion, but they can also translate to the Intel mnemonics like “MOV AX, 1”.

-----

There is a standard way of translating symbol diagrams to symbol text code.

- Identifiers
- Access operators
- Declarations
- Access controllers
- Parameters
- Arithmetic operators
-----
- Assembly

-----

```
If IsBetween(TheValue , A, B) Then
```

or

```
If TheValue IsBetween(A, B) Then
```

or

```
If TheValue IsBetween A And B Then
```

or

```
If the value is between A and B then
```

it's more or less like you're making a simple grammar to be able to notate a function call more dynamically.

-----

The text notations become extensible by being able to turn anything into a literal: attributes, objects, commands and concepts.