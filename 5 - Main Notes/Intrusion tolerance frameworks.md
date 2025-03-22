2025-03-22 15:34

Status: #done 

Tags: [[Deteção e Tolerância a Intrusões]] [[Intrusion]] [[Intel SGX]] 

# Intrusion tolerance frameworks

## Secure and fault-tolerant communication

Concerns the body of protocols ensuring intrusion tolerant communication:
- *Secure channels* (e.g., TLS/SSL) and *secure envelopes* (e.g., PGP)
- *Fault-tolerant group communication* (e.g., total order multicast)

What should be the classes of failures of communication network components?
- Baseline: arbitrary faults (maximum coverage)

## Software-based intrusion tolerance

### Software-based fault tolerance
- Tolerating hardware faults using software techniques (e.g., replication)

### Software fault tolerance
- Tolerating software design faults (i.e., bugs) by design diversity

### Main challenge: **common mode faults**
- Common mode vulnerabilities (like bugs) can be avoided using diverse components
- Attacks can also be avoided since the attacker should have to master different platforms to compromise the system

## Hardware-based intrusion tolerance

### Means to construct fail-controlled components
- Contributes to establishing improved levels of trustworthiness
- Certain components can be built in such a way that it is very unlikely that someone compromises them (e.g., Intel SGX)
- If they fail, it will be only by crashing 

Distributed algorithms that tolerate arbitrary faults are expensive in both resources and time - With fail-controlled components, we can make them more affordable.

![[Intrusion tolerance frameworks 1.png]]

## Auditing

Routinely logging actions and events is a good management procedure.
Allows “a posteriori” diagnosis of problems and their causes.

#### Audit trails are a crucial framework in security
to trace back the events and actions associated with a given time interval, subject, object, service, or resource.
- Logs should be tamperproof
- Part of the appealing of blockchains is their use as ledgers for registering transactions

## Intrusion Detection (ID)

- Encompasses all kinds of attempts to detect the presence or the likelihood of an intrusion
- Can be performed in real-time, or off-line

ID systems are supervision systems that follow and log system activity to detect and react (preferably in real-time) against any or all off:
- attacks
- vulnerabilities
- and intrusions

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585135/mod_resource/content/4/intol-01b-concepts.pdf