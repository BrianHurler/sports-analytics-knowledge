# Leakage

Leakage occurs when a model uses information that would not legitimately be available at the time the prediction or decision is made.

## Obvious leakage

Predicting whether a shot becomes a goal using a variable recorded after the shot outcome.

## Subtle sports leakage

- randomly splitting events from the same match across train and test sets
- allowing future-season information into a historical player rating
- using a post-treatment variable in a causal model
- building features from full-season aggregates when predicting earlier games

## Why sports are vulnerable

Sports datasets contain nested dependence:

**event → rally/possession → game/match → player/team → season**

A random row split can make train and test sets look independent when they are not.

## Better practice

- use temporal holdouts for future prediction
- group splits by match, player, or season when appropriate
- calculate rolling features using only information available up to that date
- document exactly what would be known at inference time

## Diagnostic question

> Could I have computed every feature in this row at the exact moment I claim the model would make its prediction?

If not, investigate for leakage.
