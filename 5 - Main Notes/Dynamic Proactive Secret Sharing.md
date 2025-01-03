2025-01-02 16:01

Status: #done 

Tags: [[Data Privacy and Security]] [[Security]] [[Encryption]]

# Dynamic Proactive Secret Sharing

A DPSS scheme is a PSS scheme that additionally allows the **group of shareholders** to **change** when performing a resharing operation.

During a **resharing operation**, new shares are computed for the updated group using a **new polynomial** while preserving the same secret.

## Auxiliary Polynomial Generation
A big challenge in both PSS and DPSS is how to generate auxiliary polynomials 𝑸, 𝑸’ and 𝑹 w/o any shareholder knowing them entirely.

- Byzantine Consensus
BC is a technique from distributed systems that allows a group of servers to decide a value, even if some of them are malicious.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554341/mod_resource/content/5/dps-03-secret%20sharing.pdf