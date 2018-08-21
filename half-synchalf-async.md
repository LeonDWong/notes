# Half-Sync/Half-Async

**One of efficient pattern of concurrency model.**

### Async

Efficient but hard to maintain. In the software architecture of BSD UNIX networking subsystem Because async can deal with I/O simultaneously, not need to wait for resources event. But it's hard to main, because programmer should know which async event should be called and give them state. Using in low-level communicaiton like IP, TCP/UDP input.

### Sync

*Need for programming simplicity and need for execution efficiency.* Just stand against explanation above. Using in higher-level like user-level programming.

### So, we use Half-Async/Half-Sync pattern

*This pattern integrates synchronous and asynchronous I/O model in an efficient and well-structured manner.* Asynchronous is using in high-level(such database queries and file transfers). Synchronous is using in low-level(such as servicing interrupts form network controllers). High-level operation is much than low-level's, this pattern localize the complexity of asynchronous processing within a single layer of a software architecture. And communication between tasks in two layers is mediated by a Queueing layer(socket layer).


## About

[origin](https://www.cse.wustl.edu/~schmidt/PDF/PLoP-95.pdf)

