Encircle Language | Broader View
================================

Errors & Warnings Broader View
------------------------------

For error handling, I may have once wanted, to pick a single sure-fire way to handle things. But now I think, I have seen so many different ways to solve the problem, that I have difficulty taking my pick. Also, depending on the specific application, it might not matter much. When integrating with systems, not all systems may work as my private hand-picked way. When using the notation to just draw clarifying diagrams, the error handling aspect might not even matter.

Errors might not always be handled the same way. I could list out different ways, I might think of, for handling errors of in a dynamic environment.

### Rolling Back

Perhaps preferably, when an error was encountered, all changes are rolled back, and either default output is produced or the error is raised again, upon which the command caller might be rolled back too. Any change to data, might be rolled back upon error. The idea is that the effect of the command might be totally erased.

A command might be rolled back, and the error thrown or default output produced. You can also choose to always return default output while you are *editing* your command.

But where does it end? Is there a master parent root command, that encompassed everything? Should the entire world system of computers be rolled back? This takes my head into a spin.

### Undo

Rolling back might be possible, because undo history may be recorded as the command runs. If data was changed from another thread already, the rollback might leave that data untouched.

### Default Output

Producing default output on error can be an ok choice in highly active systems, such as a sound generator.

### Logging

The ignored error could be optionally logged (as a warning).

### Conditions

Unnecessary rollbacks might be prevented by adding conditions to the command which are checked before the command runs. This may also produce clearer error messages.

### Automatic Conditions

Some of these conditions might be added automatically by the system, based on a command's contents.

### Catching

There’s also the option to catch the error and run alternative code to handle the error.

### Pausing

Possibly the running system, might not be paused upon an error. This might cause too many running internet threads to hang or time out. You might want the option to pause the system anyway, when you’re still debugging it, just to be on the safe side, but by rule the program might not be stopped upon error.

### Functional Errors

A program might also produce the wrong data. This might not be detected as an error. This could be called a functional error. No rollback might be performed, unless the program is maybe adapted to detect specific functional errors. A program might have a bug with a functional error. It just might become a bigger problem, when a command is exposed through the internet, and might run more frequently and cause more 'damage'.

### Loose Ideas

`<< broader view >>`  
Errors & Warnings,  
Handling Functional Errors,

There is one more thing that isn’t handled. Functional errors. Methods are usually programmed and then tested before they are published. A method that does not produce a run time error, may alter data incorrectly, even though nothing went wrong according to the computer. That is called a functional error. Unhandled functional errors could ruin data.  
This is one flaw in the highly active environment in which methods could be published before they are properly tested.

JJ

#### Out of the Original Symbol Documentation

`<< broader view >>`  
Als je een te supplyen procedure reference (pure virtual function, pure overridable) niet invult, dan heeft hij van zichzelf waarschijnlijk geen inhoud. Als je hem dan aanroept gebeurt er gewoon niks. Eigenlijk zou dan misschien ook bij niet gecreëerde objecten moeten gebeuren: je roept hem wel aan maar er gebeurt gewoon niks. Dat voorkomt foutmeldingen, maar het is eigenlijk niet de bedoeling. Of kan je erop bouwen. Misschien is het een keuze die je maakt als programmeur. Nou moet ik zeggen dat ik in mijn code er altijd voor kies dat als er iets 'verkeerds' wordt aangeroepen, dat er dan gewoon NIKS gebeurt. Er gaan niks fout, nee er gebeurt gewoon niks.