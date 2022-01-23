﻿Circular Language Broader View | Extensibility | Reflection
===========================================================

`[ Preliminary documentation ]`

Reflective data is data that describes the structure of a program. The reflective data of a program for instance contains descriptions of classes.

In ordinary programming languages, it is considered something special to be able to access data that describes a program, listing out all the classes and all of its members.

In Circular the program actually *is* a description of the structure of the program. As you make the program, you are creating this data, and it is actually the program itself, that might just be run inside an engine.

Any object simply has a reference to its class. You can access the full description of this class at all times.

In ordinary programming languages, there is textual code that is translated to binary machine code, that can run on a computer. The compiler, that turns text code into binary machine code has to link a method name in the text code to a binary position in the machine code. After everything is compiled, there is no data anymore inside the program, that describes what methods and classes the program is actually composed of.

In Circular, the program is not based on text code and the program is also not translated to binary machine code anymore. The program is run inside an engine and simply consists of data that describes the structure of the program. As you make the program, you are creating this data, and it is actually the program itself, and this data might run unalteredly inside the engine.

Because the program simply *is* data that describes the structure of the program, having reflective data available is such a normal thing, and so nothing special anymore, that I am wondering why I am even writing an article about it...