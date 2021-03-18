Circle Language | Construct Drafts
==================================

Naming
------

`[ Deprecated documentation ]`

### Ideas

*The texts below are loose ideas yet to be turned into good documentation.*

Naming,  
2009-02-10

The ‘As In’ naming expresses a role. A role is synonym to a context. You are giving a name to an object in the context of another object. So that all makes sensen

JJ

-----

Naming / Roles,  
2009-02-10

An object’s role changes based on from which it is referenced.  
As an example, take a Sound 0.9 document:

```
Document.AsBaseInWorkspace
Document.AsBlackBoxInWorkspace
Document.AsInstrumentInWorkspace
Document.AsTemplateInWorkspace
```

Which Workspace reference is filled in, determines the role of the document. Is it a Base, is it a Black Box, is it an Instrument or is it a Template. This naming is also clear English of expressing a role. There is not, however, a Role attribute, that identifies which one is. A hypothetical textual syntax as follows might be readable, however:

```
Document  Is  Base In Workspace
```

But I am not sure yet how that would be implemented.

JJ