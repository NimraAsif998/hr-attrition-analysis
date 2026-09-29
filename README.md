# HR Employee Attrition Analysis

Exploratory data analysis and feature engineering on an HR workforce dataset, to find where employee attrition is concentrated, how employee experience relates to it, and who is leaving.

**Team:** [The Data Miners], Nimra Asif, Ajwa Hashmi

> No machine learning or predictive modelling is used. All findings rest on descriptive statistics, hypothesis tests and visualisations, and they describe **associations, not causes**.

## Dataset

- File: `WA_Fn-UseC_-HR-Employee-Attrition.csv`
- 1,470 employees, 35 variables
- A public sample HR dataset (not data from a real company)
- Overall attrition: **237 leavers (16.1%)**

## Project structure

| File | Description |
|---|---|
| `HR_Attrition_Analysis_Report.ipynb` | Full analysis: code, tables, charts and written interpretation |
| `HR_Attrition_Analysis_Report.docx` | Written report with findings and recommendations |
| `WA_Fn-UseC_-HR-Employee-Attrition.csv` | Dataset used in the notebook |

## What the analysis covers

**Section A: Exploratory data analysis**
- **Q1, where is attrition?** Department, job role and overtime against attrition, with hot-spot analysis.
- **Q2, work experience:** job satisfaction, environment satisfaction, job involvement and work-life balance against attrition.
- **Q3, who is leaving?** Leavers vs stayers on age, income, total working years, tenure and time in current role.

**Section B: Feature engineering**
- **Q4, `CareerStage`:** a career-stage feature built from total working years, cross-checked against age and company tenure.
- **Q5, `EmployeeExperienceScore`:** a 0-100 score combining four survey measures, with bands and a red-flag count.

## Key findings

- **Overtime** is the sharpest divider: 30.5% attrition vs 10.4% without overtime. Overtime workers are 28% of staff but 54% of leavers.
- **Sales Representatives (39.8%)** and **Laboratory Technicians (23.9%)** are the highest-attrition roles. Laboratory Technician attrition is mostly an overtime effect; Sales Representative attrition is high even without overtime.
- **Job Involvement** is the most relevant experience measure: 33.7% attrition at the lowest rating vs 9.0% at the highest.
- Leavers are younger, lower paid and shorter-tenured. About **43% of leavers** leave within two years, and Job Level 1 holds 37% of staff but 60% of leavers.
- **CareerStage:** attrition falls from 43.9% (0-2 years of experience) to 7.7% (21+ years).
- **EmployeeExperienceScore:** the "Poor" band has 40.0% attrition vs 5.4% for "Excellent"; poor experience combined with overtime reaches 53%.

## Methods

- Attrition rates with 95% Wilson confidence intervals
- Chi-square tests and Cramér's V (effect size)
- Mann-Whitney U tests, Cohen's d, Spearman correlation
- Relative risk and "excess leavers" to compare groups by volume as well as rate
- Stratified comparisons (for example income within job level) instead of modelling

## How to run

1. Clone or download this repository and keep the CSV in the same folder as the notebook.
2. Install the requirements:
   ```bash
   pip install pandas numpy matplotlib seaborn scipy jupyter
   ```
3. Open the notebook and run all cells:
   ```bash
   jupyter notebook HR_Attrition_Analysis_Report.ipynb
   ```

The notebook already contains its outputs, so it can also be read on GitHub without running anything.

## Limitations

- The data are a single snapshot, so causation cannot be shown.
- Age, experience, tenure, pay and job level overlap strongly.
- Some segments are small (for example Sales Representatives on overtime, n = 24) and have wide confidence intervals.
- The experience score uses equal weights on four self-reported ordinal items; a sensitivity check shows results do not depend on the weighting.

## Tools

Python, Pandas, NumPy, Matplotlib, Seaborn, ydata-profiling andJupyter Notebook
