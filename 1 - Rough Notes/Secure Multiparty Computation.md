2024-09-16 18:39

Status: 

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

**Allowed adversarial behavior**: The most important parameter that must be to the actions that corrupted parties are allowed to take. There are three main types of adversaries:

- **Semi-honest adversaries**: In the semi-honest adversarial model, even corrupted parties correctly follow the protocol specification. However, the adversary obtains the internal state of all the corrupted parties (such as the transcript of all the messages received) and attempts to use this to learn information that should remain private. This is a rather weak adversarial model, but a protocol with this level of security does guarantee that **there is no inadvertent data leakage**. In some cases, this is sufficient although in today’s adversarial environment it is often insufficient.
- **Malicious adversaries**: 
# Summary

Secure multiparty computation (MPC) is an extremely powerful tool, enabling parties to jointly compute on private inputs without revealing anything but the result.
# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554326/mod_resource/content/1/3387108.pdf