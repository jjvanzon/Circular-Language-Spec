Encircle Language | Broader View
================================

Loose Ideas
-----------

`[ Preliminary documentation ]`

*The texts below are loose ideas, yet to be turned into more polished documentation.*

This documentation section covers all the coding aspects and principles of Encircle.

Some of the principles have to be implemented inside the code base. Most of the aspects can be implemented merely as an *aspect* construct, using Encircle itself.

The following principles need to be part of the code base:

- Identifiers
- Omitted Identifier
- Objects
- Sub-Objects
- Object Reference
- Related Objects
- Values
- Multiplicity
- Value Assignment
- Object Assignment

It is important to understand, that there are *coding principles*, and there are *coding aspects*. 

Coding *principles* need to be part of the code base.  
Coding *aspects* do not.

An __Aspect__ is a construct, that can be programmed in Encircle and a *principle* is something the code base can not do without. A lot of principles can be implemented as an aspect, but only *after* you have added it to the code base.

Examples of coding aspects are: classes, attributes, parameters and inheritance. So none of those need to be present in the code base. They can all be programmed using Encircle itself.

Many of the coding aspects are just as elementary to computer programming as coding principles. Functionally, coding principles and aspects blend together. That is why coding principles and coding aspects do not have separate documentation sections.

On top of that: when developing the code base, you will determine how much can be banned out of the code base, and only programmed within Encircle itself. As the aspects are described here functionally, it is not as important to determine which ones have to be part of the code base and which ones can be left out.

### Loose Ideas

*The texts below are loose ideas, yet to be turned into good documentation.*

Process Control,  
2009-05-03

Process Control like main processes and sub processes and the logging of user actions and stopping other processes from running if one process is in error state and a process monitor and notifications when something goes wrong...   
This should be part of Coding Aspects. I am not sure how yet.

JJ

-----

Symbol Roles,  
2004

- base
- base type
- base object
- base interface

JJ


### Compared to Other Programming Languages

- Looking at the 'Subtext' programming language.
- "Subtext" implies that this is always possible, but of course underlying procedures could be
- "Subtext" code when it grows is really bound to become unoverviewable.
- His assumption that humans are not good at abstract thinking is just not true in my view. Humans do nothing else.
- If he might give his functions better identifiers, it might be better off.

-----

J Code

Analyze the features of F# and find a place for it in my system.  
http://pro.tweakers.net/nieuws/49986/microsoft-stopt-functionele-taal-f-in-visual-studio.html

JJ

-----

Caché bestrijkt vele gebieden al, waar Code een oplossing voor biedt. Het relationeel en object georiënteerd unify'en, dan zit daar eigenlijk al bijna compleet in.

Afgeleide containment relaties niet, diagrammen niet en applicatie feature generatie niet, en aspecten niet (ik zal naast standaard aspecten van JJ, zorgen dan je custom aspecten kunt introduceren.) extended inheritance niet, kiezen tussen geheugen en schrijf niet, speciale security niet.

Dat soort aspecten niet, maar het hele idee relationeel en object georiënteerd gelijk trekken wel. Behalve echt 1 taal maken van OO en SQL

Relaties ingaan in SQL statements in Cache, is precies de manier waarop ik het van plan was. But I don't think it takes relations and classes as the base of the system. It's either specify tables with foreign keys, or declare objects with sub objects in them. I don't know if the two counterparts of a relation are synchronized either.

Cache integreert wel al met bestaande grote standaarden, zoals ODBC, XML, SOAP. And it provides in importing data into it from other database systems.

Wat nog steeds wel origineel is, ook ten opzichte van Cache, is de visie om OO ondergeschikt te maken aan het relationele model. In OO - Relational oplossingen wordt in object-relational mapping, OO bovenop relationeel geplaatst. Caché zet de OO benadering ook bovenaan, en de relationele benadering als handig alternatief.

### OO Versus Relational Database

Ik zie ook beweringen op het internet, dat een OO data benadering geavanceerder is dan relationeel. Maar er zijn voordelen aan relationeel, waar dan niet meer over gesproken wordt.

Ik denk dat het ook een zaak is twee-kampen. Ik zie in beide methodes het licht.

Anderen vinden OO bijvoorbeeld het beste, en voegen hier relationeel aan toe, en andere mensen vinden relationeel het handigste, en voegen hier OO aan toe. Don’t want to consider

Je moet dus echt aansporen dingen in de objectstructuur te embedded en daar met recursie op te lossen, in plaats van EEN moeilijke procedure erlangs schrijven

### Other People’s Software

Windows doesn't allow shortcuts with the same name in a folder even when the short cuts have different target types.

-----

Oracle 8.0i

-----

Zoek op in HTML for Dummies hoe je naar een 'bookmark' springt.

-----

Ideas,

Ik heb het vermoeden, dat als we alle gegevensverwerkingen via webservices zouden laten lopen, dat de boel niet vooruit te branden is.

JJ

### Other Ideas

Computer Language,

Windows Workflow raakvlakken met diagrammen.

JJ

-----

Computer Language,

I saw something call specifying the structure of a program, rather than what happens step-by-step is called declarative programming, as opposed to imperative programming.

JJ

-----

Computer Language,

I don't have ... for user program flow, for instance when using
multiple windows seemingly arbitrarily, but not...  
And also not for workflow.  
I don't know yet how workflow fits into the system.  
Probably as internet threads.

JJ

-----

Computer Language,

Ik wil gewoon dat workflow en methods die elkaar aanroepen gewoon hetzelfde aspect zijn. Method stappen kunnen parallel lopen en seriele punten hebben en vertragingen en gezette tijden hebben.

JJ

-----

Computer Language,

Dead links.

JJ

-----

Collection,

In Collection kan je ook vanalles van verschillende modules van verschillende sites combineren, tot 1 home-page. Je hoeft dus niet te kiezen tussen sites, waar je een home-page op kunt maken. Je kunt zelf alles dat ze aanbieden met elkaar combineren, zonder al te veel heisa. Ook een leuk argument om het Collection te hoemen.

JJ

-----

Computer Language,

Important statement to use: objects first, procedures second.

JJ

-----

Computer Language,

People aren't realizing that a computer program IS a domain-specific language.

JJ

-----

Computer Language,

Met diagrams in computer language wordt de systematiek echt zichtbaar.
Op het moment programmeren we eigenlijk allemaal blind en op de tast.

JJ

-----

Computer Language,

The idea of object oriented is: objects first, procedures second.

JJ

-----

Computer Language,  
2008-06-03

The diagram expression also makes it possible to use hand signs in the air to draw out relations between objects, in a technical story `you` try to explain.

JJ 

-----

Computer Language,

De kracht van programmeertalen nu, zit hem niet in de taal zelf, maar in het framework.

What makes programming languages today powerful, is not the language itself, but the framework.

JJ

-----

Computer Language,  
2008-08-15

Other programming languages and diagram expressions:
http://www.obsolete.com/dug/sorcery/oop.htm

JJ

-----

Computer Language,

Other programming languages and diagram expressions:  
Leuke zoekterm om op te googlen:  
"my own programming language"

JJ

-----

Computer Language,  
2008-08-15

Other programming languages and diagram expressions:  
http://jolt-lang.org/

JJ

-----

Single paradigm for all digital objects,

See the physical disk as an object.  
See the IO on it,  
and what source does IO on it.  
Be able to see which reference has the most activity.  
Be able to navigate through the system,  
so that you can trace the source of the activity.

That way you not only fly through the internet, and the applications, but you can also navigate through the internal workings of your computer.

I guess I do want to see magnitude of activity in the diagrams.

JJ

-----

Computer Language,  
2008-09-02

Some people seem to like isolated memory space.  
But this is just for some protection that it gives.  
Memory leaks only live inside a process.  
When it is stopped, then the memory leaks are released.  
When something crashes, it is just that process, that crashes.  
The rest keeps running.

But in my own system, the whole internet is really just one process.  
So what needs to be done, is analyse the advantages people think they can only get from isolated processes, (advantages, that are probably only precautions for problems) and see what solutions for those problems will be implemented in my own system.

JJ

-----

Computer Language,  
2008-09-02

Google using a separate process for each tab in its Google Chrome browser, is just a practical solution, relatively easy to implement.
That's why process isolation offers a solution to this problem. It is not, that with more effort, a not-yet existing solution to this problem, that does not use the isolation of processes, would not offer a better or equally practical solution, would products like that be finished today and free to use.

JJ

-----

Computer Language,

Ik ben me er wel van bewust, dat een nieuwe programmeertaal, of nieuwe manier van besturen van je computer, een bijdrage is, niet een vervanging van alle andere software. Daar zijn software giganten
veel te innovatief voor.

JJ

-----

Computer Language,  
2008-08-23

The way it is right now, the system can not change the system as much as a user can change the system.

JJ

-----

Software System

- Crap first
- Objects second
- Methods third
 
Not:

- Methods first
- Object second
- Crap third

JJ