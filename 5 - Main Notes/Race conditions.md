2025-01-08 18:02

Status: #done 

Tags: [[Software Security]] [[2nd Brain/2 - Tags/Vulnerability|Vulnerability]] 

# Race conditions

Violation of an assumption of atomicity
- during a **window of vulnerability** or window of opportunity or window of inopportunity
- two (or more) entities access concurrently the same object

The vulnerability is always due to a problem of concurrency / lack of proper **synchronization**

To exploit this kind of vulnerability, the attacker **races to break the assumption** during the window of vulnerability.

Sources of races:
- **shared data**: files and memory
- **preemptive routines** (signal or exception handlers)
- **multi-threaded programs**

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554484/mod_resource/content/7/T_races.pdf