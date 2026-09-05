# Defending a Model Choice

A strong analyst should be able to explain not only how a model works, but why it was appropriate for the question.

## Core defense questions

1. What exact problem was the model solving?
2. What was the simplest credible baseline?
3. Why was this model preferable to that baseline?
4. What assumptions does the model make?
5. How was it validated?
6. What failure modes were considered?
7. How sensitive are the conclusions to specification choices?
8. What would make you stop trusting the model?
9. How does the result affect a sports decision?

## Example: gradient boosting

A weak defense:

> "XGBoost performed best."

A stronger defense:

> "The target was out-of-sample rally-win probability. Logistic regression was the baseline. Gradient boosting improved temporal holdout performance and captured nonlinear interactions, but we separately checked calibration and feature leakage. Because the output was predictive rather than causal, we did not interpret feature importance as treatment effects."

## Example: hierarchical model

A strong defense should explain:
- why partial pooling was useful
- what groups share information
- how priors were chosen
- whether the model reproduces important features of the observed data
- how uncertainty changes the interpretation

## Principle

The goal is not to defend complexity. The goal is to show that the method, assumptions, validation, and decision all fit together.
