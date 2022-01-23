System Interfaces | Connectors & Connections
============================================

`[ Preliminary documentation ]`

[back](./)

__Contents__

- [Connectors](#connectors)
    - [Loose Ideas about Connectors](#loose-ideas-about-connectors)
- [Connections](#connections)
    - [Outward and Inward Connections](#outward-and-inward-connections)
    - [Remarks](#remarks)
        - [Class Connections](#class-connections)
        - [Value Connections](#value-connections)
        - [Data Connections](#data-connections)
        - [Clone Connections](#clone-connections)
        - [Existence, Execute & List](#existence-execute--list)

## Connectors

System command definitions are displayed in the system interface:

![](images/4.%20Connectors%20&%20Connections.001.png)

But more commonly a system command definition is displayed as a *connector*:

![](images/4.%20Connectors%20&%20Connections.002.png)

A connector represents a potential call to a system command. The connector looks like the result of the system call. The connector above is an __Get Object__ connector. It represents the __Get Object__ system command definition, and it looks like the result of a __Get Object__:

![](images/4.%20Connectors%20&%20Connections.003.png)

If a system command is not about establishing a connection between symbols, the connector looks like a system command call itself, for instance for the __New__ command:

![](images/4.%20Connectors%20&%20Connections.004.png)

But then more like a loose end, because an unconnected line is displayed at the end of the (potential) __New__ call. An actual __New__ call might look like this:

![](images/4.%20Connectors%20&%20Connections.005.png)

So a connector looks like the result of a call or otherwise like the call.

An actual connection might not replace the connector: a connector is always displayed, because others can still connect to the object as well:

![](images/4.%20Connectors%20&%20Connections.006.png)

The line at the top is an actual connection.  
The line at the bottom is the connector.

Each system command has a connector, so every system aspect has its own set of connectors. The overview below displays the different connectors.

|                                                       |                                                       |
|:-----------------------------------------------------:|:-----------------------------------------------------:|
|                    __Get Object__                     |                    __Set Object__                     |
| ![](images/4.%20Connectors%20&%20Connections.002.png) | ![](images/4.%20Connectors%20&%20Connections.007.png) |
|                                                       |                                                       |
|                   __Use As Class__                    |              __Use Reference As Class__               |
| ![](images/4.%20Connectors%20&%20Connections.008.png) | ![](images/4.%20Connectors%20&%20Connections.009.png) |
|                                                       |                                                       |
|                     __Set Class__                     |                                                       |
| ![](images/4.%20Connectors%20&%20Connections.010.png) |                                                       |
|                                                       |                                                       |
|              __Object-Bound Get Class__               |             __Reference-Bound Get Class__             |
| ![](images/4.%20Connectors%20&%20Connections.011.png) | ![](images/4.%20Connectors%20&%20Connections.012.png) |
|                                                       |                                                       |
|                     __Get Value__                     |                     __Set Value__                     |
| ![](images/4.%20Connectors%20&%20Connections.013.png) | ![](images/4.%20Connectors%20&%20Connections.014.png) |
|                                                       |                                                       |
|                     __Get Data__                      |                     __Set Data__                      |
| ![](images/4.%20Connectors%20&%20Connections.015.png) | ![](images/4.%20Connectors%20&%20Connections.016.png) |
|                                                       |                                                       |
|                   __Get Clone (2)__                   |                   __Set Clone (2)__                   |
| ![](images/4.%20Connectors%20&%20Connections.017.png) | ![](images/4.%20Connectors%20&%20Connections.018.png) |
|                                                       |                                                       |
|                        __New__                        |                       __Annul__                       |
| ![](images/4.%20Connectors%20&%20Connections.004.png) | ![](images/4.%20Connectors%20&%20Connections.019.png) |
|                                                       |                                                       |
|                      __Execute__                      |                                                       |
| ![](images/4.%20Connectors%20&%20Connections.020.png) |                                                       |
|                                                       |                                                       |
|                        __Add__                        |                      __Remove__                       |
| ![](images/4.%20Connectors%20&%20Connections.021.png) | ![](images/4.%20Connectors%20&%20Connections.022.png) |

### Loose Ideas about Connectors

System Interfaces,  
2009-09-27

Not all system commands are present here yet.  
Also: the connectors involved in pointer-to-pointer situations are not present here yet.

JJ

## Connections

This section covers any kind of connection between objects, that is a result of accessing system aspects. First the graphical overview of all possible system aspect connections is displayed. After that the details are covered.

|                                                       |                                                       |
|:-----------------------------------------------------:|:-----------------------------------------------------:|
|                    __Get Object__                     |                    __Set Object__                     |
| ![](images/4.%20Connectors%20&%20Connections.003.png) | ![](images/4.%20Connectors%20&%20Connections.023.png) |
|                                                       |                                                       |
|                   __Use As Class__                    |                     __Set Class__                     |
| ![](images/4.%20Connectors%20&%20Connections.024.png) | ![](images/4.%20Connectors%20&%20Connections.025.png) |
|                                                       |                                                       |
|                     __Get Value__                     |                     __Set Value__                     |
| ![](images/4.%20Connectors%20&%20Connections.026.png) | ![](images/4.%20Connectors%20&%20Connections.027.png) |
|                                                       |                                                       |
|                   __Get Clone (2)__                   |                   __Set Clone (2)__                   |
| ![](images/4.%20Connectors%20&%20Connections.028.png) | ![](images/4.%20Connectors%20&%20Connections.029.png) |
|                                                       |                                                       |
|                        __New__                        |                       __Annul__                       |
| ![](images/4.%20Connectors%20&%20Connections.030.png) | ![](images/4.%20Connectors%20&%20Connections.031.png) |
|                                                       |                                                       |
|                     __Something__                     |                      __Nothing__                      |
| ![](images/4.%20Connectors%20&%20Connections.032.png) | ![](images/4.%20Connectors%20&%20Connections.033.png) |
|                                                       |                                                       |
|                      __Execute__                      |                                                       |
| ![](images/4.%20Connectors%20&%20Connections.034.png) |                                                       |
|                                                       |                                                       |
|                        __Add__                        |                      __Remove__                       |
| ![](images/4.%20Connectors%20&%20Connections.035.png) | ![](images/4.%20Connectors%20&%20Connections.036.png) |

### Outward and Inward Connections

An __Set Object__ connection is an outward connection.

![](images/4.%20Connectors%20&%20Connections.023.png)

Outward connections do not have access marks. Inward connections do have access marks:

![](images/4.%20Connectors%20&%20Connections.003.png)

This is not only because outward connections are more common, but also because an outward connection is more passive than an inward connection.

When a symbol is inward connected:

![](images/4.%20Connectors%20&%20Connections.037.png)

Each consult of the symbol on the right, that connects inwards, results in a call to to the __Get__ of the target symbol. So the connection is more active in that each consult of the source object requires a __Get__ on the target object. Inward connections are also called __Get__ connections.

When a symbol is outward connected:

![](images/4.%20Connectors%20&%20Connections.038.png)

The symbol is directly connected to the target object. It stores the __ID__ of the target object and refers to it directly, without executing a __Get__ on each consult. The outward directed connection may have been established through access to a __Set__ command, but that call is history. The connection might not pass through to the insides of another object. Outward connections are called __Set__ connections. However, the __Set__ action is history and all that matters is the result, not how it was established.

Passing through to the inside of another object requires the __Get__ command of the target symbol to be executed.

This also conforms to the idea of automatic containment. In automatic containment, outward directed connections are automatically established: automatically drawn out in the diagram without an intervention of a programmer. Inward directed connects were actively established by the programmer. They follow a qualification before getting to the final object. They are more active and display an access symbol and result in active __Get__’s taking place all the time.

### Remarks

#### Class Connections

> __Use As Class__ and Set __Class__ are mentioned here. __Class Get__ is not covered here, because that is only used in active assignments, not in connections.

#### Value Connections

> Note that the indication of *direction* for __Get__ and __Set__ is switched for the __Value__ aspect, compared to the __Object__ aspect: __Get Object__ is inward, while __Get Value__ is outward.
> 
> What you can also notice, is that outward __Value__ connections do have access marks, while outward connections for the __Object__ and __Class__ aspects do *not* show access marks. This is because *outward* __Object__ and __Class__ connections are passive connections and outward __Value__ connections are *active* connections, because an __Value__ connection is always an assignment.
> 
> __Value__ connections are assignments, even though they do not have an ‘assignment notation’.

#### Data Connections

> A __Data__ connector such as the following:
> 
> __Get Data__
> 
> ![](images/4.%20Connectors%20&%20Connections.039.png)
> 
> is an abstract connector: it represents any possible __Get__ connection to any sub-sub-object. Even though there is a __Data__ *connector*, there are no __Data__ *connections*. Any __Get__ connection to a sub-object is be considered a __Get Data__ connection.

#### Clone Connections

> The diagrams above show access connections for cloning at a depth of __2__. That is just an example. Any cloning depth other than __2__ could be used.
> 
> Cloning has the exact same notation as the __Value__ aspect, but then with a number near the access mark. Cloning is *that* closely related to the Value aspect.

#### Existence, Execute & List

> This part of the documentation displays connections that are a result of accessing system aspects. For the __Object__ aspect that means an actual connection. But for the __Existence__, __Execute__ and __List__ aspects it means something different: more like a *call* or sometimes more like a *state*.