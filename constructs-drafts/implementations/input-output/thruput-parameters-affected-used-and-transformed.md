Encircle Language Construct Drafts | Input Output
=================================================

Thruput Parameters | Affected, Used and Transformed
---------------------------------------------------

`[ Preliminary documentation ]`

Further parameter passing stereotyping.

Contemplations about further thru parameter passing stereotyping would be postponed.

Throughput could have the following elements:

- affected
- used
- transformed

Affected means that what’s written to the object is not dependant on the original contents of the object.  
Affected and used means the same as affected, but also values are read from the object, but the read values do not have an effect on the object itself.  
Transformed means that what’s written to the object is dependant on what was first read from the object.

< Actually, just affected is not throughput at all, that’s output. >

-----

The thru parameter passing type can be further split up in *affected*, *used & affected*, *transformed*, *transformed same value*, *used & affected & transformed* and *used & affected & transformed same value*.

< ... >

Furthermore, thru can be either *affected*, *used & affected* or *transformed* or both. Affected is considered throughput, even though nothing is read from it, because the object is still *passed through* the command.

This gives us the following number of parameter passing situations:

- Value In
- Object In
- Reference In
- Value Out
- Object Out
- Reference Out
- Value Thru
    - Value Thru, Affected
        - Value Thru, Affected does not make sense. You’d give a parameter an initial value, that does not get used, but will be overwritten. Value In is a better choice in that case.
    - Value Thru, Transformed
    - Value Thru, Used & Affected
    - Value Thru, Used & Affected & Transformed
- Object Thru
    - Object Thru, Affected
    - Object Thru, Transformed
    - ~ Object Thru, Transformed Same Value
    - Object Thru, Used & Affected
    - Object Thru, Used & Affected & Transformed
- Reference Thru
    - Reference Thru, Affected
    - Reference Thru, Transformed
    - ~ Reference Thru, Transformed Same Value
    - Reference Thru, Used & Affected
    - Reference Thru, Used & Affected & Transformed

< When throughput it is affected and used, values are read and written from it to manipulate or coming out of other objects. When throughput is transformed, the values written to the throughput object were derived from values first read from the throughput object. >

### Brainstorm

Do I really need to stereotype this many subtile variations? Isn’t the fact that it is thru enough to tie everything together?  
This whole section in, out, thru is getting out of hand.  
It was supposed to be simple. It wasn’t even there at first.  
I have to simplify the story, keeping the split up in affected, used, transformed and ‘same value’ a detail.  
Then I need to work out the subjects under the assumption, that you only need to be concerned with in, out and thru.

### Same Value

< Perhaps when it is the exact same variable that’s read and written, this should be stereotyped in a different way as well. It is transformed, but then specific values are both used and affected. Transformed where one part of the object is used, to affect another part of the object, is also transformation, but less rigorous, so perhaps you do need some sort of stereotyping for that. >

### Throughput variations

<
combinations:

not affected, not used, not transformed  
\-
not affected, not used, too transformed  
transformed   
not affected, too used, not transformed  
used  
\>
in, not thru  
not affected, too used, too transformed  
used & transformed  
too affected, not used, not transformed  
affected  
too affected, not used, too transformed  
affected & transformed  
too affected, too used, not transformed  
affected & used  
too affected, too used, too transformed  
affected & used & transformed  

< only *used* is actually input, not throughput. >

The combinations, that are left, then:
- affected
- affected & used
- transformed
- used & transformed
- affected & transformed
- affected & used & transformed

### Value Thru, affected

Does not make sense. You’d give a parameter an initial value, that does not get used, but will be overwritten.

- used to affect another ( = input )
- used to affect itself ( = throughput )
- affected by another ( = ~ output / affected
- produced ( = output )
- temporarily existent
-----
- privates used to affect another
- privates used to affect itself
- privates affected by another
- always used / affected / produced
- not always used / affected / produced

![](images/Further%20parameter%20passing%20stereotyping.001.png)