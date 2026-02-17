# Battlefield 6 – Class & Loadout Behavioral Modeling
## Overview

This project analyzes class selection and loadout behavior using deployment-normalized metrics and slot-aware modeling.
The goal was to distinguish:
Intentional selection
Situational usage
Default/passive loadout bias
Mode-driven class dependencies

## Dataset
Two datasets were analyzed:

### Gadget / Loadout Modeling
100 players per class
Usage normalized by class deployments

### Class–Mode Correlation
100 players total
Mode buckets: Vehicle, Mixed, Infantry, BR

## Methodology
### Deployment Normalization
Usage_Count / Class_Deployments

### Behavioral Selection Threshold
≥ 0.10 uses per deployment

### Slot-Aware Weighting
Gadgets capped at 0.50 (2-slot system)
Grenades capped at 1.00 (1-slot system)

### Passive Bias Detection
Modeled based on observable alternative gadgets and usage intensity to isolate default-driven selection.

### Class–Mode Correlation
Evaluated relationships between class share and mode share.

## Key Findings
RPG shows 94% selection rate with high integration intensity.
Weapon Sling exhibits measurable passive bias.
Engineer strongly correlates with vehicle-heavy modes.
Gadget usage distribution is highly right-skewed.

### Files
Excel modeling sheets
Case study presentation (PDF)
