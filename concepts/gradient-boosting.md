# Gradient Boosting

## What problem does this solve?

Gradient boosting is a flexible supervised-learning method for prediction. It builds many weak decision trees sequentially, with each new tree focusing on errors left by the current model.

It is especially useful when relationships are nonlinear, interactions matter, and strong predictive performance is more important than a simple closed-form model.

## Why not use something simpler?

Start with a simpler model when:

- interpretability is the primary goal
- relationships are reasonably linear/additive
- the sample is small
- a simple baseline already performs well enough

Use boosting when the predictive structure is more complex and the added performance survives honest out-of-sample testing.

## Sports examples

Beach volleyball:
- predict rally-win probability from opponent strength, reception quality, phase, set context, player identity, and tactical features
- predict attack outcome from a large set of nonlinear contextual variables

Ice hockey:
- expected-goal models
- entry/exit success models
- event classification
- player or team outcome prediction

## Core idea

A boosted-tree model repeatedly adds small trees that reduce the remaining prediction error.

The model can naturally capture:

- nonlinear effects
- thresholds
- interactions
- mixed variable types

For example, the effect of opponent Elo might be different for a perfect reception than for a poor reception without manually specifying every interaction.

## Key tuning concepts

- number of trees
- learning rate
- tree depth
- minimum observations per leaf
- row/feature subsampling
- regularization

## Validation

Boosting makes disciplined validation especially important because it can fit complex patterns.

Use:

- temporal train/test splits when predicting future sport outcomes
- cross-validation within the training period
- calibration checks for probabilities
- comparison against simple baselines
- feature leakage checks
- stability checks across seasons/competitions

## Interpretation

Feature importance and SHAP-style explanations can help describe what a predictive model uses, but they do not establish causality.

A variable can be highly predictive because it occurs after the decision being studied or because it proxies for another factor.

## Decision impact

Boosting is often naturally production-oriented because new observations can be passed through a trained model to produce updated predictions.

## Explain → Build → Apply → Defend

**Explain:** Sequential trees, residual/error correction, nonlinearities, interactions, overfitting risk.

**Build:** Fit a boosted-tree model with a train/test split and evaluate it against a baseline.

**Apply:** Use boosting on a real sports prediction problem and inspect calibration and feature behavior.

**Defend:** Explain why boosting was preferable to regression, how leakage was prevented, how hyperparameters were chosen, how the model was validated, and why its probabilities should be trusted.
