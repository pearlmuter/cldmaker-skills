---
name: cld-research-to-diagram
description: Research a system and translate the evidence into a defensible causal loop diagram in CLDMaker. Use when the diagram must be inferred from papers, reports, datasets, interviews, or web research; when causal links need citations; when feedback loops or system archetypes must be identified; or when an existing research-derived CLD needs an evidence audit. Use with cld-authoring for CLDMaker operations.
---

# Research to CLD

Build an auditable qualitative model, not an illustrated literature summary. Separate sourced findings, model inference, and hypotheses requiring local validation.

Read [references/evidence-and-archetypes.md](references/evidence-and-archetypes.md) when creating the evidence ledger or evaluating system archetypes.

## 1. Frame the modelling question

State:

- the decision or question the model should illuminate;
- the actors and geography inside the boundary;
- the time horizon;
- the principal outcome behavior;
- important exclusions.

Complete this step when the boundary is narrow enough to reject relevant-but-out-of-scope variables.

## 2. Build an evidence ledger

Prioritize primary research, official statistics, systematic reviews, and authoritative institutional reports. Use secondary sources to discover evidence or represent a documented interpretation.

For every candidate causal link, record:

- cause and effect variables;
- direction and polarity;
- causal mechanism;
- source and locator;
- scope and population;
- expected delay;
- evidence status: observed, source-inferred, model-inferred, or local hypothesis;
- confidence and plausible rival explanations.

Search for disconfirming evidence when a link is central, contested, or highly context-dependent. Complete the ledger when every proposed link has a mechanism and an explicit evidence status.

## 3. Draft the causal structure

- Convert concepts into quantities that can rise or fall.
- Split a relationship when one label hides causal paths with different signs or delays.
- Phrase each link as: "If the cause increases, then the effect tends to increase/decrease, all else equal, because ..."
- Preserve access, availability, capacity, behavior, and outcomes as distinct variables when their mechanisms differ.
- Represent material delays explicitly in the rationale and, when necessary, as separate variables.
- Exclude correlations that lack a defensible directional mechanism.

Complete this step when every node varies, every link passes the causal sentence test, and the diagram remains small enough to explain.

## 4. Build and validate in CLDMaker

Follow `cld-authoring` for tool mechanics.

1. Create the initial graph with `batch_create`.
2. Call `read_state` and compare the returned structure with the evidence ledger.
3. Correct missing, reversed, duplicated, or weakly supported links.
4. Call `layout_diagram` if construction was piecemeal.

Complete this step when the application state exactly matches the reviewed causal structure.

## 5. Identify feedback behavior

- Trace directed closed cycles in the verified state.
- Explain the behavior each meaningful cycle can generate over the stated time horizon.
- Call `annotate_loop` with the ordered cycle, mechanism title, explanation, and primary supporting sources.
- Let CLDMaker derive the reinforcing or balancing classification from stored link polarities.
- Distinguish a short-run balancing response from delayed reinforcing side effects.
- Treat an archetype match as a diagnostic hypothesis and identify the exact loops and shared variables that support it.

Complete this step when every behaviorally meaningful loop is annotated and redundant composite cycles are intentionally omitted.

## 6. Challenge the model

Run an adversarial pass:

- reverse or remove each high-leverage link mentally and test whether the explanation still holds;
- look for omitted balancing loops, resource constraints, thresholds, delays, and adaptive behavior;
- test whether changing the boundary or time horizon changes a loop's interpretation;
- distinguish variables that should become stocks in a later stock-and-flow model;
- mark links requiring stakeholder or local empirical validation;
- state what the CLD cannot establish, including magnitude, parameter values, and quantitative forecasts.

Return to an earlier step when this pass changes the structure.

## 7. Deliver the model and analysis

Save the `.cld` file. Report:

- the modelling question, boundary, and horizon;
- the dominant reinforcing and balancing loops;
- likely behavior over time and important delays;
- leverage points and possible unintended consequences;
- strongest evidence, weakest assumptions, and rival explanations;
- research and validation still needed.

Finish only when a reader can inspect both the causal logic and its evidential basis without relying on unstated reasoning.
