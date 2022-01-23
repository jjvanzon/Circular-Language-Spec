Circular Language Broader View | Exchangeability | Design Time = Run Time
=========================================================================

`[ Preliminary documentation ]`

In some programming languages there is a distinction between design time and run time. This may mean, that the software is programmed first, and then run. You might only run it, after you programmed it. If the program it is not error free, the program might crash. The idea of *Design Time = Run Time* is to take away this distinction between design time and run time. This article tries to demonstrate what might happen if you could create a program and use it at the same time.

When you create a program you may be creating classes and defining relations between them. A class can also have attributes.

After defining a class, an object may be created from it, and its attribute values set. Objects with the same class might share similar contents. And those contents may change simultaneously as the class or the objects are edited. The things that might change simultaneously for all the objects, may be the *static* parts of the class. Objects can have their own individual *data*, which may be changed independently of other objects. A relation to another class might be defined. This might give the existing objects, references to other objects. These pointers may be set to an arbitrary object, or to a new object or not at all.

## Changing the Class of a Reference at Run Time

Objects might already have a class.
 
It might not be that easy, allowing an object or an object reference to change class while the program is running.

If the class of an object is changed, one possibility might be to erase an object’s original contents. If an object reference already points to an object of one class, what happens if you'd change that object reference's class? Perhaps the reference might be cleared, nullified, or marked as invalid, which may lead to a temporarily unusable object reference. Or should something be changed inside the target object?

Another possibility might be: mapping one class to another in a fuzzy way. This may be known from certain systems. The problem may not be unheard of. What is most practical may be dependent on the specific needs of the application. Just putting it out there, that this might become a bit of a problem when design time might equal run time. This problem might not exist if everything might just be thrown away everything, memory be cleared, and restart an application.

## Doubt

The idea of *Design Time = Run Time* might stand in the way of how objects might be allocated traditionally. That may make it less doable to change an object's configuration once created. Some tech might lean on that. Performance might be a reason.

Perhaps this might be thinking in terms of how things are. Not in terms of how things might be. Instead of thinking of how you might want to program and then saying: "That's impossible, because..." Perhaps it might not be so bad, defining how you might *want* to program, and then trying to find solutions for it.

What if "programming it at the same time" might not be as performant, but when you stop programming it *is* performant? That maybe leads to a usable set up. What if the performance cost is acceptable, if the class has not so many object instances? I feel holes to be poked into these ideas, while they might just be problems with solutions.

## Errors while Design Time = Run Time

The previous may just have described be the *data* aspect of it.

A more difficult issue might be: how to manage errors as *commands* run. The internet might become a single entity, and making commands accessible to others, might mean, that it could be called upon fast after making it.

The main point may be, that it might be a *problem* when design time = run time, that errors may go off for unfinished code. The solutions may differ. A different article may list out different ways of handling errors of in a dynamic environment

## Multi-User

There is one thing, that may distort the blending together of design time and run time: when everything might be running in a multi-user environment, in which multiple people might be working with the same data at the same time.

## Versioning

Versioning may help to give others a more stable version of your code, than the code as currently under construction. Tagging stable versions may allow others to retrieve that version, while you keeping the development version to yourself. Then you might keep programming and running it at the same time and it might not bother anymore.