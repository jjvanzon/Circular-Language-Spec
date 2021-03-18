Circle Language Spec
====================

Code Concepts Extended
----------------------

`[ Preliminary documentation ]`

### Circularity

Object structures can form large constructions of one object referring to another. When following redirections from one object to another, you can end up at the same object again. This means that the redirecting is circular. Circularities are in many cases no problem at all. However, sometimes circularities will make a program hang. It is hard to custom-program a way to handle such circularity problems. Therefore, standard mechanisms are available inside the new computer language to handle all kinds of circularities. When recursively processing an object structure, the process can hang, because at some point it starts to go around in circles. There are several ways to prevent this. One method is to not allow circularities to be formed at all. Another method is, that when processing an object structure, an object is never processed twice. This will make the process stop going around in circles. Another method is to allow a *maximum amount of cycles* to be processed. Circularities in data are not necessarily a problem. It only becomes a problem, when recursively processing the data. The documentation about circularities is not finished yet. It needs to become more refined.
