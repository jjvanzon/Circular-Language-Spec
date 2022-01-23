Construct Drafts | From Spec | Relationships | Line Merge & Symbol Merge
========================================================================

`[ Deprecated documentation ]`

__Contents__

- [Bidirectional Relationships](#bidirectional-relationships)
    - [Counterpart out of Sight](#counterpart-out-of-sight)
    - [`No` Reuse of Merged Imaginary References](#no-reuse-of-merged-imaginary-references)
    - [Example](#example)
- [Relations Between Objects](#relations-between-objects)
    - [Diagram Notation](#diagram-notation)
    - [Counterpart out of Sight](#counterpart-out-of-sight-1)
    - [`No` Reuse of Merged Imaginary References](#no-reuse-of-merged-imaginary-references-1)

## Bidirectional Relationships

The notation suggested here was moved away from the Circular Language Spec in favor of another notation.

Starting with:

![](images/1.%20Relationships%20Construct%20Drafts.001.png)

A suggested notation might be for the two class lines to merge together to form `the` picture below:

![](images/1.%20Relationships%20Construct%20Drafts.002.png)

This, however, might be a quite ambiguous notation. It might suggest that the two symbols joined by the line might have the same class. But that might not be what is intended. The circle inside __Class A__ might have __Class B__ and the circle inside __Class B__ might have __Class A__.

A solution to this ambiguity may be proposed.

Fortunately, `the*` notation `can*` be disambiguated using `the* rules` of automatic containment. Automatic containment `is` explained in `the*` article *Automatic Containment*. Before explaining how automatic containment leads to `the*` eventual notation, here `is the*` disambiguated notation of a relationship between two classes:

![](images/1.%20Relationships%20Construct%20Drafts.003.png)

`The*` notation `is` accomplished by first taking `the*` original picture with one class referring to another and `the*` other referring back to `the*` first class:

![](images/1.%20Relationships%20Construct%20Drafts.001.png)

`Then*`, an imaginary reference to `each` class `is` added to `the*` diagram:

![](images/1.%20Relationships%20Construct%20Drafts.004.png)

Next, `the*` class lines `are` merged, `but*` also `the*` class symbols `are` merged:

![](images/1.%20Relationships%20Construct%20Drafts.003.png)

`The*` notation `might*` still be ambiguous, `if*` it weren’t for `the*` double dashed line of `the*` merged class symbols. `So` a double dashed circle symbolizes a relationship between classes.

Examples with different multiplicities:

![](images/1.%20Relationships%20Construct%20Drafts.005.png)

![](images/1.%20Relationships%20Construct%20Drafts.006.png)

![](images/1.%20Relationships%20Construct%20Drafts.007.png)

A symbol merge in a relationship that has nonagons in it also results in a double dashed circle, `because* the*` imaginary reference to `the*` classes, that `are` put on a higher level, `are` represented by circles, `not*` a nonagons.

There is an idea where one related list might contain items from multiple classes. __Class A__ might have a __n => 1__ relationship to items of __Class B__ and __Class C__, which the picture below aims to express:

![](images/1.%20Relationships%20Construct%20Drafts.008.png)

### Counterpart out of Sight

If the counterpart of a relationship might be out of sight, a line might point out of the diagram. A catch there might be that you might not see whether the relationship counterpart might have multiplicity of __1__ or __n__. A possible solution for this, might be to express multiplicity at the end of that line that might point out of the diagram.

This might look as follows with the double dashed border notation:

![](images/1.%20Relationships%20Construct%20Drafts.009.png)

![](images/1.%20Relationships%20Construct%20Drafts.010.png)

But then again, if something is out of sight, it might just be out of sight and you cannot see things out of sight. Perhaps there is no problem here.


### `No` Reuse of Merged Imaginary References

`If*` two imaginary references `have` merged, `to become` a relationship symbol, `then*` other references to `the*` same classes won’t connect to an imaginary reference that has merged `to become` a relationship symbol. Relationships create their own imaginary references, that aren’t reused. `This is` displayed in `the*` article *Relationships Between Objects in a Diagram*, `but*` may also apply to `the*` notation of relationships between classes.

![](images/1.%20Relationships%20Construct%20Drafts.016.png)

### Example

![](images/1.%20Relationships%20Construct%20Drafts.017.png)

## Relations Between Objects

### Diagram Notation

`The*` relationship symbol `is` a double circle. `The*` reason behind `this` notation, `was already` explained in `the*` article *Relationships in a Diagram*. `The*` notation `is` accomplished by first taking `the*` original picture with one class refering to another and `the*` other refering back to `the*` first class:

![](images/1.%20Relationships%20Construct%20Drafts.018.png)

`Then*`, an imaginary reference to `each` class `is` added to `the*` diagram

![](images/1.%20Relationships%20Construct%20Drafts.019.png)

Next, `the*` class lines `are` merged, `but*` also `the*` class symbols `are` merged:

![](images/1.%20Relationships%20Construct%20Drafts.020.png)

`The*` notation `might*` still be ambiguous, `if*` it weren’t for `the*` double line of `the*` merged object symbols. `So` a double circle symbolizes a relationship between objects.

For relationships between classes `the*` relationship symbol `is` a double *dashed* circle. For relationships between objects, `the*` relationship symbol `is` a double circle drawn with *solid* lines.

### Counterpart out of Sight

`When* the*` counterpart of `the*` relationship `is` out of sight, a line `should` point out of `the*` diagram. A catch there `is`, that `you* can’t` see `if* the*` relationship counterpart `is` part of a multiplicity of __n__ or `not*`. Therefore, `the*` multiplicity `is` expressed at `the*` end of `the` line pointing out of `the*` diagram as follows:

![](images/1.%20Relationships%20Construct%20Drafts.021.png)

### `No` Reuse of Merged Imaginary References

`If*` two imaginary references `have` merged, to become a relationship symbol, `then*` other references to `the*` same objects won’t connect to an imaginary reference that has merged to become a relationship symbol. Relationships create their own imaginary references, that aren’t reused.

Here `is` a relationship between two objects:

![](images/1.%20Relationships%20Construct%20Drafts.020.png)

`The*` two objects refer to each other. `This` originally consisted of two distinct references:

![](images/1.%20Relationships%20Construct%20Drafts.018.png)

Imaginary references `were` put on one level higher:

![](images/1.%20Relationships%20Construct%20Drafts.019.png)

`If*` other references to `the*` same objects `were` also displayed in `the*` diagram, `then*` they `might*` connect to `the*` same imaginary references, put on a higher level:

![](images/1.%20Relationships%20Construct%20Drafts.022.png)

`When* you*` merge `the*` imaginary references to display that two references `are` part of a single relationship, `you* might not*` connect `all` references to `the*` merged imaginary reference:

![](images/1.%20Relationships%20Construct%20Drafts.023.png)

`You* might` keep separate imaginary references for `the*` other unidirectional relationships to `the*` objects:

![](images/1.%20Relationships%20Construct%20Drafts.016.png)
