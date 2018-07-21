## Introduction

Javascript has its own event loop because it's a event-driven script language. But somehow, the event loop between browser and nodejs is different. Event loop in nodejs is more complicate.(We don't talk about event loop in browser here).

## Phase

Event loop in nodejs has 6 phases which are timers phase, pending phase, idle prepare phase, poll phase, check phase, close callback phase. Every phase is taken in order one by one. Only once one phase executable queue is exhausted or maximum callback of queue is reached.

#### timers

Executes callbacks scheduled by `setTimeout` or `setInterval`.

#### pending

Executes callbacks in I/O event which is deferred to next loop.

#### idle prepare

Used in internally.

#### poll

Executes I/O related event, 

#### check

Executes `setImmediate`.

#### close callback

Executes close subscriber event, like `server.on('close')`.