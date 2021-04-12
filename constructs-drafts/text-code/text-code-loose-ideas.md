Encircle Language Construct Drafts | Text Code
==============================================

Loose Ideas
===========

*The text below are old material from older documents. They contain a lot of brainstorming, but possibly also usable texts for future documentation.*

## Contents

- [Explanation](#explanation)
- [Loose Ideas](#loose-ideas-1)
    - [Text Parser](#text-parser)
    - [Text Code](#text-code)
        - [Identifiers](#identifiers)
        - [Declarations](#declarations)
            - [Type Declaration](#type-declaration)
            - [Declaration General](#declaration-general)
            - [Attribuut Declaratie](#attribuut-declaratie)
            - [Relatie Declaratie](#relatie-declaratie)
        - [Examples](#examples)
            - [Declarations](#declarations-1)
                - [Type Declaration](#type-declaration-1)
                - [Attribute Declaration](#attribute-declaration)
                - [Relation Declaration](#relation-declaration)
        - [Data Manipulation Syntax Brainstorm](#data-manipulation-syntax-brainstorm)
            - [Brainstorm 5 : Definitive brainstorm](#brainstorm-5--definitive-brainstorm)
                - [Too Much Theory For Now](#too-much-theory-for-now)
            - [Brainstorm 4 : Too general a solution](#brainstorm-4--too-general-a-solution)
            - [Brainstorm 2 : Some Example Code](#brainstorm-2--some-example-code)
            - [Brainstorm 1 : Example Code](#brainstorm-1--example-code)
        - [Kleurgebruik](#kleurgebruik)
        - [Voorlopig Beperkt](#voorlopig-beperkt)
        - [Parser](#parser)
        - [Opmerking](#opmerking)
        - [Ideeën](#ideeën)
        - [Relation Declaration Alternative Notations](#relation-declaration-alternative-notations)
    - [Korten en Lange Spaties](#korten-en-lange-spaties)
    - [Symbol: Attributes Become Classes sluit daarbij aan & Creator Text Code](#symbol-attributes-become-classes-sluit-daarbij-aan--creator-text-code)
- [Loose Ideas](#loose-ideas-2)
- [From the Original Symbol Documentation](#from-the-original-symbol-documentation)
    - [Language Integration](#language-integration)
        - [Brainstorm](#brainstorm)
        - [Operators](#operators)
            - [Parameters](#parameters)
        - [Literals](#literals)
            - [Standard Literal](#standard-literal)
        - [Structure](#structure)
        - [Identifiers](#identifiers-1)
        - [Declaration](#declaration)
        - [What Is...](#what-is)
            - [Access Operators](#access-operators)
        - [Text Code](#text-code-1)
            - [Objects](#objects)
                - [Lines Shown in Create Procedure](#lines-shown-in-create-procedure)
                - [Lines Shown at declaration](#lines-shown-at-declaration)
                - [No "="](#no-)
                - [No Circle](#no-circle)
                - [Variations](#variations)
            - [Procedures](#procedures)
                - [Parameter Text Notation](#parameter-text-notation)
                - [Parameter Notations](#parameter-notations)
            - [Access Control](#access-control)
                - [Textual Notation of Exclusion](#textual-notation-of-exclusion)
                - [Textual Notation of Friendship](#textual-notation-of-friendship)
    - [Other](#other)
        - [Member call](#member-call)
        - [Method declaration](#method-declaration)
        - [In, Out, Thru](#in-out-thru)
    - [Parsing](#parsing)

## Explanation

Eventually parts of this documentation section might be moved to the concept, the text code expresses, because diagram and text code expression of a concept is placed with the concept, because that makes the documentation easier to read and easier to write.  
But for now text expression topics are not worked out with the concepts yet.

## Loose Ideas

### Text Parser

De eerste text parser (heel basaal) moet je ook handmatig maken.  
Die text parser zou je overigens in een veel later stadium in Creator kunnen herprogrammeren, en als vervanging van de oorspronkelijke parser laten dienen.

### Text Code

#### Identifiers

In identifiers kunnen haakjes en spaties worden gezet.  
Dit is mogelijk omdat spaties in identifiers 'korte spaties' zijn,  
en alle tokens worden gescheiden door 'lange spaties'.

#### Declarations

##### Type Declaration

```
Type  <Naam>
```

##### Declaration General

```
<Type>  <Naam>
<Naam>  (  <Type>  )
```

Òf eerst type en dan de naam.  
Òf eerst de naam en dan het type tussen haakjes.

##### Attribuut Declaratie

```
<Type>  -->  <Declaratie>
```

Of meerdere in een keer:

```
<Type>  :
    -->  <Declaratie>
    -->  <Declaratie>
```

Of (bij de type declaratie):

```
Type  <Type>  :
    -->  <Declaratie>
    -->  <Declaratie>
```

##### Relatie Declaratie

```
<Declaratie>  [ 1 --> 1  1 --> n  n --> n ]  <Declaratie>
```

Of (namen van relatie counterparts apart gedefinieerd):

```
<Type>  [ 1 --> 1  1 --> n  n --> n ]  <Type>  :
    <Naam>  -->  <Naam>
```

#### Examples

##### Declarations

###### Type Declaration

```
Type  Point
Type  Line
```

###### Attribute Declaration

```
Point  -->  X  (  Double  )
Point  -->  Y  (  Double  )
```

Of:

```
Point  -->  Double  X
Point  -->  Double  Y
```

Of:

```
Point  :
    -->  X  (  Double  )
    -->  Y  (  Double  )
```

Of:

```
Type  Point  :
    -->  X  (  Double  )
    -->  Y  (  Double  )
```

###### Relation Declaration

```
Line  Lines ( as point A )  n --> 1  Point  Point A
Line  Lines ( as point B )  n --> 1  Point  Point B
```

Of:

```
Lines ( as point A )  (  Line  )  n --> 1  Point A  (  Point  )
Lines ( as point B )  (  Line  )  n --> 1  Point B  (  Point  )
```

Of:

```
Line  n --> 1  Point  :
    Lines ( as point B )  -->  Point B
```

#### Data Manipulation Syntax Brainstorm

Language Elements:

< See Program elements in plan. >

##### Brainstorm 5 : Definitive brainstorm

I might start improvising the parser code soon. I might no longer write out the theory behind it.

The following statements are detected by keyword:

- Assign =
- Add
- Remove
- Comment
- With
- End With
- For Each ... In ...
- Next

Actually, Assignment, Add and Remove reach my direct goal already. So it is a question whether I might go any further after that.

Add and Remove are currently the only possible method calls for now.

These are their keywords:

| Name                | Keyword             |
|---------------------|---------------------|
| Assign              | Keyword: *=*        |
| Add                 | Keyword: *Add*      |
| Remove              | Keyword: *Remove*   |
| Comment             | Keyword: __'__      |
| With                | Keyword: *With*     |
| End With            | Keyword: *End With* |
| For Each ... In ... | Keyword: *For Each* |
| Next                | Keyword: *Next*     |

I might program the interpretation of the statements one by one, and make the most essential one first.

The text is first split up in lines by enter, and then split up in tokens by large space. Then keywords are detected.

When a keyword is found, a line is further parsed.

After assignment detection, the statement is split by =. Then the two qualifiers on both ends are parsed. Then the parsed information is used to execute the assignment. But there a special situations. An R value can be Nothing, a creation, or a literal. first that is detected, then if it isn’t any of those, it is parsed as a qualifier.

After an Add or Remove call detection, the qualifier is parsed and the call is executed.

When comment is detected, nothing is done with the entire line.

After With detection, the part after With is parsed as a qualifier. A reference to the resultant object is remembered.

After End With is detected, the original With is relieved. In with blocks it is immediately required that I can remember a stack of With blocks.  
< Why can I not use a stack in Creator by default? >

After For Each has been detected, the statement is split by In. The part before In is parsed as a qualifier, except for the first two tokens, and the part after the In is parsed. Then it is remembered on class scope, not function scope, what loop is started and what element of the loop we are at. Embedded looping I might add later. In that case a stack of loops might be remembered.

After Next detection, Parsing is actually repeated (this isn’t a perfect solution I am making) until all elements were looped through.

Parsing a qualifier goes as follows. You first split the line by period ‘.’ ( Funny enough a line can be split by multiple main delimiters, or rather a detection of a statement can cause another splitting operation, that sort of overrides the splitting operation we already did. ) After splitting by period, you go by all elements from left to right. Except for the last element, they all might be an object. The last element can be an object or an attribute.  
The first object might somehow be globally accessible. In case of With blocks, the first object is missing, but in its place comes the object remembered by the With operation. The next element might be a member object of the previous object. There are hardly any methods yet, so I really don’t have to take those into consideration much, except for the Add and Remove methods, which have to be executed if they are found along the way. Add returns an object.

###### Too Much Theory For Now

There is an order of precedence of keyword detection:

- Comment 
    - Keyword: __'__
- For Each ... In ...
    - Keyword: *For Each*
- Next
    - Keyword: *Next*
- End With
    - Keyword: *End With*
- With
    - Keyword: *With*
- Assign
    - Keyword : *=*
- Add Call
    - Keyword: *Add*
- Remove Call
    - Keyword: *Remove*

Token build-up of the statements:

- Comment:
    - *'*
    - < Arbitrary tokens >
- For Each ... In ...
    - *For*
    - *Each*
    - < Identifier >
    - *In*
    - < Specifier >
        - Delegate to other function
        - Might resolve in a list
- Next
    - *Next*
- End With
    - *End*
    - *With*
- Assign
    - < Specifier >
        - Delegate to other function
        - Can’t resolve in a list
    - *=*
    - Optionality:
        - < Value Literal > (if Specifier 1 resolves in an attribute)
        - *New* < Class > (if Specifier 1 resolves in a related item)
        - *Nothing* (if Specifier 1 resolves in an object)
        - < Specifier >
            - Delegate to other function
            - Might be object if specifier 1 is object
            - Might be attribute if specifier 1 is attribute
            - Can’t be list
- Add Call
    - Keyword: *Add*
- Remove Call
    - Keyword: *Remove*

- Specifier
    - Take tokens starting from specifier

##### Brainstorm 4 : Too general a solution

I want to use a Creator structure to enter the parsed code in.  
This Creator structure should reflect the TEXTUAL structure of the code.  
It should be purely divergent, not referential.

I do have optionality and order (mixing statement types) to consider.

I don’t want the perfect parser for now. That’s not the point.

If I am to use a Creator structure to put the parsed code in, I have to figure out the precise the embeddance of the statements.

Also, I want to use a preliminary way to program methods in C++ for Creator objects, so I can already fully use the Creator philosophy.

- Multiline embedded constructions:
    - Loop
    - With
- Single Line constructions:
    - Assignment
    - Method Calls
    - Comment

They can embed qualifiers. Or what are they called? Specifiers?

Data manipulation code consists of an arbitrary line up of these constructions.  
Some constructions can contain a line up of constructions again, next to having a start and an end, with some qualifiers in it.

```
Constructions
|
|-- any one of: Loop, With, Assignment, Method Call, Comment
|
|-- Loop
|    |
|    |-- Begin
|    |    |
|    |    |-- "For Each"
|    |    |
|    |    |-- Identifier
|    |    |
|    |    |-- "In"
|    |    |
|    |    |-- List Specifier
|    |
|    |-- Constructions
|    |    |
|    |    |-- ...
|    |
|    |-- End
|        |
|        |-- "Next"
|
|-- With
|    |
|    |-- Begin
|    |    |
|    |    |-- "With"
|    |    |
|    |    |-- Specifier
|    |
|    |-- Constructions
|    |    |
|    |    |-- ...
|    |
|    |-- End
|        |
|        |-- "End With"
|
|-- Assignment
|    |
|    |-- Specifier
|    |
|    |-- "="
|    |
|    |-- Specifier
|
|-- Method Call
|    |
|    |-- Any one of: Add, Remove
|        |
|        |-- Method Specifier
|            |
|            |-- Qualifier
|            |
|            |-- "Add" or "Remove"
|  
|-- Comment
    |
    |-- " ' "
    |  
    |-- any text

Qualifier

Specifier
|
|-- Qualifier
|
|-- Identifier
|
|-- [  ]
```

I don’t want to create the perfect parser, but I do feel an urge to think about its concepts. Perhaps because I’m going too far with it and have to spend too much time designing it, I do have to use the procedural approach anyway.

Anyway, to just wrap up the general parser idea for now:

Concepts:

- Keywords
- Precedence
    - (Hierarchical precedence. No that’s more part of sequence, repetition and optionality.)
- Look-ahead
- Look-back
- Starts / Headers
- Ends / Footers
- Delimiters
- Optionality
- Sequence
- Repetition
- Arbitrariness
- Values

Keywords are used to detect a statement, because this makes the parsing very easy. But the original concepts I worked with, in the previous, failed, project of J Parser, still should apply: sequence, optionality and repetition.

Enough of that for now. This is going too far for the goal I have right now. This is what I’m supposed to have gotten better at.

I MIGHT reorganize the text in Brainstorm 3, or perhaps rewrite it. And implement the procedural parser.

##### Brainstorm 2 : Some Example Code

(pas later van toepassing)

```
Line  .  Point A  .  X
Point  .  Lines ( as point A )  .  Add  =  Line  [  12  ]
Point  .  Lines ( as point B )  [  2  ]
```

##### Brainstorm 1 : Example Code

```
Structure  .  Classes  (  "Class"  )  .  Related Classes  .  Add  (  Structure  . Classes  (  "...

'This would traverse the Related Classes if the  Relation Class  -->  Class  
'relation was dual and Relation Class has the derived attribute Other Relation 
'Class:

    For  Each  Class  .  As Relation Class  .  Other Relation Class
        ' ...
    Next

'Try to describe Creator in Creator Creator

    With  Structure  .  Classes
        'Structure
            With  .  Add
                .  Name  =  "Structure"
            End With
        'Class
            With  .  Add
                .  Name  =  "Class"
                With  .  Attributes
                    With  .  Add
                        .  Name  =  "Class Name"
                        .  Type  =  "String"
                    End With
                End With
            End  With
        'Class Attribute
            With  .  Add
                .  Name  =  "Class Attribute"
                With  .  Attributes
                    With  .  Add
                        .  Name  =  "Name"
                        .  Type  =  "String"
                    End With
                    With  .  Add
                        .  Name  =  "Type"
                        .  Type  =  "String"
                    End With
                End  With
            End  With
        .  Add  .  Name  =  "Relation"
        .  Add  .  Name  =  "Relation Class"
        .  Add  .  Name  =  "Item"
        .  Add  .  Name  =  "Item Attribute"
        .  Add  .  Name  =  "Related Item"
        .  Add  .  Name  =  "Related List"
    End  With

    With  Structure  .  Classes  .  Item  (  "Class"  )  .  Class Attributes  .  Add
        .  Name  =  "Class Name"
        .  Type  =  "String"
    End  With

    Structure  .  Classes  
```

#### Kleurgebruik

Voorbeelden:

```
Line (as point a)  (  Line  )  n --> 1  Point A  (  Point  )
Line (as point b)  (  Line  )  n --> 1  Point B  (  Point  )

Line  Line (as point a)  n --> 1  Point  Point A
Line  Line (as point b)  n --> 1  Point  Point B
```

Dus classes in het geel, relatie pijlen in het blauw, namen in neutrale kleur (bijv. grijs), en haakjes in donkergrijs.

#### Voorlopig Beperkt

Voorlopig beperk ik me tot de volgende notatievormen:

Type declaratie:

```
Type  <Naam>
```

Declaratie algemeen:

```
<Naam>  (  <Type>  )
```

Attribuut declaratie:

```
<Type>  -->  <Declaratie>
```

Relatie Declaratie

```
<Declaratie>  [ 1 --> 1  1 --> n  n --> n ]  <Declaratie>
```

Dus:

```
Type  Point

    Point  -->  X  (  Double  )
    Point  -->  Y  (  Double  )

Type  Line

Lines ( as point A )  (  Line  )  n --> 1  Point A  (  Point  )
Lines ( as point B )  (  Line  )  n --> 1  Point B  (  Point  )
```

#### Parser

Hieronder staat een voorbeeld van hoe de Parser zou kunnen werken. Inmiddels werkt de parser al ietsje anders.

Parser splitst eerst op in regels gescheiden door enter.  
Daarna in tokens, gescheiden door op lange spaties = drie spaties.

Alle lege regels en lege tokens worden genegeerd, zodat je lege regels en spaties vrij kunt gebruiken.

De tokens worden getrimd behandeld.

Uit keywords binnen een regel, met voorrang in acht genomen wordt gezien wat voor soort statement het is:

- Zit er "1 --> 1", "1 --> n", "n --> 1" in:
    - Het is een Relatie Declaratie
- Zo niet: zit er een "-->" in:
    - Het is een Attribuut Declaratie
- Zo niet: zit er het woord "Type" in:
    - Het is een class Declaratie
-----
- Een type declaratie is verder makkelijk te behandelen:
    - Het eerste gevulde token na "Type" is de type naam.
- Een attribuut declaratie is ook niet zo moeilijk:
    - Het eerst gevulde token is de type naam.
    - Het tweede gevulde token moet "-->" zijn.
    - Het derde gevulde token is de attribuut naam.
    - Het vierde gevulde token moet een "(" zijn.
    - Het vijfde gevulde token is het attribuut type.
    - Het zesde gevulde token moet een ")" zijn.
    - De rest van de tokens moet leeg zijn.
- Een relatie declaratie wordt op soortgelijke wijze ontrafeld:
    - Het 1e gevulde token is de  Relation Class A  .  Name
    - Het 2e gevulde token moet een "(" zijn.
    - Het 3e gevulde token is de  Relation Class A  .  Class
    - Het 4e gevulde token moet een ")" zijn.
    - Het 5e gevulde token kan een van de volgende zijn:
        - 1 --> 1 : Het is een 1 --> 1 relatie
        - 1 --> n : Het is een 1 --> n relatie
        - n --> 1 : Het is een n --> 1 relatie
    - Het 6e gevulde token is de  Relation Class B  .  Name
    - Het 7e gevulde token moet een "(" zijn.
    - Het 8e gevulde token is de  Relation Class B  .  Class
    - Het 9e gevulde token moet een ")" zijn.

Dingen moeten wel eerst gedeclareerd zijn voordat ze gebruikt kunnen worden.

De vertaling naar een Creator Structure is dan ook niet zo moeilijk meer.
- \> Nou, eigenlijk wel, want ik weet nu niet hoe ik het in Generic Generic Creator moet specificeren. Het lijkt erop dat ik toch gebruik moet maken van de h , g en gg objecten? Ik moet hier nog flink over nadenken.
- \> Uiteindelijk bleek dat ik nog een Creator laag moest hebben.

#### Opmerking

Ik gebruik de hele tijd `-->`. Maar het zijn dual relations en die drukte ik ooit uit met `<-->`. Is dat beter? Of vind ik die pijltjes eigenlijk wel mooi. Er IS meestal sprake van een forward en backward relation. Daar wordt ook gebruik van gemaakt. Dus de richting doet er wel toe. En het denkt makkelijker.

#### Ideeën

Mogelijk ooit zo’n notatie:

```
 Line  :                             Point  :
     Lines (as point b)   n --> 1        Point B
     Ensure Objects                      Ensure Objects
                                         Create Objects
```

een enkel pijltje in plaats van een pijltje heen en terug lijkt misschien wel mooi, maar als je een identifier specificeert voor de backwards relation, en die identifier ziet er echt submissive aan de forward relation uit, dan ziet het er raar uit dat het statement begint met zo iets als ‘As Relation Class’. Een dubbele pijl suggereert, dat er ook een weg terug is, maar daarmee kun je meteen niet goed meer zien wat de forward en backward relation is. Ja, aan de positie in de text code, maar daarnet wou ik nog suggereren dat de twee leden van de relatie gelijkwaardig waren, dus wat wil ik nu?  
Het ziet er in ieder geval een beetje onduidelijk uit als bijna elk relation statement begint met zo iets als:

```
As Item Attribute  (  Item Attribute  )
```

Tja, als je voortaan het type eerst noemt en dan de objectnaam, dan begint het wel met een normaal gegeven, maar dat zie ik later wel.

#### Relation Declaration Alternative Notations

*None of the notations below satisfies me, really. I already implemented the one that satisfies me most.*

Alternative notation 1:

```
Structure  (  Classes  )  1 --> n  Class  (  Structure  )
Structure  (  Relations  )  1 --> n  Relation  (  Structure  )

Class  (  Class Attributes  )  1 --> n  Class Attribute  (  Class  )

Relation  (  Relation Class A  )  1 --> 1  Relation Class  (  Relation ( as relation class a )  )
Relation  (  Relation Class B  )  1 --> 1  Relation Class  (  Relation ( as relation class b )  )

Item  (  Class  )  n --> 1  Class  (  As Item  )
```

Alternative notation 2:

```
Structure  .  Classes  1 --> n  Class  .  Structure
Structure  .  Relations  1 --> n  Relation  .  Structure

Class  .  Class Attributes  1 --> n  Class Attribute  .  Class

Relation  .  Relation Class A  1 --> 1  Relation Class  .  Relation ( as relation class a )
Relation  .  Relation Class B  1 --> 1  Relation Class  .  Relation ( as relation class b )

Item  .  Class  n --> 1  Class  .  As Item
```

You do see what's coming, but I still think it is confusing

### Korten en Lange Spaties

O. Om een lange en korte spatie te maken in een programmeertaal, om ook spaties in een identifier te kunnen gebruiken, kun je voor een lange spatie twee spaties gebruiken.  
Als je dan op gewoon spatie drukt, voeg je er gewoon meteen nog een spatie bij.  
Als je ctrl-spatie of shift-spatie drukt, krijg je gewoon een enkele spatie.  
Dan kun je gewoon bestaande text boxes gebruiken.

EVENTUEEL als je een spatie weghaalt met del of backspace, haal je ook weer twee spaties weg. Maar dat hoeft eigenlijk niet meteen nodig. De simpele dubbele spatie maakt gewone tekst editors ook meteen bruikbaar.

### Symbol: Attributes Become Classes sluit daarbij aan & Creator Text Code

Ook is in Symbol een integer een rondje, net als een object. Attributes Become Classes sluit daar ook weer goed bij aan.

De notatie is ook wel mooi, dan. Als ik in Creator Text Code zo ga schrijven:

```
Type  Point
Type  Line

Point  -->  X  (  Double  )
Point  -->  Y  (  Double  )

Line (as point a)  (  Line  )  n --> 1  Point A  (  Point  )
Line (as point b)  (  Line  )  n --> 1  Point B  (  Point  )
```

Je kunt ook zo iets doen:

```
Point  -->  X  (  Double  )
       -->  Y  (  Double  )
```

Of:

```
Point
    -->  X  (  Double  )
    -->  Y  (  Double  )
```

Je neigt nu bijna naar een manier grafische manier om de structuur met pijlen weer te geven.

Maar symbol zou toch de structuur weergeven?

Even andersom proberen:

```
Line  (  Line (as point a)  )  n --> 1  Point  (  Point A  )
Line  (  Line (as point b)  )  n --> 1  Point  (  Point B  )
```

Even kleurtjes proberen:

```
Line (as point a)  (  Line  )  n --> 1  Point A  (  Point  )
Line (as point b)  (  Line  )  n --> 1  Point B  (  Point  )

Line  (  Line (as point a)  )  n --> 1  Point  (  Point A  )
Line  (  Line (as point b)  )  n --> 1  Point  (  Point B  )
```

Die laatste is toch duidelijker, omdat je duidelijk ziet welke klassen een relatie krijgen met elkaar.

Nog even zonder haakjes

```
Line  Line (as point a)  n --> 1  Point  Point A
Line  Line (as point b)  n --> 1  Point  Point B
```

Tja, redelijk.

Nog even zonder kleurtjes:

```
Line  Line (as point a)  n --> 1  Point  Point A
Line  Line (as point b)  n --> 1  Point  Point B
```

Minder.

Nog even

```
Point  -->  Double  (  X  )
Point  -->  Double  (  Y  )
```

Ik kan niet zeggen of de naam van het type of de naam van het object nu het belangrijkste is.

```
Point  -->  Double  X
Point  -->  Double  Y
```

Sounds good enough to me.

But it is a unary relation there.

However, I have expressed only unary relations above.

## Loose Ideas

The comparative operators = and <> do not only apply to numbers, but to any kind of object

Voor een iets andere syntax voor Creator structure:
- Relatie declaratie kun je gerust zo laten. Hooguit ooit eens Relation ervoor zetten
- Attribute declaratie, daar kun je nu al het woord Attribute voor zetten.   
  Het idee achter alleen het pijltje was dat het eigenlijk ook een soort relatie was.  
  Maar het Attribute keyword zou in de toekomst een soort macro kunnen zijn,  
  die de relatie speciale betekenis kan geven.  
  Een attribute ten opzichte van een related item heeft namelijk een aantal extra kenmerken,  
  o.a. dat de referentie de enige referentie naar dat object is, dat de relatie niet duaal is,  
  dat het object kan worden uitgedrukt door een literal, etc.  
  Mogelijk kun je in de toekomst de 1 in een relatie type literal weglaten.  
  Ik zou ook bij een attribute de objectnaam tussen haakjes zetten, niet het type  
  Dan heb je de notatie helemaal gesynchroniseerd:  
  `Attribute  Point  ->  Double  (  X  )`  
  Betekent dan een 1 op 1 relatie tussen Point en Double,  
  het objectnaam van de Double is X.  
  Er is geen objectnaam voor de point doorgegeven.  
  Het Attribute 'macro' keyword zorgt ervoor dat het  
  een niet duale relatie is, de enigste die naar dat specifieke object refereert,  
  etcetera.

I have yet to consider if I might come up with a system of operators that can mean only one operation (but still on different types) or the same symbol being able to mean different operations, such as the = sign, which can mean equality comparison, value assignment and object assignment.  
If attributes might become classes, it may be so much more clear what operation does what when you use a unique symbol per operation.  
But multiple meanings for the same symbol works more intuitive. I think I should make it an option to display unique operators or an intuitive simple set of operators.

Symbolen  
Aan de ene kant hou ik niet van de ambiguïteit van symbolen. Aan de andere kant moet ik daar toch rekening mee houden in parsers, enzo, en qua overloading.

Maar toch zou ik graag unieke symbolen zien.  
Dan zal ik ze toch zelf moeten verzinnen,  
want de rest van de wereld hergebruikt bestaande symbolen keer op keer. Maar dan krijg je het probleem, dat mensen allerlei symbolen moeten leren. Of je maakt het variaties op bestaande symbolen, net zo iets de verschillende = tekens, die ik in Sy had verzonnen, maar dan algemene notatie of symbolen te disambigueren.

Automatisch formatteren tijdens code typen (hoofletters enzo), zelfs terwijl je een code regel aan het intypen bent, scheelt typwerk, terwijl de code wel netjes is

Allowing usage of spaces in identifiers, by separating between a large and small space, by making a large space be two spaces, and a small space just one, makes it impossible to use double spaces in identifiers.

-----

J Code

Ambiguity can be less of a pleasure.  
[ ] : list element / optional / value range  
<> : template placeholder / not equal to / XML tag

JJ

-----

tBookingMonth.AddMonths(1)

Returns a new Date , that is a month later.  
It does not alter the tBookingMonth date object.  
One could expect the latter too.  
How can you unambiguously resolve this interpretation?

-----

Text Code,  
2008-10-01

Perhaps for text code there might be several variations:

- Brackets / Words:
    - C-like with more brackets / Basic-like with more keywords
- Keywords:
    - New keywords / C-like keywords / Basic-like keywords
- Bracket type:
    - modern brackets / classic brackets

JJ

## From the Original Symbol Documentation

### Language Integration

The following can be translated to another language, for instance text code:

- Identifiers
- Structure: Encapsulation structure
- Declaration: Procedure declaration
- Operators: Procedure call
- Literals: The state of an object

Symbol text code is established by a set of standard translations for the elements above, and a few special translations for for instance execution control procedures.

#### Brainstorm

- Normal Procedure Call Notation = Standard Operator Notation:
    - There are two ways to express parameters in text code: in a definition or in a procedure call. The declaration of a procedure can be expressed as freely as an operator or literal notation. The general form of a textual procedure call notation is nothing more than a standard operator notation for a procedure.
- Mention that access operators are operator notations of the system procedures.
- Explain what execution control text notation is (is it an operator notation?)

#### Operators

<  
Operators *are* procedures. They are assigned a special notation.  
Evaluation order, parenthesis, Precedence  
Conversion operators  
\>

An example of operators are arithmetic operators:

```
+  –  /
```

An operator is notated like a method. It resembles an operation. The difference in notation is not in the diagram code. An operator’s speciality is that it supports an alternate notation, usually textual, but not necessarily.

\+ and – operations can be represented in plain text. Powers in Basic were represented by the ^ character. I wish to change that. I want the real mathematical notation to integrate with the language. For that I define operators as procedures that have any alternate notation. The power is represented by the exponent being notated in superscript: higher and smaller than the: b<sup>e</sup>

##### Parameters

The textual notations of parameters.

Possibly notating parameters on calls differently in the diagram than usual object assignments.

Parameter notations and operators are subjects totally for the Text Code chapter.

Operators then too. 

#### Literals

Some types have special notation formats, such as Integer Number, Floating Point Number or Text:

```
415
1.32352e-1
“Hello, I am a text literal”
```

The notation as such describes the state of an object and it’s called a literal. The examples above are textual literals. To assign a literal to an Integer object, the literal is put into a Text object and the conversion procedure for Text to Integer is called. So literals are interpreted by using a conversion procedure with Text as the source type.

A literal can be a Text, but any other type might do, for instance a Picture. If a Picture serves as a literal, then to interpret the literal, the conversion procedure with. < A literal is always of a type of a type. >

There can also be a reverse for a literal interpreter. The Integer to Text conversion produces the textual integer literal.

##### Standard Literal

There’s a standard way to interpret and procedure textual literals of objects. If there is no custom conversion to text and back, you can only control the state of an object by calling its members. Say an object has the following members:

```
Integer 1
Integer 2
Reset

Object . State = { 
```

Their state can only be controlled using

Of its data members

Maybe you should be able to define orders in which 

<  
This concept is much like the operator concept, which can convert *procedures* with arguments to a textual notation and back. 

This conversions isn’t usually?) incorporated into the system procedures of procedure to textually notate, though. There is standard way to produce a textual notation from a procedure call.

The concepts ‘literals’ and ‘operators’ are very very alike, and a single word could be used that encapsulates both...  
Standard textual literals and standard textual procedure notation.  
\>

#### Structure

#### Identifiers

There can be graphical identifiers.

#### Declaration

#### What Is...

There is text code notation that I’ve introduced for which language integration techniques are used.
- Calls and parameter assignment
- Procedure declaration
- (Standard literals)
- Access operators
- Execution control statements

##### Access Operators

De access operators in text code.

In text code you sort of see the calls to system procedures and you also sort of don’t. Each system procedure has its own access operator.

|                 |           |
|----------------:|:----------|
|      State Get: | x         |
|      State Set: | =         |
|                 |           |
|  Object Access: | . Member  |
|    Object Copy: | .         |
|     Object Set: | . =       |
|         Create: | = New     |
|                 |           |
|    Type Access: | :: Member |
|      Type Copy: | ::        |
|       Type Set: | :: =      |
|                 |           |
| Interface Copy: | :         |
|  Interface Set: | : =       |

< Maybe I’ll do special operator symbols in text code that represent the object relations. Actually, that’s what I’d like a little. Except member access. I wanna keep that. >

- Access Operators
    - One for each system procedure and ones that can do for multiple system procedures, depending on the context
    - ... :: . , (), []
- Special operators. Are they operators? If they are then they should be able to be overloaded. Maybe that’s handy too.
- System procedure arguments
- Genitivity

#### Text Code

##### Objects

Here follows an example code, expressed in a diagram, that might be used as an example for the expressions in text code that follow.

![](images/0.0.%20Text%20Code%20Introduction.001.png)

Lines are set in the create procedure.

###### Lines Shown in Create Procedure

```
Circle System

    Circle Object A
    Circle Type A
    Circle Interface A

    Circle Type B
        Triangle
    End Circle

    System Procedures

        Square Create
            Object A . Type = Type B
            Type B . Triangle . Interface = Interface A
            Type A . Interface = Interface A
            Object A . Create
        End Square

    End System Procedures

End Circle
```

###### Lines Shown at declaration

```
Circle System

    Circle Object A : Type = Type B, Create
    Circle Type A : Interface = Interface A
    Circle Interface A

    Circle Type B
        Triangle : Interface = Interface A
    End Circle

End Circle
```

The calls added to the declaration are executed in the Create procedure, though.

###### No "="

```
Circle System

    Circle Object A : Type B, Create
    Circle Type A : Interface A
    Circle Interface A

    Circle Type B
        Triangle : Interface A
    End Circle

End Circle
```

###### No Circle

Circle is rather general, so maybe I ought to be able to leave it out:

```
System

    Object A : Type Type B, Create
    Type A : Interface Interface A
    Interface A

    Type B
        Triangle : Interface A
    End B

End Circle
```

Slechte voorbeeld namen, dan lijkt het erop dat Type, Object en Interface keywords zijn. Dat zijn het ook, maar niet in de identifiers die ik heb gekozen.

###### Variations

Circle System <=> Object System <=> Circular Object System  
Triangle B <=> Triangular Object B  
Square A <=> Procedure A  
End Circle <=> End Object  
End Triangle <=> End Object  
End Square <=> End Procedure  

##### Procedures

- Procedure Structure
- Parameter notations
    - Optional
    - Variable
    - Parameter order

###### Parameter Text Notation

There are several ways to notate parameters in text code. First of all, the definition of the procedure in text code might contain a parameter list:

```
Procedure Do Something ( Parameter 1 : Type A, Parameter 2 : Type B, Interface A )
```

Several notations for parameter assignments.  
What do I mean several?

Textual:
- Enumerated argument list
- Named arguments
- Reading and writing arguments like the procedure is an object
- In, Out denotation

Ik wil dit er toch tussendoor doen. En na de andere hoofdstukken moet ik het er ook weer even over hebben.

< >  
...  
- Procedure structure
- Standard call notation
- Standard procedure declaration

###### Parameter Notations

In text code a parameter

In text code there are several notations for parameter definitions and assignments call. The most common one is in a comma separated list.

< I need to explain the difference between the term parameter and argument somewhere before this section >

##### Access Control

###### Textual Notation of Exclusion

```
Object A
    Exclude B . P1, B . C . P2
    Include B . P2
End Object
```

Or: 

```
Object A
    Exclude:
        B . P1
        B . C . P2
    End Exclude
    Include:
        B . P2
    End Publish
End Object
```

Or: 

```
Object A
    Exclude B:
        P1
        C . P2
    End Exclude
    Include:
        B . P2
    End Publish
End Object
```

###### Textual Notation of Friendship

```
Object A
    Friends
        ...
    End Friends
    Exclude B:
        P1
        C . P2
    End Exclude
    Include:
        B . P2
    End Publish
End Object
```

< Execution Control? >

### Other

#### Member call

```
Return Value 1, Return Value 2 = Object . Object’s Method ( Method Argument 1, Method Argument 2 )

Return Value = Object . Object’s Method ( Method Argument 1, Method Argument 2 )
```

#### Method declaration

Method Object . Method (Word: Argument 1, Double Word: Argument 2 ) Real 32: Return Value

#### In, Out, Thru

Since I’m working with multiple arguments as well as multiple return values, I may as well use a separate argument type that is both an argument as well as a return value (not to be mistaken for a reference argument).

Arguments are then In parameters. Return values are Out parameters. The last type described would be InOut parameters, more nicely called Thru (Through) parameters.

You could also say Read, Write and Read/Write, but this creates ambiguity about who’se reading or writing: the caller or the procedure.

In, Out and Through. Now we need a notation for them

This was the notation with arguments and return values:

```
(In, In, In) Out Out Out
```

Now we need a through.

Options:

```
In: Argument1, Argument2, Thru: Argument3, Argument4, Out: Argument3, Argument4
```

I’ll stick to that for now..

Thru arguments are not to be confused by reference arguments. The values of Thru arguments are actually put on the stack and read from the stack and written to the stack by the procedure. Reference arguments are usually In parameters and not written. The reference argument is a mere number that points to an object. The object a reference argument points at can be written and read, but this object doesn’t reside on the stack. Reference arguments in other languages were often used as a trick to use multiple return values or to have arguments that are both given to the procedure and then returned to the caller possibly altered: thru arguments.

Reference arguments are still of use, but since J Core supports multiple return values (Out arguments) and thru arguments, they

Reference arguments are actually pointer arguments. 

References in Visual Basis and the Object Variables are pointers.

References in C++ are a mere altered notation of pointers, with a few restrictions (even) put on them.

Address (__In:__ First Fragment, Fragments, Position, __Thru:__ Current Physical Fragment, Current Logical Fragment, __Out:__ Address)

When only using in and out arguments I could optionally use the ‘normal’ notation:

```
Function (In1, In2) Out1, Out2
```

-----

2004,

In the C documentation a distinction is made between Lexical Grammar and Phrase Structure Grammar. 

- Lexical grammar:
    - Tokens, keywords, identifiers, constants, string literals, operators, punctuation
- Phrase structure grammar:
    - Expressions, declarations, statements, external definitions

JJ

-----

Text Code,
2008-10-16

Inversed path should be a text expression concept.

JJ

-----

JCode, Expression, Text Code,

Zo heb je een access operator, voor het overgaan naar een ander systeem:

`\\MyServer\MySourceControlSystem\\MyFolder\MySubFolder`

(`\` = access object)  
(`\\` = access system)

JJ 

-----

Encircle,

Text code is not leading anymore.

JJ

### Parsing

Onderdeelomschrijvingen opsplitsen in criteria

First you split up the string into sequences of characters of the same category. A character can belong to multiple categories.

Then you use this information to compare it to a specification containing a sequence of wildcards:

- Exact string
- Or wildcard:
    - Category: specific or not specific
    - Length: specific (?) or not length specific (`*`), between lengths (`? ???` or `?? *`)
- Not'ness
- Or'ness

Then a set of findings can be built up.

The findings can be extended with a replacement to correct the format of things.

Let's take this nomenclature:

```
!

=...
=*...

?
*
@
*@
#
*#
a
*a
.
*.
_

ch.12352->
->Ch.1423452

=*-
=>
c
h
*_
.
*_
*n

=*-    =>    c    h    *_    .    *_    *#

->Ch . 13242
-->cH.1

~=
~c~
~h~
~* ~
~.~
~* ~
~*n~
~=*-~
~=>~
```

Splitting starts with categorizing characters.

Categories could be:

- numeric
- alphabetic
- punctuation

Uppercase and accents are approached with characters categories. A a ? â á à Á à Â å a A Å ? can be seen as the same category so they might all be interpreted as 'a'.

-----

In Symbol, when you use public objects, direction is ambiguous. Also, an object in ActiveX is actually a property. Why is it a circle in my case then? Why isn't a property an object then? oh. No. Getting an object is actually a procedure, but you use it as if it's just an object. When you can set it, then that's a definite procedure. Darn. I have to revise Symbol. It's not that good this way.

-----

For string manipulations:

When you want to do two manipulations that require you to go through all characters you could use a single traverse function which you give an array of references to functions so that you only loop once, yet apply two string transformations. For instance, making the letter case of names proper and removing every third space.

More details are involved, but that's the general idea

-----

Perhaps there's an optimization to be derived from that: merging loops
