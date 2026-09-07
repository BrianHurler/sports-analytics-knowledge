# Luke Bornn — Research Guide

Luke Bornn is a useful person to study because his public sports-analytics work does not live inside one narrow methodological lane. Across basketball, soccer, hockey, and sports science, the recurring pattern is to start with a real sporting question, exploit richer data where it adds information, build a model that respects the structure of the sport, and then connect the result back to a decision.

His work is especially valuable for this repository because it cuts across nearly all seven pillars.

> **Scope note:** this is a best-effort inventory of publicly identifiable sports-analytics research and substantive methodological work involving Bornn. It intentionally excludes his generic statistics research unless it was directly applied to sport. Conference papers that later became journal articles are grouped when they represent the same core research program.

## Seven-pillar legend

- **M** — Measurement
- **P** — Prediction
- **V** — Player valuation
- **C** — Causal inference
- **S** — State & value modeling
- **D** — Decision science
- **T** — Spatial & tracking analytics

## The recurring ideas in Bornn's work

### 1. Richer data should change the question, not just add features

A major thread in the basketball and soccer work is that tracking data makes previously invisible questions measurable: who controls valuable space, how ball movement changes future opportunity, what a possession is worth at each instant, and what players contribute away from the ball.

### 2. Value is usually contextual

Bornn's work repeatedly resists one-number evaluation without context. Shot value depends on location, lineup, defender positioning, and opportunity cost. Player metrics need to be evaluated for reliability and uniqueness. Spatial control depends on the locations and movement of everyone else on the floor or pitch.

### 3. Model the process, not only the outcome

EPV, Markov models, point processes, and trajectory representations all move beyond end-state summaries. Rather than asking only whether a shot went in or a possession scored, the models attempt to describe how the play evolved and what options were available along the way.

### 4. Analytics should support counterfactual thinking

Several projects explicitly ask "what if?" questions: What if a team changed its shot policy? What if a different pass were available? What if ball movement created a better future opportunity? This is where state/value modeling connects to decision science.

---

# Research inventory

## Basketball

### Factorized Point Process Intensities: A Spatial Analysis of Professional Basketball — 2014

**Authors:** Andrew Miller, Luke Bornn, Ryan Adams, Kirk Goldsberry  
**Source:** ICML / [arXiv](https://arxiv.org/abs/1401.0942)

**What it does:** Models NBA shot attempts as a spatial point process, then uses non-negative matrix factorization to discover a low-dimensional vocabulary of shooting locations and player shot-selection styles.

**Why it matters:** This is an early example of turning raw spatial event locations into interpretable player archetypes. Instead of defining arbitrary shot zones first, the model learns recurring spatial patterns from the data.

**Pillars:** **M, V, T**

**Repository connection:** This is a strong example of representation learning before prediction. The analytical value comes from constructing a better description of player behavior, which can then feed valuation or forecasting models.

---

### POINTWISE / A Multiresolution Stochastic Process Model for Predicting Basketball Possession Outcomes — 2014–2016

**Authors:** Daniel Cervone, Alexander D'Amour, Luke Bornn, Kirk Goldsberry  
**Sources:** Sloan 2014; Journal of the American Statistical Association; [arXiv](https://arxiv.org/abs/1408.0777)

**What it does:** Develops **Expected Possession Value (EPV)** for basketball using optical tracking data. The model estimates the expected points from a possession at each instant by combining continuous player movement with discrete basketball events.

**Why it matters:** This is foundational state-value modeling. It changes the unit of analysis from a completed play to a continuously evolving game state, making it possible to value passes, movement, decisions, and defensive reactions before the possession ends.

**Pillars:** **P, V, S, D, T**

**Repository connection:** This is almost a textbook example of the State & Value Modeling pillar. It is also a useful bridge from the repo's Markov/EPA concepts into richer spatiotemporal state representations.

---

### Characterizing the Spatial Structure of Defensive Skill in Professional Basketball — 2015

**Authors:** Alexander Franks, Andrew Miller, Luke Bornn, Kirk Goldsberry  
**Source:** Annals of Applied Statistics / [arXiv](https://arxiv.org/abs/1405.0231)

**What it does:** Uses player tracking, spatial processes, matrix factorization, and hierarchical regression to estimate how defenders affect shooting across different regions of the court.

**Why it matters:** Traditional defensive statistics mostly count salient events such as steals and blocks. This work tries to measure defense as an ongoing spatial influence, including effects that never appear in a box score.

**Pillars:** **M, V, P, T**

**Repository connection:** A direct lesson for hockey or beach volleyball is that important defensive value can exist in prevented actions, altered choices, or degraded opportunities rather than recorded terminal events.

---

### Move or Die: How Ball Movement Creates Open Shots in the NBA — 2015

**Authors:** Alexander D'Amour, Daniel Cervone, Luke Bornn, Kirk Goldsberry  
**Source:** MIT Sloan Sports Analytics Conference / [paper](https://www.lukebornn.com/papers/damour_ssac_2015.pdf)

**What it does:** Uses Markov modeling and entropy-based ideas to quantify ball movement, offensive unpredictability, and the tradeoff between taking an immediate opportunity versus creating a better one later in the possession.

**Why it matters:** The model treats ball movement as something that changes the future distribution of possibilities, not merely as a count of passes.

**Pillars:** **M, S, D, T**

**Repository connection:** This is a useful example of measuring the value of *option creation*. The same thinking can apply to puck movement, transition structure, or volleyball actions that improve the quality of the next contact rather than directly producing the point.

---

### A Mixture-of-Modelers Approach to Forecasting NCAA Tournament Outcomes — 2015

**Authors:** Lo-Hua Yuan, Anthony Liu, Alec Yeh, Aaron Kaufman, Andrew Reece, Peter Bull, Alex Franks, Sherrie Wang, Dmitri Illushin, Luke Bornn  
**Source:** Journal of Quantitative Analysis in Sports / [paper](https://www.lukebornn.com/papers/yuan_jqas_2014.pdf)

**What it does:** Combines forecasts from multiple modelers for the NCAA tournament and discusses data cleaning, post-processing, forecast combination, and uncertainty around tournament outcomes.

**Why it matters:** It is a reminder that strong prediction systems are often ensembles of reasonable models rather than a single clever algorithm. It also highlights how messy public data and model disagreement become part of the forecasting problem.

**Pillars:** **M, P, D**

**Repository connection:** Useful for thinking about ensemble modeling, model diversity, calibration, and the difference between predicting individual games and optimizing a tournament-level objective.

---

### The Van Exel Effect / Adjusting for Scorekeeper Bias in NBA Box Scores — 2016–2017

**Authors:** Matthew van Bommel, Luke Bornn  
**Sources:** MIT Sloan; Data Mining and Knowledge Discovery / [arXiv](https://arxiv.org/abs/1602.08754)

**What it does:** Estimates scorekeeper generosity and bias in subjective NBA statistics such as assists and blocks, then incorporates tracking-based context to model whether a pass is likely to be credited as an assist.

**Why it matters:** Before modeling performance, the measurement process itself may need to be modeled. Recorded statistics are not always objective ground truth.

**Pillars:** **M, P, V**

**Repository connection:** This belongs squarely in the Measurement pillar: understand who generated the label, how the label is defined, and whether systematic measurement effects contaminate player evaluation.

---

### NBA Court Realty — 2016

**Authors:** Daniel Cervone, Luke Bornn, Kirk Goldsberry  
**Source:** MIT Sloan Sports Analytics Conference / [paper](https://www.lukebornn.com/papers/cervone_ssac_2016.pdf)

**What it does:** Defines dynamic "ownership" of court space using player locations and then estimates which regions of space are valuable. The framework measures how offensive players create valuable space and how defenses constrain opponents to low-value regions.

**Why it matters:** It treats space itself as an analytical object. A player's contribution can be valuable even if the player never touches the ball.

**Pillars:** **M, V, S, T**

**Repository connection:** This is closely related to pressure, spacing, support, passing lanes, and off-ball value in hockey. It is also an example of converting geometry into a value surface.

---

### Studying Basketball Through the Lens of Player Tracking Data — 2017

**Authors:** Luke Bornn, Daniel Cervone, Alexander Franks, Andrew Miller  
**Source:** *Handbook of Statistical Methods and Analyses in Sports*

**What it does:** Synthesizes the emerging statistical toolkit for basketball player tracking, including spatial representations, defensive modeling, and possession-value approaches.

**Why it matters:** This is best used as a conceptual overview of how tracking data changes both the available questions and the required modeling toolkit.

**Pillars:** **M, P, V, S, T**

---

### Possession Sketches: Mapping NBA Strategies — 2017

**Authors:** Andrew C. Miller, Luke Bornn  
**Source:** MIT Sloan Sports Analytics Conference

**What it does:** Learns a dictionary of recurring player actions from tracking data and uses a hierarchical topic-style model to organize possessions by offensive structure.

**Why it matters:** Strategy is difficult to analyze when every possession is represented as a giant set of raw trajectories. This work builds an interpretable intermediate representation: recurring actions and possession types.

**Pillars:** **M, P, T**

**Repository connection:** This is directly relevant to play-type discovery, sequence clustering, tactical archetypes, and building a vocabulary from tracking or event sequences rather than defining every category manually.

---

### Rao-Blackwellizing Field Goal Percentage — 2019

**Authors:** Daniel Daly-Grafstein, Luke Bornn  
**Source:** Journal of Quantitative Analysis in Sports / [arXiv](https://arxiv.org/abs/1808.04871)

**What it does:** Replaces raw make/miss shooting percentage with an estimator based on post-release shot trajectory and estimated make probability. Conditioning on additional information reduces estimator variance.

**Why it matters:** A noisy observed outcome can sometimes be improved by modeling the process that generated it. The result is a more stable estimate of shooting skill earlier in a season.

**Pillars:** **M, P, V, T**

**Repository connection:** This is a clean example of reliability improvement and variance reduction—highly relevant whenever small samples make raw percentages unstable.

---

### Replaying the NBA / Markov Decision Processes with Dynamic Transition Probabilities — 2018–2020

**Authors:** Nathan Sandholtz, Luke Bornn  
**Sources:** MIT Sloan; Annals of Applied Statistics / [arXiv](https://arxiv.org/abs/1812.05170)

**What it does:** Models basketball possessions as non-stationary Markov decision processes whose transition probabilities change with the shot clock. Bayesian hierarchical models estimate the transitions, and simulations evaluate alternative shot policies.

**Why it matters:** This is one of the clearest examples in Bornn's work of moving from description to **policy evaluation**. The goal is not just to estimate what teams do, but to simulate what might happen if they behaved differently.

**Pillars:** **P, C, S, D**

**Repository connection:** The counterfactual language is important. Although changing a simulated policy is not automatically causal identification, it is the right decision-science structure: define a policy, model the environment, propagate uncertainty, and compare outcomes.

---

### Deep Learning of Player Trajectory Representations for Team Activity Analysis — 2018

**Authors:** Nazanin Mehrasa, Yatao Zhong, Frederick Tung, Luke Bornn, Greg Mori  
**Source:** MIT Sloan Sports Analytics Conference / [paper](https://www.lukebornn.com/papers/mehrasa_ssac_2018.pdf)

**What it does:** Learns latent representations of player trajectories in basketball and hockey to identify individual movement styles and team-level activity patterns.

**Why it matters:** Raw trajectories are too high-dimensional to compare directly. Representation learning can compress them into useful features for classification, similarity, scouting, or tactical analysis.

**Pillars:** **M, P, T**

**Repository connection:** This is an early bridge toward embeddings and modern sequence models for tracking data.

---

### From Markov Models to Poisson Point Processes: Modeling Movement in the NBA — 2019

**Authors:** Jacob Mortensen, Luke Bornn  
**Source:** MIT Sloan Sports Analytics Conference / [paper](https://www.lukebornn.com/papers/mortensen_ssac_2019.pdf)

**What it does:** Examines methods for modeling player movement from high-frequency NBA tracking data, contrasting Markov-style approaches with point-process formulations.

**Why it matters:** The modeling choice should reflect the structure of the process. Movement is continuous, interactive, and extremely high-frequency; a convenient discrete state model may lose important information.

**Pillars:** **P, T**

---

### Measuring Spatial Allocative Efficiency in Basketball — 2019–2020

**Authors:** Nathan Sandholtz, Jacob Mortensen, Luke Bornn  
**Source:** Journal of Quantitative Analysis in Sports / [paper](https://www.lukebornn.com/papers/sandholtz_jqas_2020.pdf)

**What it does:** Uses Bayesian hierarchical spatial models to compare who takes shots with who is best positioned to take them within a lineup, measuring the opportunity cost of suboptimal shot allocation.

**Why it matters:** Efficiency is not purely an individual property. A shot can be good in isolation but inefficient relative to the alternatives available to the team.

**Pillars:** **P, V, D, T**

**Repository connection:** This is a strong example of defining value relative to alternatives rather than relative to a league-average baseline alone.

---

## Soccer

### The Pressing Game: Optimal Defensive Disruption in Soccer — 2016

**Authors:** Iavor Bojinov, Luke Bornn  
**Source:** MIT Sloan Sports Analytics Conference / [paper](https://www.lukebornn.com/papers/bojinov_ssac_2016.pdf)

**What it does:** Models where teams disrupt opponents' passing and where they retain possession, creating spatial maps of defensive and offensive strengths and weaknesses.

**Why it matters:** It quantifies tactical style spatially rather than relying on aggregate defensive counts. Pressing high and defending deep can be distinguished by where disruption occurs.

**Pillars:** **M, V, T**

**Repository connection:** Conceptually close to zone-entry denial, forechecking pressure, controlled-exit suppression, or any analysis where *where* an opponent's process is disrupted matters.

---

### Wide Open Spaces: Measuring Space Creation in Professional Soccer — 2018

**Authors:** Javier Fernández, Luke Bornn  
**Source:** MIT Sloan Sports Analytics Conference / [paper](https://www.lukebornn.com/papers/fernandez_ssac_2018.pdf)

**What it does:** Builds player and team pitch-control surfaces, estimates the value of locations, and then quantifies both occupying valuable space and generating valuable space for teammates.

**Why it matters:** It gives measurable credit for off-ball movement. A player may add value by pulling a defender away from a teammate even if the player never receives the ball.

**Pillars:** **M, V, S, T**

**Repository connection:** One of the strongest papers for thinking about off-puck value in hockey: pressure, support, defender attraction, lane creation, and space generation can all create downstream value without an event being recorded for the player.

---

### Soccer Analytics: Unravelling the Complexity of "The Beautiful Game" — 2018

**Authors:** Luke Bornn, Daniel Cervone, Javier Fernández  
**Source:** *Significance* / [article](https://academic.oup.com/jrssig/article/15/3/26/7029361)

**What it does:** Provides a practitioner-oriented overview of why soccer analytics needs tracking and spatial methods to capture off-ball behavior and tactical structure.

**Why it matters:** Useful less as a technical paper than as a statement of analytical philosophy: the available data should match the true structure of the sport.

**Pillars:** **M, V, T**

---

### Decomposing the Immeasurable Sport: A Deep Learning Expected Possession Value Framework for Soccer — 2019

**Authors:** Javier Fernández, Luke Bornn, Daniel Cervone  
**Source:** MIT Sloan Sports Analytics Conference / [paper](https://www.lukebornn.com/papers/fernandez_sloan_2019.pdf)

**What it does:** Extends EPV ideas to soccer using deep learning and full spatiotemporal tracking. The framework estimates the value of the current state and potential future actions such as passes, drives, and shots.

**Why it matters:** It makes potential actions part of the model, not just observed actions. That allows analysts to evaluate decisions relative to the opportunity set that existed at the time.

**Pillars:** **P, V, S, D, T**

---

### SoccerMap: A Deep Learning Architecture for Visually-Interpretable Analysis in Soccer — 2020–2021

**Authors:** Javier Fernández, Luke Bornn  
**Source:** ECML PKDD / [arXiv](https://arxiv.org/abs/2010.10202)

**What it does:** Uses a fully convolutional neural network to estimate spatial probability surfaces for pass success, pass selection, and pass value from tracking data.

**Why it matters:** Rather than predicting only the outcome of the pass that occurred, the model estimates what could happen if the ball were played to many different locations.

**Pillars:** **P, S, D, T**

**Repository connection:** This is a model of the **decision surface**. For hockey, the analogous question is not merely whether a completed pass succeeded, but the success/value landscape of every realistic passing, carrying, or shooting option available in the state.

---

### A Framework for the Fine-Grained Evaluation of the Instantaneous Expected Value of Soccer Possessions — 2021

**Authors:** Javier Fernández, Luke Bornn, Daniel Cervone  
**Source:** *Machine Learning* / [arXiv](https://arxiv.org/abs/2011.09426)

**What it does:** Presents the mature journal version of the soccer EPV framework, decomposing possession value into calibrated components for passes, ball drives, shots, turnovers, and potential actions.

**Why it matters:** The decomposition makes a very complex value model more interpretable and testable. Instead of one opaque end-to-end score, the analyst can inspect whether each component is calibrated and where the model is succeeding or failing.

**Pillars:** **P, V, S, D, T**

**Repository connection:** This is a strong model-defense example: decomposition helps with calibration, diagnostics, interpretation, and communication with coaches.

---

## Hockey and cross-sport tracking

### Playing Fast Not Loose: Evaluating Team-Level Pace of Play in Ice Hockey Using Spatio-Temporal Possession Data — 2019

**Authors:** David Yu, Christopher Boucher, Luke Bornn, Mehrsan Javan  
**Source:** MIT Sloan Sports Analytics Conference / [paper](https://www.lukebornn.com/papers/yu_sloan_2019.pdf)

**What it does:** Defines richer measures of hockey pace using event and possession movement rather than relying only on player skating speed or a basketball-style possession count.

**Why it matters:** "Pace" is a construct, not a naturally observed variable. The paper shows how a vague coaching concept can be decomposed into measurable team and player behaviors.

**Pillars:** **M, V, T**

**Repository connection:** Especially relevant to hockey analytics because it demonstrates the measurement-design process: start with a hockey concept, define multiple plausible operationalizations, and test whether they reveal stable and useful differences.

---

### Data-Driven Lowlight and Highlight Reel Creation Based on Explainable Temporal Game Models — 2019

**Authors:** Evin Keane, Philippe Desaulniers, Luke Bornn, Mehrsan Javan  
**Source:** MIT Sloan Sports Analytics Conference / [paper](https://www.lukebornn.com/papers/keane_sloan_2019.pdf)

**What it does:** Converts changes in an in-game value model into an "event interest" signal for automatically identifying highlights and lowlights. The hockey application can surface valuable events beyond obvious shots and goals.

**Why it matters:** State-value models can power downstream products. Once each event has a contextual impact estimate, the same model can support video retrieval, explanation, coaching review, or content generation.

**Pillars:** **M, S, D**

**Repository connection:** A useful reminder that the value of an EPA/EPV model is not confined to a leaderboard. The model can become infrastructure for querying and organizing video around meaningful changes in game state.

---

### Meta-Analytics: Tools for Understanding the Statistical Properties of Sports Metrics — 2016–2017

**Authors:** Alexander Franks, Alexander D'Amour, Daniel Cervone, Luke Bornn  
**Source:** Journal of Quantitative Analysis in Sports / [arXiv](https://arxiv.org/abs/1609.09830)

**What it does:** Evaluates sports metrics using three meta-properties: **stability**, **discrimination**, and **independence**. Demonstrations use NBA and NHL metrics.

**Why it matters:** A metric should not be judged only by whether it sounds meaningful. Analysts need to ask whether it is repeatable, whether it meaningfully separates players, and whether it adds information beyond existing measures.

**Pillars:** **M, V, D**

**Repository connection:** This should be foundational for metric QA in this repository. Any new performance metric can be challenged with: Is it stable? Does it discriminate? Is it redundant? Does it improve an actual decision?

---

## Sports science / methodological caution

### Volume and Intensity Are Important Training-Related Factors in Injury Incidence in American Football Athletes — 2018

**Authors:** Patrick Ward, Michael Tankovich, J. Sam Ramsden, Barry Drust, Luke Bornn  
**Source:** MIT Sloan Sports Analytics Conference

**What it does:** Examines relationships between training volume, training intensity, and injury incidence in American football.

**Why it matters:** This sits closer to sports science than game analytics, but it illustrates the difficulty of learning from longitudinal athlete-exposure data where workloads, health, selection, and availability interact over time.

**Pillars:** **M, P, C, D**

---

### Training Load and Injury — Methodological Critiques — 2020

**Authors:** Franco Impellizzeri, Patrick Ward, Aaron Coutts, Luke Bornn, Alan McCall  
**Sources:** Journal of Orthopaedic & Sports Physical Therapy; Journal of Athletic Training

**What it does:** Critiques common methodological problems in the training-load/injury literature, including overconfident causal interpretation and questionable research practices.

**Why it matters:** Applied sports analytics often operates in observational settings where "associated with" can easily become "causes." These papers are useful reminders to define causal questions carefully and resist turning predictive relationships into intervention claims.

**Pillars:** **M, C, D**

---

# How the body of work maps to the seven pillars

| Pillar | Bornn research themes that illustrate it |
|---|---|
| **Measurement** | scorekeeper bias, meta-analytics, hockey pace, spatial representations, off-ball space creation |
| **Prediction** | NCAA forecasting, shot-make probability, EPV components, pass probability surfaces, movement models |
| **Player valuation** | defensive spatial impact, court ownership, shooting skill, space creation, contextual metric evaluation |
| **Causal inference** | training-load critiques; careful interpretation of alternative-policy simulations |
| **State & value modeling** | basketball EPV, soccer EPV, ball-movement value, highlight/lowlight impact models |
| **Decision science** | alternative shot-policy simulation, allocative efficiency, decision surfaces for passes, opportunity-cost framing |
| **Spatial & tracking analytics** | point processes, tracking-based defense, Court Realty, Possession Sketches, trajectory embeddings, pitch control, SoccerMap |

## What is conspicuously *not* the center of the portfolio?

Traditional causal inference is less central than the other pillars. Bornn's public game-analytics work is strongest in **measurement, state/value modeling, prediction, decision modeling, and spatial/tracking analytics**. That distinction matters: simulating a different policy from a fitted Markov model can be extremely useful, but it does not automatically identify the causal effect that would occur if a real team changed behavior.

---

# A learning sequence through Bornn's work

If the goal is to learn from the portfolio rather than simply archive it, a useful order is:

1. **Meta-Analytics** — learn how to judge whether a metric is worth having.
2. **Factorized Point Process Intensities** — see how spatial behavior can be represented from raw locations.
3. **Characterizing Defensive Skill** — move from representation to contextual player evaluation.
4. **POINTWISE / Basketball EPV** — learn continuous state valuation.
5. **Move or Die** — see how current decisions change future opportunity.
6. **NBA Court Realty** — add off-ball spatial value.
7. **Possession Sketches** — learn how high-dimensional tracking can become interpretable tactical structure.
8. **Replaying the NBA** — move from state modeling into policy simulation.
9. **Wide Open Spaces** — transfer spatial-control ideas to a different invasion sport.
10. **SoccerMap + Soccer EPV** — see modern deep learning used to estimate full action/value surfaces while retaining practical interpretability.
11. **Playing Fast Not Loose** — return to hockey and focus on construct definition and measurement design.

---

# What an applied analyst should take from Luke Bornn

## 1. Do not begin with the algorithm

The work usually begins with a sporting object that existing metrics fail to capture: defense, space, possession value, ball movement, shot allocation, pace, or subjective scorekeeping.

## 2. Treat the data-generating process as part of the analysis

Who recorded an assist? What actions are missing from event data? How does tracking frequency shape the possible state representation? What does a possession even mean in soccer? These are modeling questions, not preprocessing footnotes.

## 3. Context is often the signal

A player's action cannot always be evaluated independently of teammates, opponents, location, time, and available alternatives. This is why hierarchical models, spatial surfaces, state models, and opportunity-cost framing recur throughout the portfolio.

## 4. Off-ball and prevented value deserve explicit measurement

Some of the most important contributions are actions that never appear in conventional event data: pulling a defender, occupying a valuable region, disrupting a passing option, or forcing an opponent away from a preferred state.

## 5. A good metric should survive meta-analysis

Before building another metric, ask whether it is stable, discriminative, independent, interpretable, and decision-relevant.

## 6. The most useful model often estimates the alternatives

A pass-value surface, a simulated alternative shot policy, or an EPV model becomes powerful because it evaluates what *could have happened*, not just what did happen.

## 7. Rich models still need interpretable interfaces

Several of the soccer projects deliberately decompose complex deep-learning systems into probability and value surfaces that coaches can inspect. Model complexity is not an excuse to abandon communication.

---

# Direct connections to future hockey work

Bornn's portfolio suggests several high-value directions for hockey analysis:

- **Zone-entry defense:** move beyond a binary stop by measuring carrier pressure, support-option pressure, defender spacing, and the downstream value of the resulting entry state.
- **Off-puck defensive value:** quantify how defenders remove valuable options even when they never touch the puck.
- **Passing decision surfaces:** estimate the success and future value of all realistic pass/carry/shot options from a state.
- **Tactical archetypes:** use trajectory or event-sequence embeddings to discover recurring breakout, forecheck, entry, and offensive-zone structures.
- **Metric QA:** evaluate new hockey metrics for stability, discrimination, independence, uncertainty, and incremental decision value.
- **Policy simulation:** use state-transition models to explore tactical changes while being explicit about the gap between model-based counterfactual simulation and causal identification.

The broader lesson is that advanced sports analytics is not a progression toward ever more complicated algorithms. It is a progression toward better representations of the sport, better estimates of value and uncertainty, and better-supported decisions.