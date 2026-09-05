# Which Model When?

Model choice should follow the estimand, data-generating process, and decision need.

## Start simple

A good default progression is:

1. descriptive baseline
2. simple regression or probabilistic model
3. more flexible model if the baseline misses important structure
4. hierarchical, causal, spatial, or decision methods when the question specifically requires them

## Common choices

| Need | Start with | Move beyond when... |
|---|---|---|
| Explain a relationship | Linear/logistic regression | Nonlinearity, interactions, hierarchy, or causal structure matter |
| Predict an outcome | Logistic/linear baseline | Flexible nonlinear structure improves out-of-sample performance |
| Estimate player ability | Regularized or hierarchical model | Ability changes over time or context-specific effects matter |
| Estimate treatment effect | DAG + adjusted regression/matching/weighting | Treatment heterogeneity or complex confounding needs richer methods |
| Estimate action value | Markov/EPA/EPV model | State representation or trajectories need more detail |
| Compare strategies | Simulation | Decision variables and constraints require optimization |
| Recommend an action | Optimization / expected utility | Uncertainty or adaptive strategy requires richer decision models |

## Questions before choosing a model

- What exactly am I estimating?
- Is the target descriptive, predictive, causal, or prescriptive?
- What information exists at decision time?
- What is the simplest defensible baseline?
- Is the sample size adequate for the model complexity?
- Does the data have hierarchy: player, team, game, season, opponent?
- Does time order matter?
- Are observations independent?
- Is interpretability essential?
- What failure would matter most to the decision-maker?

## Complexity rule

A more complex model is justified when it improves something that matters: predictive accuracy, calibration, uncertainty estimation, causal identification, stability, or decision quality.

Complexity by itself is not evidence of analytical sophistication.
