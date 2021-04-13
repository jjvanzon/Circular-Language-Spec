Encircle Language Broader View | Interfaces
===========================================

Imaginary Backward Relationships
--------------------------------

`[ Preliminary documentation ]`

Sometimes when a backward relation is not stored, you want to see it anyway, because it might be useful information. Particularly you always want to see all available commands inside an object, even though an object might not physically have a reference to all the commands.

Producing the backward relationship may involve scanning part of a system in which an object might be used or perhaps sped up by some sort of caching scheme.

This requires backward relations that are not stored, to be shown anyway. The solution is to draw them out as imaginary backward relations. This requires recalculation whenever the view changes. But this is only done for commands and objects in modules you actively reference. The you still might not have all possible commands on the internet available inside the object, but you might not want that anyway, because then you might see a ridiculous amount of commands. You just want the ones from sites that you are acquainted with.