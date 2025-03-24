2025-03-24 15:49

Status: #done 

Tags: [[Deteção e Tolerância a Intrusões]] 

# Fumbling

Fumbling refers to the process of systematically trying to connect to a target using a reference (e.g., IP, URL, email address)
- It is suspicious because a legitimate user would probably have the reference it needs to access the target system 
- Attackers must guess, steal, or scout that data from the system, and they will make mistakes
- These mistakes can be used to differentiate them from legitimate users

## Fumbling characteristics

- **Lookup failures**: what’s the difference between (1) few hosts looking for many non-existent references and (2) many hosts looking for a single non-existent reference?
- **Automation**: lower- vs higher-retry rate? (human-initiated vs automated protocols)
- **Scanning**: the most common form of attack traffic. Attackers try to connect to many IP:port references of a network

## TCP Fumbling

Identifying TCP fumbling requires understanding the TCP state machine
One can identify fumbling by looking at flow data, inspecting:
- TCP flags
- packet counts
- bytes per packet ratio

## Forensic Analysis of Fumbling

Building fumbling alarms
- The objective, as always, is to decrease false positives
- Scanners talk to a lot of machines/ports in a short period of time
- Scanners try to access dark addresses
- Identify if the scanner found some target

On receiving an alarm, ask:
- Who responded to a scanner?
- Did the scanner find out something about my network I didn’t know?
- What else did the scanner do?

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585137/mod_resource/content/4/intol-02b-dataanalysis.pdf