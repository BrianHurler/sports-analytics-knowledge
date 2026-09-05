# Defining the Estimand

An estimand is the exact quantity an analysis is trying to learn.

Poorly defined estimands are a common source of analytical confusion because the model can be technically correct while answering the wrong question.

## Examples

"How good is this player?" is not an estimand.

Possible estimands include:
- expected attack success against a 1900-Elo opponent
- player contribution to shot differential after adjusting for teammates and opponents
- causal effect of choosing on-two among eligible receptions
- next-season goals above expected

## Checklist

Before fitting a model, write down:

- unit of analysis
- outcome
- population of interest
- time period
- intervention or exposure, if causal
- comparison condition
- context to standardize or average over
- whether the target is current ability, future performance, or historical description

## Why it matters in sports

Statements like "Player A is better than Player B" can mean different things:
- better observed results
- better opponent-adjusted results
- higher latent ability
- better future projection
- greater causal impact on teammates
- more value in a particular tactical system

Those are different estimands and may require different models.
