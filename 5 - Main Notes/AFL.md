2025-01-08 17:27

Status: #done 

Tags: [[Software Security]] 

# AFL (American Fuzzy Loop)

Aims to fuzz diverse programs in a fast and robust way, by exploring **instrumentation** and a **genetic algorithm** to automatically discover interesting test cases (inputs)

### Pool of Test Cases
Mutation: the chosen test case is modified in different ways to produce new test cases to be executed by the target program.
New test cases are created by mutating existing test cases and then executed.

There is a **global map** of tuples, where each tuple corresponds to an edge in the control flow graph; the map starts empty and is updated as new edges are exercised by the test cases

![[AFL.png]]

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554474/mod_resource/content/7/fuzz.pdf