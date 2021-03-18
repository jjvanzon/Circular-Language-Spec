Circle Language Construct Drafts | Errors & Warnings
====================================================

Loose Ideas
-----------

`[ Preliminary documentation ]`

Ik moet Booleans HasErrors en HasWarnings hebben en ik moet de Errors en warnings terug kunnen geven op een bepaalde manier.  
Ik moet ook opvangen dat een top level menu geen separator kan zijn en een separator geen children kan hebben.

-----

Organization of structure must generate errors, but the generated code also needs better error handling. You can generate safer code, if all dependencies of the procedure are checked and specific errors are generated if something goes wrong. You will have the option of continuing always on error, breaking on error, stopping execution on error, ask what to do in case of an error or maintain an error log. Or you could choose not to generate any error handling at all.

-----

Ik begin me steeds meer te beseffen dat goede error handling heel belangrijk is. Uitgebreidere error handling dan nu in Creator. Deze error handling kan echter in Creator voor het grootste deel automatisch gegenereerd worden.

-----

Internet as a Single Computer,

There is one more thing that isn’t handled. Functional errors. Methods are usually programmed and then tested before they are published. A method that does not produce a run time error, may alter data incorrectly, even though nothing went wrong according to the computer. That is called a functional error. Unhandled functional errors could ruin data.  
This is one flaw in the highly active environment in which methods could be published before they are properly tested.

-----

Computer Language, Coding Principles, Errors & Warnings,

Handling functional errors is covered in Errors & Warnings.

JJ

-----

Errors & Warnings,  
2009-05-12

A lot of ideas are found in the article *Design Time = Run Time*.  
It demonstrates the complexity of error handling.  
Much of the ideas have to be moved from *Design Time = Run Time* to here while Design Time = Run Time should contain a summary of the idea.

JJ

### Compiler ‘Pitfalls’ ( Errors )

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

### Out of the Original Symbol Documentation

Als je een te supplyen procedure reference (pure virtual function, pure overridable) niet invult, dan heeft hij van zichzelf waarschijnlijk geen inhoud. Als je hem dan aanroept gebeurt er gewoon niks. Eigenlijk zou dan misschien ook bij niet gecreëerde objecten moeten gebeuren: je roept hem wel aan maar er gebeurt gewoon niks. Dat voorkomt foutmeldingen, maar het is eigenlijk niet de bedoeling. Of kan je erop bouwen. Misschien is het een keuze die je maakt als programmeur. Nou moet ik zeggen dat ik in mijn code er altijd voor kies dat als er iets 'verkeerds' wordt aangeroepen, dat er dan gewoon NIKS gebeurt. Er gaan niks fout, nee er gebeurt gewoon niks.