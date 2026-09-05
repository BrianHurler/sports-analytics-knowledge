# Productionization Path

Not every valuable analysis belongs in production. The useful question is: **what should persist after the analysis is complete?**

## Common path

**Question → research → finding → metric/model → decision tool → production system**

Projects can stop at any point when that is the right endpoint.

## Four common endpoints

### 1. Organizational knowledge
A one-off study changes what coaches, scouts, or analysts believe.

Example: a causal study finds that on-two attacks are beneficial only in a narrow set of reception/blocker contexts.

### 2. Production metric
The research supports a simple recurring measure.

Example: track **eligible on-two opportunity rate** rather than raw on-two frequency.

### 3. Recurring decision support
A model is rerun when a decision arises.

Examples: playoff matchup analysis, trade-deadline scenario simulation, opponent-specific serving recommendations.

### 4. Fully automated production model
New data continuously generates updated outputs.

Examples: player talent estimates, xG, Elo, EPA/EPV, win probability.

## Production-readiness questions

- Does the question recur often enough to justify automation?
- Are the inputs available reliably and on time?
- Is the output stable enough to be trusted repeatedly?
- Is model monitoring possible?
- Is the method understandable to its users?
- What happens when data are missing or malformed?
- How will model drift be detected?
- Who owns the output and how does it affect a decision?

## Principle

Research discovers what matters. Production makes what matters available repeatedly and reliably.
