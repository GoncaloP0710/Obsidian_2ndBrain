2025-03-27 15:53

Status: #done 

Tags: [[Deteção e Tolerância a Intrusões]] [[Byzantine]] 

# PBFT – Practical Byzantine Fault Tolerance

Primary-based BFT SMR algorithm
- System evolves in views, numbered sequentially
- In each view v, one server is the primary, the others are the backups

Efficient and fast
- Uses message authentication codes (MACs), instead of asymmetric crypto signatures
	- This is not so important today, so we’ll ignore it
- Prevention-tolerance mix
	- Clients’ requests and server messages are signed
	- Messages with invalid signatures are discarded

## PBFT - System Model

**Asynchronous distributed system**

Network can lose, delay, reorder and duplicate messages; but cannot do that indefinitely
- i.e., they require *fair links* to implement reliable channels

Byzantine fault model
- with fault independence (i.e., no common mode faults)
- requires 3f+1 replicas to tolerate f faults

Cryptography
- PK signatures to facilitate the protocol presentation
- Cryptographic hashes
- Adversary cannot break cryptographic primitives

## PBFT – Service Properties

**Deterministic** replicated service

Service’ safety:
- The replicated service should behave as its centralized counterpart (*Linearizability*)
	- Even with malicious replicas compromising their states

Service’ liveness (**requires synchrony**):
- A command issued by a correct client will eventually be executed (Wait-freedom) if the network transmission delay doesn’t grow faster than real time
	- This is satisfied by the partial synchronous model: the system is asynchronous, but there is an unknown global stabilization time after which it become synchronous 

## PBFT – Algorithm (version 2002)

Algorithm essentials:
- Two operation modes: **normal operation** and **view-change**
- System evolves in views (if some operation cannot be totally ordered, a new view is started)
- A **checkpoint** protocol is executed periodically
- A **state transfer** protocol is executed when needed (after a replica recovery)

Algorithm outline:
- All messages are signed
- Client multicasts a request with a command and a timestamp to all servers
- Servers reach agreement on the request to be delivered w/ a sequence number
- Client waits for at least f+1 replies with the same result (at least one correct server executed the operation and produced the result)

## Partially Synchronous System Model

A partially (or eventually) synchronous system is a
system whose runs satisfy the following properties:
- There is an upper bound δ on message transmission delays, but this bound:
	1) is not known, and
	2) holds only after a finite (unknown) time (called Global Stabilization Time - GST).
- Local processing times are negligible.

## Single-shot PBFT: Separating Safety from Liveness

The protocol works in a sequence of views
- Each view has one leader, and processes use leader($v$) to determine the leader of a view v
- The leader is the only one capable of proposing values in its v
- The protocol uses quorums of 2f+1 processes (assuming n = 3f+1)
- A Synchronizer is responsible for changing views.

### The phases of a view

1. Pre-processing
	- Each process informs the leader about the latest value it prepared in a previous view
2. Propose
	- Leader computes a *valid* proposal and sends it along with some supporting information to all others
3. Prepare
	- Processes communicate with each other to avoid to be fooled by a faulty leader
4. Commit
	- Processes communicate with each other to commit a value

A **faulty leader** may impact the first 3 phases so the system might have to start from the beginning.

The **syncronizer** can stop the view at any point.

## Why PBFT works? (Safety)

Correct processes do not prepare invalid proposal because:
- The leader sends the proposal along with some supporting information by which non leader processes can identify whether its proposal is valid or not.

Correct processes prepare at most one value in a view because:
- A correct process sends a PREPARED message only for the first PROPOSE that it receives in a view
- If there are multiple prepared values, there should be at least one correct process that sent two PREPARED messages, which is impossible.

If a correct process commits a value, all other correct processes cannot commit a different value because:
- A correct process sends a COMMITED message only if it receives PREPARED messages from 2f+1 processes
- There can not be two different quorums of 2f+1 (out-of 3f+1) replicas that send **PREPARED** messages for different values
	- These quorums would overlap on at least f+1 replicas
	- Thus, **one correct** replica should have sent contradictory messages
	- This is impossible!

## Why PBFT works? (liveness)

A Byzantine leader can decide not to send PROPOSE
messages:
- However, the Synchronizer will change the view (e.g., using timers), to elect a new leader

Liveness can be assured if eventually a view is long enough to finish the protocol execution with a correct
leader
- This is satisfied by the partially synchronous system model

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585154/mod_resource/content/4/intol-05-bftsmr-pbft.pdf