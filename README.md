# Recurrence-Free Survival: Node-Positive Breast Cancer

Survival Analysis • Cox Regression • Time-Dependent Modelling • Multiple Imputation  
**MSc Coursework Project — Advanced Statistics**

---

## 📘 Project Summary

Breast cancer recurrence risk estimation is a core clinical problem — informing treatment decisions, post-operative surveillance, and patient counselling. This project develops a **survival prediction framework** to model recurrence-free survival in women with node-positive primary breast cancer using **time-to-event modelling**.

The work includes end-to-end statistical development:

✔ Data inspection & missingness diagnostics  
✔ Multiple imputation under MAR using `mice`  
✔ Survival characterisation via Kaplan-Meier curves  
✔ Cox proportional hazards modelling  
✔ PH-assumption testing & time-dependent extensions  
✔ Model validation using C-index & time-ROC

📄 Full Report: **`/reports/2331122_Report.pdf`**

---

## 🎯 Research Motivation

Breast cancer prognosis depends on tumour biology, hormone receptors, patient age, treatment received, and pathophysiological progression. However — missing clinical data and non-proportional hazards can degrade prediction accuracy.

This project aims to:

> Build a reproducible prognostic survival model capable of estimating recurrence risk while accounting for missingness, covariate interactions, and proportional hazard violations.

---

## 🔬 Methodological Framework

| Stage                      | Decisions & Rationale                                                                       |
| -------------------------- | ------------------------------------------------------------------------------------------- |
| **Data Quality Review**    | Variable completeness inspection, MCAR/MAR evaluation, missingness patterns                 |
| **Imputation Strategy**    | Multiple Imputation (m=5) chosen to preserve variance rather than listwise deletion         |
| **Feature Screening**      | Kaplan–Meier survival curves + log-rank tests to compare hazard distributions across groups |
| **Model Development**      | Cox PH baseline → Schoenfeld diagnostics → time-dependency for violated predictors          |
| **Model Refinement**       | Hazard ratios, confidence intervals, interaction terms validated iteratively                |
| **Performance Assessment** | C-Index & time-dependent ROC to quantify predictive discrimination                          |

This workflow reflects **clinical research standards** and **computational reproducibility**.

---

## 📊 Key Outputs & Interpretation

| Indicator             | Finding                                      |
| --------------------- | -------------------------------------------- |
| Hormonal therapy      | ↓ recurrence hazard ~42% (protective effect) |
| Tumour grade          | Strongest risk amplification driver          |
| Positive lymph nodes  | Hazard ↑ with node count — dose dependent    |
| Progesterone receptor | Small yet significant protective association |
| Model performance     | **C-Index ≈ 0.67**, AUC≈69% @ 1-year         |

These results align with clinical literature and offer a **moderately predictive, interpretable survival model** suitable for future extension.

---

## 📁 Repository Overview

```

📦 Prognostic-Survival-Modelling-in-Breast-Cancer
│
├── README.md
├── .gitignore
├── renv.lock
│
├── analysis/                   → RMarkdown analysis file and reproducible code  
│   ├── 2331122_Report.Rmd 
│   ├── 2331122.Rmd
│   └── Summative Assessment.Rproj
│
├── data/                       → raw dataset
│   └── assessment.rds
│
├── outputs/                    → generated plots, tables
│   ├── figures/
│   └── tables/
│
├── reports/                    → final report, supporting material 
│   ├── 2331122_Report.pdf
│   ├── 2331122_Report.docx
│   ├── references.bib
│   └── Summative Assessment.pdf
│
└── renv/                       → reproducible R environment
```
---

## Reproducibility & Execution

### 🔽 Install dependencies

```r
install.packages(c(
  "tidyverse","survival","survminer","mice","VIM",
  "naniar","timeROC","gtsummary"
))
```

If using environment lockfile:

```r
renv::restore()
```

### ▶ Run analysis

```r
rmarkdown::render("analysis/2331122_Report.Rmd")
```

📂 All figures + summaries will appear in `/outputs/`
📄 PDF report version located in `/reports/`

---

## 🔥 Future Development Directions

* External dataset validation
* Parametric survival models (Weibull, exponential, log-normal)
* ML extensions: Random Survival Forest / XGBoost-Cox
* Bayesian survival modelling + posterior uncertainty
* Clinical decision-support prototype deployment

This project would scale naturally into a **publishable research model** or **ML-enhanced prognostic pipeline**.

---

## 📍 Academic Acknowledgement

> This work was developed and submitted as part of the **MSc Advanced Statistics Coursework Project**,
> focusing on the construction, evaluation, and clinical interpretation of survival models.

You are encouraged to reference or extend the model.

---

## 🧩 Author

**Ruchitha Meenakshi**

