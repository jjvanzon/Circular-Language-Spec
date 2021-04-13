Encircle Language | Broader View
================================

Object Storage
--------------

`[ Preliminary documentation ]`

*Object Storage* is the binding force between basic data structures on storage devices and the object logic inside Encircle. It is about how basic data structures are used to store objects. Not all of these principles are original, because many other systems use them, but they were isolated here in a single folder as a single group of concepts required to turn storage into objects.

It does sum up the required concepts to turn basic data structures into digital objects. Experiment 0.9 and 2.0 had to do with object storage in order to turn basic data structures into digital objects. But not all the ideas were used inside those implementations yet.

*Object Storage* may involve the following concepts:

- ### Introduction

    - This folder is empty. *Object Storage* may require an introduction article later.

- ### Unify Disk & Memory

    - One of the tasks of the *Object Storage* module is use disk and memory storage in a unified way. Objects should not be actively stored on disk and actively loaded into memory. Stored objects should automatically load into memory when being operated on. Memory works like a caching mechanism for stored objects. Unifying disk and memory is about using objects, that are persistent, while not worrying about actively saving them to disk or performance lags of disk-based objects compared to objects stored in memory.

    - The ideas about unifying disk and memory are not fully worked out yet. The article only contains a throw-together of ideas. It was not implemented inside any of the versions of Encircle yet. Unifying disk and memory might perhaps have been the next principle to be implemented inside experiment 2.0, but then developments took another course.

- ### Caching

    - *Caching* may not be part of *Object Storage* in the future. *Caching* is put directly under *Storage*, right next to *Object Storage*. This folder is empty. The document *Internet as a Single Computer*, though, in another part of the documentation, has a good description of the idea behind how caching might be applied inside Encircle (in the section *Cache Layering*).

    - No such caching mechanism has not been developed yet, though, but it is important to have it, when developing a serious version of Encircle.

- ### Reference Counting

    - Object lifetime might be controlled by a reference counting mechanism. When nothing refers to an object anymore, it is automatically deleted from the system.  
    You may oppose this, when looking at a system with a relational database table approach, but if an object is still in a table, then that also counts as one reference, so objects might never suddenly disappear from a table.

- ### Destruction

    - When the reference count of an object becomes 0, then the object is destroyed. Object destruction, and how it is performed, should be discussed in this article.

- ### ID's

    - ID’s are numbers that identify an object. The same object can be referenced from many different places. Each of those places can give the object an extra ID. So an object can have several ID’s. Most of the times, the ID is a position in a list. An object can also get its own unique ID, but this ID might be based on the *position* in one central list, so it is still the same concept.

- ### Positions

    - This concept emphasizes, that there is a difference between an object in a list and a position in a list. You should not use the term ‘object’ where you really mean ‘position in a list’.

- ### Removing Fields

    - It should be easy to delete a field from a list of objects. That is what this article should discuss. When you store objects as a flat table with one row being followed by the next, and all the *fields* of a row being placed in a sequence, it is not easy to remove fields from that table of objects. When you store each field in a separate sizable storage space, you can easily delete fields from the system.

- ### Changing Field Sizes

    - It should be made easy to alter a text field’s size. It is easier to store fields with a constant binary size, but text fields you might want to make bigger, when texts you want to enter in it do not fit in it anymore. A solution for that should be found and described in this article.

- ### Primary Identification

    - The *Primary Identification* concept came out of experiment 0.9. In that system you could identify an object __by object__ or __by ID__. Experiment 0.9 used the intrinsic object system of VB6. You could set for each related list, whether objects were identified by a VB6 *object reference* or by a *number*, that is the position inside the related list (the ID). A related list’s primary identification influenced other concepts, such as the __Add__, __Remove__ and __Search__ methods.

- ### Size Of Object

    - This concept should allow you to retrieve the size of an object. Retrieving the size of an object is not straightforward, because there are several ways to count an object’s size. You can count the size of its own binary storage, you can count the sizes of sub-objects with their logical residence inside it, or you can count the sizes of all sub-objects directly or indirectly referenced by the object.

- ### Do Not Store Empty Lists

    - To limit storage use, it may be an idea to not store a related list, if there aren’t any items in it yet. The class might define the lists anyway. This saves storage space. This is really an issue for the technical implementation of Encircle, but it is comforting to know that you don’t need to care much about having many related lists in a class, when most of the related lists might stay empty.  
