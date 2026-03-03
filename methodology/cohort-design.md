# Cohort Design (Prescription Claims, 2011–2015)

This document describes how the study cohort and analytical sub-cohorts were constructed from national outpatient prescription claims data for immunomodulatory therapies (DMTs) used in Multiple Sclerosis (MS).

> Note: Raw patient-level data are not included in this repository due to data protection and ethical restrictions.

---

## 1) Data source and unit of analysis

**Data source:** National outpatient prescription claims database (2011–2015).  
Each record represents an issued prescription and includes:
- patient demographics (anonymized),
- prescriber information,
- issue date,
- drug information (ATC code, product code, quantity).

**Primary unit of analysis:**  
- **Prescription-level records** are used to build **patient-level therapeutic episodes**.
- Most downstream analyses are performed at the **therapeutic episode** level.

---

## 2) Identification of MS DMTs

Eligible MS disease-modifying therapies (DMTs) were identified using ATC codes.  
Therapies were grouped into three exposure categories:

1. **Injectable DMTs**  
   - interferon beta-1a, interferon beta-1b  
   - glatiramer acetate

2. **Other oral DMTs**  
   - dimethyl fumarate (DMF)  
   - teriflunomide (TERI)

3. **Fingolimod**  
   - analyzed as a separate group due to its distinct clinical positioning

**Excluded therapies:**
- Therapies with insufficient sample size in the observed period (e.g., very low counts).
- Therapies that transitioned to hospital-only dispensing (limited continuity in outpatient claims).

---

## 3) Exposure duration estimation (DDD-based)

For each prescription, exposure duration was estimated using the Defined Daily Dose (DDD) obtained from the national drug database.

For each issued prescription:
- the dispensed product was identified via product code,
- the corresponding DDD per package was retrieved,
- the total number of DDDs dispensed was calculated,
- the number of days covered was estimated based on DDD assumptions.

This approach allowed estimation of treatment coverage duration per prescription in the absence of directly recorded “days supply” information.

DDD-based estimation reflects standardized dosing assumptions and may differ from individualized prescribed dosing.
---

## 4) Inclusion criteria

To ensure that adherence metrics based on refill timing could be calculated reliably:

- patients must have **≥ 2 prescriptions** for an eligible DMT during the study window.

Rationale:
- a single prescription does not allow estimation of refill gaps and longitudinal medication availability.

---

## 5) Index date definition

For each patient, the **index date** is defined as:
- the date of the **first observed prescription** for an eligible DMT within 2011–2015.

This index date is used to:
- characterize treatment initiation within the observed window,
- classify patients into therapy-naïve vs therapy-experienced cohorts (see below),
- anchor time-to-event analyses when appropriate.

---

## 6) Therapy-naïve vs therapy-experienced cohorts

Because claims data are bounded by the observation window, prior treatment history may be partially unobserved.

Two main patient cohorts were defined:

### A) Therapy-experienced cohort
Patients whose first observed DMT prescription may reflect ongoing treatment that started before 2011.

Operational definition (conceptual):
- patients for whom there is no sufficient pre-index “clean period” inside the database window to support a naïve classification.

### B) Therapy-naïve cohort
Patients were classified as therapy-naïve if they had **no DMT prescriptions** during a **lookback (washout) period** prior to the index date.

**Washout period:** 180 days prior to index date.

Rationale:
- reduces the likelihood that the first observed prescription is a continuation of earlier unobserved therapy.

---

## 7) Therapeutic episodes and permissible gap

Analyses were performed within **therapeutic episodes**, defined as continuous treatment periods for a given therapy.

A therapeutic episode starts at:
- the first prescription of a therapy in that episode,

and ends when:
- there is a **gap > 180 days** without medication coverage (i.e., beyond the permissible gap), or
- the patient switches to another DMT (depending on analysis definition).

**Permissible gap:** 180 days.

Rationale:
- allows for clinically realistic delays and administrative gaps while still distinguishing true discontinuation.

---

## 8) Semi-naïve cohort for time-to-event analyses

For persistence (time-to-event) analyses, a **semi-naïve cohort** was constructed to ensure more reliable estimation of treatment start times.

This cohort includes:
- all therapy-naïve patients, and
- a subset of therapy-experienced patients **entering observation at the start of a new therapy** after a recorded switch (i.e., where a clear initiation point is observed).

Rationale:
- improves validity of time-to-event modeling by avoiding episodes with unknown true start dates.

---

## 9) Outputs of cohort construction

The cohort construction pipeline produces:
- patient-level cohort labels (naïve / experienced / semi-naïve),
- therapy grouping labels (injectable / other oral / fingolimod),
- therapeutic episode boundaries,
- DDD-based exposure duration estimates per prescription,
- derived refill gaps needed for adherence and persistence modeling.

---

## 10) Limitations (cohort-level)

- Claims indicate dispensing, not ingestion (adherence is inferred).
- DDD-based duration is an approximation and may differ from individualized dosing.
- Observation window truncation can misclassify some experienced patients as naïve (mitigated via 180-day washout).
- Hospital-only dispensing is not fully captured in outpatient claims.
