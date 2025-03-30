2025-03-30 19:11

Status: #done 

Tags: [[Deteção e Tolerância a Intrusões]] [[PBFT – Practical Byzantine Fault Tolerance]] [[Byzantine]] 

# BFT - Improving Resilience

All distributed protocols can have their performance hurt by (Distributed) *Denial of Service attacks*
- There is nothing we can do about it… we need communication and timing assumptions to solve consensus

There are two attacks (≠ (D)DoS) that can dramatically decrease the performance of systems like PBFT and Zyzzyva.

#### **Attack #1**: causing view change with a malicious client without using DoS

On PBFT, clients need to send a request “signed” with an authenticator (a MAC vector).
A malicious client can send a **corrupted authenticator** that is valid for all backup replicas, but not for the primary.
- The primary will ignore the client’s request
- Other replicas will accept it and, after their timer expires, will relay it to the primary
Since the **primary will never accept** this request, other replicas will start a **view change** after a second timeout.

Conclusion: *the use of authenticators allow faulty clients to force view changes as they wish*.

#### **Attack #2**: degrading performance with a faulty primary

A faulty primary must order a request before other replicas timers expire for this request.
Assuming Timeout = 100 ms, if a faulty primary delays the ordering of each request by 90 ms, a view change will not be triggered.
Nonetheless, the performance of the system will drop dramatically.

Conclusion: *a faulty primary can inject a delay of almost Timeout ms on each request processing, making the end-to-end performance of the system orders of magnitude worse than expected*.


#### How to “patch” attack #1’ vulnerability?

Make clients sign (not with MAC vectors) their messages.
Digital signatures (like RSA) ensure that if some correct server authenticates the message, then all correct servers will authenticate the message.
Performance issues!

#### How to mitigate attack #2?

Solution 1: use decentralized (leader-free) protocols.
Solution 2: monitor the primary’s performance and start a view change if it’s too low.
Solution 3: rotate the primary periodically.

## Robust BFT SMR (Clement et al. 2009)

Clement et al. (2009) proposes a variation of PBFT that implements robust state machine replication.
- The name of the protocol is Aardvark

By robust, it means:
- Maintains a stable performance even when under attack by f malicious replicas and an unbounded number of clients

Three main differences (when compared with PBFT):
- Clients should sign requests
	- to avoid malicious clients provoking view changes
- Resource Isolation
	- to resist denial-of-service attacks against network interfaces
- Periodic view changes
	- to avoid performance degradation attacks

## Spinning (Veronese et al., 2009)

A protocol build upon PBFT, but with a modification based on a simple idea:
- PBFT’s problem is that a malicious primary can keep ordering requests very slowly without triggering view changes
- So, why not change view after each message commit?
- in this way, the sequence number of a message matches exactly the view number of its delivery

Potential problem:
- **The view change protocol is complex and costly**
- This is not a problem since the view change will deterministically happen after every committed message, so it is not necessary to have a special protocol to change primary

The resulting protocol (Spinning) makes the primary role rotates to all servers.

### Spinning (issues)

Without the repair procedure of view changes, how replicas recover from a malicious primary on some view?
- Merge operation joins one or more faulty views (i.e., with faulty primaries) with a correct view (i.e., with correct primary)
- The idea is very similar to PBFT’s view change: the new correct primary will read the state of the system and proceed ordering requests ensuring the protocol invariants

Faulty replicas can force merge operations periodically
- To avoid that, after a merge operation, **the primary of the most recent merged view is put on a blocklist**
- Every time a replica goes to this list, it stays there for a number of turns
- **Blocklisted replicas cannot be primary on their views, but otherwise can participate on the protocol as a backup**

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585155/mod_resource/content/5/intol-06-bftsmr-advanced.pdf