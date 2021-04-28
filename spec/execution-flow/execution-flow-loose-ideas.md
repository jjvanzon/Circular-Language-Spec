Circular Language Spec | Execution Flow
=======================================

Loose Ideas
-----------

`[ Preliminary documentation ]`

__Contents__

- [Execution Flow (from Original Symbol Documentation from 2004)](#execution-flow-from-original-symbol-documentation-from-2004)
    - [Basic Language Execution Flow](#basic-language-execution-flow)
    - [Execution Flow Commands](#execution-flow-commands)
    - [Selection and Repetition](#selection-and-repetition)
    - [Selection](#selection)
    - [Repetition](#repetition)
    - [Clauses: Nested Commands](#clauses-nested-commands)
    - [Unconditional Jumps](#unconditional-jumps)
    - [Text Code Blabbing < >](#text-code-blabbing--)
        - [Conditional Jumps](#conditional-jumps)
            - [Selection](#selection-1)
            - [Iteration](#iteration)
    - [Brainstorm](#brainstorm)
        - [Execution Flow Controls which call is made next](#execution-flow-controls-which-call-is-made-next)
        - [Nice Example](#nice-example)
        - [Execution Flow is Call Control](#execution-flow-is-call-control)
        - [=> Execution Flow](#-execution-flow)
- [Declared Traversions / Constructions](#declared-traversions--constructions)

### Execution Flow (from Original Symbol Documentation from 2004)

< A command’s calling one of its own clauses, is an unconditional jump >

< Cover text code entirely, right inside the story. Oh, yeah, should I? Or should I cover it in the Text Code chapter? >

#### Basic Language Execution Flow

To explain control over execution flow in Symbol I might first introduce examples of execution flow statements in the Basic programming language.

```vb
If X Then A Else B
```

This is called an __If__ statement. If __X__ returns __True__ then __A__ is called, else __X__ returns __False__ and __B__ is called.

```vb
Select Case X
    Case 0: A
    Case 1: B
    Case 2: C
End Select
```

This is called a __Select__ statement. If __X__ equals __0__ then __A__ is called. If __X__ equals __1__ then __B__ is called. If __X__ equals __2__ then __C__ is called. This is actually shorthand for a whole bunch of __If__'s, but quite handy.

```vb
For I = 0 To 5
    A(I)
Next
```

This is called a __For__ loop. __A(I)__ is executed __6__ times. The first time __I = 0__, the second time __I = 1__, the third time __I = 2__ and so on until __I__ is __5__. In this example __I__ is used as a parameter to the command __A__.

```vb
    I = 0
Do While I < 6
    A(I)
    I = I + 1
Loop
```

The same happens here as in the __For__ loop, but it’s a different notation that allows more flexible control of the repetition. First __0__ is assigned as the initial value of __I__. Then there might be looped while __I < 6__. If __I__ becomes greater than or equal to __6__ then the repetition ends. In the repetitions __A(I)__ is called, after which __I__ is incremented.

The blue parts in the code above are called the *clauses* of the control statements. Those clauses are the code whose execution is considered controlled. They are executed depending on the results of *expressions* and *assignments*, marked with red.

The start of the control statement and the end and whatever’s in between is considered the control statement.

#### Execution Flow Commands

Execution flow statements are special commands. They are given one or more references to other commands, the execution of which is controlled. These referenced commands are the clauses of the control statement and also the expressions and assignments controlling their execution. The execution flow command decides when or if any of these referenced commands are called and how many times. How the execution flow command might call its referenced commands, is dependent on what the referenced commands might do.

#### Selection and Repetition

The execution flow mentioned till now is also called conditional jumping. There are two general forms of conditional jumping: selection and repetition. Selection selects one thing to execute out of several or whether to execute something at all depending on a condition. Repetition repeats a command a number of times until a condition is met. In the repeated command actions can be taken that affect this condition. __Select__ and __If__ statements are selection. __For__ and __Do__ statements are repetition. Symbol defines but two commands: __Selection__ and __Repetition__. Depending on how the command is used it functions as an __If__, __Select__, __For__ or __Do__ and depending on that, appropriate names are notated with calls to the execution flow commands.

#### Selection

< Sub sectioning. >

< That shorthand: what if the actual reference target is two capsules up? >

This section apart from covering the selection execution flow command also explains a lot about execution flow in general, not just selection, specifically about clauses.

__Select__ and __If__ statements are both accomplished by calling the __Selection__ execution flow command. The difference between an __If__ and a __Select__ is that a __Select__ first defines the beginning of the expression to evaluate and then a list of endings for the expression. Each beginning-ending combination is treated as a separate __If__.

The __Selection__ execution flow command takes 4 kinds of command references:

- __Select__
- __If__
- __Then__
- __Else__

I call all of these command references *clauses*. Not all clauses might be filled in.

If the __Select__ clause isn’t filled in then there’s only one __If__ clause, one __Then__ clause and one __Else__ clause:

```vb
If X Then A Else B
```

__X__, __A__ and __B__ are the clauses, which are separate embedded commands. __X__ is the __If__ clause. __A__ is the __Then__ clause. __B__ is the __Else__ clause. The __If__ clause returns a condition that is either __True__ or __False__. If it is __True__ then the __Then__ clause is called, if it is __False__ then the __Else__ clause is called.

The red clauses can be seen as the cause of the selection and the blue clauses as the result of the selection.

If you *do* fill in the Select clause then there can be multiple __If__, __Then__ and __Else__ clauses. 

```vb
Select X
    If = 0 Then A Else B
    If = 1 Then C
    If = 2 Then D
    Else E
End Select
```

Each __If__ clause is accompanied by its own __Then__ and __Else__ clause. The __Else__ clause might not be filled in. Above, only the __If__ that has an __Else__ clause is the first one.  
The __Select__ clause is also accompanied by its own __Else__, which is executed if none of the __Select__ statement’s __If__'s returns __True__.

The __Select__ clause represents the beginning of the __If__ clauses. It can be any beginning of an expression:

```vb
Select X – 2 >
    If 0 Then A Else B
    If 1 Then C
    If 2 Then D
    Else E
End Select
```

The resulting expression of the first __If__ might be __X – 2 > 0__.

Symbol text code allows various representations of __Selection__ execution flow, but the notation above uses each clause’s distinctive name. An alternate notation might be as follows:

```vb
Select X – 2 >
    Case 0: A Else B
    Case 1: C
    Case 2: D
    Case Else: E
End Select
```

This notation is used when using the __Select__ clause. This makes it easier to distinct __If__ and __Select__ statements. In the __Select__ notation the __If__ clauses become __Case__ clauses and the __Then__ clauses become ‘__:__’ clauses. The joint __Else__ clause becomes the __Case Else__ clause. An additional thing about the __Select__ notation is that you can leave out __=__ signs in certain cases:

An alternate notation for:

```vb
Select Y
    Case = 0: A
    Case = 1: B
End Select
```

is:

```vb
Select Y
    Case 0: A
    Case 1: B
End Select
```

The method is that where appropriate an __=__ sign is put between the __Select__ clause and the __Case__ clause.

In diagram notation, the __Selection__ command with all its clauses looks like this:

![](images/6.%20Execution%20Control%20Ideas.001.png)

The amount of __If__ groups can vary. I’ve notated three of them in the diagram above.

All clauses are command references provided to the selection command as parameters when you call it. For that, the diagram for a call to the Selection command might look like this:

![](images/6.%20Execution%20Control%20Ideas.002.png)

In text code:

```vb
Select ...
    If ... Then ... Else ...
    If ... Then ... Else ...
    If ... Then ... Else ...
Else
    ...
End If
```

The outer squares are the clauses. The squares in the larger square are the references to those clauses.

Execution flow is so common and the notation above is rather complex. The notation above should even require grouping triangles around the __If__ groups. I already left those out, but I might do more to make it look clearer. A simplified notation for a call to the Selection command is regularly used instead:

![](images/6.%20Execution%20Control%20Ideas.003.png)

This has the same meaning as the other notation. A square drawn with dashed lines is shorthand for a square with a reference line to outside. The dashed squares are filled in with the contents of the referenced command.

| ![](images/6.%20Execution%20Control%20Ideas.004.png) | = | ![](images/6.%20Execution%20Control%20Ideas.005.png) |
|------------------------------------------------------|---|------------------------------------------------------|

Even more is done to simplify the notation. Clauses that are not filled in can be hidden. The command name __Selection__ is also left out. Squares are allowed to be drawn as rectangles. When the __Select__ clause is filled in, alternate clause names are used as explained earlier.

< Use those rules from this point onward >

```vb
If X Then A:
```

> ![](images/6.%20Execution%20Control%20Ideas.006.png)

```vb
If X Then A Else B:
```

> ![](images/6.%20Execution%20Control%20Ideas.007.png) 

```vb
If X Then A Else If Y Then B:
```

> ![](images/6.%20Execution%20Control%20Ideas.008.png) 

```vb
If X Then A Else If Y Then B Else C:
```

> ![](images/6.%20Execution%20Control%20Ideas.009.png) 

```vb
Select X 
    Case 0 : A 
    Case 1 : B 
End Select:
```

> ![](images/6.%20Execution%20Control%20Ideas.010.png) 

```vb
Select X
    Case 0 : A
    Case 1 : B
    Case Else : C
End Select:
```

![](images/6.%20Execution%20Control%20Ideas.011.png) 

You can nest Selection statements as deep as you want.

```vb
Select X
    Case 0:
        Select Y
            Case 0 : A
            Case 1 : B
            Case 2 : C 
        End Select
    Case 1 : B
    Case Else
        If Y = 2 Then D
End Select:
```

![](images/6.%20Execution%20Control%20Ideas.012.png) 

Math language (as well as text code) integrates into Symbol. When using execution selection this is very handy. Let’s take the following text code example:

```vb
If X > 3 And X < 5 Then Y = Y + X
```

Integrating math language, you can draw the following diagram:

< Picture: almost the same as text code. Clauses are put in dashed rectangles. >

When you don’t use math language it might look as follows:

< Picture: See paper. >

The __=__ operator is an operator from text code language, not math language.

#### Repetition

Now I’ve explained a lot about clauses in __Selection__, I can easily explain __Repetition__.

__Repetition__ has the following clauses:

- __For__
- __=__ (Initialization)
- __Till__
- __Step__
- __Loop__

< Picture 33: Diagram of Repetition execution flow command with all its clauses>>

Of each clause there can be only one, but not all need to be filled in.

I might express the two Basic repetition statements in diagram code. The colors denote the different clauses of the Repetition statement.

Text Code:

```vb
For I = 0 To 6 Step 2
    A
    B
Next
```

Diagram Code:

< Picture 34: Square called For with four other squares: __I__, __= 0__, __To 5__, __A B__. Use the same colors and pick some nicer ones man>>

Text Code:

```vb
I = 0
Do While I <= 6
    A
    B
    I += 2
Loop
```

< >

That was the Basic like notation. Symbol usually uses the For notation:

```vb
For I = 0 Till <= 5 Step I += 2
    A
    B
Next
```

The __Step__ clause is basically no more than the second part of the loop clause. It’s just simply executed as the second part of the loop. However, it allows a more abstract notation. When you start with a binary operator then the __For__ clause is used as the first operand. If you only supply a term, then it is added to the __For__ clause.

Oops the __For__ clause isn’t a command anymore. It’s an object whose state is gotten and set. The __Step__ clause can be a command reference, but can also be an object reference with state get and set. It’s overloaded to support

< >

Diagram Code:

< Picture 35: Square called Do with 5 other squares: I, = 0, <= 5, ++, A B. >

The algebra you see in the diagrams above (for instance __<= 5__) are actually calls to algebraic commands. The algebraic language can be integrated like that in the diagram code. The integration of other languages into diagram code is discussed in a separate chapter. Here I’ve only used it to show how using the execution flow statements can look in practice.

< Algebra covered in Math, Language embedding in a Code Language chapter >

< Tell not to worry about the algebraic operations and assignment. Algebra operations and assignment are themselves commands that can be called which are explained later. >

< Examples of simpler loops, in which 

#### Clauses: Nested Commands

The clauses discussed above might be seen as nested commands. Nested commands might sometimes be referred to with the word clause. Nested commands may have a special characteristic, that they might access the members of the command they’re embedded in.

< Picture 36 >

Nested commands may have access to the objects in their ancestor nested commands and to the objects in the eventual command definition.

< Picture 37 >

The reverse is not true: a command definition can not access an object in a nested command unless the object is public.

< Picture 38: non public nested command member, not referenced by the command definition >

And even when it’s public then it has to be written right before entering the nested command, just like a command call.

< Picture 39: public nested command member referenced by the command definition just before entrance >

You can recognize an embedded command by the fact that they’re not calls, nor command references. So they (usually) have no lines:

< picture 40: embedded commands. Mark the ones that are nested commands with a color >

Perhaps jumping might change that and the nested commands might get lines, but no lines that end up outside the command definition.

< Picture 41: nested command that might have a line because of a jump to it >

< It’s like when something’s a nested command, it ignores its parent’s borders. Conversely, the contents of a block are by default only accessible within that block. >

#### Unconditional Jumps

__Returns__ and __Jumps__

<

```vb
    1    Call A
    2    Call B
    3    Jump 5
    4    Call C
    5    Call D
```

Line 3 might make a jump to line 5. Line 4 might be skipped.

...

Returns makes you able to exit commands, a single repetition, a whole repetition loop, a select statement, etcetera.

A jump ...


Unconditional jumps are usually just regular calls to other commands. Another special unconditional jump is immediately ending the command or the block or ending the current command and the next one and so on.

You could speak of conditional calls, actually. 

\>

<  
Unconditional jumps are usually calls to other commands indendent of a boolean state: regular calls. Another special unconditional jump is immediately ending the command (returning or ending a for loop) or ending the current command and the next one and so on (ending a nested loop and also the loop its nested in)  
\>

```vb
Select X – 2 >
    If 0 Then A Else B
    If 1 Then C
    If 2 Then D
    Else E
End If
```

Breaking, because each __Case__ group is evaluated now.

#### Text Code Blabbing < >

##### Conditional Jumps

Two forms of conditional jumping are generally used: selection and iteration. Selections might do either one thing or the other depending on a __Boolean__ state. Iterations might repeat something depending on a __Boolean__ state.

###### Selection

Selection is performed with __If__ and __Select__ statements.

####### If

With an __If__ you can choose wether or not to do something depending on a __Boolean__ state:

```vb
If X Then A
```

If __X__ returns __True__ then __A__ is called

With An __If__ you can also choose to do either one thing or the other:

```vb
If X Then A Else B
```

If __X__ returns __True__ then __A__ is called. If __X__ returns __False__ then __B__ is called.

An alternative notation of the __If__ above is:

```vb
If X Then
    A
Else
    B
End If
```

You can nest __If__'s:

```vb
    If X Then
        A
    Else 
        If Y Then 
            B
        Else
            C
        End If
    End If
```

You can also use __Else If__:

```vb
    If X Then
        A
    Else If Y Then 
        B
    Else
        C
    End If
```

Or in an alternate notation:

```vb
    If X Then A Else If Y Then B Else C
```

You can use alternatives for the __Then__ keyword. You can leave it out or you can use a comma:

```vb
If X, A Else If Y, B Else C

If X
    A
Else
    B
Else If C
    D
End If
```

####### Select

Selects let you combine a large __Else If__ construction to an easier notation:

```vb
If X = 0
    A
Else If X = 1
    B
Else If X = 3
    C
Else If X = Y + 1
    D
End If
```

The three conditions above all have the same beginning:

```vb
X = 0
X = 1
X = 3
X = Y + 1
```

They all begin with __X =__ .

The __Select__ statement lets you take advantage of that to make the notation easier:

```vb
Select Case X =
    Case 0
        A
    Case 1
        B
    Case 2
        C
    Case Y + 1 
        D
End Select
```

You can also use the comma to use the same clause for multiple conditions:

```vb
Select Case X =
    Case 0
    A
    Case 1
        B
    Case 2
        C
    Case Y + 1, 4
        D
End Select
```

You can use the __:__ to avoid using so many lines:

```vb
Select Case X =
    Case 0: A
    Case 1: B
    Case 2: C
    Case Y + 1, 4: D
End Select
```

< Maybe I should just first explain the concept and then introduce all them various notations. Maybe this text notation should be explained totally separately anyway. I only needed it to give an example of an __If__ here, man. >

A Basic __Select__ statement:

```vb
Select Case X
    Case 0: A
    Case 1: B
    Case 2: C
End Select
```

Is notated in Symbol text code as:

```vb
If X
    = 0 Then A
    = 1 Then B
    = 2 Then C
End If
```

Or:?

```vb
Select X
    If = 0 Then A
    If = 1 Then B
    If = 2 Then C
End If
```

Or:?

```vb
Select X
    If = 0: A
    If = 1: B
    If = 2: C
End If
```

Or:?

```vb
Select X
    If = 0, A
    If = 1, B
    If = 2, C
End If
```

Or:?

```vb
If X
    = 0, A
    = 1, B
    = 2, C
End If
```

###### Iteration

```vb
For i = 0 To 10
    ...
Next

For i = 0 To 10 Step 2
    ...
Next

For i = 0 Till = 8 Step + 1
    ...
Next

For i = 0 Till > 8 Step + 1
    ...
Next

For i = 0 Till > 8 Step i++

For i < 3

For Till i < 3 

i = 0. Repeat As i >= 5, Step i++.
```

A comma can be used to separate

Maybe for should be called repeat

#### Brainstorm

Maybe the command references of execution flow commands need to have a certain command interface.

-----

About the order of execution without execution flow commands: Some calls might be made before others because the result of one call is used in another call. That defines (some of) the order of precedence of calls.  
The order of the calls in a command is (part) determined by dependence, independent of the order the programmer gives.

The programmer can change the order of things that are arbitrarily called and insert calls into the obligatory order or calls, but if it’s not so relevant, the programmer doesn’t even provide the call order. Most of the time it is not that relevant. (or is it, to what extent can I not see the requirement of the order of calls, even when its order is very important?

-----

If a command takes a reference to a nested command then you can do this notation:

< Square with loose squares and another square with squares pointing at those loose squares >

Defining the contents of the command references right within the

##### Execution Flow Controls which call is made next

<  
Most of what’s done inside a command is calling other commands.

Apart from executing a sequence of calls linearly, you can alter the course of the calls using execution flow.

A clause is like a command itself. For that you can see execution flow as selecting which command might be called next. Or actually which clause might be called next.

First explain that a control statement controls which call is made next. They are responsible for the arbitrarily in execution. Otherwise there might be just one way a program can execute from start to beginning and that’s that, but execution flow sees to it that there is variation in the execution of a program.

In one compiler optimization technique it is these execution flow statements that are analysed. Execution flow statements make execution variable and this compiler technique analyses how variable that actually is. Maybe the execution flow might not be reached with too many different values, let’s say, two values. In that case you might consider removing the variation in execution by making two commands one of which is one situation of the execution flow statement and the other one is the other situation of the execution flow statement. At calls to the execution flow statement or indirect calls to it, you insert the variation that applies right there.  
\>

##### Nice Example

```vb
For I = 0 to 4
    A(I)
    B(I + 1)
    If I <> 0 Then 
        C
    Else
        D
    End If
Next
```

##### Execution Flow is Call Control

This means that in Symbol the definition of execution flow is selecting what command to call next depending on a __Boolean__ state.

You could speak of conditional calls, actually. 

Calls can be managed by execution flow. Execution flow manages the regular order of the calls *and* can alter the regular traversal of calls depending on a Boolean result (__If__, __Select__, __For__, __Do__). The Boolean result can spring from any combination of forms of algebra that in the end returns a Boolean result. Comparison algebra and Boolean algebra return Boolean results.

##### => Execution Flow

But... if you pass a clause reference to an execution flow command the execution flow CAN call the clause, but only in the context of the command instance that called the execution flow command!

Execution flow commands might call clauses in the context of a *specific call* to the clause’s command definition.

### Declared Traversions / Constructions

(From Original Symbol Documentation from 2004)

< 2008-10-10 You can change this into iterators to which you pass a command reference. >

I’ve noticed that with my coding methods in deep structures in Visual Basic 6, I use code like this for instance:

```vb
With aClass
    With .Attributes
        For i = 0 To .Count - 1
            With .Item(i)
                L "Private Const " + tPrefix + .CodeName + "Field As Long = " + CStr(aIndex)
                aIndex = aIndex + 1
            End With
        Next i
    End With
    With .RelatedClasses
        For i = 0 To .Count - 1
            If .ItemUsed(i) Then
                With .Item(i)
                    If .AbstractNumber = One Then
                        If .WhenX.EditMode = ObjectEditValues Then
                            'Recursion
                                AddFieldConstants .Type, aIndex, tQualifier + .CodeNameSingular
                        End If
                    End If
                End With
            End With
        Next i
    End With
End With
```

There are actually two loops in this construction. I frequently need those loops and I then copy those constructions.

It might be an idea to be able to declare those constructions and reuse them by name:

Declaration of constructions:

```vb
Construction Type Attributes ( aClass )
    With aClass
        With . Attributes
            For i = 0 To . Count - 1
                With . Item ( i )
                    ...
                End With
            Next i
        End With
    End With
End Construction
```

```vb
Construction Related Types With Edit Values ( aClass )
    With aClass
        With . Related Types
            For i = 0 To . Count - 1
                If . Item Used ( i ) Then
                    With .Item ( i )
                        If . Abstract Number = One Then
                            If . When X . EditMode = Values Then
                                ...
                            End If
                        End If
                    End With
                End With
            Next i
        End With
    End With
End Construction
```

Use of construction:

```vb
For Type Attributes ( aClass )
    L "Private Const " + tPrefix + . Code Name + "Field As Long = " + aIndex
    aIndex = aIndex + 1
End For

For Related Types With Edit Values ( aClass )
    Add Field Constants ( . Type , aIndex , tQualifier + . Code Name Singular )
End For
```

Looking at this, I see that you could do this easily in Symbol, by making your own execution flow command.