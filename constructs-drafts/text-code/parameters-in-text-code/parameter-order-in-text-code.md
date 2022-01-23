﻿Construct Drafts | Parameters in Text Code | Parameter Order in Text Code
=========================================================================

`[ Deprecated documentation ]`

The article *Parameter Order* introduced the concept of an ordered list of parameters. In text code, you can just list them out in that order then. Textual display is totally preliminary, because text code of Circular is totally not worked out yet.

It is not clear yet, how it might be displayed in a command definition, that the parameters are not only named, but also ordered.

What is clear, though, is that if the parameters are not ordered, then in text code, you might use the parameter *names* in a call to a command:

```
Command  (  Parameter B  =  423  ,  Parameter A  =  Object A  )
```

You can put the parameters in any order. That’s the funny thing about text: even though things conceptually do not require a particular order, you can still only put them in a certain order.

And when the parameter list *is* ordered, you can leave out the names in the parameter list of a command call, and simply line up the parameters in the appropriate order:

```
Command  (  423  ,  Object A  )
```

Command calls and command definitions are not really different in Circular. They are both just command objects, so how can there be a difference in the display of command definitions and command calls? That is not clear yet, but it is to be worked out in a later project, when text code is further worked out, or differences in behavior of classes and instances are worked out.