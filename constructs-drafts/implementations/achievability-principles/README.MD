Circle Language Broader View | Achievability Principles
=======================================================

Overview
--------

`[ Preliminary documentation ]`

This sub-folder represents a category of principles that might be called the *achievability principles*. The achievability principles are a set of principles, that describe how a new computer language might be developed in a limited amount of time with a limited amount of people: what techniques might be employed to make that possible. It might cover how the development of modules of *Software System* other than the programming language might be made more achievable like that. Not all the content might be finished yet, but the *Achievability* folder may contain the following articles:

- ### [Achievability Loose Ideas](https://github.com/jjvanzon/Circle-Language-Spec/blob/master/constructs-drafts/implementations/achievability-principles/achievability-loose-ideas.md)

    - For now contains only loose ideas about the subject of *Achievability*, yet to be turned into good documentation.

- ### [Generic, No Generators](https://github.com/jjvanzon/Circle-Language-Spec/blob/master/constructs-drafts/implementations/achievability-principles/generic-no-generators.md)

    - Describes how the concept of code generators is abandoned and replaced by a better way to do it. The development of code generators is far more difficult, than an alternative method. The idea has been applied in realized software: version 2.0 of the new computer language compared to version 0.9 of the new computer language makes the transition from code generators to generic modules, that adapt themselves to a structure definition, that you assign to it. It makes it much easier to develop the new computer programming language, than when using the code generator approach.

- ### [Small Code Base](https://github.com/jjvanzon/Circle-Language-Spec/blob/master/constructs-drafts/implementations/achievability-principles/small-base-code.md)

    - This principle is about making the code base of the new computer language as small as possible and have the rest of the computer language programmed within the new computer language itself. This fundamental principle was also proven in version 2.0 of the new computer language: the code base was reprogrammed within itself.

- ### [Programming Language Programmed Within Itself](https://github.com/jjvanzon/Circle-Language-Spec/blob/master/constructs-drafts/implementations/achievability-principles/programming-language-programmed-within-itself.md)

    - The new computer language makes it easy to program large systems of software. But making the new computer language itself is hard. So the only way to easily make the new computer language, is to program the new computer language within the new computer language itself. This article tries to explain how this is possible. The description is lengthy and hard to understand. It covers too many technical details, instead of giving an easy presentation of the concept.

    - The concept *Computer Language Programmed Within Itself* has been proven with version 2.0 of the new computer language. In that version the base of the new language is actually reprogrammed using the new language itself. All other software can be based on that, which from then on is programmed only using the new computer language.

- ### [Everything Only (Lack Of Choice = Guarantees)](https://github.com/jjvanzon/Circle-Language-Spec/blob/master/constructs-drafts/implementations/achievability-principles/everything-only-or-lack-of-choice-is-guarantees.md)

    - In version 0.9 of the new computer language almost any part of the code, that was generated, was optional. This basically created a lot of different possible situations in which everything needed to still function correctly. The principle of *Everything Only* is the opposite: instead of making everything optional, everything is included without a choice. This limits all the possible situations, which makes things easier to test, there are no surprises and it is easy to give guarantees about a system’s functioning. This principle is not applied to every situation, but it can be applied selectively to make things easier to achieve: just do not make too many things optional. That will minimize the amount of possible situations.

    - This article covers the why and where it went wrong before. It is explained why this principle was come up with, but this makes it harder to read, because it is not enough a raw description of the concept. It may give you an impression of: “Why do I need to know all this? Why are you bothering me with all of this background information?”.

- ### C++ / C\#

    - This principle constitutes the mere fact, that the code base of the new computer language will initially be programmed using C++ or C#. It is called an achievability principle, because originally the new computer language was written in VB6 and this created a performance barrier. Version 2.0 of the new computer language is based on C++. Version 3 of the new computer language might be based on C# and .NET.