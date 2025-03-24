2025-03-24 17:21

Status: #done 

Tags: [[Deteção e Tolerância a Intrusões]] [[Anomaly]] [[Techniques for Anomaly Detection]] 

# Anomaly Detection

Anomalies are event patterns that are different from a certain (reference) expected behavior.

Anomaly detection techniques are typically employed to
- **Detect intrusions**
- Detect credit card frauds
- System failures
- ...

Build profiles from **normal behavior** of users, networks, hosts, etc.
Detection is based on identifying significant deviations from these profiles.
There is no profile for the **anomalies**.

![[Anomaly Detection 1.png]]

The challenge is to define the border between regions.
- This border is usually represented by a score threshold.
The borders are usually not clear.
A first step to have a reasonably clear separation is the existence of representative data sets.
This must include:
- Adversarial behavior (e.g., attacks and compromised machines)
- Dynamic behavior (behavioral changes along the time)
- Noisy data

## Challenges on Network Intrusion (Anomaly) Detection

*Big data*
- Millions of connections per day/hour in a big organization

*Dimensionality of the data*
- Amount of event attributes is normally large

*Temporal data*
- Order of collected events is relevant

*Unbalanced classes*
- Anomalies in general are very rare

*Real-time detection is desired*
- It’s always worth detecting problems earlier

## Anomaly Detection “Meta-Techniques”

**Supervised**: there is a list of pairs of input (e.g., event such as flow report) and output (e.g., normal or attack label), and the algorithm tries to learn the mapping between inputs and outputs. E.g., classifiers.

**Unsupervised**: There is no mapping, so the algorithm just try to find regularities in the inputs (e.g., flows), i.e., the inputs follow certain patterns and some patterns (e.g., normal behavior) are more common than others. We want to see what generally happens and what does not.

**Semi-supervised**: Parts of the input is mapped, and other parts are not. E.g., there are training data for the normal behavior.

## Building an Anomaly Detector

![[Anomaly Detection 2.png]]

Training Data set:
- Feature extraction
- Pre-processing
	- Normalization
	- Stratification
	- Noise removal

Training:
- Creation of the model
- Model is validated iteratively by using a validation data set (optional)
- Many algorithms and parameters are tried until the best model is found

## Pre-processing Data Sets

Data collected in the system must be pre-processed before being used for training, validation and testing.

Training and validation data sets typically can be divided in a proportion of 2 to 1, e.g.:
- Training is done using 2/3 of the collected events
- Validation is done using the other 1/3

## Features

Machine learning algorithms take as input one or more lists of events (i.e., the observations).
Each event contains several attributes or **features**
- E.g., a flow contains the data volume, duration, starting time, etc.
Each algorithm must be configured/trained to classify events as normal, or attack based on a subset of the event features.

An important question is “What features should we use?”
Why not use all available features?
- The complexity (and performance) of any classifier is directly related with the number of inputs (i.e., features of events)
- Simpler models are more robust on small datasets
- Fewer features make it easy to understand and visualize the classifier behavior
The number of features can be reduced using dimensionality reduction techniques:
- **Feature selection**: select k out of d features that give us the most information and discard the others
- **Feature extraction**: find a set of k < d features that are combinations of the original d features 

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585138/mod_resource/content/4/intol-03-attackdetection.pdf