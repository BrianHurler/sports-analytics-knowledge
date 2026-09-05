# Pillar 4: Causal Inference

## Central question

**What would happen if we changed something?**

Causal inference is about interventions and counterfactuals rather than association alone.

## Core ideas

- treatment and outcome
- counterfactuals
- confounding
- causal DAGs
- matching
- propensity scores
- inverse-probability weighting
- heterogeneous treatment effects
- mediation
- sensitivity to unmeasured confounding

## Sports examples

Beach volleyball:
- Does choosing an on-two attack increase rally-win probability when both choices are realistically available?
- Does more aggressive serving improve rally-win probability after accounting for when and against whom it is used?

Ice hockey:
- Does a tactical change improve offensive-zone possession value?
- Does changing a line combination cause performance to improve, or are the observed results driven by deployment and opponent mix?

## Explain → Build → Apply → Defend

**Explain:** Define the counterfactual and identify obvious confounders.

**Build:** Construct a basic causal DAG and implement regression adjustment, matching, or weighting.

**Apply:** Design a real observational sports study with an explicit estimand and pre-treatment covariates.

**Defend:** Explain identification assumptions, overlap, treatment timing, post-treatment bias, unmeasured confounding, robustness, and what causal claim is actually justified.

## Key warning

Adding many variables to a regression does not automatically create a causal estimate. Variable timing and the data-generating process matter.
