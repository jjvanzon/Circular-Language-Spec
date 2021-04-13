Encircle Language Construct Drafts | Implementations
====================================================

Achievability | Everything Only (Lack Of Choice = Guarantees)
-------------------------------------------------------------

`[ Out of Scope ]`

In experiment 0.9, almost any code that could be generated was optional. This basically created a lot of different possible situations in which everything needed to still function correctly.

The principle of Everything Only may be the opposite: instead of making everything optional, everything is included without a choice. This limits all the possible situations, which makes things easier to test, there are no surprises and it is easy to give guarantees to a system’s functioning.

But this principle dates out of a time when Encircle did not have extensible aspects yet.

Optionality mostly caused problems in experiment 0.9 because aspects were required by other aspects and the dependency of aspects was not worked out well, and sometimes something used by one aspect, was missing in the generated code, because a dependency aspect was turned off, because it was optional. When code was generated, the code was not compilable, because there were references to things that were turned off.

Experiment 3.0 might only give the guarantee of ‘everything only’ to the *base code*. Nothing is optional in the *base code*. But every aspect *is* optional, yet the aspects have a dependency structure. When you turn on a aspect, that requires another aspect, the dependency aspect might implicitly turned on as well. Implicitly turned on aspects could be turned off again as soon as they are not required anymore.

When you turn the aspects into separate modules, that have a dependency, optionality of aspects becomes more manageable. Everything Only only counts for the code base now. But it is still a defendable concept that can prove its use.

-----

In future experiment 3.0, the aim might be that the system might be extensible with aspects, a lot more aspects might be created than in previous versions. In experiment 0.9 all once programmed aspects were there, all of them could be turned on or off independently, but none could easily be added.

An old argument for Everything Only in experiment 0.9:

- Why might I not want to have everything in it? Wouldn't I miss something at some unsuspected point, where I'd go: gee, did I optimize that one out?

In future experiment 3.0 it might become easier to turn on extra aspects later, so it might not be a valid argument anymore, that you might miss something at some unsuspected point. In experiment 0.9 the aspects could not easily be turned on later, because they were embedded in the code generator.

In former experiments of Encircle, the principle of Everything Only might have caused performance problems, because all aspects might then be turned on at once, but in future experiment 3.0 any aspect might *be* optional, so this performance problem might not apply anymore.

### Loose Ideas

Bepaalde dingen niet toestaan in Creator.  
Bijvoorbeeld: een object referentie komt altijd tot stand door een relatie. Je moet vrij strikt conformeren aan een basis van werken met relaties. Het werken met deze relaties moet uiteindelijk werkbaar zijn voor leken, zodat het een nieuwe benadering van computers is, die met een beetje moeite grijpbaar is voor iedereen. Mensen die nu voor het eerst een computer gebruiken, moeten ook vanalles leren. Creator relaties moet ook te leren zijn. Het is weliswaar een hele andere benadering, maar voor nieuwkomers, is de huidige manier van werken met computers ook een heel aparte benadering.

Bij heldere relationele benadering van computers komen gebruikers, programmeurs en de eigenlijk werking van computers heel dicht bij elkaar te liggen.

Je kunt denk ik niet voorkomen, dat een hele hoop mensen, toch een hele hoop ellende gaan proberen en uitvinden. Die gaan dan experimentele dingen lopen doen, die helemaal niet sporen. Dingen die gewoon slechte relationeel ontwerp zijn.
