Encircle Language Construct Drafts | Implementations
==================================================

Achievability | Everything Only (Lack Of Choice = Guarantees)
-------------------------------------------------------------

`[ Out of Scope ]`

In Computer Language 0.9, almost any code that could be generated was optional. This basically created a lot of different possible situations in which everything needed to still function correctly.

The principle of Everything Only is the opposite: instead of making everything optional, everything is included without a choice. This limits all the possible situations, which makes things easier to test, there are no surprises and it is easy to give guarantees to a system’s functioning.

But this principle dates out of a time when Computer Language did not have extensible concepts yet.

Optionality mostly caused problems in Computer Language 0.9 because concepts were required by other concepts and the dependency of concepts was not worked out well, and sometimes something used by one concept, was missing in the generated code, because a dependency concept was turned off, because it was optional. When code was generated, the code was not compilable, because there were references to things that were turned off.

For Computer Language 3.0 you can only give the guarantee of ‘everything only’ to the *code base*. Nothing is optional in the *code base*. But every concept *is* optional, yet the concepts have a dependency structure. When you turn on a concept, that requires another concept, the dependency concept is implicitly turned on as well. Implicitly turned on concepts could be turned off again as soon as they are not required anymore.

When you turn the concepts into separate modules, that have a dependency, optionality of concepts becomes more manageable. Everything Only only counts for the code base now. But it is still a defendable concept that can prove its use.

-----

In Computer Language 3.0, in which the system is extensible with concepts, a lot more concepts are created than in previous versions. In Computer Language 0.9 *all* concepts were there, all of them could be turned on or off independently,  but none could easily be added.

An old argument for Everything Only in Computer Language 0.9:

- Why would I not want to have everything in it? Wouldn't I miss something at some unsuspected point, where I'd go: gee, did I optimize that one out?

In Computer Language 3.0 it will be easy to turn on extra concepts later, so it is not a valid argument anymore, that you might miss something at some unsuspected point. In Computer Language 0.9 the concepts could not easily be turned on later, because they were embedded in the code generator.

In the first version of Computer Language, the principle of Everything Only might have caused performance problems, because all concepts would then be turned on at once, but in Computer Language 3.0 any *concept will __be__* optional, so this performance problem does not apply anymore.

### Loose Ideas

Bepaalde dingen niet toestaan in Creator.  
Bijvoorbeeld: een object referentie komt altijd tot stand door een relatie. Je moet vrij strikt conformeren aan een basis van werken met relaties. Het werken met deze relaties moet uiteindelijk werkbaar zijn voor leken, zodat het een nieuwe benadering van computers is, die met een beetje moeite grijpbaar is voor iedereen. Mensen die nu voor het eerst een computer gebruiken, moeten ook vanalles leren. Creator relaties moet ook te leren zijn. Het is weliswaar een hele andere benadering, maar voor nieuwkomers, is de huidige manier van werken met computers ook een heel aparte benadering.

Bij heldere relationele benadering van computers komen gebruikers, programmeurs en de eigenlijk werking van computers heel dicht bij elkaar te liggen.

Je kunt denk ik niet voorkomen, dat een hele hoop mensen, toch een hele hoop ellende gaan proberen en uitvinden. Die gaan dan experimentele dingen lopen doen, die helemaal niet sporen. Dingen die gewoon slechte relationeel ontwerp zijn.
