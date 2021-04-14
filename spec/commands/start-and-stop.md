Encircle Language Spec | Commands
=================================

Start & Stop
------------

`[ Preliminary documentation ]`

__Contents__

- [Introduction](#introduction)
- [Previous Execution Command](#previous-execution-command)
- [Rollback Execution Command](#rollback-execution-command)
- [Rollback Execution State](#rollback-execution-state)
- [Faster Backwards Execution Command](#faster-backwards-execution-command)
- [Faster Backwards Execution State](#faster-backwards-execution-state)
- [Slower Backwards Execution Command](#slower-backwards-execution-command)
- [Slower Backwards Execution State](#slower-backwards-execution-state)
- [Reverse Execution Command](#reverse-execution-command)
- [Reverse Execution State](#reverse-execution-state)
- [Play Execution Command](#play-execution-command)
- [Play Execution State](#play-execution-state)
- [Slower Execution Command](#slower-execution-command)
- [Slower Execution State](#slower-execution-state)
- [Faster Execution Command](#faster-execution-command)
- [Faster Execution State](#faster-execution-state)
- [Go To End Execution Command](#go-to-end-execution-command)
- [Next Execution Command](#next-execution-command)
- [Pause Execution Command](#pause-execution-command)
- [Pause Execution State](#pause-execution-state)
- [Wait Execution Command](#wait-execution-command)
- [Wait Execution State](#wait-execution-state)
- [Timer Execution Command](#timer-execution-command)
- [Timer Execution State](#timer-execution-state)
- [Not Runnable Execution State](#not-runnable-execution-state)
- [Stop Execution Command](#stop-execution-command)
- [Stop Execution State](#stop-execution-state)
- [Finished Execution State](#finished-execution-state)
- [Record Execution Command](#record-execution-command)
- [Record Execution State*](#record-execution-state)
- [Error Execution State](#error-execution-state)
- [Warning Execution State](#warning-execution-state)
- [Normal Speed](#normal-speed)
- [Diagram Notation](#diagram-notation)
- [Implementation](#implementation)

### Introduction

An executable object can be run, paused, stopped, recorded, put in reverse, etcetera. Those are called *execution commands*.

You can also invoke an execution command on a thread, which is a string of commands, that automatically follow each other up. A thread, however, can also be considered a single command as well.

There is a distinction between an *execution command* and an *execution state*.

An executable object has a *state* of execution, for which the same terms are used as for the *execution commands*: play, stop, record, etcetera.

The following execution states and execution commands exist:

- __Previous__
- __Rollback__
- __Faster Backwards__
- __Slower Backwards__
- __Reverse__
- __Play__
- __Slower__
- __Faster__
- __Go To End__
- __Next__
- __Pause__
- __Wait__
- __Timer__
- __Not Runnable__
- __Stop__
- __Finished__
- __Record__
- __Error__
- __Warning__

Which execution commands you can invoke, depends on the execution state the command is in. When a command has finished, you can not play it again. When a command is not runnable, you can not play it at all.

The following ones can be execution *commands*:

- __Previous__
- __Rollback__
- __Faster Backwards__
- __Slower Backwards__
- __Reverse__
- __Play__
- __Slower__
- __Faster__
- __Go To End__
- __Next__
- __Pause__
- __Wait__
- __Timer__
- __Stop__
- __Record__

So that excludes the following ones from being an execution command:

- __Not Runnable__
- __Finished__
- __Error__
- __Warning__

The following ones can be execution states:

- __Rollback__
- __Faster Backwards__
- __Slower Backwards__
- __Reverse__
- __Play__
- __Slower__
- __Faster__
- __Pause__
- __Wait__
- __Timer__
- __Not Runnable__
- __Stop__
- __Finished__
- __Record__
- __Error__
- __Warning__

So that excludes the following ones from being an execution state:

- __Previous__
- __Go To End__
- __Next__

There is a big difference in difficulty of implementing the execution commands. This is irrelevant to their usage, but might affect their availability in early stages of development of Encircle. There are five categories of difficulty of implementation of execution commands and execution states. Here they are going from simple to difficult:

- Play, stop, next, previous, not runnable, finished
- Forward at arbitrary speeds
- Waiting
- Error and warning
- Record
- Going in reverse

The states __Play__, __Stop__, __Next__, __Previous__, __Not Running__ and __Finished__ are the most basic and more easy to implement. They are implemented first. Commands going in reverse are the worst in complexity. They include __Reverse__, __Slower Backwards__, __Faster Backwards__ and __Rollback__. They are rollback and undo functionality, that is much harder to implement. So the execution commands might not all be available in one blow.

Below each execution command and execution state is explained separately.


### Previous Execution Command

The __Previous__ execution command immediately stops the execution of the current command and positions the instruction position to the command previous in line. And if there is no previous sibling command, there might be moved a level up, to the parent command.

The __Previous__ execution command is only available if there is a previous command to go to.

The __Previous__ command might cause a __Stop__ state on the previous command for computation and might cause a __Play__ state on the previous item for playable media, making it start to run immediately.


### Rollback Execution Command

The __Rollback__ execution command might undo all changes of the current command and makes all data return to the state it was before the command had started. If the same data has already been changed by another source it may be overwritten by the original value it had before running the command or the change on that particular data item may not be rolled back at all, or some sort of concurrency resolution might be applied, but concurrency issues might be dealt with later.

In case of regular computation, a __Rollback__ might be executed as fast as possible. For video, audio or presentation or any other type of running media, Rollback means immediately going to the beginning of the execution.

The __Rollback__ execution command is only available if the command has started at all.

The __Rollback__ command might cause a __Rollback__ state on the current command.


### Rollback Execution State

After a __Rollback__ has executed, the command might be in Rollback state (rolled back), which is actually a __Stop__ state, but then after a __Rollback__.


### Faster Backwards Execution Command

The __Faster Backwards__ execution command might start or continue a rollback in a fast pace or faster pace or faster, but never entirely at top speed.

The __Faster Backwards__ execution command is only available if the command is finished or right in the middle of executing or rolling back.

The __Faster Backwards__ execution command might cause a __Faster Backwards__, __Reverse__ or __Slower Backwards__ execution state (if it is going faster but still slow).


### Faster Backwards Execution State

A __Faster Backwards__ (going fast backwards) execution state is the system’s ‘subjective’ opinion of whether the current speed of going backwards is faster than average. In that case the command, thread or playable medium might get __Faster Backwards__ execution state.


### Slower Backwards Execution Command

The __Slower Backwards__ execution command might start or continue a rollback in a slow pace, slower pace, or as slow ‘as possible’.

The __Slower Backwards__ execution command is only available if the command is finished or right in the middle of running.

The __Slower Backwards__ execution command might cause a __Slower Backwards__, __Reverse__ or __Faster Backwards__ execution state.


### Slower Backwards Execution State

A __Slower Backwards__ execution state (going slower backwards) is the system’s ‘subjective’ opinion of whether the current speed of going backwards is slower than average. In that case the command, thread or playable medium might get __Slower Backwards__ execution state.


### Reverse Execution Command

The __Reverse__ execution command might start a rollback at normal speed. In case of regular computation, normal speed might be top speed. For video, audio or presentation or any other type of running media, normal is not as fast as possible, but the normal speed of presentation but then in reverse.

The __Reverse__ execution command is only available if a command is finished or anywhere in the middle of running. 

The __Reverse__ command causes the execution to get the __Reverse__ execution state.


### Reverse Execution State

A command or other executable object gets the __Reverse__ execution state if it is rolling back at normal speed. For regular computation, normal speed is top speed. For playable media, normal reverse speed is the same speed as normal forward speed, but then in reverse.

If the speed is slower or faster than considered average, the execution state might be set to either __Faster Backwards__ or __Slower Backwards__.


### Play Execution Command

The __Play__ execution command might start or continue execution at normal speed. In case of regular computation, normal speed might be *top* speed. For video, audio or presentation or any other type of running media, normal is not as fast as possible.

The __Play__ execution command is only available if a command is runnable or anywhere in the middle of running.

The __Play__ execution command might cause the __Play__ execution state.


### Play Execution State

__Play__ is the execution state a command gets when going at normal speed. In case of regular computation normal speed is *top* speed. In case of playable media normal speed is the normal playing speed of the medium.


### Slower Execution Command

The __Slower__ execution command might make the current execution speed slow, or slower, but never come to a complete halt. If the command is in a rollback, it might make the command start to go forward again.

The __Slower__ execution command is only available if the command is runnable or in right in the middle of running.

The __Slower__ execution command might cause a __Slower__, __Play__ or __Faster__ execution state.


### Slower Execution State

A __Slower__ execution state is the system’s ‘subjective’ opinion of whether the current speed of going forward is slower than average. In that case the command, thread or playable medium might get __Slower__ execution state.


### Faster Execution Command

The __Faster__ execution command might make the current execution speed fast, or faster, but never top speed. If the command is in a rollback, it might make the command start to go forward again.

The __Faster__ execution command is only available if the command is runnable or even right in the middle of executing or rolling back, which might turn around the direction.

The __Faster__ execution command might cause a __Faster__, __Play__ or __Slower__ execution state.


### Faster Execution State

A __Faster__ execution state is the system’s ‘subjective’ opinion of whether the current speed of going forward is faster than average. In that case the command, thread or playable medium might get __Faster__ execution state.


### Go To End Execution Command

The __Go To End__ command might make the command fast-forward to the end at top speed. For normal computation this is the same as __Play__, except when normal speed is set to slower than top speed. For runnable media this is not the same as play, but going to the end of the execution as fast as possible.

The __Go To End__ execution command eventually causes the __Finished__ execution state, once it is done going forward as fast as possible. Until then, the execution state is __Faster__.


### Next Execution Command

The __Next__ execution command immediately stops the execution of the current command and positions the instruction position to the next command in line. And if there is no next sibling command, there might be moved a level up, to the parent command.

The __Next__ execution command is only available if there is a next command to go to.

The __Next__ command might cause a __Stop__ state on the next command for computation and might cause a __Play__ state on the next item for playable media.


### Pause Execution Command

The __Pause__ command pauses execution at the point it is at, until you press __Play__ or another command again.

The __Pause__ command is available when a command is anywhere in the middle of executing.

A __Pause__ can also be put on an executable object, that is not yet executing. In that case, the system might pause as soon as the object *is* going to execute.

You can also a __Pause__ on a definition. In that case any call to that definition might cause the system to pause.

A __Pause__ can also be set on a sub-command inside a definition. Then, each call to the definition might pause on that particular spot in the execution.

The __Pause__ execution command causes a __Pause__ execution state.


### Pause Execution State

See the section above: *Pause Execution Command*. A command might get the __Pause__ state if a __Pause__ was invoked on it.


### Wait Execution Command

It may be useful for an execution to be able to wait on another execution.

The __Wait__ execution command is like __Pause__, but then another executable command or a thread is selected to wait on. As soon as the other executable command is done or the selected thread has finished, the execution of the waiting command or thread continues.

The __Wait__ command is available when a command is anywhere in the middle of executing.

The __Wait__ execution command causes the __Wait__ execution state.

The implementation may use the fact that a single executable object might have multiple next-command references. The waiting command could register itself as a next command of another command in order to wait on it.


### Wait Execution State

An executable object might get the __Wait__ state if a __Wait__ execution command was invoked on it.


### Timer Execution Command

The __Timer__ command is not really an execution command. It lets you schedule the execution of a command. You could schedule it at any selected moment in time, seconds, or month from now or repeatedly have the command run at set times.

A __Timer__ can be set on an executable object, but then it can only be run once. A __Timer__ can also be set on a definition, which might create a call to it at every time it is scheduled.

A __Timer__ execution command might cause the __Timer__ execution state. At the times it is scheduled it might turn into a __Play__ state. At times, that it is not running, it is put in the __Timer__ state again and if it is no longer scheduled in the future anymore, it might get the __Finished__ state.

__Timer__ might be a good excuse to have an inactive command class redirect to another inactive command, and time the redirector, to cause a scheduling of a command definition, that resides elsewhere.

You can also put a __Timer__ on a __Record__ command, instead of a __Play__ command, to start recording something at a set time.


### Timer Execution State

An executable object gets the __Timer__ state if the executable object is scheduled to execute in the future at a given time.


### Not Runnable Execution State

A command definition might often have the __Not Runnable__ execution state. Command definitions are mostly inactive command objects. Inactive command object can never be run, because inactive command objects are usually command definitions and running a command definition may cause the command definition’s default values to change, while a command definition is considered to be static and unchanging. That’s why inactive command objects might get the execution state __Not Runnable__. Any inactive reference to a command object is also __Not Runnable__.


### Stop Execution Command

The __Stop__ command might immediately stop the execution of the command or thread. This can be dangerous, because it is better to either let a command finish completely or roll it back entirely, and not leave it in some intermediate state. But in a lot of other cases it is not much of a problem.

But it should be possible to make a command ‘unstoppable’, sort of like a database transaction, so that it can either be entirely completed or completely rolled back, but never permanently stopped right in the middle.

The __Stop__ command is only available when a command is right in the middle of running and if the command is not marked as unstoppable.

The __Stop__ command can also be used to stop a recording. In that case it might not have the danger as described earlier.

The __Stop__ command might cause the current command to be put in __Stop__ state.


### Stop Execution State

The __Stop__ execution state is not as dangerous as the Stop execution command. The __Stop__ execution command might end a procedure right in the middle. But if an executable object has not been run yet, it also has the __Stop__ state. After pressing __Stop__, a command might indeed also end  up in the __Stop__ state, but a command also has this state if it has not been run before.


### Finished Execution State

The __Finished__ execution state is there, when the command has completed normally in its entirety. In that case the executable command can not be run again. A playable medium, though, *can* be run again after it has finished.


### Record Execution Command

The __Record__ command can replace a command definition, with whatever action a user or a thread might perform, until recording is stopped.

The __Record__ execution command might cause a command to be put in __Record__ state.


### Record Execution State*

An executable object might get the __Record__ state when it is recording, after a __Record__ execution command was invoked on it.


### Error Execution State

An error may cause an immediate rollback in the new system, but perhaps a program might also pause. Perhaps only in debugging state. In that case, when an error occurs, the execution stops on the current command and the error puts it in the __Error__ execution state.


### Warning Execution State

When debugging and something uncommon happens, the execution might be put in __Warning__ state, but this actually might not might hinder execution, so one could think of a situation in which an execution is in __Warning__ state, but still continues to run.

Any object or reference line could also be put in __Warning__ state if something exceptional, but benign, is going on with it.


### Normal Speed

In a normal situation, normal speed for computation is top speed, and normal speed for a playable medium is the normal speed to play the medium. But you can indicate an alternate normal speed. If you are reviewing a playable medium, that you might be needing to look at in slow motion, you can make slow motion the normal speed. In that case __Play__ means going in slow motion, and __Faster__ means it is going faster than the normal rate of slow motion. If you are debugging, you might also set the normal speed of computation to slower. In that case you can visually follow the execution of the procedures. This normal rate of slow motion might also be the barrier for what the states __Slower__ and __Faster__ might consider the average speed.


### Diagram Notation

Each of the following commands or states has a symbol:

- __Previous__
- __Rollback__
- __Faster Backwards__
- __Slower Backwards__
- __Reverse__
- __Play__
- __Slower__
- __Faster__
- __Go To End__
- __Next__
- __Pause__
- __Wait__
- __Timer__
- __Not Runnable__
- __Stop__
- __Finished__
- __Record__
- __Error__
- __Warning__

The symbols are just about the same as those of media players of today:

| ![](images/2.%20Start%20&%20Stop.001.png) | ![](images/2.%20Start%20&%20Stop.002.png) | ![](images/2.%20Start%20&%20Stop.003.png) | ![](images/2.%20Start%20&%20Stop.004.png) | ![](images/2.%20Start%20&%20Stop.005a.png) |
|:--------:|:--------:|:----------------:|:----------------:|:-------:|
| Previous | Rollback | Faster Backwards | Slower Backwards | Reverse |
|          |          |                  |                  |         |
| ![](images/2.%20Start%20&%20Stop.005b.png) | ![](images/2.%20Start%20&%20Stop.006.png) | ![](images/2.%20Start%20&%20Stop.007.png) | ![](images/2.%20Start%20&%20Stop.008.png) | ![](images/2.%20Start%20&%20Stop.009.png) |
| Play | Slower | Faster | Go To End | Next |
|      |        |        |           |      |
| ![](images/2.%20Start%20&%20Stop.010.png) | ![](images/2.%20Start%20&%20Stop.011.png) | ![](images/2.%20Start%20&%20Stop.012.png) | ![](images/2.%20Start%20&%20Stop.013.png) | ![](images/2.%20Start%20&%20Stop.014.png) |
|  Pause | Wait | Timer | Not Runnable | Stop |
|        |      |       |              |      |
| ![](images/2.%20Start%20&%20Stop.015.png) | ![](images/2.%20Start%20&%20Stop.016.png) | ![](images/2.%20Start%20&%20Stop.017.png) | ![](images/2.%20Start%20&%20Stop.018.png) | |
| Finished |  Record  | Error | Warning | |

The commands can be displayed at the bottom of the screen to execute a selected command or on a thread, that you are following.

![](images/2.%20Start%20&%20Stop.019.png)

The order of the symbols may become different in practice. They might probably put in a straight line. Some of them can not even be execution *commands*, but can only be execution *states*, so those might be left out of the bottom of the screen.

Another example display of the execution commands and execution states:

![](images/2.%20Start%20&%20Stop.020.png)

The following symbols are also possible candidates:

![](images/2.%20Start%20&%20Stop.021.png) ![](images/2.%20Start%20&%20Stop.022.png)

Those symbols could set the speed of going forward or backward, gradually changing it from __Faster Backwards__, __Reverse__, __Slower Backwards__ and to __Slower__, __Play__, __Faster__. The first symbol simply decreases the speed or makes it go faster backwards, and the second symbol simply increases the speed or makes it go slower backwards.

The symbols for actions, that a media player also has, were retained, because I just love symbolic representation and I do not see a need to invent any other symbolic display for this.

An execution state is also be displayed at the bottom of a command symbol, to indicate its state:

![](images/2.%20Start%20&%20Stop.023.png)

The executable command above is currently running at normal speed, since it is in __Play__ state. Here are more examples of executable command object in different states.

The following command is paused:

![](images/2.%20Start%20&%20Stop.024.png)

The following command is finished:

![](images/2.%20Start%20&%20Stop.025.png)

The following command is recording:

![](images/2.%20Start%20&%20Stop.026.png)

The following command is not executable at all:

![](images/2.%20Start%20&%20Stop.027.png)

Any execution state can be indicated for a command object like that.


### Implementation

Do realize, that there is a difference in difficulty of implementation of the execution commands and execution states. Do not try to implement all the execution states and commands in one blow. There are 5 categories of difficulty of implementation of execution commands and execution states. Here they are going from easy to hard:

- Play, stop, next, previous, not runnable, finished
- Forward at arbitrary speeds
- Waiting commands
- Record command
- Commands going in reverse

The states __Play__, __Stop__, __Next__, __Previous__, __Not Running__ and __Finished__ are implemented first. They are the easiest. Going forward at arbitrary speeds includes __Slower__, __Faster__ and __Go To End__. They are nice for slowly running the steps, so you can follow better. Then there are the waiting commands, which are not that hard either. In fact it is quite important to be able to pause, so that one might be implemented sooner. The __Record__ command is easier, than commands going in reverse, but it is much less important than the commands going in reverse. And commands going in reverse are the worst. They are rollback and undo functionality, that is much harder to implement. They include __Reverse__, __Slower__, __Backwards__, __Faster Backwards__ and __Rollback__. Do not implement them all in one blow.
