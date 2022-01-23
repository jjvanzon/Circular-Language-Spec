﻿Construct Drafts | Expression | Alternative Diagram Expression
==============================================================

`[ Preliminary documentation ]`

(From the original Symbol documentation)

- Alternative diagram expressions:
    - Overlapping encapsulation
    - Using encapsulation to express the other hierarchies

## Diagram Aspects

There are the following aspects to the diagram:

- Encapsulation
- Lines
- Color
- Shape
- Names

## Standard Notation

What I have described in the previous sections is the standard notation for Symbol diagrams. 

- Encapsulation is used to express the encapsulation structure.
- Lines are used to express the delegation structure.
- Color is used to express the type/object structure.
- Shapes are used to distinguish between inheritance, encapsulation and execution.
- Names are used to indicate what something is called, what something refers to and of which type it is.

As I said: this is the standard way that the diagram elements are used to express a system. To keep things clear I only introduced you to the standard notation or it might have been futile to explain the notation at all. 

## Customization

Diagram aspects:

- Encapsulation
- Lines
- Color
- Shape
- Names

Diagram aspects can be arbitrarily exchanged between system aspects. The following is not entirely true, but it draws out the idea: any diagram aspect could represent any system aspect.

## Hierarchical Diagram Aspects

Diagram aspects:

- Encapsulation
- Lines
- Color

The encapsulation, delegation and type/object hierarchies are all tree-like structures. The diagram’s encapsulation, lines and color can each present a single tree structure. Any of these three diagram aspects can be related to any of the three hierarchies. 

Two diagram aspects can be turned off: lines and color. You can stop color from representing a hierarchy and you can stop lines from expressing a hierarchy. You might want to set up two simultaneous views in which you assign different diagram aspects to different hierarchies so for instance you don’t use color to express a diagram aspect, yet in the first diagram you use diagram encapsulation and lines to express two of the hierarchies and in the next diagram you use diagram encapsulation to express the hierarchy missing in the first diagram.

The encapsulation, lines and color aspects of the diagram can be distributed over the encapsulation, delegation and type/object structures, each hierarchical system aspect being represented by one hierarchical diagram aspect.

-----

Red, green and blue could actually express three hierarchies...  
Or tint, blackness en whiteness.

## Criterial Diagram Aspects

Diagram aspects:

- Color
- Shape

There is a set of attributes for each symbol in the system:

- Name
- Parent
- Reference
- Type
- Reference Access
- Type Access
- Inherited
- Executable
- Ordinal
- Selected

These attributes are mostly critical to system design so it is important to express them in a way in the diagram.  
< Calculated symbol attribute mapped onto an expressed symbol: > You can also match symbols to an arbitrarily formulated criterium, which could be regarded a complex or composed attribute. These criteria could be a value of a single attribute, a combination of attributes, a range of values of a single attribute or combination of attributes or could be related to hierarchy depth.

-----

__Thought__:

I could have :

- shapes and colors
- values of attributes
- ranges of attributes
- an arbitrary number of values and ranges assigned to any shape or color.

-----

*Waar dit criterium:*

```vb
Int(EncapsulationDepth / 2) = ChildDepth / 2
```

*Een (complexe) toepassing van kleur:*

```vb
R = 0.3 \* (1 - (EncapsulationDepth / DeepestEncapsulationDepth)) 
G = 0.6 \*      (EncapsulationDepth / DeepestEncapsulationDepth)
B = 0.9 \* (1 - (EncapsulationDepth / DeepestEncapsulationDepth)) 
```

*Een (complexe) toepassing van vorm:*

```vb
N = 3 + 7 \* (1 - (EncapsulationDepth / DeepestEncapsulationDepth))
```

En bij overlappende eigenschappen kleuren mixen of optellen en dubbele vormen...

Stel dat ik zelfde klassen dezelfde vorm wil toewijzen

Kan ik niet ook namen gebruiken als criterium diagram eigenschappen?

Er is een grotere complexiteit dan ik in eerste instantie dacht.  
Wat is de echte rij met kleur, naam en vorm toepassings-mogenlijkeden zonder efficiëntie van de oplossing in acht te nemen?

-----

You should be able to highlight symbols with certain simple or complex attributes. Color and shapes can take upon themselves this roll in clarification. You can assign different n-gonic shapes or colors to symbols matching certain criteria. You can easily express a wide range of criteria simultaneously with different colors and shapes

< You can also apply invisibility according to criteria. >

(the following paragraph is unclear language)  
Another thing about criterial diagram aspects is that you can assign a highlight method to be invoked *under certain circumstances only*, which means for instance that you only show members that are Protected for Reference when the symbol is Inherited and, more related to the Symbol Environment then the Symbol language, the symbol’s parent is the current symbol. That means just about the same as you can only visually see the protected members of an descendant when editing the ancestor. < That’s simply an extra criterium added to the complex criterium >

-----

I might want to switch the square and pentagon symbols.  
A square might then become a module. A pentagon might become an execution point and then execution might look like neurons between which electrons are shot...