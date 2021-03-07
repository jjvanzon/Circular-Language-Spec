Circle Language | Construct Drafts
==================================

Locking
-------

### Ideas

I have not taken into account in Symbol, that some objects need to be locked, to keep the situation snap-shotted. Locking is not covered yet in J Code

-----

This could create trouble, when a method wasn’t locking all data that was its output. In that case it would be volatile data, that should not be rolled back, because it might have been changed by something else, and that something else would want to keep it changed. You could make it possible to see whether you were the last changer, so you could rollback changes you made yourself. >  
< I have a huge problem with locking now. I don’t know how to provide a good locking scheme for now. It is required to let the internet as a single computer function. >

-----

locking data in a highly concurrent environment.

-----

I just don’t know at what point to will accept data getting unlocked and from that point basically becoming volatile.

I know it is important to lock data between certain points in time. I just don’t know when it becomes not important anymore to have it locked. But I know it is important to have it unlocked at some time again.  
At that point there is always a point of acceptance that the data is volatile.  
I prefer this locking and unlocking to go completely automatically, and not keep data locked up for too long, and ...

At what point is volatility accepted?   
Before the point where you start using a piece of data in a method, it is acceptable it is volatile.   
You only start locking it as soon as you use it.   
At what point will it become acceptable that it becomes volatile again?   
As soon as you won’t be using it anymore? No, because it might be output.   
The output might then be changed again.   
A return value is always access controlled, and new data, that at first is only accessible to the method producing it and the accessible to the caller only, until he exposes it.  
But output can also be shared data. I guess for shared data, you can set the rule that it will be unlocked as soon as the method itself won’t be using it anymore.

But what if a method enters a point where the time between its starting to use data and it not using the data anymore, takes a long time.

When you loop through data, the method won’t be using that same data in the next iteration, so that’s not a situation in which that happens.

What if there will be no locking?  
Then you’d wonder how to rollback a method. I guess a mutation should only be rolled back if the data didn’t get mutated again by another process.

Until now I only discussed locking, to be able to rollback the method.

But what else is locking good for?

I’m not sure how to do this automatically.

If you allow multiple systems or threads to change the same data. Then they simply change the same data.  
There might be points at which you need a stretch of data not to be altered.
You could either take a snapshot of the data or lock it.  
A programmer might not think of the data as being that volatile.

Bold statement:  

- A process writing to data doesn’t care about it staying consistent. A process reading data cares about data staying consistent.

So it is a process reading data, that is supposed to impose a lock.  
At what points does a proces want data to stay consistent.  
For instance when writing it to output.  
But it is a writer’s responsibility to determine at what points data is not consistent.  
My, this is a hard issue. It’s not clear to me yet, and I think that the rest of the world also has problems with it. My gut feeling just says, that there HAS to be a solution, that doesn’t require any thought of a programmer and doesn’t cause any locking *problems*.

What if the amount of things you could do to data are limited, that for each situation you can decide about an optimal way of locking it? Like writing an object’s attributes might need to be done in one blow?  
Or while working with an object, it needs to remain existent. That last part is solved with reference counting.

I have the idea that the number of situations of working with data are limited and each situation has its own optimal way to lock something.

How can you alter a method at the same time?  
Didn’t I at some point decide that when multiple users alter the same data, they should be communicating about it? Yes they should, unless it’s accepted that the data is that volatile.

A user can lock some data. That would be handy, so there will be no intruders.  
An object is also a user. It can also lock data. But unless he locks it, it can change at any time.
