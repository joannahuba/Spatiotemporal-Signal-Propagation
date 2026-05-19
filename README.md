# Spatiotemporal Signal Propagation in Multicellular ERK Signaling

## Project Overview

This project investigates spatiotemporal signaling propagation in multicellular
systems using graph-based quantitative analysis of ERK signaling dynamics.

The analysis focuses on how oncogenic mutations in the PI3K–AKT pathway alter
cell-to-cell signaling coordination, propagation strength, and temporal relay
behavior.

The workflow combines:

- classical Relative Risk (RR) propagation analysis
- statistical comparison across mutations
- lagged temporal propagation analysis
- parameter robustness assessment
- graph-based predictive machine learning
- Graph Neural Networks (GNNs)

The project progressively transitions from descriptive statistical analysis
toward predictive and mechanistic modeling of multicellular signaling networks.

---

# Environment Setup

The project uses `uv` for reproducible dependency management.

## Initialize environment

```bash
uv init
```

## Install dependencies

```bash
uv sync
```

---

# Repository Structure

## Task A1 — Mutation comparison

Notebook:

```text
notebooks-part2/Part1_Block3_Comparison.ipynb
```

Main analyses:
- Relative Risk (RR) comparison across mutations
- replicate-level statistical testing
- mutation-dependent ERK propagation strength
- Mann–Whitney U tests + Bonferroni correction

---

## Task A2 — Lagged propagation analysis

Notebook:

```text
notebooks-part3/Part2_L1_LaggedExposure.ipynb
```

Main analyses:
- WT vs PIK3CA_H1047R vs AKT1_E17K
- lagged Relative Risk curves RR(τ)
- temporal propagation dynamics
- optimal lag estimation

---

## Task A3 — Parameter robustness assessment

Notebook:

```text
notebooks-part2/Part1_Block2_ParameterSensitivity.ipynb
```

Main analyses:
- robustness of RR to spatial radius r
- parameter sensitivity analysis
- spatial propagation stability

---

## Independent Analysis — Graph-based predictive modeling

Notebook / directory:

```text
independent_analysis/
```

Main analyses:
- Logistic Regression prediction of future signaling jumps
- Graph Neural Networks (GCN)
- spatiotemporal graph representation of signaling
- predictive modeling of propagation dynamics
- evaluation using ROC-AUC, precision, recall and F1-score

---

# Final Report

The complete written report is available as:

```text
report.pdf
```

The report includes:
- methodology
- biological interpretation
- statistical analyses
- visualizations
- machine learning models
- Graph Neural Network results
- discussion and conclusions

---

# Main Findings

## Mutation-dependent propagation

- **PIK3CA_H1047R** exhibited the strongest ERK propagation
  (highest Relative Risk)
- **AKT1_E17K** and **PTEN_del** showed weaker signaling coordination
- WT displayed intermediate and temporally stable propagation behavior

---

## Temporal dynamics

- All signaling regimes reached maximal propagation at lag τ = 0
- PIK3CA_H1047R produced rapid and highly synchronized signaling waves
- WT signaling was more temporally extended
- AKT1_E17K exhibited flatter temporal propagation profiles

---

## Predictive graph learning

Graph Neural Networks successfully learned biologically meaningful
spatiotemporal signaling patterns directly from cellular interaction graphs.

Final GNN performance:

| Metric | Value |
|---|---:|
| ROC-AUC | 0.749 |
| Accuracy | 0.792 |
| Recall | 0.542 |
| F1-score | 0.339 |

These results demonstrate that future signaling activity is partially
predictable from graph topology and neighboring cellular states.

---

# Technologies Used

- Python
- pandas
- NumPy
- matplotlib
- seaborn
- scikit-learn
- PyTorch
- PyTorch Geometric

---

# Output files
- lagged_exposure_table.csv
- lagged_line_plot.png
- mutations_barplot.png
- mutations_comparison_table.csv

# Biological Motivation

Cellular signaling propagation is fundamentally a network phenomenon emerging
from coordinated interactions between neighboring cells.

This project demonstrates how graph-based computational approaches can be used
to quantify and predict multicellular signaling dynamics, providing insight
into how oncogenic mutations reshape collective cellular behavior.