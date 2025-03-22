2025-03-22 17:36

Status: #done 

Tags: [[2nd_Brain/5 - Main Notes/Intrusion Detection]] [[Deteção e Tolerância a Intrusões]] [[Intrusion detection Quality of Service]] [[Intrusion detectors]]

# ROC Curve

Intrusion detectors Quality of Service:
- *Sensitivity*: the percentage of positive classification that are correct (TP rate)
- *Specificity*: the percentage of negative classification that are correct (TN rate)

There is always a tradeoff between sensitivity and specificity.
This tradeoff is captured by the Receiver Operating Characteristic (ROC) curve, which plots sensitivity (TP rate) vs false positive rates (1 - specificity), using the Operating Characteristic as a control.

![[ROC Curve 1.png]]

## The Base-Rate Fallacy

Consider that after analyzing the ROC curve of a classifier, we set up an IDS with 99% true positive rate and 1% false positive rate.

After putting it in operation, we receive an intrusion alert from the system.

What is the probability that the alert is a true positive?
- **It isn’t 99%;** the TP rate is the probability the IDS will raise an alert if an attack takes place! (a conditional probability)

Let’s define a test as the process an IDS uses to decide if it should raise an alert or not:
- verify 10 seconds of network traffic
- Assume the probability of an actual attack to take place is 0,01% (for every 10000 tests, one is an attack – one attack each ~28 hours)
- For every 10000 tests, we will have one alarm due to an attack (due to our 99% of sensitivity)
- However, the FP rate of 1% implies that the system raises one false alarm for every 100 tests
- In 10000 tests, 101 alarms will be raised (one alarm each 17 minutes), and only one is an attack!

FP rates should be really low for an IDS to be useful

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585136/mod_resource/content/4/intol-02a-ids.pdf