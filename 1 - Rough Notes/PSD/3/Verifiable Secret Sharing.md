2025-01-02 15:51

Status: 

Tags: 

# Verifiable Secret Sharing

The only security aspect not provided by Shamir’s SS is **integrity / verifiability**.

VSS, introduced in 1985, solves this issue by adding an **integrity proof to each share** that allows the combiner to detect corrupted shares

## Commitments
A Commitment Scheme allows one to commit to a chosen value while keeping it secret and w/ the option of revealing it later to others.

The message is committed, i.e., it can no longer be changed
- Binding Property

And it remains secret until the box’s key is shared w/ the receiver
- Hiding Property

In VSS, commitments are used to **bind shares to their polynomials** without revealing them.
# References

https://moodle.ciencias.ulisboa.pt/pluginfile.php/554341/mod_resource/content/5/dps-03-secret%20sharing.pdf