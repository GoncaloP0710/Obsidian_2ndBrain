2025-01-04 14:30

Status: #done 

Tags: [[Software Security]] [[2nd Brain/2 - Tags/Vulnerability|Vulnerability]] [[Design]]

# Design Principles to Avoid Vulnerabilities

The goal is to avoid introducing design vulnerabilities.

### Never Assume or Trust
Systems built out of several components are vulnerable if one of them has weaknesses.

### Use Authentication Mechanisms that Cannot be Circumvented
Ensure there are **appropriate measures** to **authenticate users**.
Prevent users from changing their identity.
Perform authorization only after authentication.

### Identify and Protect Sensitive Data

### Understand External Components
Systems are built out of components, and therefore they have an impact on the attack surface.

### Be Prepared for System Evolution
Successful systems need to evolve over time.

### Economy of mechanism
keep the design as simple and small as possible.

### Complete mediation
Every access to every object must be checked for authority.

### Open design
The design should not be secret, Obscurity does not work.

### Least privilege
Every program and every user of the system should operate using the least set of privileges necessary to complete the job.

### Least common mechanism
Minimize the amount of mechanisms common to more than one user and depended on by all users.

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554454/mod_resource/content/8/SS_softDev.pdf