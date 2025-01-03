2025-01-02 19:24

Status: #done 

Tags: [[Multiparty Computation]] [[Data Privacy and Security]] [[Security]] 

# Secure Multi-Party Computation

MPC allows multiple non-trusting parties to jointly compute a function over their inputs w/o revealing them.

In terms of security, MPC can be categorized in two axis:
- Nº of corruptions (i.e., how many parties we assume to behave honestly?)
	- **Honest Majority** – there are more honest than corrupted parties.
	- **Dishonest Majority** – there can be more corrupt than honest parties.
- **Passive vs active corruption** (i.e., how corrupted parties behave?)

MPC protocols can additionally provide one of the following
termination guarantees:
- **Guaranteed Output** - corrupted parties cannot prevent honest parties from receiving their output.
- **Fairness** - corrupted parties receive their output only if all honest parties receive output.
- **Security with Abort** – corrupted parties can prevent the honest parties from receiving output.

![[Secure Multi-Party Computation.png]]

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554346/mod_resource/content/8/dps-08-multi-party%20computation.pdf