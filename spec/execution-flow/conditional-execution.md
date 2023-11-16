Execution Flow | Conditional Execution
======================================

`[ Draft ]`

[back](./)

__Contents__

- [Introduction](#introduction)
- [If](#if)
- [Then](#then)
- [Else](#else)
- [Else If](#else-if)
- [Select Case](#select-case)
    - [Concept](#concept)
    - [Diagram](#diagram)
- [Select Case (exact value)](#select-case-exact-value)
    - [Concept](#concept-1)
    - [Diagram](#diagram-1)
- [Select Case (split formula)](#select-case-split-formula)
    - [Concept](#concept-2)
    - [Diagram](#diagram-2)
- [Outtakes](#outtakes)

Introduction
------------

Conditional execution is a common form of execution flow control, where the next step of a program is based on a decision. The __If__ statement is the most common example of this.

The notations introduced here are just suggestions. They aim to demonstrate how Circular notation can be used for conditional execution statements, as if they were regular commands. The suggestions here might not be perfect, but it shows the principles, as a base for any variation of notation.


If
---

The __If__ statement is argueably the most common form of *conditional execution*.


Then
----

The __If Then__ statement takes a __Boolean__ condition and a reference to the command to run when the __Boolean__ is __True__.

In a diagram this looks as follows.

![](images/2.%20Conditional%20Execution.001.png)

The circle is the __Boolean__ condition. The square is the command to execute when the __Boolean__ condition is __True__.

The __Then__ command can be defined right inside the call to the __If__ statement, but you can also define the __Then__ *outside* the __If__ with the aid of a reference line:

![](images/2.%20Conditional%20Execution.002.png)

The __Boolean__ condition is usually defined elsewhere as well, making the condition point to another symbol.

![](images/2.%20Conditional%20Execution.003.png)


Else
----

The __If Else__ statement takes a __Boolean__ condition, a command reference to the command to run when the __Boolean__ is __True__ and one when it is __False__.

![](images/2.%20Conditional%20Execution.004.png)

The circle is the __Boolean__ condition. The square named __Then__ is the command to execute when the __Boolean__ condition is __True__. The square named __Else__ is the command to execute when the __Boolean__ condition is __False__. For the __If Else__ statement, the __Then__ and __Else__ are also usually defined *outside* the __If__ with the aid of a reference line reference:

![](images/2.%20Conditional%20Execution.005.png)

And the condition is usually defined elsewhere as well:

![](images/2.%20Conditional%20Execution.006.png)

The definition of the __If__ execution flow command is part of a system module of execution flow command. The public elements of the definition look like this:

![](images/2.%20Conditional%20Execution.007.png)

In the definition, the condition and the clauses are not filled in yet.

## Else If

The __Else If__ statement is a lot like the __If__ statement, but then the __Else__ has another __If__ associated to it. 

Below is an example of the diagrammatic expression of an __Else If__ statement.

![](images/2.%20Conditional%20Execution.008.png)

The diamond is the __Else If__ command. It is an overload of the __If__ command. The top circle inside the diamond is the condition of the first __If__. If the condition returns __True__, then the __Then__ clause is executed. In the middle of the diamond there is a nonagon. Inside the nonagon any number of __Else If__'s can be specified. An __Else If__ object also has a condition and a __Then__ clause. If the condition returns __True__ then the __Then__ clause is executed. If the condition is __False__, then the next __Else If__’s condition is evaluated. If none of the __Else If__’s conditions return __True__, then the __Else__ clause is executed, which is visible at the bottom of the diamond. The __Else__ clause is optional. If the __Else__ clause is not used, it can be left out of the diagram.

The conditions and the clauses can all be references to something defined outside the diamond. The conditions and the clauses can also be filled in right inside the diamond.

The *definition* of the __Else If__ command could become part of a system module of execution flow commands. The public elements of the definition would look like this:

![](images/2.%20Conditional%20Execution.009.png)

Nothing is filled in yet for the condition, the __Then__ clause or the __Else__ clause, and there are no __Cases__ defined yet. But a *class* for a __Case__ *is* defined. The __Case__ class defines a condition and a __Then__ clause.

There is another, separate definition of the __Else If__ command, that is the same as the other __Else If__ command definition, except without an __Else__ clause in it.

That way the notation for conditional execution statements could be implemented as a library just like other commands.

## Select Case

### Concept

The __Select Case__ statement is a form of conditional execution. It is also sometimes called a __switch__ statement. In this kind of statement the next step to take is selected out of a list of several options.

There are two forms of __Select Case__:

- __Select Case__ (exact value)
    - a variable to different values, to choose the next step
- __Select Case__ (split formula)
    - combines one half of a formula with several other halves of the formula, to choose the next step


The name __Select Case__ is directly taken over from the programming language *Basic*. You can choose between *Basic* naming and *C*  naming for execution flow statements. In the programming language *C*  it is called a __switch__ statement. Both names are available in Circular, as part of the multi-lingual approach of the system.

### Diagram

There are several types of __Select Case__ statements discussed here and each has a slight variation in diagram notation.

## Select Case (exact value)

### Concept

This article explains the form of __Select Case__ where a variable is compared to different values, to choose the next step to take.

This form of __Select Case__ compares a given variable with several different values. If the variable equals one of the values, the step associated with that value is executed. If the variable equals none of the values, an alternative command can be executed.

This type of __Select Case__ only works with objects, that hold a binary value.

__Select Case__ takes an object, that holds a binary value as the __Variable__ of the comparison. Furthermore, __Select Case__ defines a variable amount of __Cases__. Each __Case__-object contains a value to compare the variable to and a reference to the command to execute when the variable equals the value. __Select Case__ can also take a reference to a command, that might be executed, when the variable matches *none* of the values. This alternative command is called the __Else__ clause of the __Select Case__ statement. The __Else__ clause of the statement can be left out, if it is not required.

### Diagram

Below is an example of the diagrammatic expression of a __Select Case__ statement for comparing exact values.

![](images/2.%20Conditional%20Execution.010.png)

The diamond is a call to the __Select Case__ command. The circle inside the diamond has the title __Select__. It points to an object outside the command call. This might be the variable to which several values might be compared. In the middle of the diamond there is a nonagon, that represents the cases: values to which the variable might be compared. The nonagon can contain any number of cases. Each circle inside a nonagon is a __Case__. Each case defines a value, and the command to call, if the variable matches the value. In this example, there are two __Cases__. One __Case__ has the value __1__ and the other __Case__ has the value __2__. Each __Case__ has a command associated to it. Those command references are pointing to clauses defined outside the diamond. At the bottom of the diamond there is also a command reference called __Else__. It points to a clause defined outside the diamond. The command pointed to might be called if the variable matches none of the values defined in the __Cases__. If the __Else__ clause is not used, it can be left out of the call and then it might not be shown in the diagram.

The values for the cases were entered literally into the case. A value for a case can also be defined as a pointer to an object that holds the value. The same way, the variable could also have gotten an exact value, and not be a pointer to an object outside the diamond. The command references did not might point to something defined outside of the diamond either. The commands could have been defined right inside the diamond, but it often looks more intuitive to define clauses outside the diamond.

The *definition* of the __Select Case__ execution flow commands is part of a system module of execution flow commands. The public elements of the definition look like this:

![](images/2.%20Conditional%20Execution.011.png)

Nothing is filled in yet as the __Select__ or __Else__, and there are no __Cases__ defined, but a *class* for a __Case__ *is* defined.

There is another, separate definition of the __Select Case__ command for comparison of exact values, that is the same as the other __Select Case__ command definition, except that it might not have an __Else__ clause in it.

## Select Case (split formula)

### Concept

There are two forms of __Select Case__, as mentioned in the article *Select Case*. This article explains the form of __Select Case__ where one half of a formula is combined with several other halves of the formula, to choose the next step to take.

This form of __Select Case__ takes a fixed first part of a formula. Then it combines it to several other halves of the formula. If the complete formula returns the __Boolean__ value __True__, the step associated with that other half of the formula is executed. If none of the resultant formulas renders the __Boolean__ value of __True__, then an alternative step can be executed.

Half a formula can either be a value, or an operation for which one operand is yet to be filled in.  
If the first half of a formula is a value, then the other halves of the formula need to be operations for which an operand is yet to be filled in. The first half of the formula might then be filled in as the operand missing in the other half of the formula.  
If the first half of a formula is an operation for which one operand is yet to be filled in, then the other halves of the formula need to be values, to fill in as the operand.

It is not limited to just mathematical formulas. You can use any command for which a parameter is to yet to be filled in. This type of __Select Case__ is not limited to objects, that hold binary data. This type of __Select Case__ works with all kinds of objects. However, the result of the resultant formula has to be a __Boolean__ value.

The implementation of the __Select Case__ command one by one calculates the __Boolean__ results of the resultant formulas. If the result of formula is __True__, then the command associated with that second half of the formula is called. If multiple resultant formulas return __True__, then all the associated commands are executed. If all resultant formulas were processed and none of the formulas returned __True__, then the alternative command is run.

### Diagram

There are two forms of this statement: the first half of the formula is a value or the first half of the formula is an operation with an operand missing. These two forms have a different definition and look different in the diagram

Below is an example of the diagrammatic expression of a __Select Case__ statement for split formulas, of which the first half of the formula is a value.

![](images/2.%20Conditional%20Execution.012.png)

The diamond is a call to the __Select Case__ command. The circle inside the diamond has the title __Select__. It points to an object outside the command call. This is called the variable. It is the value, that might be filled into the missing operands of the other halves of the formula. In the middle of the diamond there is a nonagon, that represents the cases: different operations into which the variable might be filled in. The nonagon can contain any number of cases. Each circle inside a nonagon is a Case. Each case defines a command for which the variable is filled in. Each case also defines the command to call when the result of the formula is __True__. In this example, there are two __Cases__. The other halves of the formula are not drawn out in full detail. That might obscure the picture in this demonstration. The literals of the half formulas are shown. The command definitions of the half formulas are not pointed out, and the build-up of the formula’s is not fully graphically drawn out with objects connected with operations, because that might obscure the picture of this demonstration, but they do belong in the diagram, though.  
One __Case__ is the half formula __> 2__ . __X__ is to be filled in as the first operand of this formula, which might make the resultant formula __X > 2__. The second __Case__ is the half formula __= 10 – Y__. __X__ is to be filled in as the first half of the formula, which might make the resultant formula __X = 10 – Y__.  
Each __Case__ has a command associated to it. Those command references are pointing to clauses defined outside the diamond. When a resultant formula of the case returns __True__, then the command associated with the case might be executed. At the bottom of the diamond there is also a command reference called __Else__. It points to a clause defined outside the diamond. The command pointed to might be called if *none* of the formulas results in the __Boolean__ value __True__. If the __Else__ clause is not used, it can be left out of the call and then it might not be shown in the diagram.

Below is an example of the diagrammatic expression of a __Select Case__ statement for split formulas, of which the first half of the formula is half a formula, and the second halves of the formula are values to be filled in as the missing operand in the first half of the formula.

![](images/2.%20Conditional%20Execution.013.png)

The diamond is a call to the __Select Case__ command. The square at the top of the diamond is the first half of the formula. It is a *greater than* operation. The first operand of the formula is already filled in with the object __X__, by having the parameter point out of the diamond to the object called __X__. The second parameter of the operation is yet to be filled in by the __Cases__ of the __Select Case__ statement. In the middle of the diamond there is a nonagon, that represents the cases: different values to be filled in as the missing operand of the formula. The nonagon can contain any number of cases. Each circle inside a nonagon is a __Case__. Each case defines a value to be filled in as the missing operand of the formula. Each case also defines the command to call when the result of the formula is __True__. In this example, there are two __Cases__. One __Case__ is the value __2__. This value might be filled in as the missing operand of the formula. This makes the resultant formula __X > 2__. The second __Case__ is not a fixed value, but points to the variable __Y__, which is defined outside the diamond. __Y__ is filled in as the missing operand of the formula. This makes the resultant formula __X > Y__.  
Each __Case__ has a command associated to it. Those command references are pointing to clauses defined outside the diamond. Every command for which the resultant formula returns True is executed. At the bottom of the diamond there is also a command reference called __Else__. It points to a clause defined outside the diamond. The command pointed to might be called if none of the formulas results in the __Boolean__ value __True__. If the __Else__ clause is not used, it can be left out of the call and then it might not be shown in the diagram.

In the examples above, each value, that was literally filled in, could also have been a pointer to something remote. Conversely, everything that was a pointer to something outside the diamond, could also have been defined directly inside the diamond.

The definition of the __Select Case__ execution flow commands is part of a system module of execution flow commands. The public elements of the definition for a value as the first part of the formula looks like this:

![](images/2.%20Conditional%20Execution.014.png)

Nothing is filled in yet as the __Select__ or __Else__, and there are no __Cases__ defined, but a *class* for a __Case__ *is* defined. There is also a definition without an __Else__ clause in it.

The public elements of the definition for half a formula as the first part of the formula looks like this:

![](images/2.%20Conditional%20Execution.015.png)

Nothing is filled in yet as the __Select__ or __Else__, and there are no __Cases__ defined, but a *class* for a __Case__ *is* defined.

There is another, separate definition of the __Select Case__ command for formulas, that is the same as the other __Select Case__ command definition, except that it might not have an __Else__ clause in it.


Outtakes
--------

`<< implementation >>`

The implementation of the __If__ command is quite simple. It simply calls a few machine instructions to start the right command, based on whether the __Boolean__ is __True__ or __False__.

The implementation of the __Else If__ command is quite simple. It simply calls a few machine instructions to start a command, based on whether a __Boolean__ value is __True__ or __False__.

The implementation of the __Select Case__ command is not too complicated. It simply calls a few machine instructions to compare a variable to a value and to start the right command when a match is found.