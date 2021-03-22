Circle Language | Construct Drafts
==================================

Achievability
-------------

`[ Out of Scope ]`

This sub-folder represents a category of principles that might be called the *achievability principles*. The achievability principles would be a set of principles, that describe how a running new computer language might be developed in a limited amount of time with a limited amount of people: what techniques might be employed to make that possible. It might cover how the development of modules of a *Software System* other than the programming language might be made more achievable like that. Not all the content might be finished yet, but the *Achievability* folder may contain the following articles:

- ### [Achievability Brainstorm](achievability-brainstorm.md)

    - Brainstorm about dreams of how software programming might be more easily achieved.

- ### [Achievability Loose Ideas](achievability-loose-ideas.md)

    - For now only contains loose ideas.

- ### [Everything Only (Lack Of Choice = Guarantees)](everything-only-or-lack-of-choice-is-guarantees.md)

    - In an experimental version 0.9 for a computer language many parts of the code, that were generated, were optional. This basically created many different possible situations in which things preferably would still function correctly. The principle of *Everything Only* would sort of aim for the opposite: instead of making everything optional, everything might be included without much choice. This may limit the possible situations, which might make it more doable to test, there might be not as many surprises and more doable to feel a degree of guarantee about a system’s functioning. This principle might not be applied to every situation, but it might be applied selectively to try and make things more achievable: perhaps not making too many things optional. That might help minimize the amount of possible situations.

    - This article covers the why and where it may have went 'wrong' before. Where the lesson was taken from. An attempt to explained why this principle was come up with. This explaining why, may make it a bit harder to read, because it may not be enough a raw description of the concept. It may give an impression of: “Why do I need to know all this? Why would I need all this background information?”.

- ### [Generic, No Generators](generic-no-generators.md)

    - Tries to describe how the concept of code generators might be abandoned and replaced by a different way to do it. The development of code generators seemed more difficult, than an alternative method. A transition from code generators to generic modules, that adapt themselves to a structure definition, that you assign to it. It may make it easier to develop this computer programming language, than a code generator approach. The idea had been applied in experimental software: experimental version 2.0 of a computer language compared to experimental version 0.9 of a computer language.

- ### [Programming Language Programmed Within Itself](programming-language-programmed-within-itself.md)

    - A dream would be for a computer language to make it easier to program larger systems of software. But making a computer language itself seems difficult. So a way to make it easier, might be to program most of a computer language within the new computer language itself. This article tries to explain how this might be possible. The description might be lengthy and hard to understand perhaps. It may cover many technical details, instead of an easier presentation of the concept.

    - The concept *Computer Language Programmed Within Itself* was tried with experimental version 2.0 of a computer language. In that version the base of the language was reprogrammed using the new language itself. The idea was that all the other software might be based on that, which from then on, would be programmed only using the new computer language itself.

- ### [Small Code Base](small-base-code.md)

    - This principle would be about trying to make the base of the code for a new computer language as small as possible and have the rest of the computer language programmed within a computer language itself. This principle was tried in version 2.0 of a new computer language: the code base was reprogrammed within itself.

- ### C++ / C\#

    - This principle is the idea, that the base of the code for a computer language might initially be programmed using C++ or C#. It is called an achievability principle, because originally the computer language was written in VB6 and this may have created a performance barrier. A version 2.0 for a computer language was based on C++. A version 3 of a computer language might be based on C# and .NET.