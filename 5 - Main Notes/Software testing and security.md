2025-01-08 16:03

Status: #done 

Tags: [[Software Security]] [[Security]] 

# Software testing and security

There is an infinite number of possible ways that an application may fail, and organizations always have limited testing time and resources. Be sure time and resources are spent wisely!

Try to focus on the security holes that are a real risk to the business!

Tools do not make software secure! They help scale the process and help enforce policy.

Testing: evaluate the software by “observing” its execution
- **Static testing** – done without executing the software (symbolic execution, static analysis, and static taint analysis)
- **Dynamic testing** – testing while running the software (fuzzing or dynamic taint analysis)

### Various kinds of testing
- Unit testing: check if the SW units satisfy their specification
- Module testing: verify if SW modules satisfy their specification
- Integration testing: verify the conformance of interfaces
- System testing: verify if the SW satisfies its architectural design
- Acceptance testing: verify that the SW satisfies its requirements
- Regression testing: verify if changes made to SW did not impact its correctness

### Challenges of Testing
**Observability**: easiness of observing the SW behavior
- if low, it is difficult to check the results of the test
**Controllability**: easiness of providing inputs to the SW
- if low, it is difficult to run the tests
**Coverage**: capability of a test set to find all SW bugs
- if low, only certain types of bugs or only parts of the SW end up being tested

### Security vs Traditional testing
**Functional testing**: traditionally, testing aimed at checking that the SW does what it should do.

**Security testing**: check that the SW does not do what it should not do.

### Security testing phases
1. Enumerate the **attack surface**
2. Use **attack modeling** to prioritize the tests to be carried out
3. Define tests that will be carried out
4. Execute the tests
5. Given the test result, perform code review

### How do we define the tests?
- Black box testing - Tests derived from external description of the software
- White box testing - Tests derived from the source code
- Gray box testing = white + black

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554474/mod_resource/content/7/fuzz.pdf