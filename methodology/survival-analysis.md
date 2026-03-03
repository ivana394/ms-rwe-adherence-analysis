# Persistence and Survival Analysis

This section describes how treatment persistence was modeled using time-to-event methods.

Persistence reflects the duration of continuous therapy from initiation until discontinuation or switching.

---

## 1) Conceptual Definition

Persistence was defined as the time from treatment initiation to:

- permanent discontinuation, or
- switching to another disease-modifying therapy (DMT),

depending on analysis specification.

Persistence is distinct from adherence:
- Adherence measures coverage within a treatment episode.
- Persistence measures the duration of that episode.

---

## 2) Event Definition

Two primary events were modeled:

1. **Treatment discontinuation**
2. **Treatment switching**

Depending on the model:
- One event was treated as the outcome,
- Other competing events were censored.

Clear event-time definitions were applied to ensure valid time-to-event modeling.

---

## 3) Permissible Gap and Episode Termination

A 180-day permissible gap was used.

If the gap between expected end of supply and next prescription exceeded 180 days:

- The patient was classified as non-persistent.
- The discontinuation date was defined accordingly.

This approach balances sensitivity to true discontinuation with allowance for realistic refill delays.

---

## 4) Kaplan–Meier Estimation

Persistence curves were estimated using:

- Kaplan–Meier survival analysis

This method allows:

- Estimation of probability of remaining persistent over time
- Inclusion of censored observations
- Visual comparison between therapy groups

Persistence probabilities were evaluated at:
- 6 months
- 12 months
- Extended follow-up where applicable

---

## 5) Log-Rank Testing

Differences between treatment groups were tested using:

- Log-rank (Mantel–Cox) test

This non-parametric test compares survival distributions between groups.

---

## 6) Cox Proportional Hazards Modeling

To identify predictors of non-persistence, multivariate Cox regression models were fitted.

Hazard ratios were estimated for:

- Therapy type
- Prior treatment exposure
- Demographic characteristics
- Treatment switching behavior

The Cox model allows:

- Adjustment for multiple covariates
- Estimation of relative risk over time
- Handling of censored data

---

## 7) Semi-Naïve Cohort for Time-to-Event Modeling

To ensure valid estimation of treatment start time:

- A semi-naïve cohort was constructed.
- This included therapy-naïve patients and experienced patients with clearly observed new therapy initiation.

This reduces bias caused by left-truncated exposure histories.

---

## 8) Statistical Implementation

All survival analyses were performed using:

- R / RStudio
- Standard survival analysis libraries
- Supplementary descriptive analysis in SPSS

Statistical significance threshold: p ≤ 0.05.

---

## 9) Interpretation Considerations

- Claims-based persistence reflects dispensing continuity.
- True medication intake cannot be directly observed.
- Observation window truncation may influence long-term persistence estimates.
- Hospital-only therapies were not fully captured.

Despite these limitations, time-to-event modeling provides a robust framework for real-world treatment persistence analysis.
