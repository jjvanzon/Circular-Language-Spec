Construct Drafts | Implementations | Start & Stop Implementation
================================================================

`[ Out of Scope ]`

There may be differences in difficulty of implementing each execution command or execution state. They may not all be implemented in one blow.

There may be several categories of difficulty of implementing execution commands and execution states. Here is an attempt to list them going from simpler to more difficult:

- Play, stop, next, previous, not runnable, finished
- Forward at arbitrary speeds
- Waiting
- Error and warning
- Record
- Going in reverse

The states __Play__, __Stop__, __Next__, __Previous__, __Not Running__ and __Finished__ are the most basic and more easy to implement. They might be implemented first.

Going forward at arbitrary speeds includes __Slower__, __Faster__ and __Go To End__. They are nice for slowly running the steps, so you can follow better. 

Then there are the waiting commands, which might not be the most difficult either.

The __Record__ command might be less hard, than commands going in reverse, but it is much less important than the commands going in reverse.

Commands going in reverse may the worst in complexity. They may be rollback and undo functionality, that is much harder to implement. They may include __Reverse__, __Slower Backwards__, __Faster Backwards__ and __Rollback__.

So the execution commands might not all be available in one blow.

## Detail

You can also invoke an execution command on a thread, which is a string of commands, that automatically follow each other up. A thread, however, can also be considered a single command as well.