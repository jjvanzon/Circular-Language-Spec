Encircle Language | Broader View
================================

Errors & Warnings Broader View
------------------------------

For error handling, I may have once wanted, to pick a single sure-fire way to handle things. But now I think, I have seen so many different ways to solve the problem, that I have difficulty taking my pick. Also, depending on the specific application, it might not matter much, whether to inventing a way to handle errors. When integrating with systems, not all systems may work as my private hand-picked way.

Errors might not always be handled the same way. I could list out different ways, I might think of, for handling errors of in a dynamic environment.

### Rolling Back

Perhaps preferably, when an error was encountered, all changes are rolled back, and either default output is produced or the error is raised again, upon which the command caller might be rolled back too. Any change to data, would be rolled back on error. The effect of the command would be totally erased.

A command might be rolled back, and the error thrown or default output produced. You can also choose to always return default output when you are *editing* your command.

But where does it end? Is there a master parent root command, that encompassed everything? Should the entire world system of computers be rolled back? This takes my head into a spin.

### Undo

This might be possible, because undo history may be recorded as the command runs. If data was changed from another thread already, the rollback might leave that data untouched.

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

The running system might not be paused upon an error. This might cause too many running internet threads to hang or time out. You might want the option to pause the system anyway, when you’re still debugging it, just to be on the safe side, but by rule the program might not be stopped.

### Functional Errors

A program might also produce the wrong data. This might not be detected as an error. This could be called a functional error. No rollback might be performed unless the program is maybe adapted to detect specific functional errors. A program might always have a functional error. It just might become a bigger problem, when a command is exposed through the internet, and might run more frequently and cause more 'damage'.