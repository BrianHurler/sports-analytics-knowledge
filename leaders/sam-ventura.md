# Sam Ventura — Research Guide

Sam Ventura is an especially useful sports-analytics leader to study because his career connects four stages of the field that are often treated separately: **public data engineering, public statistical modeling, academic research, and NHL decision support**.

Before entering an NHL front office, Ventura co-founded War-on-Ice with Andrew Thomas, helped build open-source hockey data infrastructure, presented early expected-goals and transition-style ideas, and contributed to a culture in which public analysts could inspect, reproduce, and improve one another's work. He later moved into the Pittsburgh Penguins' research group and now leads hockey strategy and research for the Buffalo Sabres.

The most important lesson from Ventura's public record is not one single metric. It is the progression:

**collect better data → construct better measurements → test predictive value → model context → communicate uncertainty → support a hockey decision**

> **Scope note:** much of Ventura's most important NHL work is proprietary. This guide therefore focuses on publicly documented methods, talks, software, research, interviews, and organizational descriptions. It does not attempt to reverse-engineer Pittsburgh or Buffalo's internal models.

## Seven-pillar legend

- **M** — Measurement
- **P** — Prediction
- **V** — Player valuation
- **C** — Causal inference
- **S** — State & value modeling
- **D** — Decision science
- **T** — Spatial & tracking analytics

---

# Recurring ideas in Ventura's work

## 1. Data infrastructure is part of analytics

War-on-Ice and `nhlscrapr` were not merely websites or convenience tools. They lowered the cost of asking new hockey questions. Reproducible play-by-play data, contextual filters, and public model outputs enabled analysts to move beyond manually collected summaries.

**Pillars:** **M**

**Repository lesson:** a sophisticated model built on brittle or inaccessible data is not a complete analytics system. Data acquisition, cleaning, definitions, reproducibility, and interfaces are analytical work.

---

## 2. Prediction is a test of whether a metric contains signal

A recurring theme in Ventura's public presentations is the distinction between statistics that describe what just happened and statistics that help forecast what is likely to happen next. Shot attempts became useful partly because they stabilized faster than goals. Expected-goals work then attempted to preserve shot volume while adding information about shot quality.

**Pillars:** **M, P**

**Repository lesson:** whenever a new metric is proposed, ask whether it improves out-of-sample prediction relative to a simpler baseline.

---

## 3. Context should be modeled, not hand-waved

The evolution from raw Corsi toward expected goals, position-specific comparisons, zone-transition ideas, and richer player models reflects the same principle: hockey events occur in different contexts and those contexts change their meaning.

**Pillars:** **M, P, V**

---

## 4. Analytics should narrow uncertainty, not pretend to eliminate it

Buffalo's publicly described draft process is explicitly probabilistic. Prospects are evaluated across leagues, ages, tournaments, competition levels, and playing contexts; models project ranges of future outcomes rather than presenting scouting decisions as certainty.

**Pillars:** **P, V, D**

**Repository lesson:** a projection should communicate a distribution of plausible outcomes, not only a point estimate.

---

## 5. Analytics and scouting are separate information channels before they are combined

Buffalo has publicly described an approach in which the analytics group forms opinions from data before reading scouting reports or watching video, then compares those assessments with the scouting group.

This is analytically interesting because it preserves partially independent evidence streams before synthesis.

**Pillars:** **M, D**

**Repository lesson:** combining information too early can create correlated judgment and confirmation bias. Independent evaluations can make disagreements more informative.

---

# Public research and methodological work

## War-on-Ice — public hockey analytics infrastructure

**Co-founders:** Sam Ventura, Andrew Thomas  
**Period:** approximately 2014–2016

War-on-Ice provided public NHL data, advanced team/player statistics, visualization, salary information, adjusted measures, and model-based outputs during a formative period in public hockey analytics.

Its importance was broader than any individual statistic. It helped create an ecosystem in which analysts could obtain structured data and compare modern metrics without rebuilding the entire data pipeline themselves.

**Pillars:** **M, P, V**

**Why it matters:** public analytical progress accelerates when data and methods are inspectable and reusable.

**Applied lesson:** when building an internal analytics department, shared data infrastructure can produce more long-term value than isolated one-off analyses.

Sources: [Carnegie Mellon profile](https://www.cmu.edu/dietrich/statistics-datascience/people/affiliated/sam-ventura.html), [Institute of Mathematical Statistics feature](https://imstat.org/2015/10/02/statisticians-on-ice/)

---

## `nhlscrapr` and reproducible NHL play-by-play data

Ventura co-authored `nhlscrapr`, an R package designed to collect and structure NHL play-by-play information.

**Pillars:** **M**

**Why it matters:** many hockey metrics depend on reconstructing who was on the ice, game state, event coordinates, score state, and event sequences. Reliable ingestion is therefore upstream of nearly every modeling problem.

**Repository connection:** this belongs in Measurement just as much as an estimator does. The chain is:

**source data → parsing → definitions → derived variables → model → decision**

An error early in that chain propagates through everything downstream.

---

## Early expected-goals development — 2014–2015

Ventura publicly presented work during the War-on-Ice period that moved from unweighted shot attempts toward shot-quality models. The core idea was to weight attempts using contextual information rather than treat every attempt as equally dangerous.

Contemporary accounts describe logistic-regression approaches combining shot quantity and shot quality to improve estimates of future goal share.

**Pillars:** **M, P, V**

**Why it matters:** this illustrates a natural model-development sequence:

1. establish that shot volume predicts future outcomes better than goals alone;
2. identify information discarded by pure shot counts;
3. model scoring probability conditional on shot context;
4. aggregate those probabilities into expected-goal measures;
5. test whether the richer model improves prediction or evaluation.

**Repository connection:** this is exactly the question "why would I not use something simpler?" A more complicated xG model should earn its complexity by adding signal or improving decision usefulness.

Sources: [OTTanalytics summary](https://canucksarmy.com/news/a-summary-of-ottanalytics), [historical summary of Ventura's War-on-Ice presentations](https://www.expectedbuffalo.com/buffalo-sabres-expected-learning-history-class-more-sam-ventura-content/)

---

## Zone-transition / puck-progression analysis

Public summaries of Ventura's early presentations describe attempts to use NHL play-by-play event locations and timestamps to estimate how efficiently teams and players moved the puck between defensive, neutral, and offensive zones and how long they retained advantageous territorial states.

**Pillars:** **M, P, S**

**Why it matters:** this moves beyond counting final events and asks how a team progresses through states of play.

A simplified representation is:

**defensive zone → neutral zone → offensive zone → sustained offense → shot / loss of possession**

**Repository connection:** this is conceptually close to the state-transition thinking behind zone-entry models, transition offense, and possession-value frameworks. Even with imperfect public event data, analysts were trying to estimate the process that creates shots rather than only the shots themselves.

Source: [Expected Buffalo historical review](https://www.expectedbuffalo.com/expected-learning-buffalo-sabres-history-class-sam-ventura-and-war-on-ice/)

---

## Player evaluation: teammates, opponents, roles, and context

When Ventura joined Pittsburgh full time, the Penguins described his role as providing a quantitative perspective on player acquisition and on-ice strategy. Earlier public comments identified questions such as which players perform well together, how players perform against different opponents, and how deployment affects results.

**Pillars:** **P, V, D**

**Why it matters:** individual hockey performance is entangled with linemates, opposition, role, score, zone deployment, coaching, and special teams. Player valuation therefore requires contextual adjustment rather than raw rate comparison.

**Repository connection:** this belongs directly beside RAPM, hierarchical player models, expected-goal impacts, and teammate/opponent adjustment.

Source: [Pittsburgh Penguins announcement](https://www.nhl.com/penguins/news/penguins-hire-sam-ventura-as-director-of-hockey-research-289961770)

---

## Data-Driven Decision-Making in Sports — 2018

Ventura's public seminar description framed sports analytics around data analysis, visualization, statistical modeling, and competitive decision-making, including player-evaluation models in hockey and football.

**Pillars:** **P, V, D**

**Why it matters:** modeling is not the endpoint. The analytical product must alter a decision, reduce uncertainty, or change how alternatives are compared.

Source: [University of Pittsburgh seminar](https://www.mathematics.pitt.edu/sites/default/files/abstracts/SAM%20VENTURA.pdf)

---

## `nflWAR`: a reproducible method for offensive player evaluation in football — 2019

**Authors:** Ronald Yurko, Samuel Ventura, Maksim Horowitz  
**Journal:** Journal of Quantitative Analysis in Sports

Although this paper is football rather than hockey, it is valuable for understanding Ventura's general valuation philosophy. It builds a reproducible framework for translating play value into player value and eventually Wins Above Replacement.

**Pillars:** **M, P, V, S**

**Why it matters for hockey:** the general credit-assignment problem is shared across invasion sports:

**estimate event value → attribute value to participants → establish a replacement baseline → aggregate into a common value scale**

The implementation is sport-specific, but the decomposition is highly transferable.

Source: [Journal article](https://doi.org/10.1515/jqas-2018-0010)

---

# Modern NHL research program

## Buffalo draft modeling and prospect projection

Buffalo has publicly described Ventura's group as collecting information on tens of thousands of draft-eligible players, comparing prospects across many leagues and tournaments, and building models that project future NHL performance.

Important features of the publicly described process include:

- differences in age and competition level;
- multiple evaluation settings for the same player;
- progressive updating as new information arrives;
- identifying traits that translate to professional hockey;
- estimating ranges of outcomes, including floors and ceilings;
- using analytics to narrow enormous prospect populations for scouts;
- forming an independent quantitative opinion before combining it with scouting.

**Pillars:** **M, P, V, D**

**Why it matters:** amateur evaluation is a classic hierarchical prediction problem. Observations come from different leagues, ages, roles, sample sizes, teammates, opponents, and competitive environments.

A conceptual model is:

**observed junior performance + league/age/context + skill indicators → latent player ability → distribution of future NHL outcomes**

The downstream decision is then not simply "who projects highest?" Draft slot, availability, organizational need, uncertainty, risk tolerance, and alternative prospects all matter.

Source: [Buffalo Sabres — Inside the pre-Draft analytics process](https://www.nhl.com/sabres/news/buffalo-sabres-analytics-team-nhl-draft-sam-ventura)

---

## Player/puck tracking, RFID, and computer vision

Carnegie Mellon has described Ventura's current work as using computer vision and RFID/player-puck tracking to quantify events occurring continuously on the ice.

**Pillars:** **M, P, S, T**

**Why it matters:** tracking data expands the observable state beyond NHL event logs. Instead of only recording a shot, pass, or hit, analysts can begin to represent:

- player and puck locations;
- velocity and acceleration;
- spacing;
- pressure;
- passing lanes;
- support structure;
- defensive gaps;
- off-puck movement;
- sequence timing.

That enables richer state/value models and more granular skill evaluation.

Source: [Carnegie Mellon profile](https://www.cmu.edu/engage/events/tartans-on-the-rise/ventura)

---

# Seven-pillar map

| Pillar | Ventura connection | Strength of public evidence |
|---|---|---|
| **Measurement** | War-on-Ice, `nhlscrapr`, contextual statistics, richer event/tracking data | **Very strong** |
| **Prediction** | xG, future performance, prospect projection, signal testing | **Very strong** |
| **Player valuation** | contextual evaluation, acquisition support, prospect models, WAR framework | **Very strong** |
| **Causal inference** | limited explicit public causal-identification work | **Limited** |
| **State & value modeling** | zone transitions, xG, play value, tracking-based game-state representation | **Moderate–strong** |
| **Decision science** | draft, trades, acquisitions, strategy, probabilistic prospect outcomes | **Very strong** |
| **Spatial & tracking analytics** | event locations, player/puck tracking, RFID, computer vision | **Strong in modern team work; limited public model detail** |

---

# What an applied analyst should learn from Ventura

## 1. Build the data layer before chasing sophisticated models

War-on-Ice's lasting contribution was partly infrastructural. Good research requires trusted, reusable data.

## 2. Compare every complex model with a simpler baseline

Corsi was useful because it predicted future performance surprisingly well. Expected goals became useful only if incorporating shot quality added information.

## 3. Validation should match the decision

If the model will forecast future performance, test future performance. If it will rank prospects, test historical draft cohorts out of sample. If it supports player acquisition, evaluate whether its estimated differences persist under new teammates and environments.

## 4. Preserve uncertainty

A player projection is not a destiny. The useful output is often a distribution with meaningful floor, median, ceiling, and downside probabilities.

## 5. Independent information streams can improve synthesis

Analytics and scouting should communicate, but forming independent opinions before reconciliation can make disagreement diagnostically useful.

## 6. Use richer data to measure skills, not just produce fancier totals

Tracking data matters when it exposes repeatable hockey abilities—pressure, puck management, skating, passing, defensive positioning, transition contribution—not merely because it creates more columns.

## 7. Translate models into choices

Ventura's public career trajectory repeatedly returns to decisions: player acquisition, lineup/strategy questions, trades, the draft, and prospect prioritization.

The endpoint is not:

**Which model has the best fit?**

It is:

**What should the organization believe, how uncertain should it be, and what action changes because of the analysis?**

---

# Model-defense questions inspired by Ventura

When presenting a hockey model, be prepared to answer:

1. What data-generation process produced these observations?
2. Which contextual variables are missing?
3. What is the simplest reasonable baseline?
4. Does the new model outperform that baseline out of sample?
5. Are we evaluating description, prediction, or player attribution?
6. How quickly does the metric stabilize?
7. How much of the apparent player effect could be teammates, opponents, role, or league context?
8. What does the uncertainty distribution look like?
9. Does the validation period resemble the environment where the model will be used?
10. What hockey decision changes if the model is correct?
11. What is the cost if it is wrong?
12. What information do scouts/coaches have that the model does not?
13. Should those information streams be combined immediately or evaluated independently first?
14. Can the result be reproduced from the underlying data pipeline?

---

# Connection to the other leaders

### Eric Tulsky
Tulsky's public work repeatedly asks **what hockey process should we measure?** Ventura complements that by showing how to build reproducible infrastructure, test whether those measurements contain predictive signal, and scale the work toward organizational decision support.

### Luke Bornn
Bornn demonstrates how richer spatial/tracking data can represent and value complex states. Ventura's modern work occupies the NHL version of that frontier: player-puck tracking, computer vision, and increasingly granular skill measurement.

### Sunny Mehta
Mehta emphasizes decision-making under uncertainty. Ventura's public Buffalo draft process provides a concrete organizational example: probabilistic projections, independent evidence streams, and decisions made under imperfect information.

---

# Suggested learning path from Ventura's work

1. Understand why shot attempts became useful predictive measurements.
2. Reconstruct the transition from Corsi to expected goals.
3. Build a simple xG model and compare it with shot-attempt baselines.
4. Study teammate/opponent/context adjustment for player evaluation.
5. Treat data engineering and reproducibility as part of model quality.
6. Build a prospect projection that explicitly handles league, age, and uncertainty.
7. Compare model and scouting evaluations as partially independent evidence streams.
8. Move toward tracking-derived representations of pressure, spacing, transition, and puck management.
9. Finish every analysis with an explicit decision and uncertainty statement.

---

# Public sources and further reading

- [Sam Ventura — Carnegie Mellon Statistics & Data Science](https://www.cmu.edu/dietrich/statistics-datascience/people/affiliated/sam-ventura.html)
- [Inside the Sabres' pre-Draft analytics process — Buffalo Sabres](https://www.nhl.com/sabres/news/buffalo-sabres-analytics-team-nhl-draft-sam-ventura)
- [Penguins Hire Sam Ventura as Director of Hockey Research](https://www.nhl.com/penguins/news/penguins-hire-sam-ventura-as-director-of-hockey-research-289961770)
- [Q&A: Sam Ventura on War-on-Ice and analytics — Sportsnet](https://www.sportsnet.ca/nhl/article/qa-penguins-sam-ventura-talks-war-ice-analytics-off-season-moves/)
- [Statisticians on Ice — Institute of Mathematical Statistics](https://imstat.org/2015/10/02/statisticians-on-ice/)
- [Data-Driven Decision-Making in Sports — University of Pittsburgh](https://www.mathematics.pitt.edu/sites/default/files/abstracts/SAM%20VENTURA.pdf)
- [nflWAR: a reproducible method for offensive player evaluation in football](https://doi.org/10.1515/jqas-2018-0010)
- [Carnegie Mellon profile: player tracking, computer vision, and NHL analytics](https://www.cmu.edu/engage/events/tartans-on-the-rise/ventura)

## Final takeaway

Ventura's public body of work is best understood as a lesson in **building an analytics system rather than merely building a metric**.

The progression is:

**reliable data → meaningful hockey measures → predictive validation → contextual player evaluation → richer tracking data → probabilistic decision support**

That is very close to the architecture of a modern NHL research department.