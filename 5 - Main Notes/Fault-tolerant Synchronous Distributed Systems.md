2025-03-24 19:01

Status: #done 

Tags: [[Deteção e Tolerância a Intrusões]] [[Byzantine]]

# Fault-tolerant Synchronous Distributed Systems

## Byzantine agreement

The BA protocol operates in **synchronous rounds**.
In each round, generals send messages to each other.
Loyal generals must agree on a **single binary value**, despite the action of traitors.
Loyal generals have pre-agreed that they should follow the majority and, in case of ties, retreat.
How many traitors are sufficient to prevent agreement?

- 2f+1 generals are not enough for f traitors.
- Even 3f+1 generals are not enough for f traitors?!
	- Not in one communication round, but maybe in more rounds…
Let us add a round to the protocol
- Generals will firstly agree about the vote of each general, and only after that they’ll decide what to do (based on majority vote)
- For each sender p, the other three remaining processes exchange the values they have received from p to agree on its value
- This “*reliable broadcast*” is defined by the **Byzantine generals problem**

This is also called *interactive consistency* or **Byzantine (terminating) reliable broadcast**.

Two situations arise:
- The sender is faulty
- The sender is correct

### Byzantine generals problem Faulty sender

![[Fault-tolerant Synchronous Distributed Systems 1.png]]

In this case the traitor can send inconsistent votes to the loyal processes (0,1,1).
Since all remaining generals are loyal, after exchanging among them the value received from the traitor, they have the same set of values.
If they use majority criteria, all correct processes will select the same final value, i.e., majority(0,1,1)=1.

### Byzantine generals problem Sender correct

![[Fault-tolerant Synchronous Distributed Systems 2.png]]

In this case, C disseminates the same value (1) to all processes.
The remaining three processes exchange the value received:
- two correct processes (A, B) forward the value originally sent by C
- faulty process forwards some arbitrary value x
- since there is a majority of correct values, the value originally sent by C will be chosen: majority(x,1,1)=1
- in this case, majority(0,1,1)=1

### Byzantine generals problem Oral Messages algorithm

Algorithm OM(0):
1) Commander sends its order to other processes.
2) Each process decides the received value or ‘retreat’ if no value was received.

Algorithm OM(f), f > 0 (f is the maximum number of faulty processes):
1) Commander send its order to other processes.
2) Let vi be the value received by processes i from the commander, or ‘retreat’ if no value was received. Process i disseminate vi (as a commander) to the other n-2 non-commander processes using OM(f –1).
3) For each i and j not  i, let vj be the value j received from i in step (2). The value decided by i is majority(v1,v2,...,vn-1).

### Byzantine generals problem With authentication

The power of digital signatures:
- Let’s consider what happens if the messages exchanged on the previous algorithm are signed
- Important: Digital signatures are stronger than authenticated channels (or MACs) as they can be verified by a third party

Assumptions about digital signatures
- A loyal general's signature cannot be forged, and any alteration of the contents of his signed messages can be detected.
Messages with invalid signatures are discarded, and their senders are considered faulty.

![[Fault-tolerant Synchronous Distributed Systems 3.png]]

Messages are now signed… and relayed values are also signed by relay nodes.
If the traitor sends contradictory values, he will be discovered.

**With digital signatures, we need just n ≥ f+2 processes to solve the Byzantine general's problem.**

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585153/mod_resource/content/4/intol-04-bftclassics-sync.pdf