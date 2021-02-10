|<h1>***Circle Documentation***</h1>|
| :- |
## **Code Concepts Extended**
…

### *Handy Access*

*Handy Access* covers a couple of methods to access objects more easily. Instead of following the whole path to an object, an object is available more directly. It is disputable whether you always want to do this, because it might create unneccesary extra object references, increasing complexity, and it might create confusion about which object you are actually accessing: confusion, that may have been taken away by using the full path to the object. However, handy access methods can also actually be *handy*. If you create an object structure, that is quite complex, and you want to allow a user to operate on it using an easy user interface, you want to make the system look less complex, than it actually is. You can do this by leaving out a lot of redirections and create ‘handier access’ to the objects. Several methods were come up with, and will be discussed in the documentation. Handy access is already implemented in version 0.9 of the new computer language. However, the documentation is not finished up yet.

### *Circularity*

Object structures can form large constructions of one object refering to another. When following redirections from one object to another, you can end up at the same object again. This means that the redirectioning is circular. Circularities are in many cases no problem at all. However, sometimes circularities will make a program hang. It is hard to custom-program a way to handle such circularity problems. Therefore, standard mechanisms are available inside the new computer language to handle all kinds of circularities. When recursively processing an object structure, the process can hang, because at some point it starts to go around in circles. There are several ways to prevent this. One method is to not allow circularities to be formed at all. Another method is, that when processing an object structure, an object is never processed twice. This will make the process stop going around in circles. Another method is to allow a *maximum amount of cycles* to be processed. Circularities in data are not necessarily a problem. It only becomes a problem, when recursively processing the data. The documentation about circularities is not finished yet. It needs to become more refined.

### *Apply*

*Apply* mechanisms are all about how one set of things is applied to another set of things. One set of objects is used to calculate the state of another object.

There are several ways to do this. You may want to apply a calculation as soon as you try to Get the object. You may also want to reassign the result to an object immediately when a dependency changes.

It happens a lot in program code, that something has to be applied to another thing. The easiest example of this would be: when data changes, you have to redraw the screen: the changed data is *applied* to the picture on screen.

To reflect changes to one set of data onto another set of data at exactly the right moments, a large complexity of ‘applies’ has to be implemented. When programming traditional program code, a single ‘apply’ might actually consist of multiple code lines spread all over the program code. The aim of *apply mechanisms*, is to define an *apply* as a separate entity, so that the complexities of applies are simplified to a set of *apply* definitions, instead of having apply-code scattered all over the system. This will also make it easier to actually implement more robust applies than originally possible. A lot of times systems are programmed in a way, that objects get out-of-date, because other data was not applied to it, causing the need of a user-initiated refresh (for instance: a screen refresh), which actually means, that the user initiates the apply himself. The philosophy of *Apply*, is that the system automatically does this *for* you at exactly the right times. Traditionally this is very hard to program and creates complexities in the program code that just are not worth it. With Apply definitions, this is no longer a valid argument: you *can* have everything refresh at the right times, and not bother the user with old data.

All the possible apply methods and implementations are discussed in this documentation folder. However, the documentation is not finished yet.


*Author & Copyright: Jan-Joost van Zon        Date: May 5, 2009  –  January 9, 2011        Location: Oosterhout, The Netherlands        Status: Finished*

