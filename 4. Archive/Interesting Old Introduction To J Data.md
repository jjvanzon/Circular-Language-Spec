# ***Interesting Old Introduction To J Data***
**-**

*Author: Jan-Joost van Zon*

*Date: 2005-08-31*

*This story dates from a time when I looked at it from a data perspective, rather than an object perspective. I kept the name J Data in the story, instead of replacing it with Creator, so that it’s clear the story is about an older perspective.*

J Data may be *the* basic software module that makes all computing *so* easy.

J Data is about lists and trees and data structures. As J Core (the system kernel) provides spaces in memory or on disk, J Data puts them to work. J Data is the most extensively used module of Sigma. The quality of J Data is so great, that it is totally relied on by all other Sigma modules. Even the Core can trust J Data blindly. J Core only draws out the general purpose of the data it wants and J Data ensures that the most optimal data structures are used. All modules use J Data as such. This quality of J Data makes J Data one of the most important modules of Sigma. It simplifies the other modules tremendously, while performance of the data structures is optimal.

J Data accomplishes this with a general split up of the module into three parts:

- J Lists and Trees
- J Data Structure
- J Data Generator

J Lists and Trees contains classes for many basic data structures. The two basic forms data structure are the *list* and the *tree*. There are many variations of lists and trees. Each variation has its own pros and cons. One variation uses up little space, while another variation may be best for searching though a list.

The classes of J Lists and Trees, each representing a list or tree, share a common interface. This interface is a sum up of any pro or con a list or tree can have. Each list or tree returns for each of these qualities how good it is at it.

With J Data Structure you can describe a *relational structure* (which is not the same as in relational databases). This structure defines the *purpose* of the data, rather than how it’s *stored*. You can also call it the the data logic or logical data, distinguishing it from physical data: how it’s stored. I also call it the object structure or relational object structure. Each element in the object structure may be a list or tree. Object structure also defines relations between these elements.

All applications can mostly be deduced to a relational object structure. Therefore, most of the application logic can be delegeted to J Data.

J Data Generator produces a software module with an object structure that matches the data logic. From the data logic J Data Generator can read what qualities an element needs. Because each basic data structure in J Lists and Trees returns its qualities, a match is easily made. Needed qualities can also partly be derived from the actual data put into the J Data Structure.

So using J Data is quite easy: you define the *logical* data elements and how they are related. You are returned a module that has the data logic as an interface. All you really need to know is that the better you refine the data logic, the faster it operates.

Even though you can use J Data Structure for all your data, it is still possible to directly use the basic data structures provided by J Lists and Trees.
##### **Summary**
- Basic Data structures: lists and trees
- Common interface for lists
- Common interface for trees
- Common interface returns members for any olf the lists’ features and a member returning the quality of this feature of the particular list.
- Data Structure: a relational structure called the data logic or object structure. Each element is either a list or tree layer.
- The data logic determines each list or tree’s required qualities. Since data structures return what qualities they have, the pick is easily made.
- J Data Generator creates an object structure that looks exactly like the data logic.
- Internally the lists and trees are used.
- All lists and trees look the same to J Data Structure by then. Only when *picking* data structures, J Data Structure was concerned with the qualities of each lists. Now it just uses any list like any old list.

PAGE  2

