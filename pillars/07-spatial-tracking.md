# Pillar 7: Spatial & Tracking Analytics

## Central question

**How do geometry, positioning, and movement matter?**

Spatial and tracking analytics move beyond event labels to represent where players, the ball or puck, and relevant structures are located and how they evolve over time.

## Core ideas

- coordinate systems
- spatial features
- distances and angles
- trajectories and velocity
- spacing and pressure
- occupancy and control
- spatiotemporal models
- embeddings and learned representations
- computer vision / tracking

## Sports examples

Beach volleyball:
- set location and attack geometry
- blocker starting position
- defender positioning
- attack trajectories and court-space exploitation

Ice hockey:
- puck-carrier pressure
- passing lanes
- support structure
- forecheck geometry
- entry and exit trajectories

## Explain → Build → Apply → Defend

**Explain:** Describe why event outcomes miss information contained in positioning and movement.

**Build:** Engineer basic spatial features or fit a simple spatial model.

**Apply:** Use coordinates or tracking data to answer a tactical or performance question.

**Defend:** Explain coordinate quality, sampling, missingness, feature choices, temporal alignment, model validation, and whether spatial patterns are actionable.

## Key warning

More detailed tracking data does not automatically produce better insight. The representation still needs to correspond to the sports question.
