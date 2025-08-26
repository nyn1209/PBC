# PBC
PBC survival analysis on 312 patients — Python pipeline for data cleaning, Kaplan–Meier &amp; Cox PH, K-Means risk stratification, and a clinician-friendly Tableau dashboard.
Languages: Python, SQL (optional) · Libs: pandas, numpy, lifelines, scikit-learn, matplotlib
Viz: Tableau
# 1. Project Goals
- Estimate survival and compare groups (treatment/stage) with Kaplan–Meier.
- Quantify hazard and key drivers with Cox proportional hazards (Cox PH).
- Build a simple risk score/logistic model for 1-year event.
- Segment patients by lab indicators using K-Means to surface high-risk profiles.
- Ship an interactive dashboard and a concise report that non-technical users can act on.

Key takeaways from my run: disease stage dominated hazard; the Cox model reached strong discriminatory power (ROC-AUC ≈ 0.82 on hold-out), and K-Means surfaced a high-bilirubin/low-albumin cluster aligning with higher risk.

# 2. Repository Structure
PBC\\
├─ data/
│  ├─ raw/           # place original CSV here (not tracked)
│  └─ processed/     # cleaned datasets saved here
├─ notebooks/
│  ├─ 01_explore_and_clean.ipynb
│  ├─ 02_kaplan_meier_coxph.ipynb
│  ├─ 03_logistic_risk_and_kmeans.ipynb
│  └─ 04_dashboard_prep.ipynb
├─ src/
│  ├─ data_prep.py        # cleaning, imputation, feature engineering
│  ├─ survival_models.py  # KM, CoxPH helpers
│  ├─ risk_models.py      # logistic, metrics
│  └─ utils.py
├─ dashboard/
│  └─ tableau_packaged.twbx  # or .pbix if using Power BI
├─ reports/
│  ├─ executive_summary.pdf
│  └─ uat_checklist.pdf
├─ requirements.txt
└─ README.md
