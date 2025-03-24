2025-03-24 17:53

Status: #done 

Tags: [[Deteção e Tolerância a Intrusões]] [[Anomaly Detection]] [[Anomaly]] 

# Techniques for Anomaly Detection

## Neural Networks (Multi-Layer Perceptron)

![[Techniques for Anomaly Detection 1.png]]

## kth Nearest Neighbor (kNN)

One of the simplest machine learning algorithms:
- **Supervised**: need to be trained using annotated datasets
- **Non-parametric**: data does not need to follow a statistical distribution
- **Lazy learning**: all computation is deferred until classification

How the (basic) algorithm works?
- Training:
	- Labelled data (e.g., NORMAL, ATTACK) is stored
- Classification of an event e:
	- Find the k closest neighbors of e
	- e receives the classification corresponding to the majority of these neighbors, e.g.,
Variation: assign a number of votes (weight) vn proportional to the distance between the neighbor n and e.

How distances between vectors are calculated?
- Typically, the Euclidian Distance is used.

## Anomaly-based IDS: Reality Check

Anomaly detection techniques allow the detection of new attacks (zero-day)

Machine learning techniques are usually employed for anomaly-based intrusion detection.
- However, semi-supervised (traditional) anomaly detectors could solve the problem (partially), but they tend to have a high error rate (in particular, false positives)!
- Classifiers (supervised) perform well but require examples from both normal and attack classes!
- Consequently, a classifier cannot be trained with unknown events
- **So, it is not “expectable” that a classifier will detect new attacks**

Nonetheless, ML-based anomaly detectors are still useful:
- ML algorithms identify known patterns
	- Typically, events by all classes are needed, however
	- *It is not possible to generate all known attacks*
	- *It is not possible to generate all variations of known attacks*
	- *It is not possible to generate unknown attacks*
- A good anomaly-based IDS can detect:
	- Known attacks
	- Similar attacks
	- New attacks (never saw before, but sufficiently different from normal behavior)

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585138/mod_resource/content/4/intol-03-attackdetection.pdf