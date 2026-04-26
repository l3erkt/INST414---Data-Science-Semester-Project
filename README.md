# NYC Job Postings: Career Level & Salary Analysis

> *Does climbing the career ladder actually pay off in New York City government jobs — and does the answer change depending on your field?*

---

## Overview

This project is an observational data analysis of NYC government job postings, investigating the relationship between **career level** and **salary** — and whether that relationship holds equally across industries.

The short answer: yes, seniority predicts pay. But the *strength* of that prediction varies significantly by field. Engineering and Legal show the tightest link between title and salary, while Technology and Public Safety show a notably weaker one — suggesting that in some sectors, specialized skills matter more than career level alone.

This analysis was completed as a semester capstone project for a Data Science course, structured as a data-driven op-ed.

---

## Key Findings

- Career level and salary are **strongly correlated overall** (Spearman ρ = 0.62, p < 0.001, n = 1,957)
- The relationship is **strongest** in Engineering & Planning (ρ = 0.75) and Community Services (ρ = 0.74)
- The relationship is **weakest** in Technology & Data (ρ = 0.44) and Public Safety (ρ = 0.34)
- The largest salary gap between Entry-Level and Manager is in **Legal** — a +$112,816 premium (+214%)
- All 11 industries analyzed returned statistically significant correlations

---

## Figures

| # | Figure | Description |
|---|--------|-------------|
| 1 | `fig1_salary_by_career_level.png` | Box plot of salary distributions across all five career levels |
| 2 | `fig2_spearman_by_industry.png` | Spearman ρ by industry — how strongly does career level predict pay? |
| 3 | `fig3_heatmap_salary_level_industry.png` | Heatmap of median salaries across career level × industry combinations |
| 4 | `fig4_salary_gap_entry_vs_manager.png` | Dollar and percentage salary gap between Entry-Level and Manager, by industry |

---

## Data

**Source:** [NYC Jobs — NYC Open Data / Data.gov](https://data.cityofnewyork.us/City-Government/NYC-Jobs/kpav-sd4t)

**Filters applied:**
- Annual salary postings only (1,957 of 2,371 total records)
- Salary midpoint between $10,000 and $400,000 (removes placeholders and extreme outliers)
- Career levels included: Student, Entry-Level, Experienced (non-manager), Manager, Executive

**Industry groupings:** The original NYC job category labels are verbose and often list multiple categories per posting. A keyword-matching function maps them into 11 clean industry groups: Engineering & Planning, Health, Legal, Finance & Accounting, Technology & Data, Social Services, Public Safety, Admin & HR, Policy & Research, Community Services, Building & Maintenance.

---

## Methods

| Method | Purpose |
|--------|---------|
| **Salary midpoint** | Computed as the average of the posted salary floor and ceiling, giving one representative number per posting |
| **Spearman rank correlation** | Used because Career Level is ordinal (ranked, not evenly spaced) — Spearman is more appropriate than Pearson here |
| **Kruskal-Wallis test** | Non-parametric test confirming salary distributions differ significantly across career levels |
| **Industry-level Spearman ρ** | The core of the analysis — computes the correlation separately within each industry to test whether the relationship is uniform |

---

## Project Structure

```
├── nyc_jobs_analysis.ipynb          # Full replication notebook
├── Jobs_NYC_Postings.csv            # Source data (download separately)
├── fig1_salary_by_career_level.png
├── fig2_spearman_by_industry.png
├── fig3_heatmap_salary_level_industry.png
├── fig4_salary_gap_entry_vs_manager.png
└── README.md
```

---

## Setup & Usage

**Requirements**

```
pandas
numpy
matplotlib
seaborn
scipy
```

Install with:

```bash
pip install pandas numpy matplotlib seaborn scipy
```

**Running the analysis**

1. Download `Jobs_NYC_Postings.csv` from the NYC Open Data link above
2. Place it in the same directory as the notebook
3. Open and run `nyc_jobs_analysis.ipynb` top to bottom

All four figures will be saved as PNG files in the working directory.

---

## Research Design

This is an **observational study** — no variables were manipulated. The analysis reflects patterns in existing NYC city hiring data as posted. Findings describe correlations, not causal relationships: a higher career level being associated with higher pay does not mean that promotions *cause* salary increases in isolation from other factors (experience, tenure, agency, etc.).

---
