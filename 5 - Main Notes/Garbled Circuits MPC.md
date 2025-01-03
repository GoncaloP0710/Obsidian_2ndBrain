2025-01-02 19:41

Status: #done 

Tags: [[Multiparty Computation]] [[Data Privacy and Security]] [[Security]] 

# Garbled Circuits MPC

1. Circuit Generation
Any computation can be represented as a **Boolean circuit** composed only of AND and XOR gates.

2. Circuit Encryption (aka Garbling)
Construct a truth table w/ all possible inputs and, when evaluating the circuit, we just look up the result in the table.
**Encrypting the circuit** will hence be equivalent to **encrypting its truth table**.
To encrypt this truth table, the garbler (Alice) generates a **key for each possible value** and then applies a dual-key encryption to the outputs.

3. Input Encryption
4. Circuit Evaluation
Having the garbled circuit and encrypted inputs, evaluation is rather easy.
Bob simply evaluates each gate in sequence, from start to finish, decrypting each gate according to its truth table.

Performance
- Its biggest issues: it only works for Boolean circuits and for 2 parties

Security
- The protocol provides perfect secrecy, but is only secure against passive adversaries.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554346/mod_resource/content/8/dps-08-multi-party%20computation.pdf