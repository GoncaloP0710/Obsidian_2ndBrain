2025-03-24 16:28

Status: #done 

Tags: [[Deteção e Tolerância a Intrusões]]

# Beaconing

Beaconing is the process of systematically and regularly contacting a host.
- Botnets will poll their command servers for new instructions

This will appear as information flows between infected systems on the monitored site and an unknown address off-site at regular intervals.

False positives: some legitimate behaviors can be understood as beaconing (e.g., keep alives, software updates, news and weather feeds)

Beaconing detection is done in two phases:
- Identify consistent signals
- Verify if the suspect host is supposed to do beaconing

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585137/mod_resource/content/4/intol-02b-dataanalysis.pdf