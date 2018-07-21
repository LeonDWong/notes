## Introduction

Javascript has its own event loop because it's a event-driven script language. But somehow, the event loop between browser and nodejs is different. Event loop in nodejs is more complicate.(We don't talk about event loop in browser here).

## Phase

Event loop in nodejs has 6 phases which are timers phase, pending phase, idle prepare phase, poll phase, check phase, close callback phase.

#### timers

