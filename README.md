# INST414---Data-Science-Semester-Project

NYC Job Postings: Career Level & Salary Analysis
An observational data analysis exploring whether career level predicts salary in NYC government job postings — and whether that relationship holds equally across industries.
Overview
Using the NYC Job Postings dataset from Data.gov, this project investigates a deceptively simple question: does climbing the career ladder actually pay off, and does the answer change depending on your field?
The short answer is yes — but with important nuance. While higher career levels are broadly associated with higher salaries (Spearman ρ = 0.62), the strength of that relationship varies significantly across industries. Engineering and Legal show the tightest link between seniority and pay, while Technology and Public Safety show a noticeably weaker one — suggesting that in some fields, specialized skills matter more than title.
Key Findings

Career level and salary are strongly correlated overall (ρ = 0.62, p < 0.001, n = 1,957)
The relationship is strongest in Engineering & Planning (ρ = 0.75) and Community Services (ρ = 0.74)
The relationship is weakest in Technology & Data (ρ = 0.44) and Public Safety (ρ = 0.34)
The largest salary gap between Entry-Level and Manager exists in Legal (+$112,816 / +214%)
All 11 industries analyzed showed statistically significant correlations

Data
Source: NYC Job Postings — Data.gov
Filters applied:

Annual salary postings only (1,957 of 2,371 total)
Salary midpoint between $10,000 and $400,000
Career levels: Student, Entry-Level, Experienced (non-manager), Manager, Executive

Figures
FigureDescriptionFig 1Box plot of salary distributions by career levelFig 2Spearman ρ by industry — how strongly does level predict pay?Fig 3Heatmap of median salary across career level × industry combinationsFig 4Dollar and percentage salary gap between Entry-Level and Manager, by industry
Methods

Spearman rank correlation — used because career level is ordinal, not continuous
Kruskal-Wallis test — confirms salary distributions differ significantly across career levels
Salary midpoint — computed as the average of the posted salary range floor and ceiling
Industry categories simplified from verbose NYC job category labels using keyword mapping

Requirements
pandas
numpy
matplotlib
seaborn
scipy
Usage

Download Jobs_NYC_Postings.csv from Data.gov
Place it in the same directory as the notebook
Run nyc_jobs_analysis.ipynb top to bottom

Context
This project was completed as a semester capstone for a Data Science course, structured as a data-driven op-ed. The analysis is fully observational — no variables were manipulated, and findings reflect patterns in existing city hiring data.
