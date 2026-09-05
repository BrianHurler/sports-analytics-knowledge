# Research Question to Method

A useful sports analytics workflow starts with the question, not the algorithm.

| Sports question | Analytical framing | Good starting methods |
|---|---|---|
| What happened? | Description / measurement | Rates, distributions, context-adjusted summaries |
| How strong is this player? | Latent ability / player valuation | Hierarchical models, shrinkage, RAPM-style models |
| What will happen next? | Prediction | Regression, gradient boosting, calibrated probabilistic models |
| Did changing X affect Y? | Causal inference | Experiments, matching, weighting, regression adjustment, doubly robust methods |
| What is an action worth? | State/value modeling | Markov models, EPA/EPV, dynamic value functions |
| What happens over many possible futures? | Simulation | Monte Carlo, scenario simulation |
| What should we do? | Decision science | Optimization, expected utility, simulation-based policy comparison |
| How does location or movement matter? | Spatial / tracking analytics | Spatial models, trajectories, tracking features, sequence models |

## Examples

### Beach volleyball

**Question:** What would Ana Patricia be expected to do against a 1900-Elo opponent?

This is primarily a player-estimation problem. A hierarchical model with opponent Elo as a continuous predictor is more appropriate than simply filtering to a narrow Elo band.

**Question:** Would increasing on-two usage improve scoring?

This is a causal question. The key challenge is that teams choose on-two in favorable situations, so raw on-two vs. on-three efficiency is not a causal estimate.

**Question:** Given the estimated effect of on-two, how often should a team use it?

Now the problem has become a decision/optimization problem.

### Ice hockey

**Question:** Which player is likely to score more next season?

Prediction.

**Question:** How much offensive value does a player create independent of teammates and opponents?

Player valuation / adjusted plus-minus.

**Question:** Should a team enter the zone with possession more often in a particular matchup?

Potentially causal research followed by simulation or optimization.

## Rule of thumb

If the question contains **what happened**, start descriptive.
If it contains **what will happen**, think prediction.
If it contains **what if we changed**, think causality.
If it contains **what should we do**, think decision science.
