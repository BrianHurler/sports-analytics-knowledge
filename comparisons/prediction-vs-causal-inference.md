# Prediction vs. Causal Inference

Prediction and causality often use similar statistical tools, but they answer different questions.

## Prediction

**Goal:** estimate an outcome accurately.

Example: predict rally-win probability from receive quality, opponent strength, phase, and player identities.

A predictive model may use any variable available at prediction time if it improves out-of-sample performance.

## Causal inference

**Goal:** estimate what would happen under an intervention.

Example: estimate how rally-win probability would change if a team chose on-two instead of on-three in comparable situations.

The timing and causal role of variables matter. Controlling for a post-treatment mediator can remove part of the effect being studied.

## Key contrast

A model can predict extremely well and still be useless for causal decision-making.

For example, attack outcome may be highly predictive of rally outcome, but attack outcome occurs after the tactical decision and cannot tell us whether the tactical choice should have been made.

## Validation differs

Prediction asks:
- does the model generalize?
- is it calibrated?
- does it beat a baseline?

Causal inference also asks:
- is the treatment assignment plausibly ignorable after adjustment?
- is there adequate overlap?
- did we adjust for the correct pre-treatment confounders?
- how sensitive is the estimate to unmeasured confounding?

## Rule of thumb

If the question contains **what will happen**, prediction may be enough.
If it contains **what would happen if we changed X**, prediction alone is not enough.
