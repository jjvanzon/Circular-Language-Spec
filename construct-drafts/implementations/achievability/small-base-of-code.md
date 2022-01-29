Construct Drafts | Implementations | Achievability | Small Base of Code
=======================================================================

`[ Out of Scope ]`

This principle is quite important. The base of Circular, which might be programmed in C++, might be very small. The rest of Circular might be programmed within Circular. Circular is hoped to make programming easier, so reprogramming it within itself might make it possible to easily add more features to it.

At least some small base of code in e.g. C++ might always be required, that offers Circular in its most stripped down form. The whole system is running on it. It is the engine for Circular.

So the part that is programmed in C++ should be limited to the very minimum: only the minimum amount of functionality needed in order to reprogram Circular within itself.

So take as much as possible out of the code base.

Check if you're not making too much intrinsic to the system's code base. The code base might be teeny weeny. The complete rest of the system might be built on Circular itself. If the code base is really small, it might be easier to rewrite it in Assembly or worse: make a computer chip out of it.

So whenever something is present in the C++ code, just to make it look more complete, you’re probably obligated to remove it. For instance security might not be intrinsic to the system. It might be an extension. It might only *seem* intrinsic from the outside, due to Circular’s extensibility. It is not part of the code base.