2025-01-09 14:22

Status: #done 

Tags: [[Software Security]] [[2nd Brain/2 - Tags/Attacks|Attacks]] 

# Threat and Attack modeling

Objective is to model threats, i.e., to **identify** and **characterize** how **attacks** can **affect the system**.

Should be done early in the software development cycle or when the system is about to be rolled out.

- **Mitigate the threat**: placing the protection/control mechanisms to prevent the exploitation
- **Eliminate threat**: removing the vulnerability
- **Transferring the threat**: let someone or something else handle
- **Accept the risk**: accept that for some attacks you are willing to live with the risk

### Benefits of attack modeling
- helps **reduce risk** by supporting the removal of vulnerabilities
- helps **find bugs**
- helps **understanding** the **application**
- documents the application
- helps testers define what must be tested

Problems - Attack modeling does not scale

### Steps for the Analysis
0. define the scope and information gathering
1. decompose the application into some useful representation
2. identify attack objectives (or potential vulnerabilities)
3. build threat/attack tree(s) for each target
4. order vulnerabilities in terms of risk

### Step 0: Information gathering
Compile information about the application that might be useful to produce the model.

### Step 1: Decompose application
There is no unique solution to represent the decomposed application, but one possibility is Data Flow Diagrams (DFDs) or UML.

### Step 2: Identify vulnerabilities
Identify **potential attack objectives/vulnerabilities** for each interaction and component of the decomposition of step 1.

### Step 3: Build threat/attack trees
For each identified attack objective/vulnerability, one should describe the **impact** and **possible solutions**
- One possible way to represent this information is through a corresponding **attack tree**

Fault trees are used in dependability and software safety to identify failure modes.

### Step 4: Rank vulnerabilities
The goal is to help prioritize the vulnerabilities that must be addressed first
- in some cases, one can choose not to correct some vulnerabilities

Risk is a very relevant cost metric that can serve as basis for the creation of a ranking

Risk = average of the DREAD values

#### DREAD
- Damage potential
- Reproducibility
- Exploitability
- Affected users
- Discoverability

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554486/mod_resource/content/8/SS_threatAnalysis.pdf