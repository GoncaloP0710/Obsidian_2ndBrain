2025-01-08 16:31

Status: #done 

Tags: [[Software Security]] 

# Fuzzers

Today fuzzing is often used for security testing.
They brute force the application interface with erroneous input to discover if it fails.
- inputs are often generated randomly, but sometimes with the support of other mechanisms

Monitoring is often very simple (or inexistent)
- a test case is effective because the program crashed or hanged

### Sharefuzz
Simple fuzzer that tests environment variables usage.
The application is vulnerable if it crashes (no monitoring).
Method of insertion
- Creates a shared library

### Classifying fuzzers
In terms of **knowledge of the target**
- **Thin fuzzers** – tools with little knowledge or assumptions about the app tested; send random invalid input to the target
- **Fat fuzzers** – can generate input that is syntactically valid (accepted by the input parser) but irregular to test how the target handles it; better coverage

In terms of **specialization** of the **application**
- **Specialized** – implemented for a specific type of application, or network protocol, or file format; can be made more “intelligent”.
- **Generic** – can be applied to a large spectrum of targets (e.g., fuzzer frameworks).

In terms of access to the code of the application
- **Black** – no access, and all tests simply go through the interface
- **Grey** – ability to compile, eventually adding instrumentation code
- **White** – the execution of the application is emulated, looking for conditions in the input that would cause a failure

**Blind fuzzers**: have limited knowledge about the source of the target, but in any case, try to generate inputs that cause a crash

**Coverage-guide fuzzers**: use a feedback mechanism on how the processing of an input affected the processing of the target

**Hybrid fuzzers**: leverage from several kinds of program analysis techniques to complement the usual operation, with the aim of reaching deeper into the code

### How to generate test cases (inputs)?
Traditional ways of generating inputs
- **Random fuzzing**: generates random inputs
- **Recursive fuzzing**: iterating through all combinations of characters from an alphabet
- **Replacive fuzzing**: substitutes part of the test case with predefined values

Often there is a mixture of the above methods, using **mutations**.
More recently, fuzzers have taken advantage of various **feedback & analysis techniques**.

#### Mutation Operators
Deterministic Mutation: systematically mutate
- Bits: invert one or several consecutive bits in a byte, where the stepover is 1 bit
- Bytes: invert one or several consecutive bytes, where the stepover is 8 bits
- ...
Random Mutation:
- Random bytes: randomly select one byte of the test case and set the byte to a random value.
- Delete or insert or overwrite bytes: randomly select/copy several consecutive bytes and delete/insert/overwrite them
- Crossover: splice two parts from two different test cases to form a new test case

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554474/mod_resource/content/7/fuzz.pdf