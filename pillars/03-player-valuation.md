# Pillar 3: Player Valuation

## Central question

**How good is a player or team really?**

Observed outcomes mix true ability with teammates, opponents, role, environment, and randomness. Player valuation attempts to separate those pieces.

## Core ideas

- adjusted plus-minus and RAPM
- shrinkage and regularization
- hierarchical and Bayesian models
- replacement level
- aging and development curves
- role and deployment effects
- uncertainty in player estimates

## Sports examples

Beach volleyball:
- estimating an athlete's attacking ability after accounting for opponent quality
- estimating expected performance against 1900 Elo
- separating player effects from partner effects

Ice hockey:
- isolating skater impact while controlling for teammates, opponents, and game state
- estimating finishing talent rather than observed goals above expected

## Explain → Build → Apply → Defend

**Explain:** Distinguish observed performance from latent ability and explain why adjustment/shrinkage is needed.

**Build:** Fit a basic adjusted or hierarchical player model.

**Apply:** Estimate player ability in a real dataset and quantify uncertainty.

**Defend:** Explain model specification, regularization, identifiability, context controls, validation, and interpretation.

## Key warning

A player-value number is a model estimate, not a directly observed truth.
