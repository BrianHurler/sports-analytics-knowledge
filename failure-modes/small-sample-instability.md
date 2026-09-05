# Small-Sample Instability

Sports performance estimates often become unstable when data are sliced by player, opponent, phase, score state, season, or tactical context.

## Example

An athlete may have thousands of attacks overall but only a few dozen against elite opponents in a specific transition context.

A raw rate from that cell can look precise while being mostly noise.

## Common symptoms

- extreme leaderboards driven by tiny samples
- large week-to-week rank changes
- tactical conclusions that reverse after one tournament or game
- highly unstable subgroup estimates

## Better practice

- report sample size and uncertainty
- use shrinkage or hierarchical partial pooling
- prefer continuous context variables over arbitrary narrow bins when appropriate
- run stability checks across time windows
- establish minimum-evidence rules for descriptive displays

## Important distinction

Large databases do not guarantee large effective samples. Once the question becomes conditional enough, even an enormous event dataset can produce sparse comparisons.

## Diagnostic question

> If I removed or added one game, match, or tournament, would this conclusion materially change?
