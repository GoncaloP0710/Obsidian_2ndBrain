2025-01-08 18:39

Status: #done 

Tags: [[Software Security]] [[Threads]] 

# Concurrency and Reentrant Functions

### Concurrency
In programs, there is also the normal concurrency of operations that need to access shared objects.

Often, operations must be executed atomically over these shared objects, i.e., without interruption.

Mutual exclusion is a solution for some of the problems.
Difficulties with mutual exclusion
- starvation: a thread is never scheduled for execution
- deadlock: threads inter-block themselves

### Reentrancy
A function is reentrant if several instances of the function can be executed in parallel in the same address space.

Addressing reentrancy in two main sources of problems:
- **Thread-safety** – reentrancy in relation to several threads
- **Async-signal-safety** – reentrancy with signals (or exceptions)

#### Thread-safety
Requirements for a function to be reentrant:
- does not use static variables, global variables, other shared resources
- only calls reentrant functions

#### Async-signal-safety
Signals are a Unix/POSIX mechanism to indicate asynchronous events to a process.
Can be treated by a signal handler.
Signal handlers must be asynchronous-safe.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554484/mod_resource/content/7/T_races.pdf