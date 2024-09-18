2024-09-16 18:39

Status: #working 

Tags: [[segurança]] [[Data Privacy and Security]] [[Reading Assignment]] 

# Secure Multiparty Computation

**Distributed computing** considers the scenario where a number of distinct, yet connected, computing devices (or parties) wish to carry out a joint computation of some function. For example, these devices may be servers that hold a distributed database system, and the function to be computed may be a database update of some kind. The aim of **secure multiparty computation** is to enable parties to carry out such distributed computing tasks in a secure manner.

## Distributed computing Vs Secure Multiparty Computation

**Distributed computing** often deals with questions of computing under the threat of machine crashes and other inadvertent faults, **secure multiparty computation** is concerned with the possibility of deliberately malicious behavior by some adversarial entity, (Byzantine faults).

## Secure computation

Two important requirements: e **privacy** and **correctness**.
- The privacy requirement states that nothing should be learned beyond what is absolutely necessary
- The correctness requirement states that each party should receive its correct output.

## Secure multiparty computation in real life

Secure multiparty computation can be used to solve a wide variety of problems, enabling the utilisation of data without compromising privacy. Consider, for example, the problem of comparing a person’s DNA against a database of cancer patients’ DNA, with the goal of finding if the person is in a high risk group for a certain type of cancer. Such a task clearly has important health and societal benefits. However, DNA information is highly sensitive, and should not be revealed to private organizations. This dilemma can be solved by running a secure multiparty computation that reveals only the category of cancer that the person’s DNA is close to (or none). In this example, the privacy requirement ensures that only the category of cancer is revealed, and nothing else about anyone’s DNA.
It is interesting to note that in some cases privacy is more important whereas in others correctness is more important . In any case, MPC guarantees both of these properties, and more.

## Security of MPC

Secure protocols should withstand any adversarial attack (where the exact power of the adversary will be discussed later). In order to formally claim and prove that a protocol is secure, a precise definition of security for multiparty computation is required. 

- **Privacy**: No party should learn anything more than its prescribed output. In particular, the only information that should be learned about other parties inputs is what can be derived from the output itself.
- **Correctness**: Each party is guaranteed that the output that it receives is correct.
- **Independence of Inputs**: Corrupted parties must choose their inputs independently of the honest parties inputs
- **Guaranteed output delivery**: Corrupted parties should not be able to prevent honest parties from receiving their output. 
- **Fairness**: Corrupted parties should receive their outputs if and only if the honest parties also receive their outputs.

### Standard definition today

Consider an “ideal world” in which an external trusted (and incorruptible) party is willing to help the parties carry out their computation. In such a world, the parties can simply send their inputs to the trusted 
party, who then computes the desired function and passes each party its prescribed output. As the only action carried out by a party is that of sending its 
input to the trusted party, the only freedom given to the adversary is in choosing the corrupted parties’ inputs. 
Notice that all of the described security properties (and more) hold in this ideal computation. 

### When the definition is relaxed

We remark that in some cases, the definition is relaxed to exclude fairness and guaranteed output delivery. The 
level of security achieved when these are excluded is called “security with abort,” and the result is that the **adversary may be able to obtain output**, whereas the honest parties do not.

There are two main reasons why this relaxation is used. First, in some cases, it is **impossible to achieve fairness** (for example, it is impossible to achieve fair 
coin tossing for two parties). Second, in some cases, **more efficient protocols are known when fairness is not guaranteed**. Thus, if the application does not require fairness (and in particular in cases where only one party receives output), this relaxation is helpful.

### Adversarial power - Additional definitional parameter

The informal definition of security omits one very 
important issue: the **power of the adversary** that attacks a protocol execution. As we have mentioned, the adversary controls a subset of the participating parties in the protocol. 

However, we have not defined what power such an adversary has. We describe the two main parameters defining the adversary: its allowed **adversarial behavior** (that is, does the adversary just passively gather information or can it instruct the corrupted parties to act maliciously?) and its **corruption strategy** (that is, when or how parties come under the 
“control” of the adversary?):

#### Allowed adversarial behavior: 

The most important parameter that must be to the actions that corrupted parties are allowed to take. There are three main types of adversaries:

- **Semi-honest adversaries**: In the semi-honest adversarial model, even corrupted parties correctly follow the protocol specification. However, the adversary obtains the internal state of all the corrupted parties (such as the transcript of all the messages received) and attempts to use this to learn information that should remain private. This is a rather weak adversarial model, but a protocol with this level of security does guarantee that **there is no inadvertent data leakage**. In some cases, this is sufficient although in today’s adversarial environment it is often insufficient.

- **Malicious adversaries**: In this adversarial model, the corrupted parties can arbitrarily deviate from the protocol specification according to the adversary’s instructions. In general, providing security in the presence of malicious adversaries is preferred, as it ensures that no adversarial attack can succeed.

- **Covert adversaries**: This type of adversary may behave maliciously in an attempt to break the protocol. However, the security guarantee provided is that if it does attempt such an attack, then it will be detected with some specified probability that can be tuned to the application. Unlike in the malicious model, if the adversary is not detected, then it may successfully cheat (for example, learn an honest party’s input).

#### Corruption strategy:

The corruption strategy deals with the question of when and how parties are corrupted. There are three main models:

- **Static corruption model**: In this model, the set of parties controlled by the adversary is fixed before the protocol begins. Honest parties remain honest throughout and corrupted parties remain corrupted.

- **Adaptive corruption model**: Rather than having a fixed set of corrupted parties, adaptive adversaries are given the capability of corrupting parties during the computation. The choice of who to corrupt, and when, can be arbitrarily decided by the adversary and may depend on its view of the execution. We note that in this model, once a party is corrupted, it remains corrupted from that point on.

- **Proactive security model**: This model considers the possibility that parties are corrupted for a certain period of time only. Thus, honest parties may become corrupted throughout the computation (such as in the adaptive adversarial model), but corrupted parties may also become honest. The security guarantee is that the adversary can only learn what it derived from the local state of the machines that it corrupted, although they were corrupted.

## Modular sequential and concurrent composition.

In reality, a secure multiparty computation protocol is not run in isolation; rather, it is part of a system.

Canetti proved that if you run an MPC protocol as part of a larger system, then it still behaves in the same 
way as if an incorruptible trusted party carried out the computation for the parties. This powerful theorem is called modular composition, and it enables larger protocols to be constructed in a modular way using secure subprotocols, as well as analysing a larger system that uses MPC for some of the computations.

One important question in this context is whether or not the MPC protocol itself runs at the same time as other protocols. 

### Sequential composition

In the setting of **sequential composition**, the MPC protocol can run as a subprotocol of another protocol with arbitrary other messages being sent before and after the MPC protocol. However, the MPC protocol itself must be run without any other messages being sent in parallel. This is called the **stand-alone setting** and is the setting considered by the basic definition of security of Canetti.
The sequential modular composition theorem of Canetti states that in this setting, the MPC protocol indeed behaves like a computation carried out by a **trusted third party**.

In some (many) cases, MPC protocols are run at the same time as other instances of itself, other MPC protocols, and other insecure protocols. In these cases, a protocol proven secure under the aforementioned standalone definition of security may not actually remain secure. A number of definitions were proposed to deal with this setting, the most popular of these is that of **universal composability**.

### Universal composability

Any protocol proven secure according to this definition is guaranteed to behave like an ideal execution, irrespective of what other protocols run concurrently to it. As such, this is the gold standard of MPC definitions. 
However, it does come at a price (both of efficiency and of assumptions required on the system setup).

## The ideal model and using MPC in practice.

The ideal/real paradigm for defining security actually has some very important implications for the use of 
MPC in practice. 
Specifically, in order to use an MPC protocol, all a practitioner needs to do is to consider the security of their system when an incorruptible trusted party carries out the computation for which MPC is used. If the system is secure in this case, then it will remain secure even when the real MPC protocols are used.
The ideal model provides a clean and easy to understand 
abstraction that can be utilized by those constructing systems.

### Any inputs are allowed.

An MPC protocol behaves like an ideal execution, as such, the security obtained is analogous to that of an ideal execution. However, in an ideal execution, 
adversarial parties may input any values that they wish, and indeed there is no generic way of preventing this. 
Thus, if the security of an application depends on the party’s using correct inputs, then mechanisms must be 
used to enforce this. For example, it is possible to require signed inputs and have the signature be verified as part of the MPC computation. Depending on the specific protocol, this can add significant cost.

### MPC secures the process, but not the output. 



# Summary

Secure multiparty computation (MPC) is an extremely powerful tool, enabling parties to jointly compute on private inputs without revealing anything but the result.
# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554326/mod_resource/content/1/3387108.pdf