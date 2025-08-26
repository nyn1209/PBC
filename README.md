# PBC
PBC survival analysis on 312 patients — Python pipeline for data cleaning, Kaplan–Meier &amp; Cox PH, K-Means risk stratification, and a clinician-friendly Tableau dashboard. 
<br> Languages: Python, SQL (optional) 
<br> Libs: pandas, numpy, lifelines, scikit-learn, matplotlib
<br> Viz: Tableau

**Interactive dashboard:**  
➡️ https://public.tableau.com/views/PrimaryBiliaryCirrhosis/Dashboard1?:language=en-GB&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

## Contents
- **`health.ipynb`** — the entire workflow (run top-to-bottom).
- `data/`
  - **`healthcare.csv`**
  - **`healthcare.xlsx`** – input Excel with 4 sheets 
- `requirements.txt`
---

## Goals
- Estimate survival and compare groups with **Kaplan–Meier** (+ log-rank).
- Quantify drivers of risk using **Cox proportional hazards**.
- Build a light **1-year risk** classifier (logistic).
- **Segment** patients with **K-Means** to surface high-risk profiles.
- Publish an **interactive Tableau dashboard** for non-technical users.

---

## Quickstart
```bash
# Create and activate env
python -m venv .venv && source .venv/bin/activate   # (Windows) .venv\Scripts\activate
python -m pip install --upgrade pip

# Install basics
pip install pandas numpy lifelines scikit-learn matplotlib seaborn jupyter

# Run
jupyter notebook  # open and run health.ipynb
> The notebook reads these sheets to **enforce schema**, **run quality checks**, and **document assumptions** before modeling.
```

## Quick load snippet
```python
import pandas as pd
path = "data/raw/healthcare.xlsx"

df      = pd.read_excel(path, sheet_name="Healthcare")
dict_df = pd.read_excel(path, sheet_name="Data Dictionary")
biz_df  = pd.read_excel(path, sheet_name="Business Understanding")
qa_df   = pd.read_excel(path, sheet_name="Data Quality Assessment")
```


# Install basics
pip install pandas numpy lifelines scikit-learn matplotlib seaborn jupyter

# Run
jupyter notebook  # open and run health.ipynb

