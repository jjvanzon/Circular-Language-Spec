Circular Language Construct Drafts | Parameters in Text Code
============================================================

Variable Amount in Text Code
----------------------------

`[ Deprecated documentation ]`

This proposal of textual representation of variable amount of arguments is totally not final yet.

In the article *Variable Amount* it was stipulated, that for backwards compatibility purposes, and textual representation purposes, an array parameter could be typed as being the array, that represents the variable amount of arguments at the end of the parameter list. So the declaration of such a command with a variable amount of parameters may look like this:

```
Command  Command 1  (
    Text  Parameter 1  ,
    Variable  Amount  Number  Parameter List  [  ]  ) 
```

A call may look like this:

```
Command 1  (  "Hello"  ,  524  ,  324  ,  523  ,  74 )
```

But it may also be decided, that variable amount of arguments is not supported at all, but that the textual representation of initialization of an array is put between curly braces as follows:

```
Command 1  (  "Hello"  ,  {  524  ;  324  ;  523  ;  74  }  )
```

That way, the term Variable Amount might not even need to be mentioned in the command declaration:

```
Command  Command 1  (
    Text  Parameter 1  ,
    Number  Parameter List  [  ]  ) 
```