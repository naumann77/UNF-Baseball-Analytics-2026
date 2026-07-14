# 2026 UNF Baseball — Performance Analysis & Benchmarking

## Overview
This project analyzes the University of North Florida's 2026 
baseball season (31-24, ASUN Graphite Division Champions) and 
benchmarks their performance against the full 64-team 2026 NCAA 
Tournament field using advanced sabermetric metrics.

The analysis identifies UNF's strengths, performance gaps, and 
quantifies the offensive improvement needed to become a tournament 
contender in 2027.

---

## Key Findings

| Category | UNF Percentile vs Tournament Field |
|----------|-----------------------------------|
| Pitching | 67.7th percentile |
| Offense  | 14.4th percentile |
| Defense  | 10.2th percentile |

- FIP ranks 85.9th percentile — pitching staff is legitimately 
  elite at limiting hard contact
- HR/9 allowed ranks 100th percentile — best in the entire 
  65 team dataset
- OPS of .778 ranks 3.1st percentile vs tournament average of .864
- K% of 25.9% ranks 18.8th percentile. UNF strikes out more 
  than 81% of tournament teams, reflecting a roster wide 
  plate discipline gap
- Linear regression model achieves R² of 0.891 predicting run 
  production from OBP and SLG
- Raising both OBP and SLG to tournament averages projects to add 
  1.20 runs per game — approximately 66 additional runs over a 
  full season

---

## Regression Model

Built a linear regression model predicting runs per game from 
OBP and SLG across all 65 teams.

**Equation:**
Runs/Game = (33.874 × OBP) + (6.471 × SLG) + (-9.082)

**Performance:**
- R-squared: 0.891
- RMSE: 0.301 runs per game

**Key finding:** OBP is more than twice as impactful as SLG 
in predicting run production. Every 0.010 increase in OBP 
projects to add 0.339 additional runs per game.

---

## Recruiting Archetypes

Based on regression model and correlation findings:

**Archetype 1 — High Contact, High Discipline Hitter**
- OBP above .390
- K% below 20%
- BB% above 12%

**Archetype 2 — Plus Defender at Premium Position**
- Shortstop, center field, or catcher
- Fielding percentage above .975

**Archetype 3 — Power Bat with Pitch Recognition**
- ISO above .200
- SLG above .480
- K% below 25%

---

## Visualizations

| Chart | Description |
|-------|-------------|
| chart1_gap_bar | UNF percentile rankings across 17 stats |
| chart2_radar | UNF vs tournament average by category |
| chart3_category_summary | Three headline category percentiles |
| chart4_offense_scatter | OPS vs runs per game all 65 teams |
| chart5_era_vs_fip | ERA vs FIP pitching talent analysis |
| chart6_era_fip_gap | Defense impact on ERA all 65 teams |
| chart7_correlation_matrix | 16 stat correlation heatmap |
| chart8_regression | Predicted vs actual runs per game |

---

## Methodology

- Dataset specific FIP constant of 4.16 calculated from the 
  65 team sample replacing the MLB standard of 3.10
- Constant derived by anchoring FIP to league average ERA 
  across the full dataset
- Percentile rankings calculated vs 64 team tournament field 
  with UNF excluded from its own benchmark group
- Postseason games included for teams that advanced in the 
  NCAA Tournament representing a minor limitation for deep 
  tournament run teams

---

## Tools and Libraries

- Python 3.9
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

---

## Repository Structure

UNF-Baseball-Analytics-2026/
├── UNF_Baseball_Analytics_2026.ipynb  ← Main analysis notebook
├── data/
│   ├── team_benchmarks_clean.csv      ← Full 65 team dataset
│   └── unf_benchmarking_results.csv   ← Percentile rankings
└── charts/
└── [8 visualization PNG files]

---

## Author

Richard Naumann  
MS Business Analytics — University of North Florida  
Graduating December 2026  
Former Professional Baseball Player — Pioneer League  
Career Goal: MLB Player Development Analytics
