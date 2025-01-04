2025-01-04 17:35

Status: #done 

Tags: [[Over Flows]] [[Software Security]] [[Security]] [[Memory]] 

# Integer Overflows

An **Integer Overflow** happens when an arithmetic operation **exceeds the maximum or minimum value** that can be stored in a variable of a given integer type, causing the value to wrap around to a **very large** or **very small** number. This behavior can cause **unexpected results**, **program crashes**, or **security vulnerabilities**.

What happens when a signed integer is passed to an unsigned?
- overflow
- underflow
- signedness
- truncation

### Overflow
Result of expression exceeds maximum value of the type. Probably the most common integer overflow form.

### Underflow
Result of expression is smaller than the minimum value of the type
- E.g., subtracting 0-1 and storing the result in an unsigned int

### Signedness error
A signed integer is interpreted as unsigned or vice versa. Negative number interpreted as positive.

### Truncation
Assigning an integer with a longer width to another shorter.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554464/mod_resource/content/8/BO_T.pdf