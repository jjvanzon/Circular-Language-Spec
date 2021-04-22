Circular Language Construct Drafts | From Spec
==============================================

Relationships Construct Drafts
------------------------------

`[ Preliminary documentation ]`

__Contents__

- [Relationships Between Classes](#relationships-between-classes)
- [Counterpart out of Sight](#counterpart-out-of-sight)
- [Loose Ideas](#loose-ideas)

### Relationships Between Classes

A class-relationship structure might be a program's bone structure.

### Counterpart out of Sight

`When* the*` counterpart of `the*` relationship `is` out of sight, a line `should` point out of `the*` diagram. A catch there `is`, that `you* can’t` see `if* the*` relationship counterpart `is` part of a multiplicity of __n__ or `not*`. Therefore, `the*` multiplicity `is` expressed at `the*` end of `the` line pointing out of `the*` diagram as follows:

![](images/1.%20Relationships%20Construct%20Drafts.011.png)

![](images/1.%20Relationships%20Construct%20Drafts.012.png)

That proposal might be a problem, because it seems to clash with a proposed notation for optional. And also it seems to not reflect the containment structure: there might be a container in between the half shape and the other parts of the diagram. Seems unfortunate.

In another proposal:

![](images/1.%20Relationships%20Construct%20Drafts.013.png)

![](images/1.%20Relationships%20Construct%20Drafts.014.png)

It may be going a bit far. It seems to draw out part of the diagram, that is out of sight. But then it might actually have a container in between, that is not drawn.

The argument "What is out of sight, is out of sight." might be good enough to not solve this 'problem'. A proposal might be that might not be a real problem.

Here a variation that might also be dubious:

![](images/1.%20Relationships%20Construct%20Drafts.015.png)

In that image both relationship counterparts' class lines are connected to the same half shape. It might go a bit far in suggesting something it's not.

### Loose Ideas

Stereotyping relationships

Perhaps another typing can be assigned to a relation, instead of containment. For instance: *ownership* or *usage*. Perhaps a few standard ones, and it may be possible to define `your` own typing by specifying a String.

JJ

-----

Relationships,  
2008-11

`The*` roles that symbols get `when*` connecting them with lines.

JJ