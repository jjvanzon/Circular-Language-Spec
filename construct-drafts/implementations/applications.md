Construct Drafts | Implementations | Applications
=================================================

`[ Out of Scope ]`

## Introduction

Misc ideas about applications using Circular language.

## Loose Ideas

`<< applications >>`

Computer Language,

`[ Dutch ]`

Precieze tijd-statistieken van alle processtappen, zodat je precies weet in welk stukje van het proces de bottleneck zit, niet alleen gewoon dat het proces lang duurt. Dan weet je ook waar het aan ligt, anders is het gissen.

JJ

-----

`<< applications >>`

Command Basics,  
2008-08-17

It seems, that when you have active command references inside different active parent commands, you get a problem. Multiple parent commands need to wait on the referenced command object to finish.

JJ

-----

`<< applications >>`

CL,  
2008-09-18

Execution data.

```
Transport time
    Ways:
        Network (133.1.9.23) - Memory - Disk (\\local\E:)
            14 sec
        Disk - Memory
            15 sec
Processing time
    4 sec
< other times >
```

JJ

-----

`<< applications >>`

Commands,  
2004

There’s a method for turning a command into a class.

Say a command has input objects and output objects. When you call the command you set the input objects. After the call you can read the output objects.

To create a class out of the command you just take over all of the command’s objects. The command itself, stripped from objects, becomes a member of the type too.

You can freely read and write the objects. However, the command might be occasionally run.

The benefits from making a type out of a command is that you can dynamically write and write input objects and read output objects, without having to run a command all the time.

JJ