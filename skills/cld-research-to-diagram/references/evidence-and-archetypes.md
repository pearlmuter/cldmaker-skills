# Evidence ledger and archetype reference

Use this reference while building an evidence ledger or testing an archetype hypothesis.

## Evidence ledger template

| Cause | Sign | Effect | Mechanism | Delay | Evidence status | Source and locator | Scope | Confidence | Rival explanation |
| --- | :---: | --- | --- | --- | --- | --- | --- | --- | --- |
| Example variable A | + | Example variable B | Explain the causal pathway | Immediate / delayed | Observed / source-inferred / model-inferred / local hypothesis | Title, URL, page/table | Population and setting | High / medium / low | Credible alternative |

### Evidence status

- **Observed:** the cited evidence directly estimates, measures, or documents the stated relationship in the relevant scope.
- **Source-inferred:** the source supports the mechanism, while the diagram's exact variable formulation or sign is an interpretation.
- **Model-inferred:** the link follows from combining sourced findings but no source directly asserts the complete relationship.
- **Local hypothesis:** the relationship is plausible but requires participant, expert, or local-data validation.

Use confidence to represent evidence quality and transferability, not confidence in prose fluency. Preserve disagreement instead of averaging incompatible contexts into one apparently universal link.

## Loop validation

For a directed closed cycle:

- zero or an even number of negative links produces a reinforcing loop;
- an odd number of negative links produces a balancing loop.

Let CLDMaker perform the final count and classification through `annotate_loop`. Use manual counting only to audit the proposed mechanism.

## Archetype hypotheses

| Structure | Candidate archetype | Diagnostic question |
| --- | --- | --- |
| A balancing fix reduces a symptom while a delayed reinforcing side effect restores or worsens it | Fixes That Fail | Does the intervention create the condition that makes it necessary again? |
| A symptomatic balancing response weakens a slower fundamental response | Shifting the Burden | Does reliance on relief erode capacity for the underlying solution? |
| Reinforcing growth activates a limiting balancing loop | Limits to Success | Which constraint becomes dominant as success accumulates? |
| Growth raises demand for capacity, but delayed or inadequate investment constrains growth | Growth and Underinvestment | Are standards or investment decisions suppressing needed capacity? |
| Competing reinforcing loops allocate scarce resources toward the early winner | Success to the Successful | Does initial advantage change future resource allocation? |
| Individual reinforcing gains collectively activate depletion of a shared resource | Tragedy of the Commons | Are locally rational actions degrading a common constraint? |
| Two actors' balancing responses to relative position amplify one another | Escalation | Does each actor treat the other's corrective response as a new gap? |
| A balancing correction competes with pressure to lower the target | Drifting Goals | Is performance improving, or is the reference condition weakening? |

Require the stated loop structure, shared variables, delays, and behavior to support a match. Report partial resemblance as a hypothesis rather than a diagnosis.
