# Sunny Mehta — Research & Decision-Making Guide

Sunny Mehta is useful to study for a different reason than Luke Bornn or Eric Tulsky. His public sports-analytics footprint is not dominated by a long academic publication list or one famous public metric. Instead, his career illustrates how quantitative thinking can become an organizational decision system: identify information that is biased or incomplete, build better estimates, combine data with scouting and context, reason explicitly about uncertainty, and then act aggressively when the expected value is favorable.

That progression matters because Mehta eventually moved from public hockey analysis into front-office work, where most of the actual models became private. As a result, this page necessarily relies on two kinds of public evidence:

1. **early hockey-analysis work and contemporaneous references to it**, and
2. **later interviews and public statements that reveal his decision philosophy and how he thinks analytics should function inside a team.**

> **Scope note:** this is a best-effort inventory of publicly identifiable sports-analytics research, methodological work, and decision philosophy associated with Mehta. Much of his early hockey work lived on blogs that are now partially unavailable or only preserved indirectly. Once he entered NHL front offices, the core analytical work became proprietary. The goal here is therefore not to reconstruct hidden team models, but to extract the ideas that are genuinely supported by public evidence.

## Seven-pillar legend

- **M** — Measurement
- **P** — Prediction
- **V** — Player valuation
- **C** — Causal inference
- **S** — State & value modeling
- **D** — Decision science
- **T** — Spatial & tracking analytics

---

# Why Mehta matters analytically

Mehta's career is a strong example of analytics as **decision-making under uncertainty**, not analytics as model-building for its own sake.

Across poker, derivatives trading, baseball consulting, and hockey, the recurring theme is similar:

**estimate probabilities → understand uncertainty → identify where the market or conventional wisdom may be wrong → preserve flexibility → act when the edge is large enough.**

That makes his work especially relevant to the **Prediction**, **Player Valuation**, and **Decision Science** pillars, with an important foundation in **Measurement**.

His early hockey analysis also reflects a principle that remains central to modern sports analytics:

> If the recorded data are biased, incomplete, or generated differently across environments, downstream player and team evaluation can be wrong even if the modeling is sophisticated.

---

# Recurring ideas in Mehta's work

## 1. Question the measurement process before trusting the metric

One of Mehta's earliest publicly cited hockey projects examined inconsistencies in NHL shot recording across arenas. That is fundamentally a data-generating-process question: are all NHL shots being observed and recorded the same way?

If not, then save percentage, shot differential, shooting percentage, and any model built from those inputs may inherit systematic bias.

**Primary pillars:** **M, V**

---

## 2. Separate repeatable signal from noisy outcome

Early hockey-analytics discussions involving Mehta repeatedly focused on whether particular components of shot results were stable or repeatable: blocked shots, missed shots, shooting percentages, and positional differences.

That is a core analytical habit:

**before interpreting a statistic as skill, ask whether it persists.**

This connects directly to split-half reliability, year-to-year correlation, shrinkage, Bayesian priors, and modern player projection.

**Primary pillars:** **M, P, V**

---

## 3. Model context rather than accepting aggregate percentages

Mehta's early work included comparisons of shooting by forwards and defensemen and the effect of shot location/type. The important idea is not the exact historical conclusion; it is that raw percentages can confound **who took the shot, from where, under what conditions, and in what role**.

The natural analytical progression is:

**raw outcome → contextualized expectation → residual/relative performance.**

That same pattern underlies expected goals, expected save percentage, expected passing value, expected attack efficiency, and many other modern sports metrics.

**Primary pillars:** **M, P, V, T**

---

## 4. Analytics is useful only when it improves a decision

Mehta has repeatedly described probability and statistics as tools he cared about because they helped him win. That is a useful constraint on sports-analytics work: analytical sophistication is not the objective.

The objective is better decisions about players, contracts, roster construction, tactics, scouting, and resource allocation.

**Primary pillar:** **D**

---

## 5. Good decisions can produce bad short-term outcomes

Mehta's poker analogy is particularly important for sports organizations. A decision can be correct in expectation and still lose because the realized outcome contains variance.

That means process evaluation should distinguish:

- **decision quality** from **observed result**,
- expected value from realized value,
- model error from outcome randomness,
- and long-run process from short-run variance.

**Primary pillars:** **P, D**

---

## 6. Quantitative information should be integrated, not worshipped

Mehta has explicitly resisted being reduced to "the analytics guy." His public comments emphasize that player projection benefits from data, while character, psychology, culture, scouting, and other information also matter.

The useful lesson is not that "gut beats data." It is that a front office should build a process for integrating heterogeneous evidence while remaining clear about uncertainty and bias.

**Primary pillars:** **V, D**

---

# Public research and methodological work

## Arena / scorekeeper bias in NHL shot recording — c. 2009

**Public evidence:** contemporaneous hockey-analytics references describe Mehta examining inaccuracies and arena-to-arena differences in NHL shot totals. Objective NHL also discussed related rink-bias questions and explicitly referenced Mehta's work.

**What it does:** Investigates whether some NHL arenas systematically count shots differently from others.

**Why it matters:** Shot counts are treated as objective event data, but the recorded event depends on an observer and a local recording process. Systematic rink effects can distort team possession metrics and goalie evaluation.

**Pillars:** **M, V**

**Repository connection:** This is an excellent example of **measurement error before modeling**. Before comparing teams or players, ask whether the same event would have been labeled identically in every environment.

**Modern analogues:**

- tracking-vendor differences,
- scorer definitions,
- manually coded pressure events,
- inconsistent touch classifications,
- home-venue effects in event tagging,
- operator differences in scouting datasets.

---

## Forward vs. defense shooting percentage / shot-location context — c. 2009–2010

**Public evidence:** later hockey analysis credits Mehta with a guest study comparing forward and defense shooting and asking what would happen if the groups took shots from comparable locations.

**What it does:** Separates observed shooting percentage from the distribution of opportunities that produced it.

**Why it matters:** Defensemen generally shoot from different locations and situations than forwards. Comparing raw conversion rates alone therefore mixes shooting skill with shot selection and role.

**Pillars:** **M, P, V, T**

**Repository connection:** This is an early expected-value mindset. Rather than asking only "who shoots at a higher percentage?", ask:

**given the same opportunity characteristics, what outcome should we expect?**

That is the conceptual bridge to expected goals and other context-adjusted performance models.

---

## Shot blocks, missed shots, and repeatability — c. 2009–2010

**Public evidence:** later replication work explicitly credits Mehta with examining blocked and missed shot components during the 2008–09 season.

**What it does:** Tests whether teams appear to have persistent control over outcomes such as blocked shots and missed shots, rather than treating every component of Corsi/Fenwick as equally skill-driven.

**Why it matters:** A statistic can correlate with success and still be a poor player/team evaluation metric if much of its variation is noise.

**Pillars:** **M, P, V**

**Repository connection:** This belongs directly beside reliability, regression to the mean, and signal-vs-noise concepts. The correct question is not merely whether something happened, but whether it reveals a stable underlying ability.

---

## Score-state-adjusted territorial analysis — c. 2009

**Public evidence:** Objective NHL used data supplied by Mehta to examine team Corsi with the score tied at even strength.

**What it does:** Restricts possession analysis to a more comparable game state rather than mixing together situations where teams may rationally change behavior because they are leading or trailing.

**Why it matters:** Game context changes incentives. A team protecting a lead may concede shots or territory differently than a team chasing the game.

**Pillars:** **M, V, S**

**Repository connection:** A metric's denominator and state definition matter. Context adjustment often starts not with a more complex model, but with defining a cleaner comparison set.

---

## Early player-level shot-type and distance analysis — c. 2008–2009

**Public evidence:** archived public discussion shows Mehta working with individual NHL shot data including shot type and average shot distance.

**What it does:** Moves beyond goals and total shots toward the characteristics of each attempt.

**Why it matters:** It reflects the early transition in hockey analytics from aggregate box-score outcomes toward shot-quality modeling.

**Pillars:** **M, P, V, T**

**Repository connection:** This is the same conceptual move behind modern xG: characterize the opportunity before evaluating the observed finish.

---

# From public analyst to team decision system

## Phoenix / prospective ownership consulting — early 2010s

Mehta's early public hockey work led to consulting connected to a prospective Phoenix Coyotes ownership group. The important analytical lesson is that public research became useful because it could inform real asset and organizational decisions.

**Pillars:** **V, D**

---

## New Jersey Devils — Director of Hockey Analytics, 2014–2018

Mehta was hired to establish what the Devils have described as the NHL's first full-time hockey analytics department.

Public descriptions of the role emphasize support for:

- scouting,
- draft preparation,
- player evaluation,
- and broader hockey decisions.

The specific models are proprietary, but the organizational significance is important: analytics became a standing operational capability rather than an occasional consultant report.

**Pillars:** **M, P, V, D**

**Repository connection:** A mature analytics group should not merely produce dashboards. It should be connected to recurring decision processes.

---

## Washington Capitals / Zelus Analytics / MLB consulting — late 2010s

After New Jersey, Mehta completed graduate study in data science, consulted for the Washington Capitals, and worked at Zelus Analytics, which served multiple MLB organizations.

This period matters because it suggests an important development path for an applied analyst: exposure to multiple sports can sharpen the distinction between sport-specific domain knowledge and transferable modeling ideas.

**Pillars:** **P, V, D**

---

## Florida Panthers — Hockey Strategy & Intelligence → Assistant GM / Head of Analytics, 2020–2026

Mehta joined Florida's hockey operations group and eventually became Assistant General Manager and Head of Analytics. The Panthers won consecutive Stanley Cups during his tenure and reached three straight Cup Finals.

It would be inappropriate to attribute those outcomes to one individual or infer private models from roster moves. What can be learned publicly is the organizational model: analytics was integrated with hockey operations rather than kept as a separate research function.

**Pillars:** **V, D**

---

## New Jersey Devils — General Manager, 2026–

Mehta's transition to GM makes his public philosophy especially relevant. He has framed the job as repeated decision-making under uncertainty: gather different forms of information, assess risk, remain objective, and make high-quality decisions consistently.

His poker analogy also highlights **optionality**: preserve multiple paths when possible, avoid locking into weak positions, and be aggressive when the opportunity is favorable.

**Pillars:** **P, V, D**

---

# Mehta's decision philosophy

## Expected value over result worship

A useful front-office question is:

> Was the decision good given the information available at the time?

not merely:

> Did the move work?

This distinction is essential because sports outcomes contain large amounts of randomness.

### Applied example

Suppose a team signs a player whose model projects 3.0 WAR-equivalent value with a wide uncertainty interval. The player later suffers an unpredictable injury and produces almost nothing.

The signing can still have been analytically sound if:

- the prior estimate was well calibrated,
- injury risk was appropriately incorporated,
- the contract price was below expected market value,
- and no superior alternative existed.

**Pillars:** **P, D**

---

## Aggression should depend on edge, not personality

Mehta has described a poker-derived style of patience followed by aggression when the moment is right.

In analytical terms:

1. quantify the range of outcomes,
2. estimate the expected value,
3. understand the downside,
4. compare against alternatives,
5. preserve flexibility when the edge is small,
6. commit when the edge is large.

This is a useful framework for trades, free agency, offer sheets, draft decisions, and deadline strategy.

**Pillars:** **D**

---

## Optionality has value

A roster with cap space, movable contracts, draft capital, and multiple viable lineup paths is not merely "unfinished." It has **option value**.

This can be represented analytically as the value of being able to react to future states of the world.

For example:

- a star becomes unexpectedly available,
- a prospect develops faster than expected,
- a contender needs cap relief,
- an injury changes positional need,
- a contract market softens.

A roster-construction model should therefore not optimize only the current projected lineup. It can also account for future flexibility.

**Pillars:** **S, D**

---

# Seven-pillar map

| Pillar | Strength in Mehta's public body of work | Representative connection |
|---|---|---|
| **Measurement** | **Strong** | rink/scorekeeper bias, shot classification, context definition |
| **Prediction** | **Strong** | projecting player outcomes; repeatability; probability-centered decision making |
| **Player valuation** | **Strong** | context-adjusted player evaluation and front-office projection |
| **Causal inference** | **Limited publicly** | little public evidence of formal causal-identification work |
| **State & value modeling** | **Moderate** | score-state context, optionality, state-dependent roster value |
| **Decision science** | **Very strong** | expected value, risk, process quality, optionality, repeated decisions under uncertainty |
| **Spatial & tracking analytics** | **Early/moderate** | shot distance/type/location; later private work unknown |

A major lesson from this map is that **being an analytically sophisticated executive does not require every pillar to be equally visible in public research**. Mehta's differentiator is the bridge from probability and player evaluation to organizational action.

---

# What an applied sports analyst should learn from Mehta

## 1. Audit the data before modeling performance

Ask:

- who recorded this event?
- is the definition consistent?
- does venue/provider/operator matter?
- are missing events random?
- are historical rules stable?

A small measurement bias can become a large valuation bias after aggregation.

---

## 2. Treat reliability as a prerequisite for interpretation

Before calling something a skill:

- test split-half reliability,
- test year-to-year persistence,
- quantify standard error,
- shrink unstable estimates,
- compare signal to sampling variance.

---

## 3. Replace raw outcomes with contextual expectations when possible

Instead of:

**Player A converted 15% and Player B converted 9%.**

prefer:

**Given their opportunity distributions, what was each player expected to convert, and who exceeded expectation?**

This is the expected-vs-actual framework that appears repeatedly across modern sports analytics.

---

## 4. Evaluate the decision separately from the result

A good process needs prospective criteria.

Before the decision, record:

- expected value,
- uncertainty interval,
- downside risk,
- alternatives,
- assumptions,
- decision threshold.

Then evaluate later whether the process was sound rather than rewriting the logic based on the outcome.

---

## 5. Build analytics into the decision workflow

The endpoint should not be "model complete."

The endpoint should be something like:

**research → validated estimate → scouting/context synthesis → scenario comparison → recommendation → decision → retrospective evaluation.**

---

# Connection to the repository's seven-pillar framework

Mehta's public body of work fits especially well with the repository's guiding chain:

**question → estimand → data-generating process → model → validation → uncertainty → communication → decision**

His early hockey work concentrated heavily on the middle of that chain: whether the recorded data and raw percentages were actually trustworthy. His later executive philosophy extends the chain to its endpoint: make repeated decisions under uncertainty and judge the process over a long horizon.

That makes Mehta especially useful as a bridge between the technical pillars and **Decision Science**.

---

# Comparison with Bornn and Tulsky

## Luke Bornn

**Core lesson:** represent rich game states and extract value from spatial/tracking data.

Bornn asks questions such as:

- What does the full spatial state contain?
- What is possession worth right now?
- How much value does off-ball movement create?

## Eric Tulsky

**Core lesson:** improve the unit of analysis and collect the missing hockey data needed to isolate process.

Tulsky asks questions such as:

- What event actually predicts future performance?
- What is repeatable?
- What happens before the shot?
- How do zone entries create offensive value?

## Sunny Mehta

**Core lesson:** turn probabilistic estimates into repeated organizational decisions while respecting uncertainty and imperfect information.

Mehta's questions are closer to:

- Is the underlying data trustworthy?
- What is the expected outcome rather than the observed outcome?
- How confident are we?
- What alternatives do we have?
- What risk are we accepting?
- Is the edge large enough to act?

Together, the three profiles form a useful progression:

**Tulsky: define the right hockey process → Bornn: model the state richly → Mehta: use estimates to make decisions under uncertainty.**

---

# A Mehta-inspired model-defense checklist

When presenting a player or roster model, be prepared to answer:

1. **How trustworthy is the underlying measurement?**
2. **Which parts of the metric are repeatable?**
3. **What contextual factors affect the raw outcome?**
4. **What exactly are we predicting?**
5. **How well calibrated is the prediction?**
6. **What is the uncertainty around the estimate?**
7. **What information exists outside the model?**
8. **How should those information sources be combined?**
9. **What are the realistic alternatives?**
10. **What is the expected value of each alternative?**
11. **What downside are we exposed to?**
12. **What flexibility do we preserve or sacrifice?**
13. **What evidence would change the recommendation?**
14. **How will we judge the decision later without being fooled by outcome variance?**

If those questions cannot be answered, the analysis is probably not ready for an executive decision.

---

# Suggested learning exercises

## Exercise 1 — Measurement bias

Take an event metric and test whether its rate differs systematically by venue, scorer, provider, or operator after controlling for obvious context.

**Pillars:** M

## Exercise 2 — Repeatability decomposition

Choose a component metric and estimate split-half and season-to-season reliability. Compare the raw estimate with a shrinkage estimate.

**Pillars:** M, P, V

## Exercise 3 — Expected vs. actual

Build a contextual expectation model for an outcome such as shot conversion, attack efficiency, zone-entry success, or save probability. Rank performers by residual rather than raw rate.

**Pillars:** P, V, T

## Exercise 4 — Decision memo

For a hypothetical trade or signing, write a one-page memo containing:

- projected performance distribution,
- price/cost,
- alternatives,
- downside cases,
- option value,
- recommendation,
- conditions that would reverse the recommendation.

**Pillars:** V, D

## Exercise 5 — Decision retrospective

Return six months later and evaluate whether the original assumptions and probability estimates were reasonable **without using the realized outcome as the sole judge of quality**.

**Pillars:** P, D

---

# Public sources and further reading

Because much of Mehta's early public hockey work is difficult to access directly today, source quality varies. Prefer primary/official descriptions for career and philosophy, and use surviving analytics references to reconstruct only what is reasonably supported.

- New Jersey Devils / NHL.com profiles and interviews discussing Mehta's analytical philosophy and the creation of New Jersey's analytics department.
- NHL.com feature on Mehta's career path through poker, trading, analytics, Washington, Zelus, and Florida.
- MIT Sloan Sports Analytics Conference speaker profile.
- Objective NHL archives discussing rink bias and data supplied by Mehta.
- Later hockey-analytics replications that explicitly credit Mehta's early work on forward-vs-defense shooting and blocked/missed-shot repeatability.

## Source caution

Do not infer the Florida Panthers', Devils', Capitals', or Zelus Analytics' proprietary models from public roster moves or media descriptions. Team decisions are generated by many people and many information sources. The useful public lesson is the **decision framework**, not speculation about secret metrics.
