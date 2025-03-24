2025-03-24 16:40

Status: #done 

Tags: [[Deteção e Tolerância a Intrusões]] [[2nd_Brain/2 - Tags/Attacks|Attacks]]

# DDoS

DoS (Denial of Service) is a goal, not a strategy.
DoS is usually implemented in a distributed way (DDoS).
How can a DoS be implemented?
- Service level exhaustion (e.g., partial HTTP connection using Slowloris)
- SYN flood (exhaust TCP stack)
- Bandwidth exhaustion

All of them achieve the same result (make the site unavailable), but requires different number of resources from the adversary:
- Effort(service) < Effort(SYN) < Effort(bandwidth)
- In any case, DDoS is a war of attrition

Detecting and blocking DoS is easy, but detecting DDoS is much
more complicated
- How to differentiate it from flash crowds or cable cuts?
- Answer: look at the traffic pattern (as always)!

![[DDoS 1.png]]

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585137/mod_resource/content/4/intol-02b-dataanalysis.pdf