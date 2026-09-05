# Pillar 2: Prediction

## Central question

**What is likely to happen next?**

Prediction turns historical patterns into estimates of future or unseen outcomes.

## Core ideas

- regression and classification
- feature engineering
- regularization
- tree-based models and gradient boosting
- train/test separation
- temporal validation
- calibration
- uncertainty
- baseline comparison

## Sports examples

Beach volleyball:
- expected attack success against a 1900-Elo opponent
- probability of sideout from a given reception state

Ice hockey:
- expected goal probability
- probability of a successful zone entry
- player performance projection

## Explain → Build → Apply → Defend

**Explain:** Describe the target, features, loss function, and why prediction differs from explanation or causation.

**Build:** Fit and evaluate a basic predictive model.

**Apply:** Use it on a real sports problem with honest out-of-sample evaluation.

**Defend:** Explain baseline choice, leakage prevention, calibration, validation design, feature choices, and failure modes.

## Key warning

A highly predictive feature is not automatically causal, actionable, or appropriate for a decision model.
