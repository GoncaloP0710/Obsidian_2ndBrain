2025-01-09 14:44

Status: #done 

Tags: [[Software Security]] [[2nd Brain/2 - Tags/Vulnerability|Vulnerability]] [[Security]] 

# Code Review

Software auditing aims at identifying security flaws along with their root causes in software projects at the
- design phase (also called design review)
- during the implementation (also called code review)

The context of the software must be provided, allowing a tester to understand what is being assessed.
Becomes possible to give a real estimate of the likelihood of the (successful) attack and the impact of the breach.
Remediation can be performed based on the priority of the identified issues.

Phases
1. **Pre-assessment**: planning, defining the scope of review
2. **Code review**: main phase
3. **Documentation and risk analysis**: creation of documentation
4. **Remediation support**: assist those who must use the results of the review

### Code review strategies
#### Understanding the code
- Follow the (Malicious) Inputs.
	- Start at a data entry point and trace its flow on code, looking for security issues.
- Analyze separately each module.
	- Read module code line by line taking notes of possible issues
- Trace injection hits

#### Candidate (Vulner.) Points
- General candidate points approach
	- Take list of potential vulnerabilities and look for them in lowest level routines
- Simple candidate points
	- Use simple tools (e.g., grep) to find candidate vulnerabilities

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554486/mod_resource/content/8/SS_threatAnalysis.pdf