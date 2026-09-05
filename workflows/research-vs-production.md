# Research vs. Production

A common mistake is to assume that the most important analytical work must become a production model. In professional sport, research and production solve different problems.

## Four useful categories

### 1. Production models

Models that run repeatedly and feed downstream systems.

Examples:
- expected goals
- player projections
- RAPM or other player-value estimates
- Elo/team-strength systems
- expected possession value
- automated classifications

Typical flow:

**new data → model update → stored output → dashboard/report/API**

### 2. Production metrics

A research project may establish that a simple metric matters. The final production output can then be much simpler than the original study.

Example:

A causal study finds that attacking on two is beneficial only when the second-ball opportunity is genuinely available. The production dashboard may ultimately track **on-two opportunity conversion rate** rather than rerunning the entire causal study nightly.

### 3. Recurring decision-support models

High-quality analytical systems that are rerun when a decision arises rather than continuously.

Examples:
- trade or acquisition evaluation
- draft models
- playoff matchup tools
- roster simulations
- contract projections
- tournament-specific scouting models

### 4. Research / one-off investigations

Studies designed to answer a question and change organizational knowledge.

Examples:
- Does a more aggressive serving strategy increase rally-win probability?
- Does a tactical change actually improve transition offense?
- Do certain player combinations create genuine synergy?
- When does a controlled zone entry create more value than a dump-in?

The correct endpoint may simply be a well-supported conclusion.

## How research becomes production

A common pathway is:

**question → study → knowledge → decision rule → production metric/tool**

Not every project should travel all the way across that chain.

## Causal inference and production

Causal inference is often upstream of production rather than the nightly production engine itself.

For example:

1. Study whether attacking on two causally improves rally-win probability in eligible situations.
2. Identify the contexts where the effect is positive.
3. Convert those findings into a tactical rule.
4. Track whether teams recognize and exploit those opportunities.
5. Optionally embed the estimated treatment effect inside a simulation or decision-support model.

## The analytical maturity test

Before productionizing something, ask:

- Will this answer recur?
- Will new data materially change the answer?
- Does someone need the output on a predictable cadence?
- Is the metric/model stable enough to automate?
- Is automation more useful than documenting the finding?

If not, a one-off research result may be the correct product.
