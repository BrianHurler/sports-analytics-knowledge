# Model Defense Question Bank

The Defend level means being able to explain why an analysis should be trusted, not merely how it was fit.

## Universal questions

- What exact problem were you trying to solve?
- What is the estimand or prediction target?
- Why did you choose this method?
- Why not use something simpler?
- What assumptions does the model make?
- Which assumptions are most fragile?
- What would cause the model to fail?
- How did you validate it?
- What baseline did it need to beat?
- How did you prevent leakage?
- How do you represent uncertainty?
- How stable are the results across time, competition levels, or player groups?
- Which variables matter most, and does that interpretation make sports sense?
- Which variables are unavailable or poorly measured?
- How does the output change a decision?
- What would you tell a coach who disagreed with the model?

## Bayesian / hierarchical models

- Why is a hierarchical model appropriate here?
- What are the priors and why were they chosen?
- How much shrinkage occurs for low- versus high-sample players?
- What do posterior predictive checks show?
- How sensitive is the result to the prior?
- Is player ability assumed constant through time?

## Gradient boosting

- What did boosting improve over logistic/linear regression?
- How were hyperparameters selected?
- Was validation temporal or randomly split, and why?
- Are probability outputs calibrated?
- Could feature importance be mistaken for causal importance?
- What evidence suggests the additional complexity is worth it?

## Causal inference

- What is the treatment?
- What is the outcome?
- What is the causal estimand?
- Why are the comparison groups exchangeable after adjustment?
- Which variables are confounders?
- Did you accidentally control for mediators or colliders?
- Is there adequate treatment overlap?
- What unmeasured confounder worries you most?
- What sensitivity analyses did you run?
- How narrow should the causal claim be?

## Player valuation / RAPM

- What is being adjusted for?
- How do collinearity and shared ice/court time affect estimates?
- Why is regularization needed?
- What does zero mean in the model?
- How stable are estimates year to year?
- How do role and deployment enter the model?
- How would you validate a latent player-value estimate?

## State-value models

- Why were these states chosen?
- Are states Markovian enough for the intended use?
- What information is lost by the state definition?
- How are terminal outcomes handled?
- How is value assigned across consecutive actions?
- Does the model predict future outcomes out of sample?

## Simulation / optimization

- Where do the input probabilities come from?
- How sensitive is the recommendation to input uncertainty?
- What objective is being optimized?
- Are the constraints realistic?
- Does the simulation reproduce real-world distributions?
- Could optimizing the measured objective create unintended behavior?
