Circular Language Broader View | Exchangeability | Flat & Structured Interchange Loose Ideas
============================================================================================

`[ Preliminary documentation ]`

__Contents__

- [Introduction](#introduction)
- [Automatic Containment](#automatic-containment)
- [Methods & Classes Loosely Coupled](#methods--classes-loosely-coupled)
- [Loose Ideas](#loose-ideas)

## Introduction

Flat & Structured Interchange consists of a set of principles, that turn something flat and unstructured into something structured automatically. It also can approach anything structured as something entirely flat.

Some aspects of the system you do not structure yourself anymore. The system gets structured automatically following fixed rules. 

## Automatic Containment

For instance: you can’t determine the containment structure of objects yourself. The containment structure is automatically derived from the referential structure of objects.

## Methods & Classes Loosely Coupled

...

## Loose Ideas

Ik denk dat uiteindelijk die flat & structured interchange verweefd wordt met alle andere onderwerpen, en een samenvatting daarvan als fundamental principle wordt gegeven, want flat & structured interchange topics hebben een te brede invloed op allerlei concepten.

-----

Flat & Structured Interchange,  
2008-09-22

(use this in the fundamental principle topic Flat & Structured Interchange)

It is actually the flat part that is physically stored. The structured part is simply derived from it. The structured part is imaginary and volatile. The flat part is fixed and real.

JJ

-----

- Automatic Containment
- Commands & Classes Loosely Coupled
- Automatic Execution Order
- Automatic Determination Parameter In / Out / Thru
- Attributes As Tree Layers
- Automatic Object Formation

-----

Because of the exchangeability of global members and class members, a global function can boldly add a member to a class if one of its parameters is of this class and assigned to be the class to be extended.

-----

Ik had het vanmiddag met iemand over het probleem dat bijvoorbeeld neurale netwerken niet controleerbaar zijn, omdat alles een platte structuur van schakelingen is, waar geen groepering in kan worden gezien door een mens. En ik had het erover dat de controle misschien wel groter was als er een systeem was dat dit om kan zetten in groepering. Met Creator's manier om referentieel naar encapsulatief om te zetten, zou hier wel uitkomsten voor kunnen bieden. Echter, herhalende patronen moeten ook in klassen worden omgezet.

-----

Creator:  
Ook de commando structuur kan van referentiele structuur naar encapsulatief worden omgezet. Je kunt dan ook bepaalde lagen onderscheiden in de commando's binnen 1 class.

-----

Complete interchangeability between flat and structured.

Next to auto-encapsulation, you could also make automatic hierarchical subdivision by class attributes a common thing. That way unstructured and structured become more interchangeable.

The table approach is actually the unstructured approach, but it interchanges with...

Here I am searching for methods that make completely unstructured completely translate to completely structured without human intervention.

Because that could be the tool to make Symbol and Creator a single language. The same counts for how the symbols are positioned on screen by Symbol, and how text code is displayed in a structured manner.

Cool, but a long way to go.

-----

2008-03-28

A new twist to Flat & Structured Interchange is that objects on a deep level are no longer subdivided into classes. Each object is an individual, with an arbitrary number of attributes, related items and related lists. The classes of the related items and related lists don’t even need to be fixed, they are just items or lists that hold references to any other arbitrary object. This creates even more extra flatness compared to a system where a class results in its own set of files.  
I won’t brainstorm too much here, but funny enough, an object then holds an list with an arbitrary amount of attributes, a list with an arbitrary amount of related items, and a list with an arbitrary amount of lists. *Everything* has become a little list which can individually scale. This has implications for how I’m going to realize something disk based. I won’t have a file for each attribute of a class anymore.  
I need to look for a different way in which to store things on disk. Either I pack many small lists into a single space somehow, or I just insist to create a new space for each little list, but this could become costly, depending on the block size.