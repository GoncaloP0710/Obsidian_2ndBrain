2025-03-22 17:03

Status: #done 

Tags: [[Deteção e Tolerância a Intrusões]] [[Intrusion detectors]] 

# Intrusion Detection

Classically, ID encompasses all kinds of attempts to detect the presence or the likelihood of an intrusion.
ID can be performed in *real-time* or *off-line*.
It is directed at any or all attacks vulnerabilities, and intrusions.

## CIDF (Common Intrusion Detection Framework)

CIDF proposes a structure for intrusion-detection systems:
- **e-box** (event generator) gathers event information
- **a-box** (analysis box) analyses event information, detecting errors and diagnosing faults
- **d-box** (database) saves IDS persistent information
- **r-box** (response box) acts upon the results of analysis
	- in fact, r-box is not intrusion detection, but error recovery and fault treatment

## Detection mechanisms

Consider system activity specified by patterns
- **Anomaly detection** looks for deviation from NORMAL ACTIVITY PATTERNS
- **Misuse detection** looks for existence of ABNORMAL ACTIVITY PATTERNS

Both can be used with hosts, network, or (more recently) applications, and We can also have hybrids.

## Signal Detection

Intrusion detection can be seen as an instance of the classical signal detection problem.
- Intrusion manifestations are the signal to be detected, while manifestations of normal operations are the noise

Classical signal detection problem
- Both the signal and noise distributions are known a priori.
- A decision process must determine if a given observation belongs to the signal-plus-noise distribution or the noise distribution

Intrusion detectors usually know only one of these distributions
- **Misuse detectors** know the signal distribution
- **Anomaly detectors** know the noise distribution
- both distributions are hard to characterize

## Limitations of IDS

In the 90s DARPA sponsored a substantial number of intrusion detection projects, with a clear goal for the proposed detectors:
- 99% of the attacks should be detected
- with less than 1% of false positive rate

No system achieved that… some possible causes:
- Systems based on intuitive but unfounded assumptions:
	- Manifestations of certain kinds of intrusions would be so obvious that rules for detecting them could be written
	- Deviations from “normal” behaviors would usually be definite indications of malicious or intrusive activity
- Lack of theoretical foundations for the field
- Modeling human behavior is inherently hard

This is yet another reason why we need to explore the intrusion tolerance/survivability/resilience approach.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585136/mod_resource/content/4/intol-02a-ids.pdf