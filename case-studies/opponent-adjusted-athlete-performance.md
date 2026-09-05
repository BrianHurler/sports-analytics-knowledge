# Case Study: Opponent-Adjusted Athlete Performance

## Question

What is an elite beach volleyball athlete's expected attack performance against a 1900-Elo opponent?

## Why the naive answer is insufficient

Filtering to opponents near 1900 Elo can leave a small, noisy sample and ignores information contained in the athlete's performance against other opponent strengths.

## Data available

At minimum:
- athlete identity
- attack outcome
- opponent Elo at the time of the match
- event/date

Potentially useful context:
- first-ball vs. transition
- on-two vs. on-three
- set quality/type
- court side
- partner and opponent identities

## Estimand

The athlete's expected performance at opponent Elo = 1900 under a clearly defined context or context distribution.

## Candidate approaches

1. Narrow Elo-band descriptive estimate
2. Regression with continuous opponent Elo
3. Hierarchical model with player effects and Elo response
4. Hierarchical model with player-specific Elo slopes

## Chosen conceptual approach

A hierarchical model allows the entire dataset to inform how performance changes with opponent strength while preserving athlete-specific ability estimates and uncertainty.

A simplified structure is:

\[
\text{logit}(p_{ij}) = \alpha + u_j + \beta_j(Elo_i-1800)
\]

where player intercepts and slopes are partially pooled.

## Assumptions

- Elo is a useful representation of opponent strength.
- Relevant context is either standardized or modeled.
- The functional form for Elo is adequate, or a nonlinear alternative is used.
- Historical observations are informative about current ability unless time variation is modeled explicitly.

## Validation

- temporal holdout
- calibration of predicted probabilities
- comparison with a simple regression baseline
- posterior predictive checks for a Bayesian implementation
- stability across tournaments and Elo ranges

## Decision implication

The result supports statements like: "Given the evidence available, this is the athlete's expected performance against elite opposition," rather than treating a small filtered sample as exact truth.

## What could still be wrong?

Opponent Elo may hide stylistic matchup effects, athlete ability may change over time, and unmodeled set/phase context may create misleading player comparisons.

## Productionization

The model could eventually feed recurring opponent-adjusted athlete estimates into reporting tools, but the first version can remain a research model until stability and usefulness are demonstrated.
