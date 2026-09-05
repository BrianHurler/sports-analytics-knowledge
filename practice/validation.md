# Validation

Validation asks whether an analysis deserves to be trusted for its intended use.

## Start with the intended use

Different goals require different evidence.

### Prediction
Ask:
- does it generalize out of sample?
- is it calibrated?
- does it beat a simple baseline?
- does it remain stable across time, teams, and contexts?

### Player valuation
Ask:
- are estimates stable across samples?
- do they predict future performance?
- are extreme estimates supported by enough evidence?
- how sensitive are results to regularization or prior choices?

### Bayesian models
Ask:
- do posterior predictive checks reproduce important data patterns?
- are priors reasonable and sensitivity-tested?
- are chains/convergence diagnostics acceptable?
- is the model calibrated on held-out or simulated data when appropriate?

### Causal inference
Ask:
- is the identification strategy credible?
- is there adequate overlap?
- are adjusted groups balanced?
- how sensitive is the conclusion to unmeasured confounding or alternative specifications?

## Sports-specific split strategy

Random row-level train/test splits are often too optimistic because sports observations are nested within players, games, matches, teams, and seasons.

Prefer temporal holdouts when the intended use is future prediction. Consider grouped splits when the same player or match appearing in both train and test would create unrealistic information sharing.

## Baseline principle

A model should earn its complexity.

Useful baselines include:
- league average
- player historical average
- simple logistic/linear regression
- Elo-only prediction
- previous-season estimate

## Core question

> What evidence would convince a skeptical analyst that this model will work on the decision it was built for?
