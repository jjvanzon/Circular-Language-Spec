Encircle Language Construct Drafts | From Spec
==============================================

Commands Construct Drafts
-------------------------

`[ Preliminary documentation ]`

- [Sub-Commands in a Diagram](#sub-commands-in-a-diagram)
- [Loose Ideas](#loose-ideas)

### Sub-Commands in a Diagram

`<< terminology >>`  

Sub-commands `are` active commands `contained` inside a parent command. `You can` encounter them inside `any` command symbol: both active and inactive commands symbols `can` contain sub-commands. `The` sub-commands `are` *active* commands: command calls, active clauses or active command references.

Below `is` a picture of two sub-commands inside an inactive command:

![](images/1.%20Commands%20Main%20Concepts.048.png)

`The` __Parent Command__ `is` an inactive command, because it `is` a square. In `the` diagram above, `the` __Parent Command__ `contains` two sub-commands. `The` sub-commands `are` displayed as diamond shapes. One of `the` sub-commands `is` a call, because it `has` a dashed line `going` outside `the` __Parent Command__, `tying the` sub-command to its command definition. `The` other sub-command `is` an *active clause*, because it `might not` redirect its command definition.

Below `is` a picture of two sub-commands inside an active command:

![](images/1.%20Commands%20Main%20Concepts.049.png)

It `is the same` picture as `the` other diagram, `only now the` __Parent Command__ `is` an executable command symbol, `not` an inactive command.

### Loose Ideas

`<< rule rich >>`  
Expected behavior might be that a command call might only run once.

-----

`<< rule rich >>`  
When a call might be placed directly inside an *object,* it might* be a question what might actually happen to it. It may be an idea, that the command might only be run manually. Another idea might be, that those calls might run just after the object was created (perhaps a bit like constructors from object oriented programming).

-----

`<< rule rich >>`  
A command reference may commonly be inactive. But a command reference might also be active.

-----

`<< rule rich >>`  
`Both the` command reference and its target `can` be `either` active or inactive.

-----

`<< rule rich >>`  
An *active* reference to an *inactive* command `might not` be executed. `The` `final` target of object redirections `is the` object itself, and when it `is` inactive, `the` command object `can not` be executed, `but only function` as a prototype.

`You can not` execute an *active* command object through an *inactive* command reference `either`. But an active reference to an inactive reference to an active command `*can*` be executed.

-----

`<< rule rich >>`  
In Encircle command references and their target commands could in theory be either inactive or executable.

![](images/1.%20Commands%20Main%20Concepts.025.png)

It `might not matter` whether it `is` squares or diamonds, `because the only` difference between a square and a diamond, `is` that a square `can not` be executed and a diamond `*can*`.

-----

`<< rule rich >>`  
A clause `might not` redirect its definition, because then `it might` be a command call.

-----

`<< rule rich >>`  
A clause `might not` redirect its object, because then `it might` be a command reference.

-----

`<< rule rich >>`  
A clause `is never` situated inside an object, or `it might` not be a clause.

-----

`<< rule rich >>`  
Active clauses, command calls and active command references in parent commands `are always` private, because `you can not` reference a sub-command.

![](images/1.%20Commands%20Main%20Concepts.052.png)

But *inactive* clauses `*can*` be referenced and might be made public.

![](images/1.%20Commands%20Main%20Concepts.053.png)

-----

`<< rule rich >>`  
Only when an executable object `is actually` executed, it `is` called an execution. When an executable object `is` not executing yet, it `is still only` a *potential* execution.

-----

`<< rule rich >>`  
A command, that might be used as a definition, `is usually` not executable. Only `individual` calls to `the` command, that `use the` command as a definition, might be executable. If a command definition `is` executable `after all`, then it `is clearly` mentioned, that it `is` an *active* command definition, because it might be a special situation.

-----

`<< rule-rich >>`  
A command reference `is` considered data. A command reference in a parent command `is` considered data of `the` parent command, `even when` it `is` active, `in case of which` it `*is*` considered a sub-command `but a special` form of it. Even though it `executes`, it `is still` a reference to an executable object `*elsewhere*`. Only `the` *pointer* part `is the` data. Command references `are` *data* that can be *private* or *public*.

