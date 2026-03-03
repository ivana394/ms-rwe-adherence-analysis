# Adherence Modeling (CMA5 Framework)

This section describes how medication adherence was operationalized and calculated within the study.

Adherence was assessed using pharmacy claims data and modeled within persistent therapeutic episodes.

---

## 1) Conceptual Definition

Adherence was defined as the extent to which medication use (based on dispensing records) corresponded to the prescribed dosing schedule.

Adherence was evaluated **only during periods of persistence**, in accordance with established taxonomies (ABC and ISPOR frameworks).

---

## 2) Method Selection: CMA5

Adherence was calculated using the **CMA5 (Continuous Multiple-Interval Measure of Medication Availability)** methodology, as described by Vollmer et al.

CMA5 is conceptually equivalent to a PDC-based interval method and has the following properties:

- Measures proportion of days covered within an observation window
- Accounts for refill gaps
- Caps adherence at 100%
- Allows carryover of oversupply into subsequent intervals
- Is calculated within a defined therapeutic episode

This approach was selected over traditional MPR because:

- MPR may exceed 100%
- CMA5 better handles overlapping prescriptions
- CMA5 is more appropriate for longitudinal interval-based adherence modeling

---

## 3) Observation Window

Adherence was calculated within:

- The time interval between the first and last prescription in a therapeutic episode
- Excluding coverage from the final prescription beyond the observation window
- Within a persistence-defined episode (180-day permissible gap)

Observation window length therefore varied across patients and therapeutic episodes.

---

## 4) Permissible Gap

A **180-day permissible gap** was used to define treatment continuity.

If the time between expected end of supply and next prescription exceeded 180 days:

- The therapeutic episode was considered discontinued
- A new episode could begin upon re-initiation

This threshold balances clinical realism and discontinuation sensitivity.

---

## 5) Threshold-Based Classification

Adherence was summarized:

- As a continuous CMA5 value (median, mean, CI)
- As a dichotomous variable using a ≥90% threshold

Therapeutic episodes with CMA5 ≥ 90% were classified as adherent.

---

## 6) Implementation

Adherence calculations were performed using:

- R / RStudio
- The `AdhereR` package
- Custom preprocessing for DDD-based exposure estimation

---

## 7) Interpretation Considerations

- Claims data reflect dispensing, not ingestion
- DDD assumptions may not perfectly reflect prescribed dosing
- Adherence was evaluated within persistent treatment only

Despite these limitations, CMA5 provides a robust standardized framework for real-world adherence estimation.
