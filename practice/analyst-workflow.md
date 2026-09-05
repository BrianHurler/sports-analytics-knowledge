# Analyst Workflow

A repeatable workflow for sports analytics projects.

## 1. Define the sports decision
What decision could change because of this work?

## 2. Write the analytical question
Convert the vague sports question into a precise analytical problem.

## 3. Define the estimand or prediction target
State exactly what quantity the analysis is trying to estimate.

## 4. Understand the data-generating process
How were the observations created? Who chose the action? What was known at the time? What is missing?

## 5. Establish a simple baseline
Use the simplest reasonable method first.

## 6. Choose a method
Select the model family because it fits the question and data, not because it is fashionable.

## 7. Separate model fitting from validation
Use temporal or grouped validation when random row splits would leak player, game, or season structure.

## 8. Quantify uncertainty
Report ranges, posterior distributions, confidence intervals, or simulation uncertainty when decisions depend on precision.

## 9. Test assumptions and failure modes
Look actively for leakage, confounding, overfitting, instability, poor calibration, and selection bias.

## 10. Translate back to the sport
Express the finding in the language of the coach, scout, athlete, or decision-maker.

## 11. Choose an endpoint
Decide whether the output should remain:
- one-off research
- organizational knowledge
- recurring analysis
- a production metric
- a production model

## 12. Document what would change the conclusion
A good analysis should make its own limits visible.

## Senior-analyst habit

Before asking "which model should I use?", ask:

> What exactly am I trying to estimate, and what evidence would make me trust it?
