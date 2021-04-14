Encircle Language Construct Drafts | From Spec
==============================================

Basic Diagram Elements Construct Drafts
---------------------------------------

`[ Preliminary documentation ]`

__Contents__

- [Loose Ideas](#loose-ideas)
- [Brainstorms Shape vs Line Type](#brainstorms-shape-vs-line-type)
    - [Executions & Parameters Brainstorm](#executions--parameters-brainstorm)
    - [When Shape Types, When Line Types](#when-shape-types-when-line-types)

### Loose Ideas

- Notation Methods versus System Rules
    - Implicit calls are but notation methods, that don’t affect the behavior of the system. Type genericity, interface genericity and type interface genericity are system rules. They affect the behavior of the system.

-----

Basic Diagram Elements,  
Relations Between Symbols,  
2008-11-13

If you can see object usage, you can not see class-sub-object usage.

You might look at the usage of the sub-objects of the objects of that class, to see the class's sub-object usage. Indirectly you might be able to see the dependency on a class's sub-object.

Doesn't a sub-object have a reference to the class's sub-object or might the parent object only have a reference to the class?

\> 2020-06-13: I now think, that a sub-object of an object might not have a reference to the sub-object of a class. I guess the relationship is implied by form/shape/name/aspect correspondence. I get how that might be bothersome. Then there might be relationships in the diagram that are expressed with neither lines nor containment. Maybe it is something to not be bothered by. Maybe it is something to mention as another type of relationship between symbols. There might be a spot for it in Basic Diagram Elements for that, next to the other types of relationships between symbols that might be named there. Maybe 'it is just a notation' might be the way to think about it. There might not be a precise mathematical definition of why shapes are used and the choice of containment vs association is also left as an arbitrary design choice so why might this not be ok as something arbitrary about the notation? If it turns out to be bothersome, maybe a different kind of line to express a different kind of correspondence could be used. But that may be something not to make part of the initial release of Encircle language spec.

A curly line (like a spring) may be introduced. And optionality of them being displayed, since form/shape/name/position(?) may imply the connections already

JJ

-----

Basic Diagram Elements,  
Relations Between Symbols,  
2020-06-18

There might be more occurrences where connections are left out, since implied by the class:

![](images/Basic%20Diagram%20Elements.060.png)

Object's members a and be might be class-connected to Related Class 1 and Related Class 2. But a notational choice was made to leave those out, since they seem implied. Perhaps it might not even be wordt to point out. But perhaps at one point one could desire an exactness in notational choices like that, and awareness that there are these notational choices, might help. But it could also be regarded up to the reader's imagination what he or she might do with it or not. It might not seem essential for the general idea.

The phenomenon may be called 'implicitly connected through parent'. It may have once have been thought apart of the currently out-of-scope idea of Automatic Containment. But maybe it is not specific to Automatic Containment.

JJ

### Brainstorms Shape vs Line Type

This might be (possibly complicated) text for justification of a diamond symbol rather than a call line. It also seems sort of a mystery when something is symbolized with a shape, and when by a line drawn with a certain style.

If there is nothing to point to, while there is an aspect to express visually, that may exclude a line from being used and may 'require' a shape, but then why one time the same shape with a different line type versus a different shape? The choice 'different shape' vs. 'shape drawn with different line style' seems not easy to rationally pinpoint. Maybe it could be used as food for thought when 'abusing diagram expression' might be worked out some day perhaps. Then the idea was a systematic overview all methods of symbolizations used in Encircle vs possibility to express aspects of systematics using that symbolization.

#### Executions & Parameters Brainstorm

__This IS the text that lead me to wanting a diamond symbol instead of a call line.__

< Why not, actually? Ok, you can’t do it in other languages, but why can’t you do it here. Oh. When you reference a call, it makes the call line function as a reference line rather than a call line. If you want this to be different, a reference to call might become a call, which is not something you want to happen in your system. The reference target might get control over if the source might be a reference or if the source might execute. The source might have no say in that. Unacceptable. So, a candidate for an alternative rule for A Call Can’t be Called or Referenced is: if you reference a call, its call line is treated as a reference line.   
If you call the reference to a call… 

Een call line is eigenlijk een reference line, maar als de parent square execute, dan execute ook de call. Hmmm… het is bijna of het allemaal reference lines zijn en sommige squares executen nou eenmaal. O! Dat is ook zo! Clauses moeten ook kunnen executen en ik zeg nu dat iets alleen execute als het een call line heeft! Hmmm… o, een call is een tag, niet een line!

Een call een aparte line maken is net zoiets als een triangle een aparte line maken. Hetzelfde mankement. Dan lijkt het logisch, dat een call een apart symbool krijgt, niet een aparte line. O. Welk symbool?

#### When Shape Types, When Line Types

< So, there’s a call trace and a definition trace. >  
< Target call, target definition >  

<  
Misschien mag ik dan al wel verklappen dat de call zo’n beetje het object is en de definition de klasse.  
En waarom het dan aparte symbolen zijn en niet verschillende line types. Eigenlijk moet ik dan de keuze voor alle line types en symbolen aangeven.  
Je kunt maar 1 reference line hebben. Dat is zo’n beetje de reden. Hè, ik moet het inderdaad goed opschrijven 

Call is een hoedanigheid van het symbool, dat geen line behoeft.  
Type is niet een hoedanigheid van een symbool, het is waar een symbool voor kan dienen.  
Een triangle is gekozen voor interface implementation, omdat een interface implementation ook een hoedanigheid is van het symbool, dat geen line behoeft. 

Eigenlijk is het wel een beetje zo dat: alles wat ik aan mezelf heb moeten uitleggen, moet ik aan de lezer uitleggen.  
\>

A definition is a lot like a type of procedure, while an execution is an instance of the procedure. As I state this relation, it may seem strange to you that I picked *separate symbols* to denote a procedure symbol’s execution and definition, while for objects I use different *line types* to separate objects from types. Diamond is actually the extra symbol picked to represent an execution. An execution of a definition is like an object of a type. However, an execution has another special characteristic: it executes. 

When an object symbol has a type line it’s behavior in the container isn’t as much different as ...

However, object symbols aren’t different to their container if they ...

To find the definition you follow the reference line between ...

Just consider: if a diamond doesn’t have a line it is an executing clause, when a square doesn’t have a line, it’s a non executing clause. In both cases it’s a definition. But the two case differ in that in one case it executes and in the other it doesn’t. If an object symbol has no line, it’s an object. Simply stated, it needs an object line for it not to be a type. A procedure symbol shouldn’t need a line to be an execution.

When a characteristic’s presence shouldn’t be dependent of the presence of a line, it needs to be drawn out with a shape type. If a characteristic is dependent of the presence of a line, it’s the line presence that gives it the characteristic. If I’d want object symbols to serve only as a type and not as an object, then I’d need to reserve a special shape to separate types from objects. Now, to make an object symbol serve as a type only and not as a type, I make the Object Get Inaccessible? NO. That’s not true. Actually I’d might not be able to Symbol Get if it’s for the purpose of assigning an object line.

A square is never an object.

For a procedure symbol to function as a reference and not as an execution is not up to the possibility to have a symbol as an execution target.

Ok, if I wanted it so that an object symbol could only function as a type, but not as an object, I should reserve a separate shape for it. But that doesn’t mean that an object shape can’t serve as a type. An execution shape can serve as the definition too.

It’s important for some procedure symbols not to function as an execution. Otherwise the system might behave complete different. It’s not as important for an object symbol not to function as an object, only as a type. The system isn’t really harmed as severely by that. The same goes for triangles: if a triangle is suddenly a circle, the system behaves completely differently.

I’m still in doubt. I think it’s good that there’s a diamond symbol and that there aren’t separate object, type and interface shapes. I just can’t define *why* yet.

It totally makes sense to use separate type, interface and object shapes, but … it’s just not that important. Not as important as the function of diamonds, triangles and pentagons. 

Sure it is nice to see in a system that one set of object symbols serve as the types… So it might be an idea to make it possible to give them a different shape type… when you can’t use the symbol as an object target.

The total reason of the diamond and triangle symbols is that the effect of it has greater consequences for the behavior of the system. A diamond symbol makes rules easier to understand: it’s easier to get: “you can’t place a diamond in an object symbol”, than it is to remember “a procedure symbol in an object symbol can’t have a call line”

*“The reason why both call and reference lines need to be followed is because call and reference lines are actually both kind of like reference lines. However, a call line has the side effect that its square might execute if its parent square executes.”*

Dat is zo’n beetje waar het kwartje begon te vallen dat het een shape moest zijn en geen line type.

Een andere shape wordt in basis Symbol alleen gebruikt als het echt nodig is. Als het niet echt nodig was om andere shapes te gebruiken, dan maakte ik het *allemaal* cirkels.