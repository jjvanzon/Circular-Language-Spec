Object Resolution | Melding
===========================

`[ Preliminary documentation ]`

[back](./)

Melding objects means that for instance a relation class or a progressed object have the same item object name, and meld together to a single property command, in which all functionality of both commands is embedded.

## Loose Ideas

*These were moved here from the Projects documentation, to the System documentation, to integrate them with the System documentation. Remaining ideas should be moved back to the Projects documentation after that. The Projects documentation is where Ideas belong.*

### Melding

J Code

Melding is a method for easier access to the structure. If you let all applications share the same Find Control,
or let separate applications have their own Find Control, it is a matter of applying melding or not?

JJ

### Brainstorm Involving Synchronization

Het probleem komt voort uit het feit dat je *één* object referentie hebt, voor *verschillende* relation classes. Dat komt, omdat de Item Object Name van de twee relation class hetzelfde is. Mogelijk moet je het verbieden om dezelfde ItemObjectName te geven  aan meerdere related classes. Dan krijg je bijvoorbeeld een relatie: 

```
Application Of Current Line Style 1=>1 Current Line Style
```

en een relatie:

```
Application 1=>n LineStyles.
```

Maar je zou ze ook moeten kunnen samensmelten? Dan krijg je dus mogelijk meerdere synchronisaties in dezelfde property command.

Nu is de vraag nog: moet ik echt overlappende synchronisatie hebben, waarbij een object referentie eigenlijk 2 verschillende relation classes voorstelt? Progressions kunnen op die manier ook integreren in 1 object referentie, die hoort bij meerdere progressions, of relation classes. maar er moet wel een warning verschijnen als in de relaties A =>1 B en A =>1 C, dezelfde item object name is gekozen voor B en C en dat daarmee B.A en C.A altijd gelijk gesynchroniseerd worden. De warning zou kunnen worden uitgezet als je expliciet in de relatie aangeeft, dat het de bedoeling is.

De blauw gekleurde teksten stellen slechts een afvraging voor: Moeten twee related objects (=>1) kunnen samensmelten tot één object referentie, en kunnen progressions, dedimensionalities en skipping structure layers hier ook mee samensmelten?

Samensmelten moet een apart topic worden.

### Good Example Where Melding Might Cause Problems

Be careful in Synchronization 1=>1. For instance in J Graphics: the relation Application <=> Current Line Style. If Line Style . Application is assigned, Application . Current Line Style should not be synchronized with that Line Style. Therefore you can set Relation Class . Synchronize = False. You set Synchronize = False for the Relation Class that should stay most constant and be the least volatile, so in this case the Current Line Style relation class gets Synchronize = False.