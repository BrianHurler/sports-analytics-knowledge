# Pillar 5: State & Value Modeling

## Central question

**What is each action or game state worth?**

State-value models estimate the expected future value of being in a particular game situation, then evaluate how actions move the game between states.

## Core ideas

- state representation
- transition probabilities
- Markov models
- expected possession value (EPV)
- expected points added (EPA)
- action value
- credit assignment
- context dependence

## Sports examples

Beach volleyball:
- value of a receive state
- value added by a set or attack decision
- transition from serve to receive to set to attack

Ice hockey:
- value of puck possession in different locations and configurations
- value added by entries, passes, carries, and shots

## Explain → Build → Apply → Defend

**Explain:** Describe how state values represent expected future outcomes.

**Build:** Construct a simple Markov or expected-value model.

**Apply:** Use state values to evaluate actions or players in real event data.

**Defend:** Justify state definitions, transition assumptions, terminal outcomes, credit assignment, validation, and whether the model captures the important context.

## Key warning

A state representation that is too coarse hides important context; one that is too detailed becomes sparse and unstable.
