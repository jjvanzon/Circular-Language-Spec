Encircle Language Broader View | Exchangeability
================================================

Design Time = Run Time
----------------------

`[ Preliminary documentation ]`

In some programming languages there is a distinction between design time and run time. This may mean, that the software is programmed first, and then run. You might only run it after you programmed it. If the program it is not error free, the program may crash.

The idea of *Design Time = Run Time* may take away this distinction between design time and run time. This article tries to demonstrate what might happen if you could create a program and use it at the same time.

When you create a program you may be creating classes and defining relations between them. A class can also have attributes.

After defining a class, an object may be created of it, and its attributes set. You might also define a relation to another class. This should immediately give the existing objects references to other objects. These pointers may be immediately be set to any arbitrary object, or to a new object. It might go like that, when defining classes and creating objects at the same time. That may be the same as programming it and using it at the same time. But this may just be the data part of that.

Objects can have a class. Objects with the same class might share similar contents. And those contents may change simultaneously as the objects or class are edited. The things that might change simultaneously, may be the *static* parts of the class. Objects can have their own individual *data*, which may be changed independently of other objects even of the same class.

### Doubt

The idea might stand in the way of how objects might be allocated traditionally. That may make it less doable to change an object's configuration once created. Some tech might lean on that. Perhaps this would be thinking in terms of how things are. Not in terms of how things might be. What if "programming it at the same time" might not be as performant, but when you stop programming it *is* performant? That might lead to a usable set up. What if the performance cost is acceptable, if the class has not so many object instances? I feel holes to be poked into these ideas, while they might just be problems with solutions. Perhaps defining how you might *want* to program and then trying to find solutions for it, might not be that bad. Instead of thinking of how you might want to program and then saying: "That is not possible, because..."

### Errors

A more difficult issue might be how to manage errors in *procedures*. The internet might be a single entity, and making a method accessible to others, might mean, that it could be called upon quite soon.

For error handling, I might have wanted to pick a single sure-fire way to handle things. But now I think I have seen so many ways to solve the problem, that I have difficulty taking my pick. Also, depending on the specific application it may or may not matter much to invent a way of handling errors. When integrating with systems, not all systems may work as my private hand-picked way, which I might never make perfect. I could list out all the different ways of handling errors I might think of in a dynamic environment. The main point may be that it might be a *problem* when design time would equal run time. The solutions may differ.

Errors might not always be handled the same way.

### Error Implementations

#### Rolling Back

Perhaps preferably, when an error was encountered, all changes are rolled back, and either default output is produced or the error is raised again, upon which the method caller might be rolled back too. Any change to data, would be rolled back on error. The effect of the method would be totally erased.

A command might be rolled back, and the error thrown or default output produced. You can also choose to always return default output when you are *editing* your method.

But where does it end? Is there a master parent root command, that encompassed everything? Should the entire world system of computers be rolled back? This takes my head into a spin.

#### Undo

This might be possible, because undo history may be recorded as the method runs. If data was changed from another thread already, the rollback might leave that data untouched.

#### Default Output

Producing default output on error can be an ok choice in highly active systems, such as a sound generator.

#### Logging

The ignored error could be optionally logged (as a warning).

#### Conditions

Unnecessary rollbacks might be prevented by adding conditions to the method which are checked before the method runs. This may also produce clearer error messages.

#### Automatic Conditions

Some of these conditions might be added automatically by the system, based on a method's contents.

#### Catching

There’s also the option to catch the error and run alternative code to handle the error.

#### Pausing

The running system might not be paused upon an error. This might cause too many running internet threads to hang or time out. You might want the option to pause the system anyway, when you’re still debugging it, just to be on the safe side, but by rule the program might not be stopped.

#### Functional Errors

A program might also produce the wrong data. This might not be detected as an error. This could be called a functional error. No rollback might be performed unless the program is maybe adapted to detect specific functional errors. A program might always have a functional error. It just might become a bigger problem, when a command is exposed through the internet, and might run more frequently and cause more 'damage'. 

### Multi-User

There is one thing that may distort the blending together of design time and run time: when everything would be running in a multi-user environment, in which multiple people might be working with the same data at the same time. More ideas about that might be found in another article.

### Changing an Object Reference's Class in Runtime

When an object or an object reference might be assigned a class, its class might not be easily changed. This may be one of the exceptional situations that might occur if design time equals run time.

In practice: An object that might have a class might be assigned a different class. That might erase an object’s original contents. If an object reference already points to an object of one class, what happens if you'd change the object reference's class? Perhaps the reference might be cleared, nullified, or marked a an invalid temporarily unusable object reference. Or should something happen to the target object?

Mapping one class to another in a fuzzy way, may be known in certain systems, so the problem may not be unheard of. What is most practical may be dependent on the specific needs of your application. Just putting it out there that this might become a bit of a problem when design time would equal run time. This problem might not exist if everything might just be thrown away everything, memory be cleared, and restart an application.

### Loose Ideas

#### Other Loose Ideas

Design Time = Run Time,  
Implementation,  
2009-05-12

I do not know yet how to ventilate changes to classes to their derived objects.

JJ
