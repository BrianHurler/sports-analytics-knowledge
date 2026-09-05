# Failure Modes

Sports data are especially vulnerable to misleading conclusions because observations are repeated, contextual, strategic, and non-random.

This folder catalogs ways an analysis can look convincing while being wrong.

## Core failure modes

- [Leakage](leakage.md)
- [Confounding](confounding.md)
- [Small-sample instability](small-sample-instability.md)

Future additions may include overfitting, selection bias, survivorship bias, poor calibration, metric gaming, and distribution shift.

## Practice

For every important analysis, ask:

1. How could this result be an artifact of the data-generating process?
2. What information accidentally leaks from the future?
3. What unmeasured factor could explain both the predictor/treatment and outcome?
4. Is the estimate stable under reasonable alternative specifications?
5. Would the result hold next season, against different opponents, or for different players?
