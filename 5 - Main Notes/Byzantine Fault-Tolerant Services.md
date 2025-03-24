2025-03-24 18:27

Status: #done 

Tags: [[Deteção e Tolerância a Intrusões]] [[Fault Tolerance]] 

# Byzantine Fault-Tolerant Services

Consider a server accessed by several clients.
How to make it Byzantine fault-tolerant (BFT)?
- Byzantine faults: a faulty process (client or server) can deviate arbitrarily from its specification, i.e., upon a failure, anything can happen. Can model hardware defects, software bugs and intrusions!

Which services can benefit from this?
- Typically, a trusted third party that we want to make trustworthy
- Anything that can be modelled as a deterministic state machine

## An Example: Blockchains

Integrity, auditability, non-repudiation properties, i.e., a malicious party cannot (undetectably):
- Insert/Modify a block in its copy of the chain
- Delete a block from the middle of its copy of the chain
- Invalidate or repudiate any of the blocks in a copy of an honest party

Is it just a secure log of transactions?
- Yes, but now it is called *Secure Ledger*
What is new?
- It is distributed, maintained in a P2P way, a *Distributed Secure Ledger*
It requires solving **distributed consensus** with *Byzantine faults*
- Given a blockchain of i blocks, and several proposals for block i+1, how to decide (in a distributed way) which proposal to adopt?

## Byzantine Consensus

The **Byzantine distributed consensus** problem provides processes an operation propose() which takes a value as an input and returns a value.
- If a process $p_i$ invokes propose(v) and obtains the value w, we say “$p_i$ proposes v”, and “$p_i$ decides w”.

Properties of the consensus (one-shot) problem:
- **Validity**: If all correct processes propose the same value v, only v can be decided.
- **Agreement**: No two correct processes decide different values.
- **Termination**: Each correct process decides a value.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585153/mod_resource/content/4/intol-04-bftclassics-sync.pdf