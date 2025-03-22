2025-03-22 14:37

Status: #done 

Tags: [[Deteção e Tolerância a Intrusões]] [[Managing Risk]]

# Risk

RISK is a combined measure of the level of threat to which a system is exposed, and the degree of vulnerability it possesses

Can we remove every flaw of the system (**vulnerabilities**) or avoiding all attacks it may be subjected to (**threats**)?
Probably no:
- it might be too costly and infeasible
- certain attacks come from the kind of service being deployed
- certain vulnerabilities are attached to the design of the system

If we work on an **all-or-nothing perspective**, every time we cannot ensure something is completely secure, we have a problem with representation.

## Assumption and Coverage

What are we missing?
- we need to leave the all-or-nothing perspective
- we need to represent “more or less secure” formally

**Separate concerns**
- between *specification* and *implementation*

Provide a notion of **coverage**
- Property A specifies a good thing about system S
- System S is implemented to satisfy A
- Implementation meets A with a confidence of Pr
- *Coverage of A being provided by S is Pr*

The notion of coverage is not only important for **system components**, but also to the **environment** the system will run (including the adversary we consider).
- A well-designed System assume certain properties from the **Environment** and capabilities from the **Adversary**
- These properties and capabilities only make sense if satisfied with high coverage by the system’s target deployment scenario

## Trusted vs. Trustworthy

B is **trustworthy** in the measure its properties are met
- and that coverage is < 1 in real systems
B should be **trusted** only to the extent of its **trustworthiness**
- trust may have several degrees, quantitatively or qualitatively
- related not only with security-related properties
- trust and trustworthiness lead to complementary aspects of the specification/design and implementation/verification process

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/585135/mod_resource/content/4/intol-01b-concepts.pdf