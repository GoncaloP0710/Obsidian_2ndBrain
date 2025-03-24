2025-03-24 18:39

Status: #done 

Tags: [[Deteção e Tolerância a Intrusões]] [[Distributed Systems]] [[Fault Tolerance]] 

# Distributed system models

A distributed system is a set of connected process sharing some part of its state.

Two main components:
- A set of *process* (usually we will consider a set of n servers and an unknown number of clients)
- These processes *communicate* through *bidirectional links*

Process can also communicate through shared memory or broadcast networks.
- There are a lot of possible system models…

The system model must be chosen in such a way to increase the coverage of our system.

*Processes*:
- Timing assumptions
	- The process have access to real-time clocks?
	- These clocks are synchronized?
	- ...
- Fault model
	- Omissive (e.g., crash) or assertive (e.g., Byzantine)?
- Memory
	- The process has access to stable memory?

*Communication*:
- Topology:
	- Everyone is (directly) connected to everyone
- Timing assumptions
	- Communication delay is bounded
	- Communication delay is eventually bounded
- Fault model
	- Channel can lose messages
	- Channel can modify messages
- Authenticated or not
	- The channels are authenticated?
- Ordered delivery or not
	- Messages are delivered in FIFO order

# Summary of the Fault-tolerant Distributed Systems Course

System models are what define your assumptions about the environment.
They also define what you can and cannot do in your system.
They should be defined carefully to ensure coverage of the assumptions in the real world.
We do not have reliable channels in the real world, only **fair channels**.
**Reliable broadcast** can be implemented without time assumptions (asynchronous systems).
**Replication** (usually) needs *consensus*.
**Consensus** is equivalent to *atomic* (or total order) *broadcast*, which is equivalent to a *distributed ledger*.
(Crash) **Fault-tolerant consensus**:
- Cannot be solved deterministically in asynchronous systems
- Can be solved probabilistically by using randomization
- Can be solved in eventually synchronous systems
Failure detectors allow us to encapsulate the use of time in many distributed computing problems.
- **Perfect failure detectors** only exist in synchronous systems
- **Unreliable failure detectors** are sufficient to solve consensus and they can be implemented on eventually synchronous systems

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585153/mod_resource/content/4/intol-04-bftclassics-sync.pdf