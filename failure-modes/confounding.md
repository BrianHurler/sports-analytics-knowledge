# Confounding

Confounding occurs when a third variable influences both the exposure/treatment and the outcome, creating a misleading association.

## Beach volleyball example

Suppose on-two rallies have higher win rates than on-three rallies.

Receive quality may affect both:
- the probability of choosing on-two
- the probability of winning the rally

Then raw on-two vs. on-three differences mix treatment effect with situation quality.

## Hockey example

A player may have excellent goal share when deployed with strong teammates against weak competition. Teammate and opponent quality confound the relationship between player presence and outcomes.

## Better practice

- draw the causal structure before choosing controls
- distinguish pre-treatment confounders from mediators
- use matching, weighting, adjusted regression, or experimental variation when appropriate
- inspect overlap and covariate balance
- perform sensitivity analyses for unmeasured confounding

## Warning

Adding more variables is not automatically safer. Conditioning on mediators or colliders can introduce bias.

## Diagnostic question

> What factors could plausibly affect both why this action/player/context occurred and the outcome I am measuring?
