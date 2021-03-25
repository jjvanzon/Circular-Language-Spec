Encircle Language | Construct Drafts
====================================

Concurrency
-----------

`[ Preliminary documentation ]`

Concurrency problems might be solved with several mechanisms. Which is the best one is yet to be determined. In this document you will find a lot of ideas about it.

The current document is under construction.  
Look inside the document Internet As A Single Computer for a better description of the problem.

### Concurrency resolution

In hoeverre lost automatic containment concurrency problemen op?

-----

Parallel processing,  
2008-06-16

Parallel processing could be applied in a For Each loop.

JJ

-----

Verder verschilt het ook nog of iets formeel input, output of throughput is (volgens de command definities) of dat iets actueel input, output of throughput is, dus of er bij een specifieke aanroep van een command bijvoorbeeld wel of niet iets ergens naartoe geschreven wordt.  
In eerste instantie is dit minder belangrijk, maar misschien maakt de automatische controle op wat actueel input, output en throughput is wel wat meer mogelijk voor concurrency resolution, naast dat de formele in, out en thru configuratie dan waarschijnlijk ook helpt voor concurrency resolution.

-----

<  
2008-07-03  
In automatic execution order you can see, that when you first assume arbitrary order of sub-commands, that do reads and writes, you have a concurrency situation. If you can solve THAT concurrency situation with automatic execution order, you can solve an arbitrary concurrent data-use situation with automatic execution order too. If everything is programmed, where does arbitrariness of the concurrency situation come from? The arbitrariness comes from users. Somehow a bigger whole, than a command with sub-commands would need to be treated as a single command, and the techniques of automatic execution order should be applied to that. Automatic execution order has not been fully described yet.  
/>

#### Concurrency is not considered

Concurrency was not considered in automatic execution order. On top of that, any connection between objects can change *just like that*, so you are only sure which piece of data will be read the moment you are reading it. The only time you know what data gets accessed concurrently, is *when* the data actually gets accessed concurrently. So you only know what readings and writings to specific data will influence each other, the moment *they are* influencing each other. So the *automatic* determination if sub-commands are data-dependent on each other is not possible. It is only possible as soon as reads and writes *are* accessing the same data, which converts this to a concurrency resolution problem, that is not within the area of subject of automatic execution order anymore. Automatic execution order will not consider any volatile concurrency situation for now.

#### Concurrency issues

2008-07-06 Concurrency

Laten we zo zeggen:  
Een plotselinge write, waar de reader niet van op de hoogte is, is nooit gewenst door de reader.

Dus als er plotseling een reader commando aankomt, moet een command dat write rollbacken tot het punt waarop het voor het eerst naar de input van het  andere commando schrijft. Niet gelet op sub-objecten, gaat het erom: het punt waarop het commando voor het eerst iets met de parameter DOET.

Als er allemaal readers aankomen tijdens het runnen van het writer command, blijft het writer command telkens de boel rollbacken, totdat er lang genoeg niemand read. Als de writer zijn command kan afmaken terwijl er niemand leest, dan is het eindelijk gelukt.

Een reader kan verder zijn afhankelijkheid van een writer aangeven, als hij juist wil, dat een writer z'n werk doet, voordat hij leest.

Een reader zou ook kunnen aangeven, dat hij het niet erg vind als een waarde plots verandert, dan is dat heel fijn voor de writers.

Je moet voor concurrency resolution eerst maar eens omschrijven, hoe een command, die meermaals dezelfde data benadert, zich vergelijkt met gebruikers, of meerdere lopende commando's, die dezelfde data benaderen. Het lijkt wel of daar zich een command manifesteert, dat er eerder niet was.

Nou eigenlijk draaien er meerdere calls tegelijk.  
Dat is concurrency.  
Als er meerdere calls tegelijk draaien, die precies dezelfde data benaderen, dan worden die meerdere calls eigenlijk 1 commando, waarop automatic execution order moet worden losgelaten.

Dat wil dus wel zeggen, dat readers de writers on hold zetten, en dus eigenlijk de data locken, totdat de readers klaar zijn. Eigenlijk wordt de data niet gelockt, maar wordt de executievolgorde tussen readers en writers bepaald.

Maar het zou in timeouts kunnen resulteren.  
Het lijkt net, of het er niet veel anders uit komt te zien als hoe concurrency is opgelost in bestaande database systemen.

JJ

-----

Can you apply automatic execution order to accesses, that are actually happening? I think that is what locking actually is: one piece of procedure waits on another piece of procedure to be finished with the data.

In my system it might become a little different. Instead of locking data, which locks procedures, the order of the procedures trying to access the same data is determined. 

If the data does not become available soon enough, the procedure that tries to get access will give up and fail. This causes a rollback of the whole procedure.

If you can’t automatically determine the execution order for a procedure definition, but you can only determine the execution order of running procedures, then you’re only working on concurrency, no longer on automatic execution order.

When you apply the method where readers get access first, and a writer as soon as the reader tries to read, rolls back and tries again until it succeeds without any reads in between, then you might still get inconsistent data, because maybe data items far apart still need to be consistent.

How about you define that two fields, for instance the balance of two bank accounts need to be consistent. Define it for structure elements, rather than in specific transactions.  
You simply cannot write a balance, if you don’t subtract the very same amount from another balance.  
I don’t know.  
Actually

#### Other Ideas

< Parameters not used in a specific execution: non-put >

-----

Threads,

Thread convergence.  
You might at one point at which parallel processes require a point of sequentiality, have the threads wait on each other and converge back to one thread. Try to make that transparent.

JJ

-----

Concurrency & Persistence Delay,

When you create an SQL command object inside a method, so recreate a command object every time you call a method, rather than creating the command object inside a class, and use the same object every time you call the method, could give you a problem in a multi-threaded situation, where you use the same instance of the class to call a method, that uses the same command object. If the method creates a new command object every time you call it, the multi-threaded situation works well again. this doesn't account for database locks, though.

But recreating the command call for each call to the method, is a 'Work on a copy' principle. A 'Work on a copy' principle can solve concurrency in a multi-threaded situation. It's also analogous to temporary caching data before you commit it to the database.

Perhaps this can be considered next time I think about concurrency issues, and issues regarding 'persistence delay', which part solve concurrency issues.

JJ

-----

Concurrency resolution,  
2008-08-15~

The whole idea of a user only ever performing an action by creating an executable object and running it, visualizes the volatility of command calls, when they are not programmed, but executed arbitrarily, like users make them do. This instantly creates new concurrency situations inside objects and commands that do not have a class or definition (that have arbitrary contents). Compared IO and automatic execution order can be a key to solving concurrency for user-executed commands just as well as command-executed commands.  
So there you have your procedures, that are run volatilily, for which concurrency needs to be managed, and they are now the same as a program. So instant creation of commands, and instant interweaving of command execution order starts here.

JJ