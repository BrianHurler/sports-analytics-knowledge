# Causal Inference

## What problem does this solve?

Causal inference asks what would happen under an intervention, not just what variables move together.

The core question is counterfactual:

**What would have happened to the same unit if the treatment had been different?**

Because we never observe both potential outcomes for the same rally, shift, player, or game, causal analysis tries to construct credible comparisons using design, assumptions, and statistical adjustment.

## Treatment, outcome, confounders

Every causal study should begin by defining:

- **Treatment:** the decision or intervention being evaluated
- **Outcome:** what the intervention is intended to change
- **Confounders:** variables that affect both treatment choice and outcome

## Beach volleyball example: attacking on two

Treatment:
- on-two attack vs. on-three attack

Outcome:
- rally win

Potential confounders:
- reception quality
- ball location
- athlete identities
- opponent quality
- score state
- blocker position if known before the choice

A raw comparison of on-two and on-three rally-win rates is not causal because on-two attacks are often selected in better situations.

The more meaningful estimand is:

**Among situations where both choices were realistic, how would rally-win probability change if the team chose on two instead of on three?**

## Causal DAGs

Directed acyclic graphs help reason about which variables should and should not be controlled.

If reception quality affects both attack choice and rally outcome, it is a confounder and creates a backdoor path.

By contrast, if serving aggressiveness changes reception quality, then reception quality occurs after the treatment and may be a mediator. Controlling for it can remove part of the total effect of the serve.

## Common tools

- regression adjustment
- matching
- propensity-score methods
- inverse-probability weighting
- doubly robust estimators
- instrumental variables in appropriate settings
- sensitivity analysis

These are tools for causal estimation; none automatically makes an observational analysis causal.

## Propensity scores

A propensity model estimates the probability of receiving treatment given pre-treatment covariates:

`P(treatment | X)`

This can help identify comparable treated and untreated observations and reveal whether sufficient overlap exists.

## Heterogeneous treatment effects

The average effect may hide useful tactical variation.

An on-two attack might be strongly beneficial after an excellent reception, neutral in a medium-quality situation, and harmful against a particular blocking structure.

The applied question often becomes:

**When does the intervention help, and for whom?**

## Assumptions to inspect

- Were important confounders measured?
- Are all adjustment variables truly pre-treatment?
- Is there sufficient overlap/common support?
- Is treatment defined consistently?
- Could selection into treatment depend on information missing from the data?
- Does interference between units violate the design?

## Validation and robustness

Causal estimates cannot be validated exactly like ordinary predictions because the counterfactual is never observed. Instead inspect:

- covariate balance
- overlap
- placebo or falsification tests
- alternative specifications
- sensitivity to trimming/weighting choices
- sensitivity to unmeasured confounding
- whether conclusions are consistent with sports mechanisms

## Prediction is not causation

A model can predict rally outcomes extremely well using variables observed after a tactical decision. That does not mean it can answer whether changing the decision improves the outcome.

Prediction asks:

**What will happen?**

Causal inference asks:

**What happens if we change X?**

## Explain → Build → Apply → Defend

**Explain:** Counterfactuals, confounding, treatments, outcomes, DAGs, post-treatment bias.

**Build:** Create a causal DAG and implement a basic adjusted/matched/weighted analysis.

**Apply:** Conduct a real observational sports study with a clearly defined estimand and treatment eligibility.

**Defend:** Explain identification assumptions, variable timing, overlap, robustness, unmeasured confounding, and the exact scope of the causal claim.
