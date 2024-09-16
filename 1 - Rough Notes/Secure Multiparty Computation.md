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
- **Privacy**: No party should learn anything more than its prescribed output. In particular, the only information that should be learned about other parties’ inputs is what can be derived from the output itself.
- **Correctness**: Each party is guaran￾teed that the output that it receives is correct.
- 
# Summary

Secure multiparty computation (MPC) is an extremely powerful tool, enabling parties to jointly compute on private inputs without revealing anything but the result.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554326/mod_resource/content/1/3387108.pdf