Encircle Language | Construct Drafts
====================================

Aspects
--------

`[ Preliminary documentation ]`

__Contents__

- [Loose Ideas](#loose-ideas)
    - [Aspects](#aspects-1)
    - [Loose Ideas](#loose-ideas-1)
    - [Aspects & Principles](#aspects--principles)
    - [More Ideas](#more-ideas)

### Loose Ideas

*This is unfinished documentation of possibly lower quality. It only has unfinished descriptions and loose ideas.*

#### Aspects

The *aspect* construct might become important in Encircle, only it might not be implemented yet in future experiment 3.0. However, experiment 3.0 might be implemented in a way that the aspects construct might be added to it later. Aspects might be useful enough to do this. In order to feel comfortable about this, I might like to know more about aspects, so I might work out a preliminary, brainstorm-style design here.

For this I might look into the experiment 0.9 code, in which I might see what aspects might need to be capable of and I might list out what you have to be able to define inside an aspect and then maybe I might get a picture of how this should look in a diagram.

-----

A lot of times aspects might tap into other methods or other aspects’ methods and pre- or post-extend the method. And the pre- or post-extension might be in a specific point in the code of the method into which code is injected.  
In experiment 0.9 there is a distinction between injecting it inside the Set’s If Value has changed or outside the Set’s If Value has actually changed. I am not sure the distinction is needed in the new version but it might have to be a feature.  
The idea about injecting code a specific point was that this point of injection is determined by dependency on other aspects. Some parts of other aspects might either be finished or not started yet when the code of the dependent aspect is run. So pinpointing this position is done by pinpointing the dependency on another aspect and whether something has to be done before or after a part of another aspect is finished. So it is about Before or After an element of another aspect or Before or After a number of elements of a number of other aspects. That is how the position of code injection might be defined.  
The idea is that with aspects everything is possible that is possible with code generation, only in a more structured way.  
Aspect dependency also means that another aspect might be implemented for the dependent aspect to be active. And sometimes even certain (optional) elements of an aspect might be active in order to make a dependent aspect work. This may also have to be definable.    
Sometimes aspects just add extra methods to an object.  
Perhaps the extra method might be part of the object itself. Perhaps it might become an extra interface of the object, perhaps it might become part of the object’s system interface and visible like an extra system aspect. I dunno, that is not the most important.

The idea is that you can apply aspects to an existing system. Might the existing system decide to use the aspect or might the user of the system choose to apply an aspect? The problem with the last thing is that this might harm the interface of the original object. The solution might be to use inheritance to keep the original interface in tact and only specialize the object adding more aspects. This might be something for system inheritance, which might have a functional definition which is still open to discussion.

So an aspect can add members to an existing object, to an existing object’s system interface and add pre- and post- extensions to methods of an object, or methods added by other aspects.

Wait, if each bit of code injected is its own method, then the code of a dependent aspect might not need to be put in a specific order compared to their code injected by the other aspect, it may just need to become the pre- or post-extension of the method of the other aspect.

You only get a problem when pre- or post- dependency exists to multiple aspects.  
So there might be thought of a way to make the same pre- or post-extension to multiple methods.

In Aspects, which replace code generation, you have to accept that members are freely added, that is what code generation is, but if you want to keep interfaces stable you can easily do this by means of separation of interfaces, this is what separation of interfaces is meant to solve.

But in its basic form, aspects just use the specialization techniques defined in the functional design of inheritance.  
When you take pre-extension as an example, something is tricky though. The extensions and member additions apply not to a specific object or class, but to a selection of objects. So you need a proxy object inside the aspect definition, that stands for any object the extension might be applied to. And there should be a condition that tells which objects might get the extension. So it is really starting to look like aspect oriented programming: you have code, you have join points and an expression defining which objects it applies to. The join points, however are defined through specialization techniques defined in the inheritance documentation, and the code is just code, like in aspect oriented programming and the objects it applies to is a proxy object inside the aspect definition, which an expression selecting the proper objects.

I might look over a few more aspects in experiment 0.9 later, but for now I might go on with the brainstorm.

The definition of an aspect might be an as concrete as possible depiction. So the definition of an aspect is basically code, that specializes a proxy object, which stands for objects that adhere to certain criteria, so that the right objects are selected. Furthermore, you can add dependency aspects, that make sure the dependent aspect is not applied when the dependency aspect is not supported, and also make you able to apply specialization techniques to code that is added by the dependency aspect. If a piece of code is added by the aspect, then this piece of code is a separate method, that is tied to a specific pre or post of a specific other method, which can also yet another pre or post. This probably accounts for the complexity needed to implement aspects.

Then there is another side to it: how might the resultant code look? Because aspects extend other objects. Either the objects are augmented with code, or in order to keep the interface of the original object stable, a derived object is created and the aspects are applies to the derived object.

The specialization techniques in the functional design of Inheritance and the system events in the functional design of Events really suffice here.

It all comes together. Aspects can be separately programmed mostly using the existing constructs + aspect dependency + proxy objects + object selection expressions. You just have to make the data that defines the aspect an as direct depiction of the aspect as possible. And aspects can be applied to systems in either an interface-stable, or an interface-unstable way. How that last part might look, might need to prove itself in practice. I just do not want to work out the theory. I just want to program it and see how it works instead of just trying to imagine it in my head.

I have an adequate brainstorm here about how things should be and I am confident that nothing might stand in the way of implementing the aspect construct even when I totally ignore it in the first version. The aspect construct might not overthrow the basics of the notation of the language or the basics of the other constructs. Hooray!

P.S.: Aspects can probably also have their own code, that might not really extend other objects, but is called upon by other objects. However that might be implemented, this might not be a problem.

#### Loose Ideas

An aspect not only can extend an item, but can also extend a class definition.  
Preferably keep the extension an aspect imposes under a subobject. Don’t merge the aspect into the rest of the item.

-----

The aspects should be extensible as well, so somebody can program their own aspects. But with the genericity of Creator itself, this option should be open.

-----

De programmeerbaarheid en uitbreidbaarheid van Aspecten moet je eigenlijk ook zo snel mogelijk doorvoeren.

-----

Aspects operate using reflective data. As such they can be applied to any system.

-----

Relational as Carbon-Base,

The class-relation structure of a program can also be called the bone-structure, or the carbon base of the program, to which everything else is attached.

JJ

-----

Aspects,  
2008-06-10

Be able to support a whole module of aspects,  
but able to exclude ones from it as well.

JJ

-----

Aspects,  
2008-06-16

The amount of referrers of a __Number__ *object* may be small, but the amount of referrers of the __Number__ *class* is humongous. The class might even have a __Referrers__ list, when the class is not a created object, because __Referrers__ applies to both symbols and objects.

You might want to turn the __Referrers__ aspect *off* for the __Number__ class and *on* for __Number__ objects. But the problem here is, that a class is a blueprint for an object. An object only supports __Referrers__, because the *class* supports it.

The first solution proposed was to simply not support the __Referrers__ aspect for classes that are widely used. But then __Referrers__ might by *not* be supported for widely used classes. That is against the idea of supporting the __Referrers__ aspect by default.

If you can not stop a class from supporting __Referrers__ without stopping objects from supporting __Referrers__ at the same time, then the __Referrers__ aspect might not be widely used anymore.

Therefore, you are going to have to specify for a symbol or object, that it is a non-practitioner of an aspect. Derivation of objects might take over the specified aspect, but not the non-practitioner aspect.

JJ

-----

The Principle of Aspects,

Je programmeert gewoon een soort template code, met placeholders erin. Een object kan een aspect ondersteunen. Daarmee krijgt een object alle code van de template ingevoegd.
Naast dat de template members toevoegt aan het object zelf, kunnen ook system members worden toegevoegd aan een object references (binnen het object of aan object referenties overal naar het object dat het aspect ondersteunt?) Je kunt ook bestaande system members extenden. Aspects zijn zeg maar de vervangers van code generators. Een soort partial class, met placeholders erin. bij het programmeren, moet je doen of je al een een doelclass gaat programmeren, en daarna extraheer je de generieke code...

JJ

-----

Extension Procedures,  
Aspects / System Interfaces,  
Classes,  
2008-07-21

A class defines the extension procedures, but a class is an object, so an object defines the extension procedures.

JJ

-----

Aspects mostly operate using the reflective data. The fact that aspects they operate using reflective data makes them inherently applicable to any system.

Some things that in other programming languages are considered fundamental coding principles, can be implemented as an aspect in Encircle. Examples of this are: parameters, enums, events, type safety, inheritance. (There are even things called fundamental in other programming languages, that are considered mere plug-in modules in Software System, such as basic math.)

So expressing the system in text code is considered an aspect built on top of the principles already offered by the code base. We might be lost without actually expressing computer code, but eventually the code runs without it, only it can’t be written by a human being if it wasn’t for expression.

-----

Aspects,  
2008-09-20

Do not mix the term aspect and the term aspect. System aspects are more basic than aspects. Aspects in Encircle are like aspects in Aspect Oriented Programming, but I use the term aspect. The term aspect is too much the idea of part-of-something, inseparable. The term aspect is more like something separate, that you can sell separately, that can be applied to anything.

JJ

-----

Aspects,  
2008-10-09

Aspects are about extension.

JJ

#### Aspects & Principles

An aspect is a piece of software that can be applied to *any* existing object or system. A clear characteristic of it is that it operates using the reflective data of an object or system. This makes it possible for features of software that might otherwise be intrinsic to the program, to be plugged into any existing system.

If something is an intrinsic part of a system and it can’t be replaced by a module operating on reflective data only, it is not called an aspect, but a Principle. The word Principle expresses a stronger being bound to it, than the word Aspect. A Principle is an intrinsic aspect that can not be applied through any extensible model. The word Aspect expresses something general, that can be *applied* to anything.

An aspect can only work because of a system’s pure reflectivity. It operates only on this reflectivity. Reflectiveness itself is a *Principle* inside the system, that cannot be worked around.

-----

How to program aspects is not yet clear to me.  
I’m not sure how their systematics need to be stored,  
how they need to be coded in text code,  
and how they should be expressed in diagram code.

-----

But I still need something to make extend the language with aspects that alter access, in the ways required.

#### More Ideas

Aspects / aspects,  
2008-12-24 

Brainstorm about Aspects:  
What I call aspects, is close to what the rest of the world calls aspects.  
Aspects extend existing procedures, and extend existing classes.  
Aspects do that too. Actually, aspects operate on reflective data in order to extend procedures and classes. You can extend a whole system of procedures and objects using aspects. Aspects do that too. What I add to aspects is that aspects can also be separate classes, that link to another class, and use the other class’s reflective data to do something with it, rather. So that is also a way to use an aspect. Anyway, I think I have to call it aspects, because the rest of the world also calls it aspects, and also I have to look at aspect oriented programming as an example for aspects.

It worries me, because of the danger, that before I even finish this programming language, most of it might prove to not even be original anymore. But on the other had, might it have to be original? Can’t it just be a language, that converges all good ideas from the world into a single programming language?

JJ

-----

Aspects can extend system commands with more code, through pre-extension, post-extension and other object extension coding aspects.

-----

Aspects / Aspects,

An application of this new model, that is my software system, might be
for instance, that someone comes up with something that makes any lengthy
process pauzable, items in it skippable, etcetera. Just a handy aspect
for handling lengthy processes.

A handy user could inherit an existing system and extend it with a new
aspect, that was not applicable to the system yet.

I think in order for a system to be adaptable to new aspects, there
might be a set of standards to be upheld. Otherwise a program might be just
one big method, and that can not adopt new aspects.
So you have to impose design rules in order to make a program
adaptable to new aspects.

JJ