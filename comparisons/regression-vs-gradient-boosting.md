# Regression vs. Gradient Boosting

Both can predict outcomes, but they offer different tradeoffs.

| Dimension | Regression | Gradient boosting |
|---|---|---|
| Interpretability | Usually high | Usually lower |
| Nonlinearity | Must be specified | Learned flexibly |
| Interactions | Must be specified | Learned naturally |
| Small samples | Often strong | Can overfit |
| Prediction | Strong baseline | Often stronger with complex signal |
| Calibration | Often good, still verify | Must be checked explicitly |
| Causal use | Sometimes appropriate with careful design | Usually not a causal answer by itself |
| Communication | Easier | Harder |

## Sports example

Suppose the target is rally-win probability from pre-attack context.

A logistic regression gives a transparent baseline and forces explicit assumptions about Elo, receive quality, phase, and interactions.

Gradient boosting may outperform it if the relationship contains nonlinear thresholds and complex interactions, such as opponent Elo mattering differently by receive quality and attack type.

## Decision rule

Use boosting because it improves validated predictive performance or captures important structure — not because it is more advanced.

If the primary need is explanation or causal interpretation, a simpler structured model may be preferable even when boosting predicts slightly better.
