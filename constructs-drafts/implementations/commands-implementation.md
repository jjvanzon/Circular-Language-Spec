Encircle Language Construct Drafts | Implementations
====================================================

Commands Implementation
-----------------------

`[ Out of Scope ]`

### Implementation as an Aspect

The behavior, that turns an object into an executable command, is implemented as the __Command__ aspect. When an object supports the __Command__ aspect, it automatically becomes a command. The code base only needs to support an object’s ability to execute in some basic form. But most of the functionality for commands might be programmed within Encircle itself. The code base only supplies the very minimum basic need to facilitate it.

### Implementation as Stand-Alone

Anything not allowed for command symbols, is allowed anyway, but generates a warning and generates alternative behavior, that IS allowed, because this allows direct conversion back and forth between a command and an object, so there will not be any loss of structure of you just convert an object symbol into a command and back again.
