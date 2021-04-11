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

### Errors while Design Time = Run Time

A more difficult issue might be how to manage errors in procedures. The internet might become a single entity, and making commands accessible to others, might mean, that it could be called upon quite soon.

The main point may be that it might be a *problem* when design time = run time, that errors may go off for unfinished code. The solutions may differ. I could list out different ways of handling errors of in a dynamic environment. A different article may do so.

### Versioning

Versioning may help to give others a more stable version of your code, than the code as currently under construction. Tagging stable versions may allow others to retrieve that version, while you keeping the development version to yourself.

### Multi-User

There is one thing that may distort the blending together of design time and run time: when everything would be running in a multi-user environment, in which multiple people might be working with the same data at the same time.

### Changing the Class of a Reference at Run Time

When an object or an object reference might be assigned a class, its class might not be easily changed. This may be one of the exceptional situations that might occur if design time equals run time.

In practice: An object that might have a class might be assigned a different class. One possibility might be to erase an object’s original contents. If an object reference already points to an object of one class, what happens if you'd change that object reference's class? Perhaps the reference might be cleared, nullified, or marked as invalid, which may lead to a temporarily unusable object reference. Or should something be changed inside the target object?

Mapping one class to another in a fuzzy way, may be known in certain systems, so the problem may not be unheard of. What is most practical may be dependent on the specific needs of your application. Just putting it out there that this might become a bit of a problem when design time would equal run time. This problem might not exist if everything might just be thrown away everything, memory be cleared, and restart an application.