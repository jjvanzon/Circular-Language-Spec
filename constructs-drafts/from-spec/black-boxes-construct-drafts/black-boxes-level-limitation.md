Construct Drafts | From Spec | Black Boxes | Level Limitation
=============================================================

`[ Deprecated documentation ]`

< Exclusion is restriction set by a container. Level restriction is like exclusion set by a child *for* the container. >

-----

\> 2009-06-27: I am not sure why I might need a child object to restrict the number of levels up it is accessible... why? for protection? Well... I might better resort to use access control for such protections...

-----

Basic access controllers are decisive, but level limitation adds additional restriction. 

Level limitation is paired with the basic access controller.

Pairing object level limitation with the Public access modifier, makes a command public only to limited number of levels up the ancestry.

> Public *Up 2*

A command with this access modifier is accessible but two levels up the ancestry. Outside those levels, the command is inaccessible.

*No object level limitation: Public:*

| ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.001.png) | ≈ | ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.002.png) |
|-----|-----|-----|

*Object Level Limitation: Public Up 2:*

| ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.003.png) | ≈ | ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.004.png) |
|-----|-----|-----|

Level limitation works the same for the Protected access modifier, but gets the additional restriction that comes with that access modifier:

- __Protected *Up 2*__

A command with this access modifier is accessible two levels up the ancestry, but inaccessible outside the first circular descendant.

*Protected Up 2, contained in three triangles:*

| ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.005.png) | ≈ | ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.006.png) |
|-----|-----|-----|

*Protected Up 2, contained in a triangle contained in two circles:*

| ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.007.png) | ≈ | ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.008.png) |
|-----|-----|-----|

*Protected Up 2, contained in three circles:*

| ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.007.png) | ≈ | ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.009.png) |
|-----|-----|-----|

Level limitation can also be applied to deeper exclusion than __Public__ and __Protected__. So a parent can impose level limitation on a child command.

*Level limitation on deeper exclusion:*

| ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.010.png) | ≈ | ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.011.png) |
|-----|-----|-----|

You can also apply level limitation for on symbols shallower than the target command.

*Level limitation on deeper exclusion:*

| ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.012.png) | ≈ | ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.013.png) |
|-----|-----|-----|

Level limitation is defined there where it doesn’t have effect yet. It only has effect higher in the ancestry. Basic exclusion is always defined there where it has effect. So level limitation automatically excludes members at *n* levels up the ancestry.

< Figure out a better diagram notation. >

Maybe call it Level Restriction.

## Module Level Limitation

< Pictures >

Apart from object level limitation there is also module level limitation.

- __Public *Module Up 1*__

When an access modifier is paired with a module level limitation, the access modifier works normally *n* level up the *module ancestry*. But for higher modules the member is inaccessible.

*Public:*

| ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.014.png) | ≈ | ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.015.png) |
|-----|-----|-----|

*Public Module Up 1:*

| ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.016.png) | ≈ | ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.017.png) |
|-----|-----|-----|

*Public Module Up 2:*

| ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.018.png) | ≈ | ![](images/2.0.%20Black%20Boxes%20Construct%20Drafts%20Ideas.019.png) |
|-----|-----|-----|

Protected Module Up N works the same as Public, but adds the extra restriction that comes with protected.

- \> 2009-06-27: Module level limitation is that VB6 Friend idea. That is probably why I also introduced object level limitation to begin with: as a bridge towards the concept module level limitation. It is more like overkill... I do not know yet how VB6 Friend access is supposed to look, but perhaps you’d better just appoint inside which module you still have access to it or something, instead of coming up with Object level limitation and only to build module level limitation only to have a substitute for VB6 friend access control.
- \> 2009-06-29: But level limitation and then module level limitation is a lot of systematics to introduce just to facilitate a VB Friend access modifier.

< Pictures with that? >

< ‘Module Up 2’ is too long, because Public Module Up 1 might be used commonly. Visual Basic’s Friend access modifier is the same as Public Module Up 1. I might need to invent a specific term for Public Module Up 1. I won’t use ‘Friend’, because that might conflict with >