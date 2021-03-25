Encircle Language Spec | Execution Flow
=======================================

Conditional Execution
---------------------

`[ Preliminary documentation ]`

### Concept

Conditional execution is a form of control over *execution flow*. Execution flow is explained in the article *Execution Flow*.

Conditional execution is a main form of execution flow, where the next step of a program is based on a decision. The __If__ statement is the most common form of conditional execution.

There are four forms in which to express conditional execution:

- __If__
- __Else If__
- __Select Case__ (exact value)
- __Select Case__ (split formula)

Each form is explained in a separate article.

### Diagram

Conditional execution is a form of execution flow explained in the article *Conditional Execution*. The articles that follow only explain its expression in a diagram.

There are three forms in which to express conditional execution:

- __If__
- __Else If__
- __Select Case__ (exact value)
- __Select Case__ (split formula)

Each form is explained in a separate article. See the articles *If in a Diagram, Else If in a Diagram*, *Select Case in a Diagram (exact value)* and *Select Case in a Diagram (split formula)*.

### If

#### Concept

The __If__ statement is the most common form of *conditional execution*. Conditional execution is a kind of execution flow statement, explained in the *Conditional Execution* article.

The __If__ statement runs a command if a certain condition is met. On top of that, the __If__ statement can run an alternate command when the condition is *not* met.

The __If__ command takes one or two command references as a parameter. That is the command run, when a condition is met and the command run, when a condition is not met. The condition is also passed along to the __If__ command as an argument. The condition is a reference to a __Boolean__.

The command to run when a condition is met is called the __Then__ clause. The command to run when a condition is *not* met is called the __Else__ clause.

There are two versions of __If__. There is the __If Then__ statement, that does not have an __Else__ clause. And there is __If Else__ statement, which does have an __Else__ clause.

The implementation of the __If__ command is quite simple. It simply calls a few machine instructions to start the right command, based on whether the __Boolean__ is __True__ or __False__.

#### Diagram

The __If Then__ statement takes a __Boolean__ condition and a reference to the command to run when the __Boolean__ is __True__.

In a diagram this looks as follows.

![](images/2.%20Conditional%20Execution.001.png)

The circle is the __Boolean__ condition. The square is the command to execute when the __Boolean__ condition is __True__.

The __Then__ command can be defined right inside the call to the __If__ statement, but you can also define the __Then__ *outside* the __If__ with the aid of an esthetic reference:

![](images/2.%20Conditional%20Execution.002.png)

The __Boolean__ condition is usually defined elsewhere as well, which will make the condition a pointer to another symbol.

![](images/2.%20Conditional%20Execution.003.png)

The __If Else__ statement takes a __Boolean__ condition, a command reference to the command to run when the __Boolean__ is __True__ and a command reference to the command to run when the __Boolean__ is __False__.

![](images/2.%20Conditional%20Execution.004.png)

The circle is the __Boolean__ condition. The square named __Then__ is the command to execute when the __Boolean__ condition is __True__. The square named __Else__ is the command to execute when the __Boolean__ condition is __False__. For the __If Else__ statement, the __Then__ and __Else__ are also usually defined *outside* the __If__ with the aid of an esthetic reference:

![](images/2.%20Conditional%20Execution.005.png)

And the condition is usually defined elsewhere as well:

![](images/2.%20Conditional%20Execution.006.png)

The definition of the __If__ execution flow command is part of a system module of execution flow command. The public elements of the definition look like this:

![](images/2.%20Conditional%20Execution.007.png)

In the definition, the condition and the clauses are not filled in yet.

### Else If

#### Concept

__Else If__ form of *conditional execution*. Conditional execution is a kind of execution flow statement, explained in the article *Conditional Execution*. The __Else If__ statement is a lot like the __If__ statement, but then the __Else__ has another __If__ associated to it. If the condition of the second __If__ is met, then the associated command is called. If the condition is not met, then the __Else__ of the second __If__ might have another __If__ associated to it, and so on, until no more __Else If__’s are defined. If none of the __Else If__’s conditions are met, then the final __Else__ is executed, if provided.

The __Else If__ command takes an argument, that is the condition for the first __If__. It also takes a command reference __Then__ as a parameter. The command is executed if the __If__ condition is __True__. Furthermore, the __Else If__ command takes a variable amount of __Else If__’s. Each __Else-If__-object contains a condition and a reference to the command to execute when the __Else If__’s condition returns __True__. The __Else If__ command also take a reference to a command, that will be executed, if none of the __Else If__’s conditions are __True__. This alternative command is called the __Else__ clause of the __Else If__ statement. The __Else__ clause of the statement can be left out, if it is not required.

The implementation of the __Else If__ command is quite simple. It simply calls a few machine instructions to start a command, based on whether a __Boolean__ value is __True__ or __False__.

#### Diagram

Below is an example of the diagrammatic expression of an __Else If__ statement.

![](images/2.%20Conditional%20Execution.008.png)

The diamond is the __Else If__ command. the top circle inside the diamond is the condition of the first __If__. If the condition returns __True__, then the __Then__ clause is executed. In the middle of the diamond there is a nonagon. Inside the nonagon any number of __Else If__’s can be specified. An __Else If__ object also has a condition and a __Then__ clause. If the condition returns __True__ then the __Then__ clause is executed. If the condition is __False__, then the next __Else If__’s condition is evaluated. If none of the __Else If__’s conditions return __True__, then the __Else__ clause is executed, which is visible at the bottom of the diamond. The __Else__ clause is optional. If the __Else__ clause is not used, it can be left out of the diagram.

The conditions and the clauses can all be references to something defined outside the diamond. The conditions and the clauses can also be filled in right inside the diamond.

The *definition* of the __Else If__ command is part of a system module of execution flow commands. The public elements of the definition look like this:

![](images/2.%20Conditional%20Execution.009.png)

Nothing is filled in yet for the condition, the __Then__ clause or the __Else__ clause, and there are no __Cases__ defined yet. But a *class* for a __Case__ *is* defined. The __Case__ class defines a condition and a __Then__ clause.

There is another, separate definition of the __Else If__ command, that is the same as the other __Else If__ command definition, except that it does not have an __Else__ clause in it.

### Select Case

#### Concept

The __Select Case__ statement is a form of conditional execution. Conditional execution is a kind of execution flow statement, explained by the article *Conditional Execution*.

In a __Select Case__ statement the next step to take is one out of several options.

There are two forms of __Select Case__:

- __Select Case__ (exact value)
    - a variable to different values, to choose the next step
- __Select Case__ (split formula)
    - combines one half of a formula with several other halves of the formula, to choose the next step

The two forms will be explained in separate articles.

The name __Select Case__ is directly taken over from the programming language *Basic*. You can choose between *Basic* naming and *C*  naming for execution flow statements. In the programming language *C*  it is called a __switch__ statement. Both names are available in the new computer language, as part of the multi-lingual approach of the system.

#### Diagram

Each type of __Select Case__ has a slight variation in diagram notation. There are three definitions of __Select Case__ commands. They will be covered in the articles *Select Case (exact value) in a Diagram*, *Select Case (split formula) in a Diagram*. (*Split formula* has *two* variations. Hence the three definitions of __Select Case__.)

### Select Case (exact value)

#### Concept

There are two forms of __Select Case__, as mentioned in the article *Select Case*. This article explains the form of __Select Case__ where a variable is compared to different values, to choose the next step to take.

This form of __Select Case__ compares a given variable with several different values. If the variable equals one of the values, the step associated with that value is executed. If the variable equals none of the values, an alternative command can be executed.

This type of __Select Case__ only works with objects, that hold a binary value.

__Select Case__ takes an object, that holds a binary value as the __Variable__ of the comparison. Furthermore, __Select Case__ defines a variable amount of __Cases__. Each __Case__-object contains a value to compare the variable to and a reference to the command to execute when the variable equals the value. __Select Case__ can also take a reference to a command, that will be executed, when the variable matches *none* of the values. This alternative command is called the __Else__ clause of the __Select Case__ statement. The __Else__ clause of the statement can be left out, if it is not required.

The implementation of the __Select Case__ command is not too complicated. It simply calls a few machine instructions to compare a variable to a value and to start the right command when a match is found.

#### Diagram

Below is an example of the diagrammatic expression of a __Select Case__ statement for comparing exact values.

![](images/2.%20Conditional%20Execution.010.png)

The diamond is a call to the __Select Case__ command. The circle inside the diamond has the title __Select__. It points to an object outside the command call. This will be the variable to which several values will be compared. In the middle of the diamond there is a nonagon, that represents the cases: values to which the variable will be compared. The nonagon can contain any number of cases. Each circle inside a nonagon is a __Case__. Each case defines a value, and the command to call, if the variable matches the value. In this example, there are two __Cases__. One __Case__ has the value __1__ and the other __Case__ has the value __2__. Each __Case__ has a command associated to it. Those command references are pointing to clauses defined outside the diamond. At the bottom of the diamond there is also a command reference called __Else__. It points to a clause defined outside the diamond. The command pointed to will be called if the variable matches none of the values defined in the __Cases__. If the __Else__ clause is not used, it can be left out of the call and then it will not be shown in the diagram.

The values for the cases were entered literally into the case. A value for a case can also be defined as a pointer to an object that holds the value. The same way, the variable could also have gotten an exact value, and not be a pointer to an object outside the diamond. The command references did not have to point to something defined outside of the diamond either. The commands could have been defined right inside the diamond, but it often looks more intuitive to define clauses outside the diamond.

The *definition* of the __Select Case__ execution flow commands is part of a system module of execution flow commands. The public elements of the definition look like this:

![](images/2.%20Conditional%20Execution.011.png)

Nothing is filled in yet as the __Select__ or __Else__, and there are no __Cases__ defined, but a *class* for a __Case__ *is* defined.

There is another, separate definition of the __Select Case__ command for comparison of exact values, that is the same as the other __Select Case__ command definition, except that it does not have an __Else__ clause in it.

### Select Case (split formula)

#### Concept

There are two forms of __Select Case__, as mentioned in the article *Select Case*. This article explains the form of __Select Case__ where one half of a formula is combined with several other halves of the formula, to choose the next step to take.

This form of __Select Case__ takes a fixed first part of a formula. Then it combines it to several other halves of the formula. If the complete formula returns the __Boolean__ value __True__, the step associated with that other half of the formula is executed. If none of the resultant formulas renders the __Boolean__ value of __True__, then an alternative step can be executed.

Half a formula can either be a value, or an operation for which one operand is yet to be filled in.  
If the first half of a formula is a value, then the other halves of the formula need to be operations for which an operand is yet to be filled in. The first half of the formula will then be filled in as the operand missing in the other half of the formula.  
If the first half of a formula is an operation for which one operand is yet to be filled in, then the other halves of the formula need to be values, to fill in as the operand.

It is not limited to just mathematical formulas. You can use any command for which a parameter is to yet to be filled in. This type of __Select Case__ is not limited to objects, that hold binary data. This type of __Select Case__ works with all kinds of objects. However, the result of the resultant formula has to be a __Boolean__ value.

The implementation of the __Select Case__ command one by one calculates the __Boolean__ results of the resultant formulas. If the result of formula is __True__, then the command associated with that second half of the formula is called. If multiple resultant formulas return __True__, then all the associated commands are executed. If all resultant formulas were processed and none of the formulas returned __True__, then the alternative command is run.

#### Diagram

There are two forms of this statement: the first half of the formula is a value or the first half of the formula is an operation with an operand missing. These two forms have a different definition and look different in the diagram

Below is an example of the diagrammatic expression of a __Select Case__ statement for split formulas, of which the first half of the formula is a value.

![](images/2.%20Conditional%20Execution.012.png)

The diamond is a call to the __Select Case__ command. The circle inside the diamond has the title __Select__. It points to an object outside the command call. This is called the variable. It is the value, that will be filled into the missing operands of the other halves of the formula. In the middle of the diamond there is a nonagon, that represents the cases: different operations into which the variable will be filled in. The nonagon can contain any number of cases. Each circle inside a nonagon is a Case. Each case defines a command for which the variable is filled in. Each case also defines the command to call when the result of the formula is __True__. In this example, there are two __Cases__. The other halves of the formula are not drawn out in full detail. That would obscure the picture in this demonstration. The literals of the half formulas are shown. The command definitions of the half formulas are not pointed out, and the build-up of the formula’s is not fully graphically drawn out with objects connected with operations, because that would obscure the picture of this demonstration, but they do belong in the diagram, though.  
One __Case__ is the half formula __> 2__ . __X__ is to be filled in as the first operand of this formula, which would make the resultant formula __X > 2__. The second __Case__ is the half formula __= 10 – Y__. __X__ is to be filled in as the first half of the formula, which would make the resultant formula __X = 10 – Y__.  
Each __Case__ has a command associated to it. Those command references are pointing to clauses defined outside the diamond. When a resultant formula of the case returns __True__, then the command associated with the case will be executed. At the bottom of the diamond there is also a command reference called __Else__. It points to a clause defined outside the diamond. The command pointed to will be called if *none* of the formulas results in the __Boolean__ value __True__. If the __Else__ clause is not used, it can be left out of the call and then it will not be shown in the diagram.

Below is an example of the diagrammatic expression of a __Select Case__ statement for split formulas, of which the first half of the formula is half a formula, and the second halves of the formula are values to be filled in as the missing operand in the first half of the formula.

![](images/2.%20Conditional%20Execution.013.png)

The diamond is a call to the __Select Case__ command. The square at the top of the diamond is the first half of the formula. It is a *greater than* operation. The first operand of the formula is already filled in with the object __X__, by having the parameter point out of the diamond to the object called __X__. The second parameter of the operation is yet to be filled in by the __Cases__ of the __Select Case__ statement. In the middle of the diamond there is a nonagon, that represents the cases: different values to be filled in as the missing operand of the formula. The nonagon can contain any number of cases. Each circle inside a nonagon is a __Case__. Each case defines a value to be filled in as the missing operand of the formula. Each case also defines the command to call when the result of the formula is __True__. In this example, there are two __Cases__. One __Case__ is the value __2__. This value will be filled in as the missing operand of the formula. This makes the resultant formula __X > 2__. The second __Case__ is not a fixed value, but points to the variable __Y__, which is defined outside the diamond. __Y__ is filled in as the missing operand of the formula. This makes the resultant formula __X > Y__.  
Each __Case__ has a command associated to it. Those command references are pointing to clauses defined outside the diamond. Every command for which the resultant formula returns True is executed. At the bottom of the diamond there is also a command reference called __Else__. It points to a clause defined outside the diamond. The command pointed to will be called if none of the formulas results in the __Boolean__ value __True__. If the __Else__ clause is not used, it can be left out of the call and then it will not be shown in the diagram.

In the examples above, each value, that was literally filled in, could also have been a pointer to something remote. Conversely, everything that was a pointer to something outside the diamond, could also have been defined directly inside the diamond.

The definition of the __Select Case__ execution flow commands is part of a system module of execution flow commands. The public elements of the definition for a value as the first part of the formula looks like this:

![](images/2.%20Conditional%20Execution.014.png)

Nothing is filled in yet as the __Select__ or __Else__, and there are no __Cases__ defined, but a *class* for a __Case__ *is* defined. There is also a definition without an __Else__ clause in it.

The public elements of the definition for half a formula as the first part of the formula looks like this:

![](images/2.%20Conditional%20Execution.015.png)

Nothing is filled in yet as the __Select__ or __Else__, and there are no __Cases__ defined, but a *class* for a __Case__ *is* defined.

There is another, separate definition of the __Select Case__ command for formulas, that is the same as the other __Select Case__ command definition, except that it does not have an __Else__ clause in it.
