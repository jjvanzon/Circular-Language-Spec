Circular Language Broader View | Binarals
=========================================

`[ Draft ]`

*Binarals* might be analogous to *literals*. A literal may be a textual representation of an object's state (for instance a literal number `3` or literal string `"Hi!"`). A *binaral* might be the translation of an object’s state to a single stretch of consecutive binary. The binaral may for instance be compiled computer code, or an object's data in a specific binary layout.

Sometimes you have an object, that has to be translated to a consecutive string of binary in order to further process it: for instance messages over the internet that might follow a strict binary protocol.

In another example an object (a `struct` for instance) might represent the binary layout of a file header by setting individual members and if you want the actual binary of the file header, the members need to be translated to this piece of binary.

Another example: a command, that represents an assembly instruction, allows you to set the parameters of the instruction. The binaral of the command is a piece of binary derived from the command’s settings, that are the exact binary machine code for the machine instruction.

When you design an object to represent a piece of consecutive binary, you may give it members to configure it, but the way the members are stored might not be exactly the binary you want to build up. In order to get the consecutive binary string, the objects’ members may need to be translated to a binaral.

You do not necessarily need a binaral in order to let an object represent binary content. You can also design an object whose members write directly to a piece of binary, so that the format in which the object is stored is the exact binary format we want. In that case you do not need a binaral: you just use the object’s value. Every object can control its own piece of binary value. A binaral is used when it is not convenient to have the members directly write the binary value of an object. A binaral requires translation of the object members to a single stretch of binary. When directly writing to the binary value of an object, this translation is not necessary. The need for translation is the difference between the value of an object and the binaral of an object.

Just like a literal can be assigned to an object, a piece of binary might also be assigned to an object: then the binaral is translated to the object members.