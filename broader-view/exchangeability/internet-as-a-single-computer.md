Encircle Language Broader View | Exchangeability
================================================

The Internet as a Single Computer
---------------------------------

`[ Preliminary documentation ]`

__Contents__

- [Introduction](#introduction)
- [A unified paradigm for all digital objects](#a-unified-paradigm-for-all-digital-objects)
- [My insecurities](#my-insecurities)
- [A single bulk of storage](#a-single-bulk-of-storage)
    - [Cache Layering](#cache-layering)
- [Execution of programs running across machine boundaries](#execution-of-programs-running-across-machine-boundaries)
- [Security](#security)
- [Control of concurrent use](#control-of-concurrent-use)
- [Communication between computers](#communication-between-computers)
    - [Summary of the internet protocol](#summary-of-the-internet-protocol)
    - [One big electronic circuit](#one-big-electronic-circuit)
    - [Traffic](#traffic)
    - [Uniquely identifying resources on the internet](#uniquely-identifying-resources-on-the-internet)
    - [ID’s](#ids)
    - [Grid Computing](#grid-computing)
    - [Site Merging](#site-merging)
    - [Parallel processing](#parallel-processing)
    - [Mirroring & synchronized copies](#mirroring--synchronized-copies)
    - [Connection Lost!](#connection-lost)
- [Implications for other concepts](#implications-for-other-concepts)
    - [Collection](#collection)
- [Integration Modules](#integration-modules)
- [Requirement Summary](#requirement-summary)
- [Loose Ideas](#loose-ideas)

### Introduction

If the new code base of the new computer language does not turn the internet into a single computer, I wouldn’t call it a final version.

In the field of system engineering, networked computers are central to the material worked with. But in the field of software programming, people do not seem to have gotten used yet to all those computers being connected to each other. When something is done on a single computer, the program’s source code looks good, but when multiple machines need to start working together, things look... different. I feel that things should not look... different. I think a computer programming language should primarily describe what happens on whole a network of machines, instead of what happens on each computer individually with a sort of glue-code in between, that makes those computers work together. As long as computer code deals with individual computers glued together, instead of describing primarily what happens on the whole network of computers, software will never take full advantage of the internet. Most programming languages are dealing with how source code translates to machine code, that first and foremost runs on a single machine. When the program’s execution extends over multiple machines, the source code is split up into bits, usually written in all sorts of different computer languages, and each bit runs on a separate computer. I feel, that a computer program should really just be *one* program operating in a network of machines.

### A unified paradigm for all digital objects

For the internet to function as a single computer, I want everything to be accessed the same way. A default view on contents of the internet in a unified paradigm for all digital objects. The diagrammatic expression of the new computer language can function as a default expression in which anything digital can be abstractly expressed. You can also view things in a tree control. Objects in such a default view can also be opened in another view. Documents such as pages with text and video files can be opened in the appropriate view. As such there are user interfaces for specific object types, but there are also user interfaces through which all the objects and their linkage can be viewed in a unified way.

*Hyperlinks = Referential Structure* has already explained how the web pages on the world wide web can be expressed as a referential structure of interlinked objects, in order to have them integrate with the single construction, which all the other digital objects are a part of. It is not that you will only be seeing diagrams, not webpages anymore. Webpages can be opened in a different view, but can also be seen through a default view through which to view objects.

### My insecurities

Before I started writing this article, I had no idea how I was going to solve this problem. My biggest insecurity now is concurrent use of data. I would not want to program in a system where you would constantly be working around concurrency issues. I want concurrency to be something you don’t need to think about. But I haven’t solved that yet. But first let’s discuss issues, that *are* clearly worked out.

### A single bulk of storage

One of the requirements for the internet to function as a single computer, is for all hardware on the internet to be abstracted to a single bulk of hardware which you either have access to or you don’t. Storage media in particular will blend together to form a single bulk of storage, that you have access to, be it a disk, running anywhere, be it RAM, be it a USB memory stick. Any storage medium will become part of a single bulk of storage space, that you can access. Local storage media, that only you have access to, also become part of this single bulk of storage. Say you have a subscription, that gives you the right to some part of a physical disk running somewhere... You still have some control over individual storage devices. They can still be administrated separately. Some storage media will be connected to the internet permanently. Some storage media will be disconnected frequently. Storage media, that are not always plugged into the internet, might only be used for local caching.

Hardware other than storage will usually be used locally. But you should also be able control devices remotely, for instance for a printer or a camera with a movable lense.

It is possible to make a copy of an object and put it on another storage. But why have more than one copy of something? Everything is directly accessible online. The only good reason to have a copy of something, is to have better access to it. An unaltered copy is always linked to the original. Multiple originals can be maintained to improve access to the object. Those instances are linked to each other in a mirroring or synchronization scheme. You can keep local copies, when your terminal is not always connected to the internet, but this should really just be considered a cached mirror. Copies can be useful for other purposes than better access as well, though. For instance: for backup purposes or to preserve an older version of an object, or to make a new object, for which the original object is a first draft.

Some data is received in large quantities and not intended for storing for a long time, such as a movie you are watching over the internet. Streaming access is a slightly different way of handling data that is coming in, in large quantities at a time.

The term single bulk of storage should not be mistaken for being able to identify each byte on the internet individually. That would be undoable, because there are virtually an infinite amount of bytes on the internet. What it does mean, is that to a user, the storages *he or she* has access to, seem to be a single bulk of storage. The user does not see the difference between the local hard disk, the RAM memory or permanent storage on the internet. A user can just create objects, that are permanently stored somewhere, and accessible over the internet.

You have subscriptions to storages permanently connected to the internet, and software uses these storages along with your local storages in a caching scheme, where you don’t see where exactly an object is stored. It’s not that every byte on the internet is individually indexed, you just don’t see any distinction between the different storage devices you are using, unless there is functional use for it, for instance: permanent local storage, for access when you’re offline, or: storage on a USB stick, so you can plug it out and transfer it to another computer.

#### Cache Layering

The local storage devices and storage on the internet are used in a caching scheme. In this caching scheme, multiple devices are used, but each piece of data always has a target storage, which is the permanent residence of the data. Above the target storage, there are cache layers that reside on devices increasingly faster in access, but also having less storage space. When working with data intended to be written to the target storage, the work can first be done on a faster device, until the work is finished, and then the cached data is flushed to the permanent storage. There could be multiple cache layers in between that. Data frequently used could be placed in the top cache layer. When that data has not been used for a while, or free space is needed in the top cache device, the data is written to a cache layer below that. Subsequently data is written to lower caching layers, until it is stored on the target device. This subsequent moving from one cache layer to another happens on a time basis (how long has the data not been used) on a need-space-in-cache-layer basis, or on the basis of gathering up a minimum of data before writing anything to the slower device, because it is faster to write things to a device in one blow. The data in a cache layer can also be immediately flushed to the target storage to keep the data stored on the target device consistent.

When the *target* storage is limited in size, data that has not been used for a while, can be written to a cache layer even *below* that, that offers more storage space, but slower access. However, the data is moved back to the target storage as soon as it needs to be taken in use again.

The stack up of cache layers goes from large, slow storage to small, fast storage. Smaller slow storage is usually not followed up by larger fast storage, because that just wouldn’t make sense from an economic point of view. You only have a limited amount of fast storage, because it’s more expensive than slower storage. The reason slower storage is larger, is because it’s cheaper. If slow storage is smaller and more expensive than fast larger storage, it wouldn’t really be a good product.

Memory (RAM) and disk are managed using the same system for managing space on a storage device. They are connected to each other in a caching scheme. They are both cache layers. Usually data will always have permanent storage as the target storage. A target storage is usually a disk, but not necessarily your own local disk. A disk on a network might also be the target device for data, while your local disk is only used for faster access. A target device on the network may very well be faster than your hard drive.

The cache layering becomes a little more complex, considering that devices also have other properties other than being fast, big, slow or small. Some storage devices are usable offline. Some storage are only usable online. Some storage is not protected enough against the internet, some is secure from access from the internet. Depending on the demands for the data, the cache layering differs for every piece of data.

### Execution of programs running across machine boundaries

Another requirement of having the internet function as a single computer is having the execution of a program run across machine boundaries.

As an example of what I don’t want: on the World Wide Web, when you access a web page, every now and then the client program asks for a page from the server. The server sends a page back to the client. The server waits for a request, the client sends one, the server receives it, processes it to a message to send back, sends back the message, and the client, waiting for the message, gets signalled, downloads the message and processes it, before it displays it as a web page.  
Client and server interaction looks like sending messages back and forth and waiting on them.

I don’t want to see that. I just want the things, that happen between the client and the server to be part of one program flow, that goes from one step to the next seamlessly, whether there is a boundary between computers between that or not. Whether or not the next step happens on a different computer, I want the interaction to seem to run over a single thread of execution in a single procedure. In reality there are two local threads: one on the server, waiting on a request from the client, and one on the client, that can be waiting for a response from the server, but I want it to logically look like a single thread. Also: when a server retrieves more data from *another* server, I want that to happen in the same internet thread too.

But that’s just the way it goes on the World Wide Web. In the new unified paradigm for all digital objects it is methods, that are running. A method could run anywhere, really. A method could run anywhere, and the data (the objects) it uses could be anywhere. Just like there is a caching scheme for data, and a way to handle multiple copies of the same data, there is also a caching scheme for methods, and a way to handle multiple copies of the same method. One method could be the original, or a group of multiple copies of the same method could function as a set of synchronized originals.  
A method seems to be part of an object, but you could also say it is only part of the class. But really it is a totally separate entity, that can be part of any class that is a parameter for the method. The object may be stored in one place, the class definition may be stored elsewhere and the method code may be stored somewhere totally else as well. However, it would be optimal for the method code and the data to be close to each other, but in theory they could be on either end of the world. To optimize this, caching is applied. Simply put, it would be preferred, that if you have the data stored on one machine, you want its methods also to run there.  
However, methods can operate on *multiple* objects, so if those multiple objects are far apart, where should the method best be? Cache the objects on the same device where you’ll be running the method, you would say.

The structure of a program, rather than its data, holds class definitions and methods. This structure of a program is *data* just as well. If you have objects permanently stored on a machine, you probably want the class information at least cached on that machine too.

An internet thread is a single thread of execution, but while a method runs on one machine, this method may call another method, that resides on a totally different machine, and so on. It’s still a single thread. It has a single identity, and changes made to data are marked as being changed by that same thread.

Multiple copies of data can complement each other, for faster access to it, but multiple copies of code can also complement each other, for faster access to it. It doesn’t matter where the code or data is. Wherever they are, they can be run in a single internet thread of execution. But preferably cached copies of the data and the code are used to make things run faster.

### Security

Another requirement for the internet to function as a single computer is security. But I do want it to be more easy that it is currently on the world wide web.

If you log on to the internet from anywhere, you will be able to access all the digital stuff, that you have access to. You will be logging into the internet once, and get access to anything permanently stored anywhere on the internet, that are you are allowed access to.  
If you have an account on some web site, it will be linked to your internet user. You don’t need to log into that web site anymore, for you are already logged on to the internet and the web site knows which user you are and that you are allowed access to the web site. If you can make changes to objects on an internet site, and you chose not to stay anonymous, your user gets automatically logged as the author of that change.

For personal security reasons, internet users should stay anonymous, with a fictional name on the internet. If somebody knows your last name and the town you live in and he means you harm, he can easily track you down using a digital phone book.

However, in a company network, people *do* need to know each other on the network. You may want to refrain from identifying too much personal information about a person in his user details on your company network. You might even give the employees a fictional name, one that somebody in your company *can* logically link to a specific person, though.

### Control of concurrent use

An effect of having the internet function as a single computer, to which many users log on, is that a lot is happening concurrently. This mostly goes well, until inevitably multiple users are using the same data and one of those users makes a change. In that case one user might see a version of the data, that the next moment is not current anymore. This can create problems.

Unfortunately it is not clear to me yet, what is the best solution for this. This is what I am still most insecure about. There are multiple candidate concepts, that may offer a solution. I am aware of the solution offered by present day database systems. I am just not happy with it, because it requires a programmer to think too much about problems around concurrency, instead of focussing on the functionality of the program. And even when a programmer has thought hard and long about the problems around concurrency, there still is a chance to get strange behavior and things getting in each other’s way. I have this gut feeling that there is another solution for it, that is just totally outside the frame of thought of the locking schemes provided by present day database systems.

Usage of the same data may cause problems. For instance: when you use a value multiple times in the same procedure, and it’s required that the value stays the same, but another procedure changes the value half way. In that case the operation can have unpredictable results. A locking scheme could be applied. The way this is done would be covered in the article *Locking*.

But perhaps problems with multiple users accessing the same data may also be solved by casting events when data changes, and being able to reject a change when busy with data. I’m not sure yet if that can offer any improvement to the locking scheme, but these issues will be covered in the article *Events*.

Each user has his own undo history, so that he can undo the steps he took. But if somebody else changes the same data, the first user’s change can’t be undone anymore. So the option to undo the change falls away. A solution for that needs to be found. Perhaps it’s just that: the option to undo the change falls away. The user must be notified about the change, though, and may be able to reject the change. These problems need to be discussed in the article *Undo*.

When people are working on exactly the same piece of data at the same time, it would only be practical if these people would actually be communicating about their changes in some form, I guess... but I’m not sure.

I have a gut feeling that automatic execution order may solve concurrency issues mathematically, by determining which things can be executed in parallel, and which things must be executed serially, independent of the ‘earthly’ logic of the methods, but approaching it like a mathematical equation consisting of references to objects and procedure calls. Multiple methods interweave to become a single method. I'm just not sure yet how, but I just have a hunch here. Execution order is fixed in normal programming languages, because it is text, in which an order is an inevitable fact, that you cannot go around. A diagram however does not have a specific order, so the execution order may be determined based on the correlation between individual elements.  
Perhaps this can prevent locking and waiting, and just make a single sequence out of two methods instead of two sequences waiting on each other, and eventually giving up.

Unfortunately it is not clear yet which of the concepts will best solve control of concurrent use. I would prefer a scheme where a programmer does not even need to consider the problems around concurrent use anymore. I will have to extend the explanations here after these specific concepts are better worked out.

### Communication between computers

In the story above, the actual communication between computers seems to be a trivial concept, because I didn’t even have to explain it. But it does have a lot of implications.

#### Summary of the internet protocol

The internet protocol is used to connect one computer to another. You can connect to another computer, by specifying its *domain name*. This domain name is looked up using a Domain Name System. The Domain Name System translates the name to an IP address, sort of like using a phonebook, which translates somebody’s name to a phone number. An IP address is sort of like a phone number for a computer and a computer can also have a name. A connection to a computer can be requested directly using the IP address, but also by specifying the domain name, but the last method requires a lookup. The IP address of the computer you want to connect to is sent to your Internet Service Provider’s operator computer, which has an IP address as well, but this number is a fixed setting stored on your computer. 

Your primary connection to the internet, is through a computer of your Internet Service Provider.  
The internet service provider’s computer can determine the optimal route between your computer and the other computer you are trying to connect to. The connection between the two computers could be very direct, but also several computers could be in between your computer and the one you are trying to connect to. The internet service provider might delegate finding the optimal routing between your computer and the one you’re requesting access to, to another computer, perhaps to an Internet Exchange Point, which is a primary node between computers on the internet, which also centrally holds the domain name registrations. Just like any other computer, the Internet Exchange Point has an IP address as well. Computers on the internet are identified by a *public* IP *address*, to which a domain *name* can be connected. Behind such a public IP address could be an entire network of computers. This is called a subnet, a private network or a local area network. This subnet can use its own numbering of computers. The numbering of computers within the subnet, can overlap with the numbering on the internet.

That way, an IP number on the internet could be overridden by an IP number on the private network. Then the IP number on the internet can not be reached within the private network anymore. The resource on the internet is shadowed by a resource on the local network, when it uses the same IP number. This doesn’t happen much, and if the resource on the internet is needed anyway, you could change the private IP number.

In the numbering on the internet, each computer has a unique number. An IP address can only uniquely identify approximately 4 billion computers. Believe it or not: we’re running out of numbers. That’s why they are introducting a new numbering, which can identify more individual computers on the internet. But within a *subnet* in theory you are able to identify *another* 4 billion computers. You won’t be exposing all 4 billion private IP addresses to the internet. Your local network will only be connected to the internet by using just a few internet addresses.

You can also connect two sub-networks to each other, independent from the internet. In that case, only the two private subnets are connected. They are not connected through the internet, but only communicate with each other on a private connection.

#### One big electronic circuit

The internet can be seen as one big electronic circuit.

Usually, your Internet Service Provider’s machine will be part of the routing between your computer and another one that you are trying to connect to. There may be more than one machine in between your computer and the other one you connect to. Each of those machines in between is called a router. Each packet of data sent between two computers also specifies the route it should follow.  
As soon as two computers are connected, the route is not recalculated all the time, but the same routing is reused when sending more packets of data over the connection. You are actively connected and data will stream from one computer to the next, following a specific routing. The data streams or computers are connected in a way, that the packages automatically follow the right path. After connection, the electric circuit is just set to follow the right path between computers.

It’s just like the computers all become part of a single electric circuit. Just like a CPU has switches all part of the same electric circuit, and the peripherals around it are part of that same electric circuit, the wires connecting the internet make all those computers become part of a single electric circuit. Only the circuit goes over a longer wire. But the transfer rate over those wires is becoming faster and faster.

It’s just an electrical circuit. No more, no less.

It’s not *just* a peripheral, that network device. It is precious data coming in. It can be the result of a tough calculation, that your machine didn’t have to perform, that another computer, perhaps much more powerful than yours has performed for you, and here it is just coming in on this peripheral, and your computer did not even have to do anything for it. It shouldn’t be a device, that slows down your computer, it’s supposed to speed it up.

It is really comforting to look at it this way. Pampering to the idea, that you’re loosing control over your nicely controlled environment, that is your single computer. 

It is actually weird that the world wide web has such an active client-server *waiting* experience, because the whole internet is really just a single electric circuit.

However, there is a catch. On your local computer you can pretty much count on it, that each device will keep functioning, and when one device asks for a result from another device, it will promptly return that result. On the internet you can expect the opposite: the possibility of failure is always hanging over your head. Asking for a result is no guarantee that it will arrive. And when you send something over the wire, the possibility is very present, that it won’t arrive. This is the one thing, that you loose control over. You don’t know how badly the electric circuits on the internet are performing. Perhaps there is a malfunctioning computer on the route, perhaps computer hardware is simply failing in between, perhaps a computer in between is too busy to handle the tasks appointed to it, perhaps a line is cut, perhaps there’s power down somewhere, perhaps a sattelite is malfunctioning, perhaps there’s interference in a mobile signal. But it is still a well functioning electric circuit, because if a packet of data fails to arrive, the electric circuit triggers *itself*  to resend the data, preferably using a different route.

#### Traffic

Internet as a single computer may look like you loose control over the use of your resources, but this can be managed by monitoring the resource use. Monitoring programs should also allow you to set quotas for activity and storage use, so that the resource usage can be regulated. You can indeed not always predict the exact resource usage, but you can regulate it. This is no different than in networks as they are today.

I still have doubts about how certain concepts will function, when there is a lot of communication over the internet, instead of everything happening on a single machine. For instance, methods that call each other over the internet and especially when I want to extensively use events, this might render a bunch of traffic over the network. Packet loss and things not arriving immediately may delay notification of data changes and so on.

But I am going to insist to have all the capabilities I want on a computer also present on a whole network. And I am going to assume that the traffic that generates, won’t be a problem.

It may become a lag in the system that computers will be sending many small messages to each other, with insisted, guaranteed arrival in synchronous operations. On the other hand, the fact that you can easily boost performance by hooking up computers onto the grid and turn the grid into a computer that’s more powerful than a single computer, turns networking into performance boost again, so where did that performance lag go now?  
I am just going to have to see this system in action for it to become apparent what problems there will be. It’s easier to create a first version of this and see how it runs, instead of trying to work out everything in theory first, and assume there will be problems.

#### Uniquely identifying resources on the internet

It has a lot of implications, that computers need to communicate with each other.

The main problem in this area is the fact, that the computers in the world hold so many resources, that you can’t individually identify each and every digital object with a unique number.

Consider, for instance, that on a local computer the list of known classes may be limited to a few thousands. Each object can easily identify its class with a number between 0 and a few thousand. But on the internet the amount of classes is basically infinite. What number are you going to use to uniquely identify the class of an object? This is one of the questions I asked myself. It is simply undoable to put up a list of all classes known on the internet. Believe me, it is.

Fortunately, the Internet Protocol has already solved this problem for me. Phew.

Even though the internet will function as a *single* computer, resources will still be exposed through separate internet *sites*. The resources exposed through a single site are considerably limited compared to all the resources on the whole internet. A single internet site can choose to maintain a list of all the classes defined on that site, which can be identified with a unique number.

Luckily, next to the resources on a single site being limited, the internet is built so that the amount of sites is also limited. The reason that the amount of sites on the internet is relatively limited, is not only because there are only a limited amount of internet addresses available, but also because not everything is exposed to the internet. Some things are only exposed on a local network. Some things are even only accessible from your local computer. Only a selection of resources is exposed to the internet.

On your terminal computer, you can identify a class by simply identifying the site the class is on, and which class of the site you’ll use.

The number of sites is not infinite, and the number of classes on a site is also not infinite. The whole number of classes on any computer in the world is virtually infinite, but not all classes are exposed to the internet. Some classes are only known on the terminal itself, some classes are known only within the local network you use.

So not everything is exposed to the internet, and this is what makes the resources more manageable and more easy to uniquely identify.

Do not be afraid, that this makes so many resources inaccessible through the internet. There is enough room on the internet, to expose anything genuinely interesting to the outside world.  
But there is so much on your local computer, that is genuinely *not*  interesting to the outside world.

Now, not only classes are resources on the internet. I just used that as an example to present the problem area. Individual objects are also resources on the internet. And modules, that contain multiple classes and objects are also a resource on the internet. Each *method*  is also an individual resource on the internet, because a method can be seen as separate from its class, next to being able to see it as part of a class. An internet address can identify an individual object, an individual class, an individual method, a lists of classes, a list of objects, a single module containing multiple objects, classes and methods, or a list of modules. Because classes, methods and modules are also objects, objects, classes, methods and modules on a site are identified in a single numbering. The site is represented by a single object, holding all the other resources. 

Perhaps in the future there will be ideas about how to abstract it, and not see the boundaries between sites at all. However, I kind of like the idea of subdividing things into areas. It works fine for the human mind, because our own world is also split up into cities with areas, with houses and central places. Administrating networks in the new computer language will still be a lot like networks are adminstrated today, only more transparent as to where everything is. It would no longer be something abstract that lays behind network administration screens and IP numbers, you will see the landscape of it before you in a computer language diagram.  
Personally, I would like to use a different term for IP addresses and domain names. I would like to call them site names and site ID’s.

#### ID’s

At first the idea was to have the object’s identification consist of:

- IP Address
- Module ID
- Class ID
- Object Position

But in Computer Language modules and classes are also objects. In fact, all objects, including the classes and modules, are accessible from a single flat list of objects.  
So whether you want to identify a specific object from any module or class, or if you want to identify just a module, you only need to specify the IP Address and an Object Position, which is an object’s storage position on disk. An object’s identification will be a combination of the site’s IP address and the object’s position on disk:

- IP Address
- Object Position

Actually, the IP Address points to a domain. A domain has selected a single object, that will represent whole domain as it is presented to the internet. That object exposes the public contents of the domain. A single domain on the internet is a single object, that can expose other objects, collections of objects, classes and modules, which can again contain objects and classes. Each of those elements exposed by the domain are identified with a unique number. The domain can also directly represent a collection, a class, a module, a set of modules, etcetera.

Sometimes, you may want to access an object only through a specific path. Linking to a specific object, you keep linking to the same object. But the object found at the end of a path you follow, may be different all the time. You’d be assuming, that the location referred to a while ago, still references the same object that was there back then.  
In that case, you’d follow a path of object accesses, until you arrive at the target object reference that you are interested in. It could be a whole string of object accesses.

A client can just access one object after another, to eventually arrive at the target object. In that case the identification looks like:

- IP Address
- Position of object 1 to access
- IP Address
- Position of object 2 to access
- IP Address
- Position of object 3 to access
- ...
- ...
- IP Address
- Target Object Position 

A client may also send the whole string of ID’s to the server, have the server lookup the target object, and then return it to the client. That would save a bunch of communication back and forth between the client and server on each object access. In that case the object is identified by:

- IP Address
- Position of object 1 to access
- Position of object 2 to access
- Position of object 3 to access
- ...
- Target Object Position 

There isn’t a real distinction between clients and servers on my internet, but in this case the client is the one asking for something, and the server is the one answering with something.

Accessing an object by following a path can be a choice of the client, but it could also be a requirement set by a server, if the server has access-controlled the object. Access-controlling an object can prevent an object from being directly accessible through the site, and may require you to follow a path in order to access it.

Grid computing, such as site-merging and mirroring has implications on how ID’s work. This is because in site merging several storage devices are combined and objects participate in a single numbering, that doesn’t exactly correspond to a position on a disk anymore. And in case of mirroring multiple synchronized copies of the same object exist and an object is identified differently on each site that mirrors the object, so the ID of the same object isn’t always the same. But details about this are discussed in the sections below, under *Grid Computing*.

#### Grid Computing

There are even more topics about communication between computers.

There are several concepts that can be considered *grid computing*, in which a whole set of computers is controlled like a single machine or used as a single bulk of storage:

- Site merging
- Parallel processing
- Mirroring
- Synchronized copies

Site merging and parallel processing are the only grid computing concepts considered a requirement for the internet to function as a single computer, because they logically turn multiple computers into a single resource of storage or a single resource of processing power.

In site merging, a collection of objects is spread out over multiple machines, but the objects collection is accessed as a single resource with a single IP address.

In parallel processing, processing is spread over multiple machines and later the results are recombined as one.

Mirroring and synchronized copies are also grid computing concepts, but not requirements for the internet to function as a single computer. However, they are quite handy. There may be even more concepts, that are just as important as the ones I mention here, but not requirements for the internet to function as a single computer.

In mirroring, multiple copies of an object are maintained, that can be synchronized to the original object.

In synchronized copies, multiple resources exist independently, but periodically a process updates those resources, giving them the same data again.

#### Site Merging

In site merging, a collection of objects is a single resource, but the objects are spread out over multiple machines. The different objects are spread over multiple computers, to spread the load of data. The collection of objects is accessed as a single resource, as a single site, with a single numbering of objects. What counts here for objects, also counts for the spreading of modules, classes and methods over multiple machines. If the user has permission, a merged site not only hosts existing objects, but new objects can also be create within that domain. The new objects are equally spread over the different machines.

On a single storage device, an object is identified by its physical position on the storage device. When the same collection of objects is spread out over multiple storage devices, you will have overlap in the objects’ numbering. In that case an object can be identified by the storage device’s IP address, and then the object’s physical position on the storage device. But you want to access this object collection, that is spread out over multiple devices, as a single resource, with one IP address and a single numbering of the objects. The trick is, to have one machine be the gateway to the other machines or domains.

One possibility is that you let the gateway host a *union*. A union is no more than an expression, that returns a collection of objects that combines all the objects coming out of different sources into one collection. If you *add* an object to the union, the objects added are equally spread out over the sources.

The merged domain can be very widely spread as such. You can include any resource within the union.

The union could be stored as an index, in case of which the results of the expression are permanently stored and maintained real-time. This union index is a list of references to all the objects that are spread out over the multiple domains. For each object, the IP address and the Object Position is stored. The size of such an index is acceptable. I’m not sure if a stored union index would be faster, than an unstored union. The union index would best reside on a single machine: on the gateway itself. In theory the central union index could also be distributed over multiple machines, but that would require the union index to be again *placed* on a *merged* site. It is not wise for the union index of a merged site, to be placed on a merged site again. That would not be a good idea.   
The machines you are merging, are best accessed *only* through the gateway. However, this is not a requirement at all. If external changes could be made separate from the merged domain to a machine within the merged domain, the gateway would have to pick up events from that machine and adapt the index accordingly.

It can also be, that on a single computer there are multiple permanent storage devices. The machine may only have one IP address, so will already be a single site. The object ID’s on the multiple storage devices can also overlap. In that case also an index is used on the local machine, to create a single numbering for all the objects spread over the multiple storage devices. The index will not hold IP addresses and object positions, but device ID’s and object positions.

Another option, that I formerly proposed, was not as good. The proposition was: just use a single numbering of bytes over all the storage devices, by having one number range be about the first disk, and the next number range about the second disk, and so on. But this creates a dangerous situation. What if the first disk is a virtual disk, of which the size could be increased. Then you can create number overlap if the size of a device is increased. You also have this problem if you migrate the data of one disk to a new disk, that is greater in size.

I’m not sure yet if an Object Position will be the exact byte position on disk, or identified by both a Storage ID and the byte position within that storage, or somehow another way to identify a position in another subdivision in files. I am not sure about the exact way I will store the data on disk. In certain ways of storing the objects on disk, it might work to use a different range of numbers for each disk. I’m not sure.

Note, that site merging can also make a single collection of objects out of home-hosted objects on multiple terminal computers. However, the merge has to be hosted on a single gateway, that holds the union.  
A terminal computer could also host its own union, that combines the objects stored on the terminal computer with a collection of objects on the internet. That way, you can combine local resources with ones on the internet, without exposing the local resources *to* the internet.

Details about Site Merging will eventually be moved to a subject under Internet Concepts when those articles are further worked out.

#### Parallel processing

Aside from spreading objects, modules, classes and methods (all *objects* in a way) over multiple machines, you can also spread *threads* over multiple machines, to spread the *workload*, instead of the data. This is called parallel processing.

In parallel processing, the processing of data is spread over multiple machines and later the results are recombined.

Bits of work are delegated to computers that take part in the parallel processing scheme.

Parallel processing can not be applied in every situation. The computation performed has to lend itself for it.  
The computation should not require any sequentiality. In many situations things just need to happen one thing after another, in case of which it does not make as much sense to spread the work over multiple machines. This is exactly where you can’t apply parallel processing. For things that cannot go parallelly, you can’t use parallel processing at all.

If the results from multiple machines should combined before moving on to a next step, the waiting until the computers are all done should be worth it. These points at which there must be waited until all the results are gathered, are also called points of sequentiality.

It would also be nice if the delegated computations do not have to be done synchronously. That means, that there is no requirement for waiting until a computer is done at all. So no point of sequentiality even follows.

Things that don’t need to be done in a particular order, can be done all at once.

I have plans to make something, that automatically can determine the optimal execution order of a method, when you only specify, what the method is supposed to do, but not in what particular order. This is called the Automatic Execution Order concept. Automatic Execution Order can automatically see which things can be done in parallel. In those cases parallel processing can be applied.

Parallel processing is most effective when huge amounts of data need to be processed, that don’t have to be processed in a particular order.

Even though you spread the threads, you still have to transport the data that is processed in those threads to the computer on which the thread is running. All data has to be communicated over the network. All the data to process, and all the process results have to be transferred over the network. If the computation is much harder than the transportation of data, than it might be worth it to parallel process it. Or at least, there must be some sort of viable ratio to it.

There should be a central host of the parallel process. This host manages the delegation of work to the different computers.

The ratio that makes it viable to parallel process something looks something like this:

```
Total time to process > total time to process / amount of clients + host total time for transport + total client time for transport.
```

Summary of requirements for parallel processing:

- Processing of data spread over multiple machines
- No sequentiality, only parallellity
- Waiting till all computers are done
- No requirement for waiting till a computer is done at all
- Automatic execution order
- Data transfer
- Central host

There is also another reason to spread workload over multiple machines, other than parallel processing. Serial processing can also be spread over multiple machines, to not keep a single machine busy for too long, so a machine can more easily pick up other tasks, but this is another topic.

#### Mirroring & synchronized copies

At first I thought mirroring would be multiple copies being accessible as a single instance, that always stay identical. Somewhere along the way I realized that this could make reading an object faster, but writing to the object would become really slow, because the multiple copies would have to stay synchronous. It would also require a lot of extra administration under the surface, and it would become quite hard to realize.  
It simply isn’t easy to link all the copies around the world together, keep them synchronous at all times, and have any gain in speed at all.

I realized that mirroring that way wasn’t even that important a concept, and there might not even be any gain to it this way.

Then I decided to keep it simple and let mirroring be no more than having a copy, that can be synchronized with its original. Finding the closest-by mirror is only considered an advanced feature, that is not to be happening automatically all the time.

A mirror is no more than an upgraded object reference, that stores a copy of the original object. You can synchronize the mirror to the original, by replacing the mirror copy by the data of the original object. A mirror is only intended for reading. Writing should be done to the original.

In theory, any reference to an object can become a mirror, for faster access.

A user could synchronize a mirror to the original, or a batch process could run, synchronizing a whole mirrored site.

Mirroring in this sense is a form of caching. You are keeping a copy closer to you on the network, in order to access it faster. Only, a mirror is there permanently, a cache layer is cleared after flushing it to the target storage. You can also keep a local mirror, that you can access offline. This creates the same functionality as keeping a local copy of something, only this copy always links back to the original.

A mirror doesn’t have to be up-to-date. That’s a consequence of accessing a mirror. But this should not be considered a problem.

A nice thing about mirroring would be to be able to find the mirror that is closest to you, the one that you have fastest access to. If you’re going to want that, you’re going to have to have a mirror portal, that has references to all the mirrors, and can pick out the one closest to you. The mirror portal could be the original object itself, but it doesn’t have to be, or otherwise the feature would only be available when you configure the original object to maintain links to all the mirrors that exist and the original object might not feel like doing that. Therefore, the original object does not have to be the mirror portal.

What counts here for objects, also counts for modules and classes, because they are basically also objects. They can also be mirrored. It also counts for methods. Because methods are also stored as data, they can also become data that is duplicated multiple times. However, duplicates of methods can run separately, but they are operating on the same data anyway, and it will be like running the same method concurrently.

When a mirror would be *writable*, the changes to it should be ventilated back to the original. In that case it’s not called mirroring, but it is called *synchronized copies*. Changes are not ventilated back to the original straight away. A synchronized object may be put on an internet site closer by, or even be stored locally. Then you can make changes to the object when you are offline, and ventilate changes back to the original when you are online again.

#### Connection Lost!

On the internet, it can always happen that a computer crashes. It might be just a computer that was routing data. In that case, the Internet Protocol will make sure the packet is sent again, using a different route, and usually everything will be ok. However, it can also be, that a more important computer crashes, a computer that holds a database, or an important index to data around the world. In that case, it would not be so nice, to have that computer hang.

It is always *processes* that are affected by a computer that hung. It’s never data itself that is affected by a hanging computer. It’s always something accessing and processing the data. So a computer that crashed affects a running method. Hanging computers can cause a method to fail. The main thing that happens to a method when it fails, is that the results of the method are rolled back, the calling method is rolled back, and so on, until there is a method that catches the error, and that will stop any more from rolling back. The details around what happens when a method fails will are covered in Errors & Warnings, but the subject is also covered in Design Time = Run Time in Fundamental Principles. 

You could also think of a scheme in which you cache the effects of a method, and send it over the line again later, but this will not work in every situation. You can see it as an application of a synchronized copy in that case. Perhaps on failure as such, it could be an immediately instantiated synchronized copy. Perhaps the method will keep running as long it can just use such synchronized copies, until it reaches a point where it can’t anymore, and *then* it fails.

A backup machine may be an effective concept to use, to keep the method running. With the backup machine concept, a resource is duplicated on multiple machines. The multiple duplicates are kept identical at all times, contrary to mirroring, in case of which the duplicate always lags behind. Logically, keeping them synchronous can make them slower than having a single machine.

The backup machine concept is also effective, in cases where a computer or disk has reached its end of life, and will never be up and running again at all.

### Implications for other concepts

Having the internet function as a single computer can have implications for other concepts. In each concept it must be considered how it is applied under the principle *internet as a single computer*. It’s not a fundamental principle for nothing. But I am sure that I will come up with a solution for it in each of those cases. I will not cover all concepts here. The current article adequately describes the idea behind internet as a single computer and how the main problems around that are solved. However, I will cover the concept of Collection here, just to demonstrate. 

#### Collection

The *Collection* concepts make is possible to query for objects as if Computer Language were a relational database. In relational database, all objects of a certain class are stored in one table in a single database. In Computer Language the objects of a class can be spread all around the internet. This becomes a problem, because you can't search the whole internet for objects.

If you want to query the whole class, an index must be hosted somewhere, that is simply a list of pointers pointing to all the objects of that class that are scattered around the earth. In that case, the objects of that class are obliged to always register themselves in that index.

But the real solution is to accept you will no longer be querying the whole class of objects. You will be querying objects from a specific collection. You don’t have a central database, so not all objects of the same class will be centrally registered. The objects of a class are spread all around the world. This may blow the socks off some relational database purists. These people usually insist, that when selecting objects from a table, you are querying the whole class. So the table must have a singular name, not plural, because it references a class, not a collection. From now on you are not querying a class: you’re querying a collection, which is a resource that contains a *selection* of references to objects of a certain class. This collection *might* represent all the objects on the internet of this class, but it may very well not be. So you’re querying a collection, not a class, so for all of you that insist table names should get singular names, table names will usually be *plural* again. Believe it or not, there are internet forums full of people fighting about that.

In the future you can also query a list of objects that have different classes. If the different classes have mutual members, you can set criteria for these members. When objects of different classes have an interface in common, they have mutual members. If you select objects setting criteria for attributes, and an object doesn’t even have this attribute, the object won’t be part of the selection at all.

It’s all up to the discretion of the people designing the system, if they are going to have a list of object that have an arbitrary class, a list of object that have at least one specific interface in common, a list of object that can only have a limited set of classes, or objects of exactly the same class. You can set this for the collection your are publishing: a programmer / system designer can set whether the class is fixed or not, or whether the objects added to the collection must at least implement a certain interface, or the objects in the collection can only have particular classes.

### Integration Modules

Integration modules are created, so that existing systems can participate in the scheme, and integrate into the whole system. This imports loads of functionality available through the internet available through other technologies. Web pages can be integrated into the object landscape. A relational database can be accessed as if this data is part of the same object system. File systems can be accessed like objects. Module systems can run, such as ActiveX, etcetera. Soap services are accessible. Databases are accessible through ODBC links.  
There are also integration modules for different file types and network protocols that the Software System doesn’t really use itself.

It also goes the other way around: any functionality that runs inside the system can be exposed through another technology, so anything functioning inside Software System is accessible from other operating systems too. You can access the object living inside software system as a relational database, as a file system, you can access them through SOAP... You can also access user interfaces built for Software System from a web browser on any operating system.

### Requirement Summary

Here follows a summary of all the principles and concepts required to make the internet function as a single computer.

There are seven groups of requirements for turning the internet into single computer:

- Communication between computers
- A unified paradigm for all digital objects
- A single bulk of storage
- Execution of programs across computer boundaries
- Security
- Control of concurrent use
- Failure handling

There are many concepts that need to work together in order to achieve this:

- Communication between computers

    - The internet protocol
    - Uniquely identifying resources on the internet
    - Network being able to handle the traffic
    - These concepts create a lot of traffic:
        - Methods
        - Events
    - Site Merging
    - Parallel Processing
    - Copies / Mirroring
    - Synchronized Copies
 
- A single bulk of storage:
    - Cache
    - Unify Disk & Memory Based
    - Streaming Access
    - Site Merging

- A unified paradigm for all digital objects:

    - A default expression in diagrams
    - Integration modules, to integrate any system into the same paradigm for digital objects:
        - Web 
        - Hyperlinks = Referential Structure
        - Relational Database IO
        - File System IO
        - Module Systems IO
        - SOAP IO
        - ODBC IO
        - E-mail
        - File Types IO
        - Protocols IO

- Execution of programs across computer boundaries:

    - Internet Threads
    - Parallel Processing

- Security:

    - Access Control

- Control of concurrent use:

    (potentially involved)

    - Locking / Transactions
    - Undo
        - Undo histories are cross linked when multiple users are using the same data at the same time.
    - Events
    - Automatic Execution Order

- Failure handling

    - Backup Machine
    - Errors & Warnings
    - Synchronized Copies

Other concepts do enrich the landscape of the internet, but are not requirements for making the internet work as a single computer.

In each concept it must be considered how it is applied when the internet needs to function as a single computer.

### Loose Ideas

*The texts below are loose ideas, yet to be turned into good documentation.*

Internet as a Single Computer,  

Met een synchronized copy of met een caching scheme kun je daarmee packets opsparen tot je ze verstuurd. Als je in een method een remote waarde zet, die je vervolgens weer gebruikt, kan de waarde die je leest oud zijn dan.

Wanneer je klaar bent met data, is dat niet subjectief?  
Wanneer mag een waarde weer veranderen in iets willekeurigs?

JJ

-----

Internet as a Single Computer,

Load balancing:  
Bepaalde onderoudsprocessen automatisch gespreid kunnen laten schedulen. Je kunt hieronder ook rekenen het spreiden van processorkracht en opslag gebruik door middel van site merging en parallel processing.

JJ

-----

Internet as a Single Computer,

In 'Connection Lost!':  
What if in the rollback the resource to rollback a change on, cannot be reached?

JJ

-----

Internet as a Single Computer,

Ik heb toch het idee, dat er iets niet klopt,  
dat er iets te complex is.  
Dat is waarschijnlijk ook zo.  
Er zijn veel dingen niet 100% helder en niet 100% uitgewerkt. Er worden ook veel details genoemd, die in een ander artikel thuis horen, terwijl alleen de samenhang tussen dingen genoemd had moeten worden, en de details overschaduwen de samenhang.  
Failure is een grote onduidelijkheid.  
Concurrency ook.

JJ

-----

Internet as a Single Computer,

There are too many comparisons to existing systems in my explanations. It clouds them. But it's all because of it being new material. I just try to convince people, that are used to present day techniques. In the future, I shouldn't do that, because I'd spend too much time defending the system. You should just describe it, not defend it. But for now there's no other way.

JJ

-----

Internet as a Single Computer,

Ik wil het fysieke pad van data overdracht / routing via het internet zien. Kan dit makkelijk in het D., aangezien het fysieke en logisch daarin moet samensmelten?

JJ

-----

Internet as a Single Computer,
Caching  
2008-09-08

In essence: things need to be on the same computer in order to use them in the same operation. This counts in particular for the smallest units of operations, that software can let hardware execute. A CPU can only operate on registers and memory. If you want it to operate on something else,
that something else first needs to be loaded into
memory or into a register. Perhaps this fundamental caching need can be propagated to larger operations on objects,
that are spread around the world.

JJ