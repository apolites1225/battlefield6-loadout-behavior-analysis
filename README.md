# Battlefield 6 – Class & Loadout Behavioral Modeling
## Overview

This project analyzes class selection and loadout behavior in Battlefield 6 through deployment-normalized behavioral modeling and slot-aware weighting frameworks. The framework was designed to separate intentional gameplay integration from structural or default-driven selection bias.

The objective was to distinguish between:
- Intentional selection
- Situational usage
- Default/passive loadout bias
- Mode-driven class dependencies

Rather than relying on raw usage counts, the model evaluates behavioral intent through normalization and slot-aware weighting techniques.

## Dataset
Two datasets were analyzed:

### Gadget / Loadout Modeling
- 100 players per class (Assault, Engineer, Recon, Support)
- Player–item level data
- Usage normalized by class deployments

### Class–Mode Correlation
- 100 players total
- Mode share bucketed into:
    - Vehicle
    - Mixed
    - Infantry
    - Battle Royale (BR)

## Methodology
### Deployment Normalization
Usage_Count ÷ Class_Deployments

This removes playtime bias and reflects behavioral frequency rather than raw volume.

### Behavioral Selection Threshold
Intentional selection defined as:

≥ 0.10 uses per deployment

(At least once per 10 deployments)

This filters incidental usage while preserving meaningful gameplay integration.

### Slot-Aware Weighting
Because loadouts contain structural slot constraints:
- Gadgets (2 slots) capped at 0.50
- Grenades (1 slot) capped at 1.00

Weights were scaled proportionally to reflect loadout capacity and prevent structural inflation.

### Passive Bias Detection
A Passive_Likelihood model was introduced to quantify default-driven selection inflation.

The model evaluates:
- Number of observable alternative gadgets
- Total alternative gadget usage intensity
- A percentile-based usage threshold
  
This distinguishes high selection driven by gameplay integration from high selection driven by default behavior.

### Class–Mode Correlation
Correlation analysis was performed between class share and mode share to quantify structural dependencies between class specialization and map environment.

## Key Findings
- RPG demonstrates a 94% selection rate with high integration intensity, indicating structurally dominant meta status.
- Weapon Sling exhibits measurable passive bias, indicating selection inflation from default behavior.
- Engineer selection strongly correlates with vehicle-heavy modes.
- Gadget usage distribution is highly right-skewed, with a small number of items dominating usage.

## Design Implications
- Selection rate alone is insufficient to evaluate balance health.
- Slot-aware weighting prevents structural inflation in multi-slot systems.
- Passive bias detection isolates default-driven meta distortion.
- Mode-specific class correlation informs targeted balance adjustments.

## Files
- [Case Study Presentation (PDF)](presentation/Battlefield6_Loadout_Behavior_Analysis_CaseStudy.pdf)
- Excel modeling files available in the /data directory for full metric logic and calculations.

