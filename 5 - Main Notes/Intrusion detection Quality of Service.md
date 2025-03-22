2025-03-22 17:47

Status: #done 

Tags: [[2nd_Brain/5 - Main Notes/Intrusion Detection]] [[Deteção e Tolerância a Intrusões]] [[Intrusion detectors]]

# Intrusion detection Quality of Service

Intrusion detection is an *applied classification problem*.
IDSes are binary classifiers that identify data entries as satisfying a giving property or not.
- **False Positive** - FP (the opposite of True Positive - TP): when something that does not have the property is classified as having the property
- **False Negative** - FN (the opposite of True Negative - TN): when something that have the property is classified as not having the property

IDS Quality of Service:
- **Sensitivity**: the percentage of positive classification that are correct (TP rate)
- **Specificity**: the percentage of negative classification that are correct (TN rate)

A perfect IDS has sensitivity=specificity=100%, while the worst IDS flip a coin for each entry: sensitivity=specificity=50%.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585136/mod_resource/content/4/intol-02a-ids.pdf