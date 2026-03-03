# Real-World Evidence Analysis of Adherence and Persistence in Multiple Sclerosis Therapy

## Project Overview

This project presents a retrospective population-based pharmacoepidemiological study assessing adherence and persistence to immunomodulatory therapies (disease-modifying therapies, DMTs) for Multiple Sclerosis (MS).

The analysis is based on national outpatient prescription claims data (2011–2015) and applies advanced statistical modeling and survival analysis methods to evaluate real-world treatment patterns.

Full thesis publication (official university repository):
https://dk.um.si/IzpisGradiva.php?id=79334&lang=eng

⚠ Raw prescription data are not publicly available due to data protection and ethical restrictions.

---

## Research Objectives

- Assess medication adherence using CMA5 methodology  
- Estimate treatment persistence using survival analysis  
- Compare oral and injectable therapies  
- Evaluate fingolimod relative to other DMTs  
- Identify predictors of non-adherence and treatment discontinuation  

---

## Study Design

**Type:** Retrospective population-based cohort study  
**Data Source:** National prescription claims database (2011–2015)  
**Population:** Patients receiving ≥2 prescriptions for immunomodulatory therapy  

### Cohort Construction

- Identification of DMTs using ATC classification  
- Exclusion of hospital-only therapies  
- Separation into:
  - Therapy-naïve cohort  
  - Therapy-experienced cohort  
- Definition of therapeutic episodes using a 180-day permissible gap  
- Semi-naïve cohort constructed for time-to-event modeling  

---

## Adherence Modeling

Adherence was estimated using the **CMA5 methodology** (equivalent to PDC-based interval modeling).

Key characteristics:
- Adherence calculated within persistent treatment episodes  
- 180-day permissible gap definition  
- Threshold-based classification (≥90%)  
- Implemented in R using the *AdhereR* package  

---

## Persistence Analysis

Persistence was analyzed using time-to-event methods:

- Kaplan–Meier survival curves  
- Log-rank (Mantel–Cox) testing  
- Cox proportional hazards regression  

Events modeled:
- Treatment discontinuation  
- Treatment switching  

---

## Statistical Methods

- Descriptive statistics (mean, median, CI)
- Kruskal–Wallis and Wilcoxon tests
- Multivariate logistic regression
- Cox proportional hazards modeling

**Software used:**
- R / RStudio  
- IBM SPSS  

---

## Key Analytical Insights

- Oral therapies (teriflunomide, dimethyl fumarate) demonstrated higher adherence compared to injectable therapies.
- Fingolimod showed superior persistence rates.
- Prior therapy exposure and treatment switching significantly influenced adherence behavior.
- Real-world prescription data can effectively model drug utilization using survival and regression frameworks.

---

## Skills Demonstrated

- Real-World Data (RWD) analysis  
- Pharmacoepidemiology  
- Cohort design and exposure modeling  
- Survival analysis  
- Multivariate risk modeling  
- Statistical programming in R  
- Evidence-based interpretation  



