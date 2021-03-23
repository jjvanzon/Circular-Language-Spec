﻿Circle Language Construct Drafts | From Spec
============================================

Relationships Construct Drafts
------------------------------

`[ Deprecated documentation ]`

### Relationships Between Classes

`The*` class-relationship structure `is the*` bone structure of a program.

### Bidirectional Relationships

The notation suggested here was moved away from the Circle Language Spec in favor of another notation.

Starting with:

![](images/1.%20Relationships%20Construct%20Drafts.001.png)

A suggested notation would be for the two class lines to merge together to form `the` picture below:

![](images/1.%20Relationships%20Construct%20Drafts.002.png)

This, however, might be a quite ambiguous notation. It would suggest that the two symbols joined by the line would have the same class. But that would not be what is intended. The circle inside __Class A__ would have __Class B__ and the circle inside __Class B__ would have __Class A__.

A solution to this ambiguity may be proposed.

Fortunately, `the*` notation `can*` be disambiguated using `the* rules` of automatic containment. Automatic containment `is` explained in `the*` article *Automatic Containment*. Before explaining how automatic containment leads to `the*` eventual notation, here `is the*` disambiguated notation of a relationship between two classes:

![](images/1.%20Relationships%20Construct%20Drafts.003.png)

`The*` notation `is` accomplished by first taking `the*` original picture with one class referring to another and `the*` other referring back to `the*` first class:

![](images/1.%20Relationships%20Construct%20Drafts.001.png)

`Then*`, an imaginary reference to `each` class `is` added to `the*` diagram:

![](images/1.%20Relationships%20Construct%20Drafts.004.png)

Next, `the*` class lines `are` merged, `but*` also `the*` class symbols `are` merged:

![](images/1.%20Relationships%20Construct%20Drafts.003.png)

`The*` notation `would*` still be ambiguous, `if*` it weren’t for `the*` double dashed line of `the*` merged class symbols. `So` a double dashed circle symbolizes a relationship between classes.

Examples with different multiplicities:

![](images/1.%20Relationships%20Construct%20Drafts.005.png)

![](images/1.%20Relationships%20Construct%20Drafts.006.png)

![](images/1.%20Relationships%20Construct%20Drafts.007.png)

A symbol merge in a relationship that has nonagons in it also results in a double dashed circle, `because* the*` imaginary reference to `the*` classes, that `are` put on a higher level, `are` represented by circles, `not*` a nonagons.

There is an idea where one related list might contain items from multiple classes. __Class A__ would have a __n => 1__ relationship to items of __Class B__ and __Class C__, which the picture below aims to express:

![](images/1.%20Relationships%20Construct%20Drafts.008.png)

#### Counterpart out of Sight

If the counterpart of a relationship would be out of sight, a line might point out of the diagram. A catch there might be that you might not see whether the relationship counterpart would have multiplicity of __1__ or __n__. A possible solution for this, might be to express multiplicity at the end of that line that might point out of the diagram.

This might look as follows with the double dashed border notation:

![](images/1.%20Relationships%20Construct%20Drafts.009.png)

![](images/1.%20Relationships%20Construct%20Drafts.010.png)

But then again, if something is out of sight, it might just be out of sight and you cannot see things out of sight. Perhaps there is no problem here.

Here are examples of what it could look like in case of relational ring notation, with explicit relationship counterparts:

![](images/1.%20Relationships%20Construct%20Drafts.011.png)

![](images/1.%20Relationships%20Construct%20Drafts.012.png)

That proposal might be a problem, because it seems to clash with a proposed notation for optional. And also it seems to not reflect the containment structure: there would be a container in between the half shape and the other parts of the diagram. Seems unfortunate.

In another proposal:

![](images/1.%20Relationships%20Construct%20Drafts.013.png)

![](images/1.%20Relationships%20Construct%20Drafts.014.png)

It may be going a bit far. It seems to draw out part of the diagram, that is out of sight. But then it might actually have a container in between, that is not drawn.

The argument "What is out of sight, is out of sight." might be good enough to not solve this 'problem'. A proposal might be that might not be a real problem.

Here a variation that might also be dubious:

![](images/1.%20Relationships%20Construct%20Drafts.015.png)

In that image both relationship counterparts' class lines are connected to the same half shape. It might go a bit far in suggesting something it's not.

#### `No` Reuse of Merged Imaginary References

`If*` two imaginary references `have` merged, `to become` a relationship symbol, `then*` other references to `the*` same classes won’t connect to an imaginary reference that has merged `to become` a relationship symbol. Relationships create their own imaginary references, that aren’t reused. `This is` displayed in `the*` article *Relationships Between Objects in a Diagram*, `but*` may also apply to `the*` notation of relationships between classes.

![](images/1.%20Relationships%20Construct%20Drafts.016.png)

#### Example

![](images/1.%20Relationships%20Construct%20Drafts.017.png)

### Relations Between Objects

#### Diagram Notation

`The*` relationship symbol `is` a double circle. `The*` reason behind `this` notation, `was already` explained in `the*` article *Relationships in a Diagram*. `The*` notation `is` accomplished by first taking `the*` original picture with one class refering to another and `the*` other refering back to `the*` first class:

![](images/1.%20Relationships%20Construct%20Drafts.018.png)

`Then*`, an imaginary reference to `each` class `is` added to `the*` diagram

![](images/1.%20Relationships%20Construct%20Drafts.019.png)

Next, `the*` class lines `are` merged, `but*` also `the*` class symbols `are` merged:

![](images/1.%20Relationships%20Construct%20Drafts.020.png)

`The*` notation `would*` still be ambiguous, `if*` it weren’t for `the*` double line of `the*` merged object symbols. `So` a double circle symbolizes a relationship between objects.

For relationships between classes `the*` relationship symbol `is` a double *dashed* circle. For relationships between objects, `the*` relationship symbol `is` a double circle drawn with *solid* lines.

#### Counterpart out of sight

`When* the*` counterpart of `the*` relationship `is` out of sight, a line `should` point out of `the*` diagram. A catch there `is`, that `you* can’t` see `if* the*` relationship counterpart `is` part of a multiplicity of __n__ or `not*`. Therefore, `the*` multiplicity `is` expressed at `the*` end of `the` line pointing out of `the*` diagram as follows:

![](images/1.%20Relationships%20Construct%20Drafts.021.png)

#### `No` reuse of merged imaginary references

`If*` two imaginary references `have` merged, to become a relationship symbol, `then*` other references to `the*` same objects won’t connect to an imaginary reference that has merged to become a relationship symbol. Relationships create their own imaginary references, that aren’t reused.

Here `is` a relationship between two objects:

![](images/1.%20Relationships%20Construct%20Drafts.020.png)

`The*` two objects refer to each other. `This` originally consisted of two distinct references:

![](images/1.%20Relationships%20Construct%20Drafts.018.png)

Imaginary references `were` put on one level higher:

![](images/1.%20Relationships%20Construct%20Drafts.019.png)

`If*` other references to `the*` same objects `were` also displayed in `the*` diagram, `then*` they `would*` connect to `the*` same imaginary references, put on a higher level:

![](images/1.%20Relationships%20Construct%20Drafts.022.png)

`When* you*` merge `the*` imaginary references to display that two references `are` part of a single relationship, `you* will not*` connect `all` references to `the*` merged imaginary reference:

![](images/1.%20Relationships%20Construct%20Drafts.023.png)

`You* will` keep separate imaginary references for `the*` other unidirectional relationships to `the*` objects:

![](images/1.%20Relationships%20Construct%20Drafts.016.png)

### Bidirectional Relationship Synchronization Implementation Details

`When* you*` let one of `the*` object references link to another object, `then* the*` link from `the*` old counterpart to `the*` object `should` be broken and a link from `the*` new counterpart to `the*` object `should` be established. `The*` object synchronizes `the* old` counterpart *out*, and it synchronizes `the*` new counterpart *in*.

In `the* new computer language you* are` still able to create `just` a unidirectional relationship. In a programming environment `you* should` be able to automatically turn a unidirectional relationship to a bidirectional relationship. In a programming environment `you* should` be able to turn two `already defined` unidirectional relationships into a single bidirectional relationship.

`So` whenever a __Jar__ changes its __Lid__, `the*` original __Lid__’s reference to `the*` __Jar__ `is` annulled, and `the*` new __Lid__ get a reference to its new __Jar__. `This actually` explains synchronization between __1 => 1__ related objects. Synchronization happens `when*` assigning a related item. `When*` assigning a related item, `the*` related item gets a reference back to `the*` first item.

Relationship synchronization happens `when* you*` assign a related object. `When* you*` assign __Lid . Jar__, `then*` synchronizing `the*` relationship, consists of, in turn, assigning __Jar . Lid__.

For `every` relationship type it works in a different way.

There `are` three relationship types:

- __1 <=> 1__
- __1 <=> n__
- __n <=> n__

`But*` synchronization `is` managed separately for `each` end of `the*` relationship, `so` synchronization `is` managed in `the*` following four of ways:

- __1 => 1 synchronization__
- __1 => n synchronization__
- __n => 1 synchronization__
- __n => n synchronization__

#### Synchronization Types

There `are` four synchronization types:

- __1 => 1 synchronization__
- __1 => n synchronization__
- __n => 1 synchronization__
- __n => n synchronization__

`Every` synchronization type follows a slightly different procedure, to make `sure` that on assignment of one relationship counterpart, `the*` other relationship counterpart goes along with it.

#### 1 => 1 Synchronization

__1 => 1__ synchronization `is quite` easy. In a __Jar =>__ __Lid__ relationship, `when*` assigning __Lid . Jar__, `The* old` __Jar . Lid__ `is` set to __Nothing__, while `the*` new __Jar . Lid__ `is` set to __This__.

#### Risk of infinite loop 1 => 1

`When*` a relationship `is` synchronized, `you*` may `have` a risk to an infinite loop.
`When* you*` assign __Jar__ to __Lid__, `then*` __Lid__ `is` assigned to __Jar__, upon which __Jar__ `is` assigned to __Lid__ again, and `so` on. Fortunately, `when*` a __Jar__ `is` assigned a __Lid__ it `already` has, `the*` whole assignment `is not*` executed. `So` it `only` goes as far as: __Jar__ `is` assigned to __Lid__, upon which __Lid__ `is` assigned to __Jar__ again, upon which __Jar__ `is` assigned to __Lid__ again, `but*` __Jar__ `already` had that __Lid__, `so` that assignment `is` never executed.

#### 1 => n Synchronization

In a __1 => n__ relationship between __Parents__ and __Children__, `every` time `you*` assign a __Child__ to a __Parent__, __Child . Parent__ `is` overwritten. `The* old` __Child__ `is` assigned __Nothing__ as `the*` __Parent__, and `the*` new __Child__ `is` assigned its new __Parent__.

Also, `the*` original __Child__’s __ID In Parent__ `is` yielded over to `the*` new __Child__. `The*` original __Child__’s __ID In Parent__ `is` reset.

There used `to be` a misunderstanding, that one __Parent__ `could*` reference `the*` same __Child__ multiple times. `But*` that idea `was` abolished, `because* when*` a __Parent__ relates to a __Child__ twice, `the*` __Child__ `has to` relate back to `the*` __Parent__ twice. A __Child__ `can* only have` one __Parent__, `so` it `can*` never relate back to `the*` same __Parent__ twice. Something `like` that `would* require` an __n => n__ relationship, for `the*` __Child__ `to be` able to hold multiple references to `the*` same __Parent__.

#### Risk of infinite loop 1 => n

Infinite loops for __n => 1__ synchronization `are` prevented `the*` same way as for __1 => 1__ synchronization. `When* you*` assign a __Parent__ to a __Child__, `The*` __Child__ `is` added to `the*` __Parent__, upon which `the*` __Parent__ `is` again assigned to `the*` __Child__. `But* the*` __Child__ `already` had that __Parent__, `so the*` assignment `is` never executed. `So` that prevents an infinite loop there.

#### n => 1 Synchronization

In a __Child  n => 1  Parent__ relationship, `when* you*` change __Child . Parent__, `the*` __Child__ `is` removed from its original __Parent__ and added to `the*` new __Parent__. `So you* can never have the*` same __Child__ in several __Parents__.

A __Child__ `can* not*` appear multiple times in `the*` same __Parent__, `because*` that, in turn, `should` give a __Child__ multiple references back to `the*` __Parent__, `but*` a __Child__ holds `only` one reference to a __Parent__.

#### Risk of infinite loop n => 1

`When*` a __1 => n__ relationship `is` synchronized, `you*` may `have` a risk to an infinite loop. `When* you*` add a __Child__ to a __Parent__, `then* the*` __Parent__ `is` assigned to `the*` __Child__, upon which `the*` __Child__ `is` added to `the*` __Parent__ *again*.

An earlier solution proposed for `this, is` that in synchronizing `the*` relationship, `you*` never boldly __Add__ `the*` __Child__ to `the*` __Parent__, `but* you*` execute a __Find Or Add__, which prevents `the*` __Child__ from being added again, `when*` it `is already` in `the*` __Parent__’s list. `This would* have` worked, `but*` n => n synchronization `already required` a different solution, that `will` be more efficient for n => 1 synchronization as well.

`When* you*` assign an item to a list for synchronization purposes, `no` synchronization `is to be` executed on `the*` other side again.  
`You’d* have to` call a `special` __List Item Set__ procedure, accessible `only` to `the*` related class, that simply won’t synchonize back again.

#### n => n Synchronization

One *related item* in one object always creates *one related item* inside `the*` other object.

Two items, related to each other in an __n => n__ relationship, `are` always connected to each other, by connecting two `specific` list positions to each other.

In __n => n__ synchronization, __Object A__’s reference to __Object B__ `will` be replaced by a reference to __Object C__. `When*` __Object B__ `is` removed from __Object A__’s list, `then*` __Object A__ `is` also be removed from __Object B__’s list. After that, __Object A__ `is` added to __Object C__’s list.

An item in one list `is` aware of its position in `the*` other list. That makes it easy for an item in one list, to remove itself from `the*` other list.

#### Risk of infinite loop n => n

`But* when* you*` add __Object A__ to __Object C__’s list of related items, `then*` __Object C__ `will` try to add itself to __Object A__’s list of related items, upon which __Object A__ `will` add itself to `the*` list of __Object C__ again. An infinite loop `should` be prevented here.

`When*` synchronizing `the*` relationship between two objects in an __n => n__ relationship, `you* will` add a position to `the*` list of `the*` referrer, and next assign an item to `this*` position.

`When* you*` assign an item to a list for synchronization purposes, `no` synchronization `is to be` executed on `the*` other side again.  
`You'd* have to` call a `special` __List Item Set__ procedure, accessible `only` to `the*` related class, that simply won’t synchronize back again.

Another solution opted at first, `was` to execute a __Find Or Add__ for synchronization, instead of executing an normal __Add__ command. That `would*` prevent a related item from being added and added again. `But* then* you* have the*` problem: maybe `the*` same item *`should`* be added twice to `the*` list, `because*` one item `can*` relate to another item multiple times, which also `requires the*` other item to relate back to `the*` first item multiple times. For `each` reference to an item, `the*` item `must have` a reference back to `the*` referrer.

`So the*` new option `is` better: `you* have` a `special` __List Item Set__ procedure, possibly called by a `special` __Add__ procedure, used solely for relationship synchronization, that won’t synchronize *back* again.

#### `The*` abolished multiplicity of x

Earlier `I` had invented a multiplicity of __x__, which `is` plural, `but* then*` a fixed set of items, for instance three items. `But*` __x__ `can*` be replaced by three separate __=> 1__ relationships. __X__ `was` abolished in particular, `because*` it `would*` cause a `lot` of unpredictable behavior `when*` trying to synchronize `the*` two relationship counterparts, especially in __n/x => n/x__ synchronization.

#### Confusions about relationship synchronization

There used `to be` two points at which there `was` confusion about `the*` workings of relationship synchronization.

##### Confusion 1

What `can*` be confusing `is` that, `when*` a __1 => n__ relationship `is` synchronized, it `can*` never be used as an __n => n__ relationship. In `the*` relationship __Parent  1 => n  Child__, `every` time `you*` add a __Child__ to a __Parent__, __Child  .  Parent__ `is` overwritten. `When* you*` change __Child  .  Parent__, `the*` __Child__ `is` removed from its original __Parent__ and added to `the*` new __Parent__. `So you* can*` never `have the*` same __Child__ in several __Parents__. `If* you*` want to use multiple __Parents__, `you* can’t.`

It `is` often easier to `define` something in __1 => n__ relationships, `without` thinking about it, that `the*` backward relationship might be __=> n__ `too. But* when*` a relationship `is` synchronized, `the*` system falls apart `when*` a __1 => n__ `is actually` intended as __n => n__ and `you’re*` trying to *use* it that way.

`This can*` be misconceived as an error in `the* new computer language`, or an inability of it, while it’s `really just` a wrongly `defined` relationship.

`So then*` it becomes `really important` to `define the* exact` relationship type of something, even `when*` it’s more difficult.

`If* you*` do want to use `the*` __1 => n__ relationship as an __n => n__ relationship, `you*` `should` change `the*` relationship type, `but* you* could*` also choose to split `the*` bidirectional relationship into two unsynchronized unidirectional relationships. However, `you* will` be loosing out on functionality and loosing integrity and coherence of `the*` system.

A system in which `all` relationships `are` bidirectional and given `the*` correct relationship type, functions in perfect harmony and everything `is` logical, correct and solid.

##### Confusion 2

Synchronization `could*` cause confusion in `older` versions of `the* computer language`, where `you* have` two bidirectional relationships to `the*` same class, that `are` given `the*` same __Item Object Name__. In that case, one relationship’s counterpart synchronizing back to `the*` related object `could*` affect `the*` other relationship. By default it `is not*` allowed to `have` one class __A__ being __1 =>__ related to multiple classes, in which __A__ has `the*` same __Item Object Name__. That `is only` allowed `if* the*` other relationships `are` made unidirectional, and `not*` bidirectional, or `if*` *melding* `is` enabled. *Melding* `is` a topic, which makes it possible for multiple relationship classes or for instance *progressed objects* (article *Progression)*, `to be` referenced as a single related item, `but*` it `has to be` stated explicitly that `this is the*` intention. See `the*` article *Melding*.

## Loose Ideas

Stereotyping relationships

Perhaps another typing can be assigned to a relation, instead of containment. For instance: *ownership* or *usage*. Perhaps a few standard ones, and it may be possible to define `your` own typing by specifying a String.

JJ

-----

Relationships,  
2008-11

`The*` roles that symbols get `when*` connecting them with lines.

JJ

### ± 2004

(Specific implementation in Creator 0.9)

`The*` main unit in a relational structure `is the*` *class*. There `is` a list of *classes*.
`The*` classes `are` tied together with *relationships*. One class `is` tied to another.

`The*` main object that `defines` a relational structure `is the*` __Structure__ object. `The*` __Structure__ object `contains` a __Classes__ collection and a __Relationships__ collection. `If* you*` want to add a class, `you*` do that in `the*` __Classes__ collection. `If* you*` want to add a relationship, `you*` do that in `the*` __Relationships__ collection.

`The*` __Classes__ collection `contains` objects of class __Class__.  
`The*` __Relationships__ collection `contains` objects of class __Relationship__.

`Every` __Class__ `has` an __Attributes__ collection. A __Person Class__, for instance, `could* have` a __Name Attribute__ and an __EmailAddress Attribute__ and more attributes such as __Street__, __HouseNumber__, __ZipCode__, etcetera. A __Class__ also `contains` a __RelatedClasses__ collection, which reflects `all` of `the*` class’s related classes. `You* can’t` add __RelatedClasses__ to `this` collection. `You* have to define` relationships in `the*` __Structure.Relationships__ collection and they `will` be *reflected* in `the*` __Class.RelatedClasses__ collection. Other members of `the*` __Class__ class `are*` explained in other sections, `covering` different concepts. However, `all` members `are` briefly explained in a sub section below.

A __Relationship__ consists of two __RelationClasses__. It `contains` two __RelationClass__ objects that `define the*` two classes of `the*` relationship and how they relate to one another.

A __Relationship__ also `defines` whether `the*` relationship `is` __Bidirectional__ or __Unidirectional__, by `the*` __Boolean__ __Bidirectional__ member. `If*` a __Relationship__ `is` __Bidirectional__, `then*` both classes `are` aware of eachother and refer to one another. `If*` a __Relationship__ `is` __Unidirectional__ `then* only` __RelationClassA__ `is` aware of __RelationClassB__ and refers to it, `but*` __RelationClassB__ `is` unaware of __RelationClassA__ and doesn’t refer to it.

Even though a __Bidirectional__ relationship `would*` seem to make __RelationClassA__ and __RelationClassB__ equal opponents, __RelationClassB__ in `many` cases `is the* inferior` one. For instance, in writing XML files, __RelationClassB__ `is` seen as `contained` in __RelationClassA__ and `not* the*` other way around. In that case *direction* of `the*` relationship does matter. However, still in `many` cases __RelationClassA__ and __RelationClassB__ `are` technically equal opponents. `When* you*` keep in mind which __RelationClass__ `is` inferior and which one `is` superior, things `like` XML writing go well automatically. `If* you* are` sloppy with choosing `if*` something `is` __RelationClassA__ or __RelationClassB__, `you* could*` get trouble that makes `you*` obliged to switch `the*` two relationship classes within `the*` relationship, `but*` usually `you*` won’t notice `anything` going `wrong. So` relax, `but*` beware.

`The*` two __RelationClass__ objects `define the*` relationship furtherly.

`The*` member __Class__ of __RelationClass__ `is very important` to set, and it `defines` which class makes part of `the*` relationship. `Define the*` __Class__ in both __RelationClasses__ of `the*` __Relationship__ and `you’ve*` made a relationship between `the*` two classes.

A `very important` member of a __RelationClass__ `is the*` __AbstractNumber__. `This defines` whether a relationship class `is` __1__, __x__ or __n__. `If* you* define the*` __AbstractNumber__ for both of `the*` two relationship classes, `you* can*` for instance make a 1<=>n relationship between `the*` two classes or a x<=>n relationship or whatever. __AbstractNumber__ `is` __1__ by default.

To `define the*` quantity of x, `you*` set __ExactNumber__. For instance, in a 
__Line n<=>2 Point__ relationship, `you* define` for `the*` __Point__ __RelationClass__ that its __AbstractNumber = x__ and its __ExactNumber = 2__.

Two other `important` members of a __RelationClass__ `are` __CreateObjects__ and __EnsureSubObjects__. __CreateObjects__ `is` by default __True__, exceptions `not*` regarded. __CreateObjects__ says that `when*` a new position `is` created within `the*` related list, an object `is` instantly *created* in that position (See *Objects and Object Positions*). In `many` cases `you*` want that to happen. Sometimes `you*` don’t want objects `to be` created, `because* you’d*` want to assign an object to that position yourself. `Then* you*` set __CreateObjects__ to __False__. Furtherly, __EnsureObjects__ `will` see to it that `you* can’t*` assign __Nothing__ to `the*` object position. It `is` __True__ by default, `but* can*` be set to __False__. For more information see `the*` sections *Create Objects* and *Ensure Objects*.

And `then*` there’s another member of __RelationClass__ that `is important` to mention. And that `is` __ListType__. __ListType__ `is usually` set to __NormalListType__, `but* can*` also be set to __ReferenceCountedListType__, __RegistrationListType__, __SharedListType__ or __SelectionListType__. `The*` list `then*` gets `very special` behavior. For more information see `the*` *Specialized Lists* section. Although `I` don’t explain them here `very` thoroughly, __ListType__ does `mean` a `lot` for `the*` general structure of `the*` system.

`You* can*` see that inside a __RelationClass__ object, `much` more `is defined` than `just the*` __Class__. That`’s` why __RelationClass__ `is` a separate class. `Many` times `I will` speak of a relationship class, and `you*` shouldn’t confuse it with `just` a class `then*, because*` it `will` be defining a class as it `is` in `the*` context of a relationship.

`The*` elements as `I’ve` described them in `this` section, form `the*` following structure of  __Classes__, __Attributes__ and __Relationships__.

```
Structure
|
|-- Classes
|    |
|    |-- Class ()
|        |
|        |-- Attributes
|        |    |
|        |    |-- Attribute ()
|        |
|        |-- RelatedClasses
|            |
|            |-- RelationClass ()
|
|-- Relationships
   |
   |-- Relationship ()
        |
        |-- Bidirectional
        |
        |-- RelationClassA and RelationClassB
            |
            |-- Class
            |-- AbstractNumber
            |-- ExactNumber
            |-- CreateObjects
            |-- EnsureObjects
            |-- ListType
```

`Every` other concept of J Data `is` hung up on `this` main structure of __Classes__, __Attributes__ and __Relationships__.

For instace, `the*` physical appearance in the user interface of a list `defined` in a __RelationClass__ with __AbstractNumber = n__, `is defined` inside that __RelationClass__ object. `The*` whole appearance of a __List Control__ `is defined` inside a __RelationClass__. That `is` an example of how `the*` user interface `is defined` right inside `the*` general structure above. `The*` same way *`all`* of `the*` application’s features `are defined` in `the*` context of `the*` relational structure of __Classes__, __Attributes__ and __Relationships__.