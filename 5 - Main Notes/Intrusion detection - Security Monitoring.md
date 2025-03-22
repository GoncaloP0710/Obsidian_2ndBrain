2025-03-22 18:36

Status: #done 

Tags: [[Intrusion Detection]] [[Deteção e Tolerância a Intrusões]] [[Intrusion detectors]] 

# Intrusion detection - Security Monitoring

![[Intrusion detection - Security Monitoring 1.png]]

IDS alert processing has three steps: IDS test data; generates an alert; the alert is sent to security analysts either directly or through a SIEM system.

There is always an interim analytical step between alert and action.

What kind of analysis?
- Analysts must figure out what the alert means, which usually requires the execution of many queries on the collected data
- Relate internal information with other data sources on the internet
	- Are there a (new) vulnerability being exploited?
	- Are there other reports about it?

There are systems and tools to help analysts gain context and investigate problems.
- Snort - Network-based
- Suricata - Network-based
- OSSEC - Host-based

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585136/mod_resource/content/4/intol-02a-ids.pdf