﻿Circular Language Construct Drafts | Parameters in Text Code
============================================================

`[ Deprecated documentation ]`

Parameters For Objects in Text Code
-----------------------------------

Parameters for objects in text code actually look like objects, that have a parameter. They look much like command calls then.

Declaration:

```
Pressure  (  Time  )
```

Call:

```
Pressure A  =  Pressure  (  Time  =  3  )
```

It indeed just looks like an object with a parameter, just like the diagram looks like an object with a parameter.

It looks like a command call, and since a command is also an object, you might think it is the same as supplying parameters to a command call, but it is not completely the same. A command’s parameters are the *object’s* sub-objects that are filled in. An object’s parameters are the *related object’s* sub-objects, that are filled in, so system interface objects.

Perhaps the textual notation for filling in system interface objects, instead of the object’s sub-objects, might be as follows:

```
Pressure A  =  Pressure  [  Time = 3  ]
```

So it might be more like indexing. Perhaps another type of bracketing might be introduced, though, because I have plans for another type of bracketing, in which the brackets look a lot like halves of the graphical symbols, that you see in the diagram.