2025-03-22 15:09

Status: #done 

Tags: [[Deteção e Tolerância a Intrusões]] [[2nd_Brain/2 - Tags/Attacks|Attacks]] [[Risk]] [[Intrusion]]

# Fault models

Although it is desirable to specify our fault model as detailed as possible, it is not practical.
So, for most intrusion-tolerant systems, we assume that machines can be compromised.
Intruder-controlled machines can be seen as components subject to **Arbitrary (Byzantine) faults**.
- It allows maximum coverage, because nothing is assumed

## Attack-Vulnerability-Intrusion composite fault model

attack + vulnerability → intrusion → error → failure

![[Fault models 1.png]]

## Cascading Faults through error propagation

Faults caused by an intrusion can be propagated through the whole system.

![[Fault models 2.png]]

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585135/mod_resource/content/4/intol-01b-concepts.pdf