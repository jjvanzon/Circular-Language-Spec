Circular Language | Construct Drafts
====================================

Peels
-----

`[ Deprecated documentation ]`

__Contents__

- [Introduction](#introduction)
- [Shape Peels](#shape-peels)
    - [Extra Borders](#extra-borders)
    - [Exits and Entrance Separation](#exits-and-entrance-separation)
    - [Line Type](#line-type)
    - [Type of Crossed Border: Studs](#type-of-crossed-border-studs)
    - [Name of Symbol Crossed](#name-of-symbol-crossed)
    - [Exceptionals](#exceptionals)
        - [Single Solid Border](#single-solid-border)
        - [No Crossings](#no-crossings)
    - [Peels for Other Symbols.](#peels-for-other-symbols)
    - [Abstract Meaning](#abstract-meaning)
        - [Symbol Has A Line](#symbol-has-a-line)
        - [Symbol’s Line Crosses Many Borders](#symbols-line-crosses-many-borders)
        - [Other Abstract Meanings](#other-abstract-meanings)
    - [Expressible in the Symbol Border](#expressible-in-the-symbol-border)
    - [Only Use Peel Notation Where It’s Useful](#only-use-peel-notation-where-its-useful)
- [Line Peels](#line-peels)
- [Ambiguity In Peels](#ambiguity-in-peels)
- [Overview of Peals](#overview-of-peals)
- [Loose Ideas](#loose-ideas)
    - [Create Argument and Call Argument’s Members](#create-argument-and-call-arguments-members)

### Introduction

An additional notation technique exists to express information about lines. It’s called the peel notation.

![](images/98.%20Peels%20(a%20rejected%20concept).001.png)

This symbol has three peels, which express information about a symbol’s lines. 

The notation is invented for the following purposes:

- More overview in complex situations,  
  because it allows you to hide (a many) lines, while you can still read information about the lines.
- To give more information about a line if part of the diagram is out of view
- To provide an easier notation for common situations  
  in which for instance a large group of symbols has the same sort of lines and line destinations.
- To express similarity in line targets

### Shape Peels

Sometimes a line is not drawn or the destination of a line is out of view. There can be several reasons why you don’t want to draw a line. The lines in the view might distract you from the main point or you might not care much about the line in the view. It can also be the case that the destination of a line is out of view. Anyway, if you can’t see all or part of a line you might still want to show some information about the line.

Alternative borders for shapes can tell something about the lines of the symbol.

#### Extra Borders

The basic method used is to add extra borders to a shape:

![](images/98.%20Peels%20(a%20rejected%20concept).002.png)

![](images/98.%20Peels%20(a%20rejected%20concept).003.png)

Each *peel* of the symbol represents a border that a lines *crosses*.

The double circle (circle drawn with a double line) suggests that the circle has a line that crosses two borders. For instance:

![](images/98.%20Peels%20(a%20rejected%20concept).004.png)

The triple circle suggests that three borders are crossed, for instance:

![](images/98.%20Peels%20(a%20rejected%20concept).005.png)

or:

![](images/98.%20Peels%20(a%20rejected%20concept).006.png)

or:

![](images/98.%20Peels%20(a%20rejected%20concept).007.png)

So multiple peels of a symbol’s border don’t say all about the ‘travelings’ of a line. They only say how many borders are crossed.

One *peel* represents one border crossed by a line. It can be any kind of border crossing, so a triple circle may mean:

| ![](images/98.%20Peels%20(a%20rejected%20concept).008.png) | = | ![](images/98.%20Peels%20(a%20rejected%20concept).006.png) |
|-----|-----|-----|

just as well as:

| ![](images/98.%20Peels%20(a%20rejected%20concept).008.png) | = | ![](images/98.%20Peels%20(a%20rejected%20concept).007.png) |
|-----|-----|-----|

You can do more with a symbol’s border, so that you can express more about its lines than just how many borders are crossed.

#### Exits and Entrance Separation

The exits and entrances of a line are separated by additional lines:

![](images/98.%20Peels%20(a%20rejected%20concept).009.png)

They are called *exit-enter* marks. The inner peels are exits and the outer peels are entrances. So in the example above there are two exits and then one entrance. The exit-enter mark is reminiscent of where you put an access symbol to denote direction: between the exits and entrances. First are the exits, so the inner peels represent exits. The outer peels represent entrances.

With the exit-enter marks the symbol above could still mean:

| ![](images/98.%20Peels%20(a%20rejected%20concept).010.png) | __=__ | ![](images/98.%20Peels%20(a%20rejected%20concept).011.png) |
|-----|-----|-----|

but no longer: 

| ![](images/98.%20Peels%20(a%20rejected%20concept).010.png) | __`≠`__ | ![](images/98.%20Peels%20(a%20rejected%20concept).012.png) |
|-----|-----|-----|

#### Line Type

Solid peels are used to express information about the *object line*. For type lines you use dashed peels and for interface lines you use dotted peels. For instance:

![](images/98.%20Peels%20(a%20rejected%20concept).001.png)

This border expresses that the symbol’s object line crosses one border and that the type line crosses two.

The different looking peels are called *peel types*, analogous to the term *line* types. As such you also speak of object peels, type peels and interface peels.

I’ll continue with another example:

![](images/98.%20Peels%20(a%20rejected%20concept).013.png)

This border suggests that the type line crosses two borders and the object line crosses three. It could for instance mean the following:

![](images/98.%20Peels%20(a%20rejected%20concept).014.png)

*The blue symbol could be drawn having the peels in the previous picture.*

The object line exits one border, after which it enters two before it reaches its destination. The type line exits one border, then enters one.

You can also draw exit-enter marks in a border with multiple peel types:

![](images/98.%20Peels%20(a%20rejected%20concept).015.png)

When you express exit-enter distinction, you can put the object peels and type peels apart with some space or it might be hard to tell them apart:

![](images/98.%20Peels%20(a%20rejected%20concept).016.png)

Not keeping space between the peel types when showing exit-enter marks can *not* cause ambiguity *if* you show the exit enter-marks for all peel types. But if you don’t show the exit-enter marks for all peel types, ambiguity could occur if an exit-enter mark is exactly in between peel types. The presence of another exit-enter mark annuls this ambiguity. When there is undoubted ambiguity, then it is obligatory to put space between peel types. In the other cases it’s not, but for readability it can be advised to put spacing in between peel types anyway, but if you don’t want to, you might not.

In another example:

![](images/98.%20Peels%20(a%20rejected%20concept).017.png)

You draw out the peel notation with exit-enter marks as follows:

![](images/98.%20Peels%20(a%20rejected%20concept).018.png)

The object line exits one borders and the type line exits two.

Keeping space between the different peel types can also cause ambiguity, though, because in small symbols they could suggest that there are two symbols:

![](images/98.%20Peels%20(a%20rejected%20concept).018.png)

In larger symbols you might see the difference more easily, though:

![](images/98.%20Peels%20(a%20rejected%20concept).019.png)

#### Type of Crossed Border: Studs

To express the shapes of the symbols that are crossed, you can draw little shapes through the peel:

![](images/98.%20Peels%20(a%20rejected%20concept).020.jpeg)

You can repeat the shapes multiple times if you want:

![](images/98.%20Peels%20(a%20rejected%20concept).021.jpeg)

#### Name of Symbol Crossed

To express what symbol is entered or exited, you can put names with peels as follows:

![](images/98.%20Peels%20(a%20rejected%20concept).022.jpeg)

#### Exceptionals

##### Single Solid Border

A single solid border:

![](images/98.%20Peels%20(a%20rejected%20concept).023.png)

can suggest that its object line crosses one border. It could also just be an object symbol.

To denote explicitly that the line crosses one border, you might include an exit-enter mark so that you can see that it’s a border expressing line information:

| ![](images/98.%20Peels%20(a%20rejected%20concept).024.png) | ![](images/98.%20Peels%20(a%20rejected%20concept).025.png) |
|:------------------:|:-----------------:|
| *Enter one border* | *Exit one border* |

So in that case you are forced to draw out if it’s an exit or entrance. If you draw peels different from borders, thinner for instance, you may ignore this rule.

##### No Crossings

To express that an object symbol has a line that enters nor exits any border you use the following notation:

![](images/98.%20Peels%20(a%20rejected%20concept).026.png)

Which can represent any of the symbols of:

![](images/98.%20Peels%20(a%20rejected%20concept).027.png)

Which is, by the way, not used a lot.

#### Peels for Other Symbols.

The peel notation above works the same for triangle symbols. It also works for command symbols, except that command symbols have a different set of line types, so a different set of peel types: reference peels and interface peels.

#### Abstract Meaning

A border with peels can also express more abstract facts. Here are some of such meanings:

- A symbol has a line
- Line crosses many borders
- Line exits borders
- Line exits many borders
- Line enters borders
- Line enters many borders
- Line exits and enters borders
- Line exits many borders and enters many borders
- Line exits many borders and enters borders
- Line exits borders and enters many borders
- Line exits an interface
- Line enters an interface
- Etcetera

##### Symbol Has A Line

With a simple alternative shape border you can express that a symbol has a line of a certain type.

|                                          |                                  |                                         |
|:----------------------------------------:|:--------------------------------:|:---------------------------------------:|
| ![](images/98.%20Peels%20(a%20rejected%20concept).028.png) | ![](images/98.%20Peels%20(a%20rejected%20concept).029.png) | ![](images/98.%20Peels%20(a%20rejected%20concept).030.png) |
|      *Double solid object symbol:*       |     *Dashed object symbol:*      |        *Dotted object symbol:*          |
|   *object symbol with an object line*    | *object symbol with a type line* | *object symbol with an interface line*  |

|                                        |                                         |
|:--------------------------------------:|:---------------------------------------:|
| ![](images/98.%20Peels%20(a%20rejected%20concept).031.png) | ![](images/98.%20Peels%20(a%20rejected%20concept).032.png) |
|        *Double command symbol:*        |        *Dotted command symbol:*         |
| *command symbol with a reference line* | *command symbol with an interface line* |

The solid border needs to be doubled, because otherwise you don’t see that information about the line is expressed. When you denote that a symbol has both an object line as well as a type line, you can use a single solid peel, because then it’s clear that you’re expressing line information. 

![](images/98.%20Peels%20(a%20rejected%20concept).033.png)

When denoting the mere existence of a line, the destination of the line is undetermined, but it’s is usually just outside the parent. This assumption is analogous to the first line direction rule: the outwards rule. A line simply most commonly points outwards and most commonly only crosses a single border.

##### Symbol’s Line Crosses Many Borders

To denote that many borders are crossed, usually three peels are used. So three peels come in the place of where otherwise an exact amount of peels is put. A line that crosses many borders is also said to have a far away line target.

|                             |                                |                                |
|:---------------------------:|:------------------------------:|:------------------------------:|
| ![](images/98.%20Peels%20(a%20rejected%20concept).034.png) | ![](images/98.%20Peels%20(a%20rejected%20concept).035.png) | ![](images/98.%20Peels%20(a%20rejected%20concept).036.png) |
| Triple solid object symbol: | Triple dashed object symbol:   |  Triple dotted object symbol:  |
|    object symbol with a     |     object symbol with a       |      object symbol with a      |
| far away object line target |   far away type line target    | far away interface line target |

|                                |                                |
|:------------------------------:|:------------------------------:|
| ![](images/98.%20Peels%20(a%20rejected%20concept).037.png) | ![](images/98.%20Peels%20(a%20rejected%20concept).038.png) |
|         Triple square:         |      Triple dotted square:     |
|     command symbol with a      |      command symbol with a     |
| far away reference line target | far away interface line target |

##### Other Abstract Meanings

I might simply give a sum up of the other abstract meanings I’ve mentioned and give the peel notation for them.

|                                                             |                                                             |
|:-----------------------------------------------------------:|:-----------------------------------------------------------:|
|                   *Line exits borders:*                     |                    *Line enters borders:*                   |
| ![](images/98.%20Peels%20(a%20rejected%20concept).025.png)  | ![](images/98.%20Peels%20(a%20rejected%20concept).024.png)  |
|                                                             |                                                             |
|                *Line exits many borders:*                   |                 *Line enters many borders:*                 |
| ![](images/98.%20Peels%20(a%20rejected%20concept).039.png)  | ![](images/98.%20Peels%20(a%20rejected%20concept).040.png)  |
|                                                             |                                                             |
|             *Line exits and enters borders:*                |     *Line exits many borders and enters many borders:*      |
| ![](images/98.%20Peels%20(a%20rejected%20concept).041.png)  | ![](images/98.%20Peels%20(a%20rejected%20concept).042.png)  |
|                                                             |                                                             |
|       *Line exits many borders and enters borders:*         |        *Line exits borders and enters many borders:*        |
| ![](images/98.%20Peels%20(a%20rejected%20concept).043.png)  | ![](images/98.%20Peels%20(a%20rejected%20concept).044.png)  |
|                                                             |                                                             |
|                  *Line exits a triangle:*                   |                   *Line enters a triangle:*                 |
| ![](images/98.%20Peels%20(a%20rejected%20concept).045.jpeg) | ![](images/98.%20Peels%20(a%20rejected%20concept).046.jpeg) |

You can come up with other abstract meanings for peel notations using your imagination.

#### Expressible in the Symbol Border

So the following about a line can be expressed in a symbol’s peels:

- Line type
- Crossings
- Exits and entrances separation
- Shape of crossed symbol

The peels can also only have a more abstract meaning.

Unless you name the peels, the only thing you can’t express in a symbol’s peels is *which* symbol is entered. You *might* know which symbol is exited, because only the parent can be exited.

That means that you can express a whole lot in a symbol’s peels. If you count names with peels, you can express everything about a line in a shape peel notation.

#### Only Use Peel Notation Where It’s Useful

Only use peels where they’re useful. Again: peels are only used in special situations, in which they provide more clarity. This can be the case:

- if a line or part of a line is out of view 

or

- the line target is hard to find

or

- lines might obscure the picture.

or

- Similarity in line destination might be emphasized

So don’t use shape peels… unless the reasons above weigh out. < zwaarder wegen? >

### Line Peels

Peel notation can be applied to lines just as well. For example: a double line suggests that the line crosses two borders.

![](images/98.%20Peels%20(a%20rejected%20concept).047.png)

You can use line peels when a line’s destination is out of view or if it’s not easy to find due to complexity of the diagram.

When you use line peels, shape peels are usually not used, but no rule stops you from using both.

![](images/98.%20Peels%20(a%20rejected%20concept).048.png)

Don’t put an exit enter mark through a line, or it might seem to be an access symbol: one of the exit-enter marks is left out in the diagram above for this purpose.

In the peels of a *line* you can’t express exit-enter separation or the type of symbol crossed. You can however express that a line with a single peel expresses the amount of crossed borders, by using an extra mark:

![](images/98.%20Peels%20(a%20rejected%20concept).049.png)

The little blue mark with the type line denotes that the line expresses the amount of borders crossed: one. If the line has more than one peel then this *crossing mark* is not required anymore. The crossing mark is analogous to the exit-enter mark you are required to add to a symbol with a single peel in order to say that the line crosses one border. If you draw line peels different from normal lines, thinner for instance, you can leave out the crossing mark.

### Ambiguity In Peels

Here is a list of a few ambiguity risks when using peels:

- Multiple shape peel types may suggest the existence of another symbol.
- Line peels may suggest the existence of multiple lines.

Ambiguity risks might be widely covered in the ‘Diagram Metrics’ in the book ‘Symbol Language Advanced’.

### Overview of Peals

- Double lined shapes:
    - The line can be left out in these cases, but doesn’t might.
    -----
    - Double solid line object symbol:
        - It’s an object reference or
        - It’s an object reference to an object in the parent
    - Triple solid line object symbol:
        - It’s an object reference to an object in the grandparent
    - Etcetera
    -----
    - Dashed line object symbol:
        - It has an external type or
        - It has a type that’s inside the parent
    - Double dashed line object symbol:
        - It has a type that’s inside the grandparent
    - Etcetera
    -----
    - Dotted line object symbol:
        - It has an external interface or
        - It has an interface that’s inside the parent
    - Double dotted line object symbol:
        - It has an interface that’s inside the grandparent
    - Etcetera
    -----
    - Double solid line square:
        - It is a call
        - It’s a call to a command in the parent
    - Triple solid line square:
        - It’s a call to a command in the grandparent
    - Etcetera
    -----
    - Dashed square:
        - It’s a command reference
        - It’s a command reference to a command in the parent
    - Double dashed square:
        - It’s a command reference to a command in the grandparent
    - Etcetera
-----
- Double lines:
    - In these cases, alternate shape borders are usually not used
    - Double line:
        - Line points two capsules outwards
    - Triple line: 
        - Line points three capsules outwards
-----
- Ambiguity in alternate notations:
    - Double shape borders can seem ambiguous to double encapsulation
    - Double lines can seem ambiguous to two separate lines.
    - Line grouping can make ambiguity of double lines even worse.

You can decide on your own what kind of notation you want to use, but the programming environment adopts standard ways to draw a diagram. It automatically uses different notations in different views on the system.

### Loose Ideas

#### Create Argument and Call Argument’s Members

`<< peels >>`

You can let the separate object seem to be the argument itself, by using a peel notation:

![](images/7.%20Commands%20Ideas.058.jpeg)

The creation might still be visible, but you’ve excluded the line, without loosing the information that it’s really an external object. 

Of course you might not show the implicit creation.

![](images/7.%20Commands%20Ideas.059.jpeg)

Then you just see that the object is created, and you might be satisfied knowing only *that* it is created, not where and when. This is just about exactly the effect of:

```vb
Command ( New Type )
```
