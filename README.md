# A/B Test Analysis: Cookie Cats Gate Placement

End-to-end experimentation and product-analytics project: did moving the first gate from level 30 to level 40 change player retention and engagement, and should the product team ship it?

## Dataset
Cookie Cats mobile game A/B test (Kaggle: "Mobile Games A/B Testing - Cookie Cats"). Columns: `userid`, `version` (`gate_30` control / `gate_40` treatment), `sum_gamerounds`, `retention_1`, `retention_7`. Download `cookie_cats.csv` and place it next to the notebook.

## What the notebook does
1. Data sanity checks (missing values, duplicates, outliers)
2. Sample Ratio Mismatch check (chi-square) to validate randomisation
3. SQL analysis in SQLite, including a window function (`NTILE`) for engagement quartiles
4. Two-proportion z-test with 95% confidence intervals for day-1 and day-7 retention
5. Multiple-testing correction (Bonferroni)
6. Skewed engagement data: winsorising, Mann-Whitney U test, bootstrap confidence intervals
7. Power analysis: required sample size and minimum detectable effect
8. Bayesian Beta-Binomial analysis: probability that the treatment is better
9. A/A simulation showing how peeking at results inflates false positives
10. Visual summary and a written business recommendation

## How to run
```
pip install pandas numpy scipy matplotlib jupyter
jupyter notebook ab_test_cookie_cats.ipynb
```

## Results
_Fill this section with YOUR own numbers after running the notebook (retention rates, differences, confidence intervals, p-values, recommendation)._

## Tech
Python, pandas, NumPy, SciPy, SQL (SQLite), Matplotlib
