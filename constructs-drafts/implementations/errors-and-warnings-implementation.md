Encircle Language Construct Drafts | Implementation
===================================================

Errors & Warnings Implementation
--------------------------------

`[ Out of Scope ]`

### Loose Ideas

Ik moet Booleans HasErrors en HasWarnings hebben en ik moet de Errors en warnings terug kunnen geven op een bepaalde manier.  
Ik moet ook opvangen dat een top level menu geen separator kan zijn en een separator geen children kan hebben.

-----

Ik begin me steeds meer te beseffen dat goede error handling heel belangrijk is. Uitgebreidere error handling dan nu in Creator. Deze error handling kan echter in Creator voor het grootste deel automatisch gegenereerd worden.

-----

Organization of structure must generate errors, but the generated code also needs better error handling. You can generate safer code, if all dependencies of the procedure are checked and specific errors are generated if something goes wrong. You will have the option of continuing always on error, breaking on error, stopping execution on error, ask what to do in case of an error or maintain an error log. Or you could choose not to generate any error handling at all.

#### Creator 0.9 Compiler Pitfalls ( Errors )

- In Visual Basic 6 komt een interface als member benaderen door de compiler heen, terwijl Visual Basic 6 crasht als je de reference werkelijk benadert.
- Pitfall: Selection List Chain Must Be Consecutive
- List to Select From moet een van een Dual relation zijn, omdat een ID Attribute nodig is en als een lijst zicht niet bewust is van z’n Parent, dan kent hij ook zijn ID in die Parent niet.
- Failure when generating controls and there are no main lists.
- Circular object creation hazard (e.g. 1<->1 relation both of which have CreateObjects) -> Out of Stack Space)
- Name too long pitfall
- Bad identifier pitfall
- Inherited member different signature than the shadowing derived class member
- Duplicate class name, duplicate attribute name, duplicate enum name, etcetera.
- Inheritance Circularity pitfall
- How should I check if name ambiguities will occur? Not for the moment.
- In de meeste gevallen als de J Data Base output niet te compileren is zijn er:
    - Namen dubbel gespecificeerd.
    - Visual Basic keywords gebruikt voor elementen.
- Check of er geen dubbele klassen in zitten (wel het specificeren toelaten, om vrij te kunnen blijven editen)
