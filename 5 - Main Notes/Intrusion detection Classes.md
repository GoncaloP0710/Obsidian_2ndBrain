2025-03-22 17:51

Status: #done 

Tags: [[Deteção e Tolerância a Intrusões]] [[2nd_Brain/5 - Main Notes/Intrusion Detection]] [[Intrusion]] 

# Intrusion detection Classes

## Behavior-based (or anomaly detection) systems

- no knowledge of specific attacks
- provided with knowledge of normal behavior of monitored system, acquired, e.g., through extensive training of the system
- *advantages*: they do not require a database of attack signatures that needs to be kept up-to-date; capable of detecting new attacks
- *drawbacks*: potential false alarms; no info on type of intrusion, just that something unusual happened

### Anomaly Detection Techniques

Underlying assumptions:
- Intrusive actions (attacks or intrusions) are **necessarily different** from non-intrusive actions at some level of observation
- Intrusions will be accompanied by manifestations that are **sufficiently unusual** to allow detection
Limitations:
- These assumptions can be broken by a highly-skilled attacker
- How to efficiently model the noise

## Knowledge-based (or misuse detection) systems

- rely on a database of previously known attack signatures
- whenever an activity matches a signature, an alarm is generated
- *advantage*: alarms contain diagnostic information about cause
- *drawback*: potential omitted or missed alarms, e.g., new attacks

### Misuse Detection Techniques

This relies on attack descriptions
	- Simple strings that will be matched with packets
	- State machines represent sequences of actions/packets
	- Neural network models
Such descriptions can be Very concrete or abstract representations of a class of attacks.
Limitations:
- The knowledge base must be kept up to date
- No way to detect completely new attacks or zero-day vulnerabilities


# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585136/mod_resource/content/4/intol-02a-ids.pdf