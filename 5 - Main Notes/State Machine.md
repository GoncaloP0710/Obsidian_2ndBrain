2025-03-27 15:54

Status: #done 

Tags: [[Deteção e Tolerância a Intrusões]] 

# State Machine

## State Machine Replication

Characteristics
- **confinement** - *atomic* commands/operations
- **fault tolerance** – “easy” replication

Execution model
- **Initial state** - All correct replicas start in the same state
- **Coordination** - All correct replicas execute the same
commands in the same order
- **Determinism** - The same sequence of commands executed in the same state in any two correct replicas generates the same final state and sequence of outputs

Programming
- message-based request/reply interactions
- requires *deterministic execution*
	- No local clock reads, random numbers, etc.
	- No multi-threading 
## Byzantine State Machine Replication (classes of algorithms)

**Leader-based**
- BFT protocol like Paxos or RAFT
- There is a *primary (or leader) server* that orders the requests
- The leader imposes the same sequence of requests in the same order to non-primary servers, in some Byzantine-resilient way
- When primary is suspected to be *faulty*, a new primary is chosen (e.g., PBFT, BFT-SMaRt) or it changes periodically.

Decentralized
- No distinguished server
- Order of requests defined in a decentralized way, thorough a Byzantine-resilient consensus algorithm (e.g., randomized)

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585154/mod_resource/content/4/intol-05-bftsmr-pbft.pdf