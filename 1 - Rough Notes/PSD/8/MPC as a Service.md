2025-01-02 20:06

Status: 

Tags: 

# MPC as a Service

The goal of MPC as a Service is to have computations executed by a set of servers that are always online.

## Fluid MPC
Fluid MPC presents an MPC as a Service model where
computations are split in **epochs**.

- Clients provide inputs in an initial Input Phase
- Servers can join the computation for one or more epochs

Between epochs, the server set can remain the same or change completely.
- Hence, a mechanism is needed to transfer state between epochs while preserving its privacy.

Performance
- O(N2)

Security
- Fully-malicious in the Honest Majority setting
- Only offers Security with abort termination

# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554346/mod_resource/content/8/dps-08-multi-party%20computation.pdf