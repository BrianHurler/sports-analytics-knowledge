# Bayesian Modeling

## What problem does this solve?

Bayesian modeling provides a coherent way to combine prior information with new evidence while explicitly representing uncertainty.

At a high level:

**prior knowledge + observed data → posterior knowledge**

This is especially useful when observations are noisy, sample sizes differ dramatically, or estimates should borrow strength across players, teams, situations, or seasons.

## Why not use something simpler?

A simple average may be enough when sample sizes are large and the target is purely descriptive. Bayesian modeling becomes more useful when the goal is to estimate an underlying quantity rather than just summarize observed outcomes.

Examples:
- estimating true finishing talent rather than observed shooting percentage
- estimating an athlete's expected attack performance against 1900 Elo despite relatively few attacks in that exact band
- estimating player effects across many sparse tactical contexts

## Core idea

Suppose a player's latent ability is `theta`.

A Bayesian model starts with a prior distribution for plausible values of `theta`, observes data, and updates that distribution to a posterior.

With little data, the prior has more influence.

With lots of data, the likelihood dominates and the posterior is driven mostly by the observations.

## Partial pooling

Hierarchical Bayesian models are especially valuable in sports because players share information without being treated as identical.

A generic structure might be:

`player ability ~ population distribution`

Players with small samples are pulled more strongly toward the population estimate. Players with large samples are influenced mainly by their own data.

## Beach volleyball example: performance vs. 1900 Elo

Instead of filtering only to attacks against opponents near 1900 Elo, model attack outcome as a function of:

- athlete
- opponent Elo
- phase/context
- other relevant pre-event variables

Then generate a posterior prediction for a specific athlete at opponent Elo = 1900.

A hierarchical extension can allow athletes to have both:

- different baseline ability
- different sensitivity to increasing opponent quality

The output is not just a point estimate. It is a distribution of plausible performance values.

## Ice hockey example

A player's current finishing talent can be modeled using several seasons of shot outcomes while allowing talent to evolve over time. A poor 20-game stretch updates the estimate, but does not automatically erase years of prior evidence.

## Assumptions to inspect

- Are the priors reasonable?
- Is the likelihood appropriate for the outcome?
- Is the hierarchy structured sensibly?
- Are important sources of heterogeneity omitted?
- Does the model assume ability is static when it is actually changing?

## Validation

Useful checks include:

- posterior predictive checks
- calibration
- out-of-sample prediction
- prior sensitivity analysis
- comparison against simpler baselines
- inspecting whether shrinkage behaves sensibly for large- and small-sample players

## Decision impact

Bayesian models are most valuable when the uncertainty itself matters. Two athletes with the same estimated performance but very different uncertainty should not always be treated as equivalent.

## Explain → Build → Apply → Defend

**Explain:** Priors, likelihood, posterior, shrinkage, partial pooling, credible intervals.

**Build:** Fit a simple hierarchical player model and generate posterior predictions.

**Apply:** Estimate a real player or team quantity where samples differ or context matters.

**Defend:** Justify the prior, likelihood, hierarchy, validation strategy, uncertainty interpretation, and why a simpler estimate is insufficient.
