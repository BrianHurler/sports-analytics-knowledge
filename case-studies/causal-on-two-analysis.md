# Case Study: Causal Effect of Going On-Two

## Question

Among beach volleyball situations where both on-two and on-three are realistic options, what is the causal effect of choosing on-two on rally-win probability?

## Why the naive answer is insufficient

Raw on-two efficiency is confounded because teams choose on-two disproportionately after favorable receptions and in situations where the blocker or defender is vulnerable.

## Treatment

\[
T=1 \text{ for on-two}, \quad T=0 \text{ for on-three}
\]

## Outcome

Rally win indicator or another pre-specified scoring outcome.

## Pre-treatment confounders

Potential examples:
- receive quality
- receive location
- attacker/setter identities
- opponent strength
- serve type
- score state
- blocker position if observed before the choice

## Important design choice

Only include plays where both choices are genuinely plausible. If a broken reception makes on-two impossible, that rally provides little useful counterfactual information.

## Candidate approaches

- adjusted regression
- matching
- inverse-probability weighting
- doubly robust estimation

## Assumptions

- no important unmeasured confounder remains after adjustment
- adequate overlap between on-two and on-three situations
- treatment is defined consistently
- covariates are measured before the tactical decision

## Validation / diagnostics

- examine propensity-score overlap
- check covariate balance after weighting or matching
- run sensitivity analyses
- compare multiple reasonable specifications
- inspect whether conclusions change materially by athlete or blocker context

## Decision implication

The useful result is not simply "on-two is better." A stronger conclusion is conditional: when, for whom, and under what situations does choosing on-two improve expected scoring?

## What could still be wrong?

Unobserved visual cues—especially blocker movement—may affect both the tactical choice and outcome. That is a central limitation, not something a more complex algorithm automatically solves.

## Productionization

The causal study may remain one-off research. Its finding could instead create a recurring metric such as **eligible on-two opportunity rate**, or later feed a tactical decision model.
