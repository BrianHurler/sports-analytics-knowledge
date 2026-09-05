# Sports Analytics Knowledge

A sport-agnostic knowledge base for developing advanced sports analytics skills and connecting statistical methods to real decision-making problems in professional sport.

This repository is designed primarily as a working reference: a place to organize concepts, revisit mental models, track competency, and connect methods to applied sports questions. It is also intended to be readable enough that someone skimming the repository can quickly understand how the pieces fit together.

## Core learning framework

Every major topic is developed through four levels:

1. **Explain** — Can I explain the idea clearly, including the intuition behind it?
2. **Build** — Can I implement a basic version correctly?
3. **Apply** — Can I recognize a real sports problem where it is useful and use it appropriately?
4. **Defend** — Can I justify the method, assumptions, validation, limitations, and decision impact?

For each method, five questions matter repeatedly:

1. **What problem does this solve?**
2. **Why would I not use something simpler?**
3. **What assumptions am I making?**
4. **How do I validate it?**
5. **How does it change a sports decision?**

## Seven pillars

| Pillar | Central question |
|---|---|
| [Measurement](pillars/01-measurement.md) | What actually happened? |
| [Prediction](pillars/02-prediction.md) | What is likely to happen next? |
| [Player valuation](pillars/03-player-valuation.md) | How good is a player or team really? |
| [Causal inference](pillars/04-causal-inference.md) | What would happen if we changed something? |
| [State & value modeling](pillars/05-state-value-modeling.md) | What is each action or game state worth? |
| [Decision science](pillars/06-decision-science.md) | What should we do? |
| [Spatial & tracking analytics](pillars/07-spatial-tracking.md) | How do geometry, positioning, and movement matter? |

See the full [competency map](competency-map.md).

## How the pieces fit together

A useful way to think about advanced sports analytics is:

**description → prediction → causation → decision**

A descriptive metric might tell us that an elite beach volleyball attacker performs worse against stronger opposition. A predictive model might estimate that athlete's expected performance against a 1900-Elo opponent. A causal study might estimate whether changing attack selection would improve rally-win probability. A simulation or optimization model might then recommend how often that option should be used in a specific matchup.

In ice hockey, the same progression could move from shot rates, to expected goals, to player-value models, to estimating the effect of tactical choices, and finally to lineup or roster optimization.

## Repository structure

- `pillars/` — the seven broad competency areas
- `concepts/` — focused explanations of individual methods
- `workflows/` — how analytical work moves from question to research to production
- `projects/` — templates for applied studies
- `model-defense/` — questions for testing whether a method is truly understood
- `glossary.md` — concise definitions

## Applied examples

Examples may use several sports, especially beach volleyball and ice hockey. The goal is not to build sport-specific production code here, but to use realistic sports problems to make abstract concepts concrete.

Examples may include questions such as:

- What is Anders Mol's expected attacking performance against elite opposition?
- How much should a small-sample player estimate be shrunk toward a population mean?
- Does attacking on two improve rally-win probability when both on-two and on-three options are realistically available?
- How should an NHL player's isolated impact be estimated while accounting for teammates, opponents, and deployment?
- How does a puck carrier's location, defender spacing, and support structure change expected possession value?

## Guiding principle

The objective is not to collect algorithms. It is to become better at moving through the full analytical chain:

**question → estimand → data-generating process → model → validation → uncertainty → communication → decision**

Sometimes the correct endpoint is a production model. Sometimes it is a one-off research result that changes how a coach or analyst thinks. Both are valuable.
