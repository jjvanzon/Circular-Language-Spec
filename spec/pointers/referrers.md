Pointers | Referrers
====================

`[ Draft ]`

[back](./)

__Contents__

- [Object Referrers](#object-referrers)
    - [Concept](#concept)
        - [`Not*` Supporting `the*` Referrers Concept](#not-supporting-the-referrers-concept)
    - [Diagram Notation](#diagram-notation)
- [Class Referrers](#class-referrers)
    - [Concept](#concept-1)
        - [`Not*` Registering Class Referrers](#not-registering-class-referrers)
    - [Diagram Notation](#diagram-notation-1)
- [Interface Referrers](#interface-referrers)
- [Command Referrers](#command-referrers)
    - [Command Object Referrers](#command-object-referrers)
    - [Command Definition Referrers](#command-definition-referrers)
- [Referrers Versus Related Objects](#referrers-versus-related-objects)
- [`The*` Referrers Concept](#the-referrers-concept)
- [Loose Ideas](#loose-ideas)

## Object Referrers

### Concept

Objects can have references to other objects. A referenced object may not aware of its referrers, but it might be an option to explore for an object to have all its referrers registered in a list.

`The*` referrers `are not* the*` parents `containing the*` references to `the*` object, `but* the*` referrers `are the*` *references* to `the*` object `themselves`.

`When*` a related item `is set to point` to a `certain` object, `the*`  __Related Item  .  Object  .  Set__  command `might` update `the*` target’s list of __Referrers__. `So the*` *referrers* `update the*` target’s __Referrers__ list. `The*` referenced object `might not*` update `the*` __Referrers__ list `itself`.

`The*` __Referrers__ list `consists` of references *back* to `the*` referrers, `but*` that `might not* mean the*` object `in turn becomes` a referrer of `the*` referrer `again`.

An object `can* have` a referrers list, `but*` an object reference, `so` a related item or related list item (see `the*` *System Interfaces* articles), `can*` also `have` its `own` referrers list for references that `refer` to references.

#### `Not*` Supporting `the*` Referrers Concept

An object `could*` choose `not*` to support `the*` __Referrers__ concept, `if* the*` programmer `knows,` that `this` object `might` be referenced `so many` times, and there `is so little interest` in `knowing all` its referrers, that it `might*` be `ridiculous` maintain a list.

`But* by default, the*` __Referrers__ concept `is always` supported.

### Diagram Notation

`The*` referrers of an object `are simply` displayed as a sub-list called __Referrers__, `every` item of which `points` back to `the*` references to `the*` object:

![](images/5.%20System%20Objects%20Misc%20Issues.014.png) 

`The*` entry in `the*` __Referrers__ list `is` pointing to a related item in `the*` parent object __A__, `not* directly` to an object.

`The*` lines `coming out` of `the*` referrers list `are usually not*` shown, `because*` a line `tied *to*` an object `already *implies*` a referrer. `The*` diagrams `might have more` features `later`, and the referrer lines `might* obscure the*` picture.

![](images/5.%20System%20Objects%20Misc%20Issues.015.png)

`Even the* whole` referrers list may `even` be `left out` of `the*` diagram `by default, but*` it `is not* clear yet, if*` that `is the* way to go`.

`If*` something `refers` to a reference, `then* this` may look `like this` in a diagram:

__b__ in __A__ `is` a reference to `the*` reference to __c__ inside __B__. `To display the*` referrers in `the*` diagram, `you* could*` < > `do` something `like this` < >:

![](images/5.%20System%20Objects%20Misc%20Issues.016.png)

![](images/5.%20System%20Objects%20Misc%20Issues.017.png)

## Class Referrers

### Concept

`The*` *Referrers* article `explained how` an object `can*` be `made aware` of its referrers. A *class* `can* also` be `made aware` of `the*` objects `using` it as a class.

~Classes `are` implemented as an aspect.~ That concept `adds` an object reference to `the*` system interface. `This` object reference `points out` which other object `is` its class. `So oddly`, an object reference, that `points` out `the*` class, `is already` added to `the*` class’s list of referrers. `The*` classes `are registered` inside `the* same` list of referrers as object referrers. `This is actually just fine. The*` __Referrers__ list `is supposed to be` a `low-level` view on `the*` referrers.

A class `is usually only` *used* as a class, and `not* also used` as an object, `so in practice, the*` __Referrers__ list of a class, `actually already *is*` a list of class referrers. `So` a `separate` list of __Class Referrers__ `might not*` be `implemented`.

`But* if*` in `the* future` there `is` a `need` to `also maintain` a `separate` list of class referrers, a `separate` __Class Referrers__ concept `could*` be `implemented. In that case, when*` a related item’s *class* `is` set, `the*` __Related Item  .  Class  .  Set__ `might` update `the* target`’s list of __Class Referrers__.

#### `Not*` Registering Class Referrers

`The*` amount of referrers of a __Number__ *object* may be `small, but* the*` amount of referrers of `the*` __Number__ *class* `is humungous. The*` class `might even have` a __Referrers__ list, `when* the*` class `is not*` a created object, `because*` __Referrers__ `applies` to `both` symbols and objects.

`You* might* want to` turn `the*` __Referrers__ concept `*off*` for `the*` __Number__ class and *on* for __Number__ objects. `But* the* problem here is`, that a class `is` a blueprint for an object. An object `only supports` __Referrers__, `because* the*` *class* `supports` it.

`The* first solution proposed was` to `simply not* support the*` __Referrers__ concept for classes that `are widely` used. `But* then*` for `widely` used classes, `the*` __Referrers__ concept `never` be `supported`. That `is against the*` idea of `supporting the*` __Referrers__ concept `by default`.

`If* you* can* not* stop` a class from `supporting` __Referrers__ `without stopping` objects from `supporting` __Referrers__ at `the* same time, then* the*` __Referrers__ concept `might not*` be `widely` used `anymore`.

`Therefore, you* are` going to `might specify` for a symbol or object, that it `is` a non-practitioner of a concept. Derivation of objects `might` take over `the* specified` concept, `but* not* the*` non-practitioner aspect. Or perhaps instead of calling it non-practitioner, `you* could*` call it __Objects Support Concept Referrers__, or something.

### Diagram Notation

< `The*` notation of a reference to an object reference’s class `needs to be determined` in `the* future`. >

`Because* the*` concept of referrers `simply also functions` as `the*` concept of class referrers, it `can*` be displayed in a diagram `the* same way, except`, that classes and class references `are` displayed with dashed lines.

![](images/5.%20System%20Objects%20Misc%20Issues.018.png)

`The*` reference line of `the*` item in `the*` __Referrers__ list `is` displayed, `then*` it `has to` point to `the*` class redirection of symbol __b__. There `is no final` notation `yet` for a to something `else’s` class. `But*` a preliminary notation `could* either` be a reference to `the*` __Class__ inside __b__’s system interface:

![](images/5.%20System%20Objects%20Misc%20Issues.019.png)

`Or` a reference line `connected` to __b__’s class line:

![](images/5.%20System%20Objects%20Misc%20Issues.020.png)

`The*` referrers `are` pointed at by solid lines, `because*` they `are just` references to `the*` objects, that `use` it as a class. `No implicit` notation of `making the*` referrer lines *dashed* `might` be used `here, because*` that `might` introduce `too much ambiguity` in `the*` diagram `notation`.

As `mentioned` in `the*` article *Referrers*, it `is not* clear yet` under which circumstances `the* whole` referrers list might be `completely` left out of `the*` diagram.

`If*` a class `defines` that its objects `support` __Referrers__, `but* the*` class `itself won’t` register its __Referrers__, `then* the*` Referrers list of `the*` class `might` be drawn out with dashed lines.

![](images/5.%20System%20Objects%20Misc%20Issues.021.png)

`Obviously, the*` inactive referrers list `might not* contain any` object references.

## Interface Referrers

The *Referrers* concept has been explained in the *Relations* chapter. The article *Class Referrers* explains the concept for classes. It works exactly the same for interfaces. It might not be further explained here. Mind that commands can have interface referrers as well.

## Command Referrers

`<< referrers >>`

### Command Object Referrers

The *Referrers* article explained how an object can be made aware of its referrers. The concept of referrers applies direction to command objects as well.

If a command and its references both support the __Referrers__ concept, then every command reference might register itself in the __Referrers__ list of the target command.

Refer to the article *Referrers* for an explanation on how the Referrers concept works.

### Command Definition Referrers

The *Referrers* article explained how an object can be made aware of its referrers. A command is an object as well and the __Referrers__ concept already provides a command with *command definition referrers* functionality. An inactive command is the only type of command symbol that can be referenced. Am inactive command symbol can implement the __Referrers__ concept to register every call or reference to it.

When a site hosts a command definition, that is widely used all over the world, you might not want the command definition to register its referrers, because it might be a very long list to maintain. You can turn off the Referrers concept for any command definition.

If another site uses this widely used command definition, the using site could add a command reference to the command definition on the other site. A command reference has its own list of referrers. The using site could then redirect calls and references to its own command reference. Then the using site has a registration of anything on its site that uses the external command definition.

## Referrers Versus Related Objects

Referrers `are` handy, `when* so many` classes relate to another class, that `the*` other class might `not*` want to maintain a separate list for `each` class that links to it.

It `is` also handy for `when*` a class `can't*` be aware of its related classes, `so can* not*` automatically get a relation back to classes, that want to link to it. In that case `the*` other class `can* not*` establish a dual relation with `the*` remote class, probably, `because*` it might `not* have` permission to alter `the*` remote class. Or `the*` remote class denies dual relationships to it altogether.

To make `the*` remote class or object aware of its referrers anyway, `you* can*` let it support `the*` referrers concept.

## `The*` Referrers Concept

A __Number__ class `could*` choose to support `the*` __Referrers__ concept. `This might` give a __Number__ object `only` one list of `all` referrers, instead of a separate list for `every` class that uses __Numbers__. __Numbers__ may be used by `many` classes, `but*` an individual __Number__ object, `is` never used `much`. It `is not*` a `lot` of data to register inside an __Number__ object, which objects refer to that particular __Number__.

`But* then* the*` __Number__ class `might` also register `all` its *class referrers*, which `is` undoable, `because*` a humongous amount of objects refer to `this` class. `But*` a solution for `this was already` proposed by `the*` article *Class Referrers*. `You* can*` choose for a class to `not*` register its class referrers, while objects do register their referrers.

## Loose Ideas

Taken out of `the*` Referrers article:

< Compared to giving a number class a related list for `every` class that uses integers >

A number class `could*`, however, choose to support a single list of `all` referrers. `Then*` a number object `might have only` one related list. Numbers may be used by `many` classes, `but*` an individual number object, `is` never used `much`. It `is not*` a `lot` of data to register inside an integer object, which objects refer to that particular number.

JJ

-----

Referrers,  
2008-08-10

`The*` Referrers concept `needs to be` redone. Consider `the*` system interface and make `sure you* can*` register referrers in a reference, as well as referrers to an object, and consider whether `you*` want `the*` referrers list to point to references or `the*` parents of `the*` references. `The*` article Referrers in a Diagram, Class Referrers in a Diagramand Command Definition Referrers in a Diagram `are` involved.

`I was` looking at `the*` Refferes diagrams. It’s `not*` correct. `The*` referrers list registers `the*` parents of `the*` references. `I`’m thinking now: they `should` register `the*` references themselves. `I might have` been that `I was` unaware of `the*` workings of `the*` system interface back `then*`...

JJ

-----

Referrers,  
2008-08-28

Referrers `has to be` redone. It `has to` become a list of related items and related list items, that they `are` inside their parents.

Redoing Referrers `was` postponed in `the*` project Work Out Basic Command Articles, `because*` it involves `too much` other material, that takes `too much` time to go into.

Referrers `is` mainly part of Relations.  
`You* are` probably going to `might` read over `the*` whole Relations article group.

`The*` following articles may `might be` redone, `when*` redoing Referrers:

- Referrers
- Referrers in a Diagram
- Class Referrers
- Class Referrers in a Diagram
- Referrers Versus Related Objects
- Command Object Referrers
- Command Object Referrers in a Diagram
- Command Definition Referrers
- Command Definition Referrers in a Diagram

JJ

-----

Referrers,  
2008-08-28

`The*` referrers articles `are not* finished`, because referrers `needs to be` reconsidered later, and it involves `much` different material, that takes time to go into.

- `I` hate it, that `I could* not* finish the*` referrers articles.
- `But*` it `is too much` to go into `just like` that.
- `I might` accept that `the*` produced article group `might` contain two subjects, that `are not* finished`.

JJ

-----

Referrers,

Referenties naar een copy functie wil je ook niet in de in de copy command definitie zelf bijhouden. Maar je zou wel de mogelijkheid willen hebben om te querien welke kopieeracties er binnen een bepaald systeem zijn. Je kunt altijd een ruwe sequentiële zoek-query uitvoeren op een subsysteem. Maar je wilt het misschien ook centraal bijhouden. Dan zou je een filter index moeten kunnen maken, maar een filter index gezet op een elders gedefinieerde method of class.

Ik heb er toch best moeite mee, dat je in een stuk diagram niet ziet wat er allemaal naar een bepaald object verwijst, maar alleen waarnaar de objecten in de diagram verwijzen. O, wacht, dat gebeurt voor objecten wel, omdat de gerelateerde objecten als sub objecten worden getoond. Heen en weer relaties tussen objecten in principe gelijkwaardig. Maar bij methods `is` het anders. Die hebben altijd een richting, en de relatie terug `is` echt de backwards verwijzing.

Het `is` zeg maar een kwestie van 'belachelijk om allemaal bij te houden'.

Alleen soms wil je voor een definitie, die zijn referrers niet bijhoudt, toch referrers bijhouden.

Eigenlijk moet dan een systeem de referrers naar een definitie van een ander systeem bij kunnen houden.

Je maakt bij methods eigenlijk ook relaties tussen method definitions aan. Die zouden dan ook referrers bij kunnen houden, en een gesynchroniseerde relatie aan kunnen gaan.

JJ

-----

Referrers,  
2008 +/-

< The expression of referrers in a diagram needs to be redone, because the referrers list refers to the parents of the references, which is not necessarily the way to go. I’m not sure yet. I might want to register the related items and related lists items that are the references to the command definition, instead of registering their parents, and an ID, that the reference has inside the parent. >

JJ