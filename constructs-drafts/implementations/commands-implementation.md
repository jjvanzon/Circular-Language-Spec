Encircle Language Construct Drafts | Implementations
====================================================

Commands Implementation
-----------------------

`[ Out of Scope ]`

__Contents__

- [Implementation as an Aspect](#implementation-as-an-aspect)
- [Implementation as Stand-Alone](#implementation-as-stand-alone)
- [Changing Inactive to Executable](#changing-inactive-to-executable)
- [Loose Ideas](#loose-ideas)

### Implementation as an Aspect

The behavior, that turns an object into an executable command, is implemented as the __Command__ aspect. When an object supports the __Command__ aspect, it automatically becomes a command. The code base only needs to support an object’s ability to execute in some basic form. But most of the functionality for commands might be programmed within Encircle itself. The code base only supplies the very minimum basic need to facilitate it.

### Implementation as Stand-Alone

Anything not allowed for command symbols, is allowed anyway, but generates a warning and generates alternative behavior, that IS allowed, because this allows direct conversion back and forth between a command and an object, so there might not be any loss of structure of you just convert an object symbol into a command and back again.

### Changing Inactive to Executable

`<< implementation >>`  
When `you design` a command definition, `you` might want to do it using an active command object:

![](images/1.%20Commands%20Main%20Concepts.042.png)

and `test` it `once` by `running the` active command definition:

![](images/1.%20Commands%20Main%20Concepts.043.png)

After that `you can` change it to an inactive command definition and `give` it `the appropriate` default values.

![](images/1.%20Commands%20Main%20Concepts.044.png)

If `you decide` to change `the` inactive command definition back to an active command, then `you can not` run it again, because `the` command object `has` `already` run:

![](images/1.%20Commands%20Main%20Concepts.045.png)

`Others might` still have a reference to it `to be` able to read its output.

If `you` want to run `the` command definition again, `you might` make a call to it instead:

![](images/1.%20Commands%20Main%20Concepts.046.png)

If `you change` an inactive command definition to an executable command definition:

![](images/1.%20Commands%20Main%20Concepts.047.png)

then `you can all of a sudden` run it, which may overwrite `the` executable’s default output values.

### Loose Ideas

*Active* clauses, command calls and active command references in parent commands `are always` private, because `you can not` reference a sub-command.