2025-01-11 14:48

Status: #done 

Tags: [[Information security risk analysis and management]] 

# Managing Risk

**Risk appetite** - the quantity and nature of risk that organizations are willing to accept.
The key is for the organization to find balance in its decision-making processes and in its feasibility analyses.

**Residual risk** is the amount of risk that remains after the organization has implemented policy, education and training, and technical controls and safeguards.

## Feasibility and Cost-Benefit Analysis
**Cost avoidance** - the money saved by using the defense strategy via the implementation of control.

**Economic feasibility** - the most common criterion used when evaluating a strategy to implement InfoSec controls and safeguards.
Economic feasibility analysis beings by valuing the information assets and determining the loss in value if those assets become compromised.

**Cost-benefit analysis (CBA)** - A form of feasibility study that compares the life-cycle **cost** of **implementing** a **control mechanism** **against** the estimated economic **benefit** that would accrue from the implementation of the control.

**Asset valuation** - the process of assigning financial value or worth to each information asset.

### ALE model
**Single loss expectancy (SLE)** - the calculated value associated with the most likely loss from a single occurrence of a specific attack.

SLE = asset value (AV) x exposure factor (EF)
- Where EF = percentage loss that would occur from a given vulnerability being exploited

**Annualized rate of occurrence (ARO)** - indicates how often you expect a specific type of attack to occur.

**Annualized loss expectancy (ALE)** - a comparative estimate of the losses from successful attacks on an asset over one year.
- ALE = SLE x ARO

#### ALE cons
- The ALE measure implicitly assumes that losses, conditional on breaches occurring, remain constant over time.
- The ALE focuses on expected losses and ignores other relevant characteristics of risk, such as dispersion.

### CBA Model
The CBA determines whether the benefit from a control alternative is worth the associated cost of the control.

Easiest way to calculate it is by using the ALE from earlier assessments:
- CBA = ALE(precontrol) - ALE(postcontrol) - ACS
- ALE(precontrol) = ALE of the risk before implemented
- ALE(postcontrol) = ALE after the control has been in place for a while
- ACS = annual cost of the safeguard

## Other Methods of Establishing Feasibility
The next step in measuring how ready an organization is for the introduction of controls is to determine the proposal’s:
- Organizational feasibility
- Operational feasibility
- Technical feasibility
- Political feasibility

### Organizational Feasibility
Organizational feasibility - examines how well the proposed InfoSec alternatives will contribute to the efficiency, effectiveness, and overall operation of an organization.

### Operational Feasibility
Operational feasibility - refers to user acceptance and support, management acceptance and support, and the system’s compatibility with the requirements of the organization’s stakeholders.

### Technical Feasibility
Technical feasibility - determining whether an organization already has or can acquire the technology necessary to implement and support them.

### Political Feasibility
Political feasibility - considers what can and cannot occur based on the consensus and relationships among the communities of interest.
Limits imposed by InfoSec controls must fit within the realm of the possible before they can be effectively implemented

# References

https://drive.google.com/drive/folders/10Z3JIrjEfe03_BvBG0SaSFlUAfZw8Vle