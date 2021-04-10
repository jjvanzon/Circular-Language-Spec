Encircle Language Construct Drafts | Text Code
==============================================

Identifiers
-----------

`[ Deprecated documentation ]`

Identifiers are names for objects, collections, attributes, sites, programs, modules or any other element of a system. Any element of a system can get an identifier.

In other computers languages there are limitations to identifiers. For instance: identifiers can’t contain spaces. This is so, because spaces are used as a separator, to separate elements of a textual expression in computer code. Identifiers without spaces make it easier for the text code parser.

In Encircle identifiers *can* contain spaces. To make it easy for the text code parser, there are *two kinds* of spaces: large spaces and small spaces. Small spaces are the ones you can use in identifiers. Large spaces are spaces, that separate elements in a text code expression.

In Encircle, text code elements are *always* separated by large spaces. You can’t, for instance, put a plus-sign right next to an identifier.

```vb
Value1+Value2
```

You have to put spaces around the plus-sign now.

```vb
Value1  +  Value2
```

It looks much better too. But things can look even more natural: you can use spaces in identifiers now.

```vb
Value 1  +  Value 2
```

You’re going to have to put spaces around anything: even around parenthesis characters.

```vb
(  Value 1  +  Value 2  )  \*  Value 3
```

It also just looks more readable this way, but there’s another benefit. Because text code elements are *always* separated by a large spaces, and *any* text between two large spaces is a single element, you can use *any* character in an identifier. That’s right: identifiers can be composed of *any* string of characters.

Identifiers now look like regular human language text. There is no distinction anymore between an identifier in text code and a name shown inside a computer program: a system element’s identifier is a name you will see in the program.

This does imply, that identifiers will need another capability in the future: they need to be able to work in a multi-lingual way. Each language can get its own translation of an identifier, and the identifiers in text code depend on the language you picked.

You might think, this will make it awfully hard on the text code parser, but unlike in other programming languages, text code isn’t leading anymore. The system is not stored as text code. The system is stored in binary as connections between system elements. When you see text code, it is derived from the binary storage of connections between system elements. When you edit the text code, what you type in is merely *applied* to the binary storage of connections between system elements. Text code is merely a temporary view on the system, only built up when you need to see it, and thrown away again, when you don’t need to see it anymore.

When you type in an identifier to identify an element of the system, it needs to be recognized. Other programming languages recognize names either *case-sensitive* or *case-insensitive*. In Encircle the recognition of identifiers is *half*-case-sensitive: the recognition doesn’t pay attention to upper case or lower case letters, unless it has to. Only when two identifiers with the same name are within scope with different case usage, a case *sensitive* match needs to be made. This gives you the best of both worlds. It leaves out the problems that come with case-sensitive name matching, and reintroduces it only when required.

The first versions of Encircle will store a large space as two spaces next to each other. This does, however, imposes the restriction on identifiers, that you can’t use several spaces right next to each other.

### Loose Ideas

Statement:
- The ‘As’ or ‘In’ notation for relation names is applied when it isn’t the only relation between the two classes
- \> Find out if that’s true, and if you can find rules about when to use in and when to use As. Perhaps when it has a containment character?

#### Out of the original Symbol documentation

An identifier is a name for a symbol (for instance for a circle). It can be any string of characters. Unlike a lot of other programming languages, identifiers in Symbol can contain spaces and they can begin with numbers. Examples:

```
Id
Id1
1toNFilters
1 to N Filters
I’m an identifier
Object A
```

A type gets an identifier, but also the separate objects get their own identifiers.

The same name can be used for different symbols. Which of the *Johns* you’re talking about depends on its context (where it resides). Siblings usually don’t have the same name, because they reside in the same context. Only in a very special case siblings can have the same name.