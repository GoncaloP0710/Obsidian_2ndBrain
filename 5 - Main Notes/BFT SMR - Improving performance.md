2025-03-30 17:49

Status: #done 

Tags: [[Deteção e Tolerância a Intrusões]] [[Byzantine]] [[PBFT – Practical Byzantine Fault Tolerance]] 

# BFT SMR - Improving performance

PBFT performance is competitive with crash fault-tolerant systems, and in some cases even with non replicated systems.

However, in the expected common situation in which
- There are no faults
- The system is synchronous
- There is no concurrency (no contention)
PBFT still requires $2n^2 + n$ messages and 5 communication steps.

![[BFT SMR - Improving performance 1.png]]

## Zyzzyva – Speculative BFT

Main idea: PBFT with *speculative execution*
- Each replica (speculatively) executes a request just after receiving the sequence number of this request by the primary
- After executing the request, they send a reply to the client
- The consistent state of the replicas only matter to clients, so let them verify if all replicas are on the same state
- If there is some problem (e.g., the primary sends different operations to different replicas), a correct client will detect it
- This client will inform the replicas, which must roll back to a safe state and change the primary

Improves latency and throughput on the best case
- 3 communication steps and $2n$ message exchanges

![[BFT SMR - Improving performance 2.png]]

![[BFT SMR - Improving performance 3.png]]

### Issues

Speculative execution on servers might not be a good idea
- You need to be able to roll back to a committed state if a view change is triggered
- This makes your server code more complicated

If you wait for replies from all replicas, you will always be waiting for the slowest one.
- In non-synchronous networks, you will have to calibrate your **timeout** value carefully

Zyzzyva is vulnerable to several attacks, just like PBFT.

## Abstract – BFT Composability

Generalizes the idea of creating “optimistic” protocol phases.
Encapsulate these phases in sub-protocol modules, called abstract, simplifying the design of new BFT protocols.

Main idea:
- Each Abstract is like a state machine replication (SMR) implementation that clients interact with
- However, in SMR, all client requests are committed in total order, while an abstract module may abort and stop if certain conditions are not meet (e.g., synchrony, no failures)
- Abstract modules can be aborted and switched (i.e., we can stop one and start another) to ensure progress

![[BFT SMR - Improving performance 4.png]]

### Abstract – Aliph

Aliph is a very efficient protocol that makes use of three Abstract modules.

![[BFT SMR - Improving performance 5.png]]

### Resource-Efficient BFT

The same principles of Abstract can also be used to decrease the number of active replicas in failure-free executions, improving the resource usage (e.g., CPU, network bandwidth) of the system.

Main idea:
- Use only n-f active replicas to run the protocol and execute requests
- The f passive replicas just receive and store updates
- If a failure is detected, switch to the normal mode with n replicas

![[BFT SMR - Improving performance 6.png]]



# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585155/mod_resource/content/5/intol-06-bftsmr-advanced.pdf