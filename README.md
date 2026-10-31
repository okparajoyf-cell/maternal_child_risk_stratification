# An Explainable XGBoost Framework for Maternal Health Risk Stratification in Nigerian Primary Healthcare

MSc dissertation project. A risk-stratification pipeline for maternal health
screening in Nigerian primary healthcare, built so that every individual score
carries a clinician-readable explanation.

## Data
2024 Nigeria Demographic and Health Survey, Individual Recode.
39,050 women → 12,671 with antenatal care data → 8,856 final analytic sample.
The second restriction removed women with zero antenatal visits, for whom the
visit-timing variable is deterministically missing and who automatically meet
one of the outcome markers. That is structural near-leakage, not correlation.

Data is not redistributed here, under DHS Program terms. Access is free on
request from dhsprogram.com.

## Method
PostgreSQL schema, Python, scikit-learn, XGBoost, SHAP (TreeSHAP).
Benchmarked against tuned logistic regression, random forest and a dummy baseline.
Survey weights applied in training. 2,000-sample bootstrap confidence intervals.

## Results
| Model | ROC-AUC |
|---|---|
| Tuned XGBoost | 0.722 (95% CI 0.697–0.747) |
| Tuned logistic regression | 0.726 |
| Random forest | 0.718 |

XGBoost did not outperform logistic regression. Paired bootstrap of the
difference: −0.004 (95% CI −0.012 to 0.003). McNemar p = 0.79.

Recall fell from 0.965 in the poorest wealth quintile to 0.000 in the richest.
Group-specific thresholds largely close the gap, but by redistributing
sensitivity rather than creating it.

Probabilities are over-confident in every bin. Brier score 0.209.

## Limitations
The outcome is a proxy built from four survey markers, reviewed informally by
five practising clinicians who did not fully agree with one another. This is
face validity, not clinical validation. The model is a research prototype and
must not be used to allocate care.
