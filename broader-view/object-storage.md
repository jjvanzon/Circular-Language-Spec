Encircle Language | Broader View
================================

Object Storage
--------------

`[ Preliminary documentation ]`

*Object Storage* is the binding force between basic data structures on storage devices and the object logic inside the new computer language. It is about how basic data structures are used to store objects. Not all of these principles are original, because many other systems use them, but they were isolated here in a single folder as a single group of concepts required to turn storage into objects.

The documentation is not finished. It is the bone-structure of documentation yet to be finished. It does sum up the required concepts to turn basic data structures into digital objects. Some of the concepts, though, should be moved elsewhere to another *Storage* documentation section. Into this bone-structure, loose ideas are dropped as well as (unfinished) texts out of the documentation of the new computer language version 0.9, as well as texts made during the development of the new computer language version 2.0. Software has been developed using these concepts, because both those versions of the new computer language had to do with storage principles in order to turn basic data structures into digital objects. But not all storage principles were used inside those implementations yet.

The *Object Storage* folder contains the following sub-folders:

- ### Introduction

    - This folder is empty. *Object Storage* may require an introduction article later.

- ### Unify Disk & Memory

    - One of the tasks of the *Object Storage* module is use disk and memory storage in a unified way. Objects should not be actively stored on disk and actively loaded into memory. Stored objects should automatically load into memory when being operated on. Memory works like a caching mechanism for stored objects. Unifying disk and memory is about using objects, that are persistent, while not worrying about actively saving them to disk or performance lags of disk-based objects compared to objects stored in memory.

    - The ideas about unifying disk and memory are not fully worked out yet. The article only contains a throw-together of ideas. It was not implemented inside any of the versions of the new computer language yet. Unifying disk and memory was the most important principles yet to be implemented inside version 2.0 of the new computer language, but then developments took another course.

- ### Caching

    - *Caching* may not be part of *Object Storage* in the future. *Caching* is put directly under *Storage*, right next to *Object Storage*. This folder is empty. The document *Internet as a Single Computer*, though, in another part of the documentation, has a good description of the idea behind how caching will be applied inside the new computer language (in the section *Cache Layering*).

    - No such caching mechanism has not been developed yet, though, but it is important to have it, when developing a serious version of the new computer language.

- ### Reference Counting

    - Object lifetime will be controlled by a reference counting mechanism. When nothing refers to an object anymore, it is automatically deleted from the system.  
    You may oppose this, when looking at a system with a relational database table approach, but if an object is still in a table, then that also counts as one reference, so objects will never suddenly disappear from a table.

    - The reference counting article is not finished yet. It is just a throw-together of ideas. Reference counting was an optional mechanism inside version 0.9 of the new computer language. Reference counting was to be applied to the storage mechanisms of version 2.0 of the new computer language, but that did not get off the ground, because developments took another course.

- ### Destruction

    - When the reference count of an object becomes 0, then the object is destroyed. Object destruction, and how it is performed, should be discussed in this article.
     
    - The article is not written yet. In the realized versions of the new computer language, object destruction was always borrowed from the underlying system, and never actively implemented inside any of the versions of the new computer language yet.

- ### ID's

    - ID’s are numbers that identify an object. The same object can be referenced from many different places. Each of those places can give the object an extra ID. So an object can have several ID’s. Most of the times, the ID is a position in a list. An object can also get its own unique ID, but this ID will be based on the *position* in one central list, so it is still the same concept.

    - This article contains a lot of loose ideas about the subject, but was not turned into well-readable text. The concept of identifying an object by its position in a list was applied in both versions 0.9 and 2.0 of the new computer language. It is the fastest reference to an object there is.

- ### Positions

    - This concept emphasizes, that there is a difference between an object in a list and a position in a list. You should not use the term ‘object’ where you really mean ‘position in a list’.

    - The article is not finished. The concept was applied inside *Basic Data Structure* modules, to properly use the term object and position in the identifiers in the basic data structure classes.

- ### Removing Fields

    - It should be easy to delete a field from a list of objects. That is what this article should discuss. When you store objects as a flat table with one row being followed by the next, and all the *fields* of a row being placed in a sequence, it is not easy to remove fields from that table of objects. When you store each field in a separate sizable storage space, you can easily delete fields from the system.

    - The article is not finished yet and is in Dutch for now. Easily removing fields like that was not implemented yet in versions 0.9 and 2.0 of the new computer language.

- ### Changing Field Sizes

    - It should be made easy to alter a text field’s size. It is easier to store fields with a constant binary size, but text fields you would want to make bigger, when texts you want to enter in it do not fit in it anymore. A solution for that should be found and described in this article.

    - This article is not finished yet. Versions 0.9 and 2.0 of the new computer language used String objects intrinsic to the environment on which they were based, so they borrowed this functionality from the system. Both versions did not manage object storage on disk, except for saving to XML, so the difficulty of changing field sizes was never encountered during the development of those systems.

- ### Primary Identification

    - *Primary Identification* is a concept out of version 0.9 of the new computer language. In that system you could identify an object __by object__ or __by ID__. Version 0.9 of the new computer language used the intrinsic object system of VB6. You could set for each related list, whether objects were identified by a VB6 *object reference* or by a *number*, that is the position inside the related list (the ID). A related list’s primary identification influenced other concepts, such as the __Add__, __Remove__ and __Search__ methods.
     
    - The article is a description coming out of the old documentation of version 0.9 of the new computer language. In a future version, the concept may not be needed anymore.

- ### Size Of Object

    - This concept should allow you to retrieve the size of an object. Retrieving the size of an object is not straightforward, because there are several ways to count an object’s size. You can count the size of its own binary storage, you can count the sizes of sub-objects with their logical residence inside it, or you can count the sizes of all sub-objects directly or indirectly referenced by the object.
 
    - This article is not written yet. It should cover all variations of counting an object’s size. The concept has not been implemented yet inside either version 0.9 or version 2.0 of the new computer language.

- ### Do Not Store Empty Lists

    - To limit storage use, it may be an idea to not store a related list, if there aren’t any items in it yet. The class will define the lists anyway. This saves storage space. This is really an issue for the technical implementation of the new computer language, but it is comforting to know that you don’t need to care much about having many related lists in a class, when most of the related lists will stay empty.  

    - This article is not yet finished, and the concept has not been implemented in either version 0.9 or version 2.0 of the new computer language.