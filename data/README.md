# Data

Raw data is **not** committed. `src/data.py` downloads and caches it here on first use.

## Main dataset — Default of Credit Card Clients (Taiwan, 2005)

- Source: UCI Machine Learning Repository, dataset id 350
  https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients
- License: CC BY 4.0 (per the UCI page)
- Content (per UCI/Kaggle descriptions): 30,000 credit card clients, 23 explanatory variables
  (credit limit, sex, education, marital status, age, 6 months of repayment status, bill amounts and
  payment amounts) and a binary target "default payment next month". Period: April–September 2005.
- Reference: Yeh, I-C. & Lien, C-H. (2009). *The comparisons of data mining techniques for the predictive
  accuracy of probability of default of credit card clients.* Expert Systems with Applications, 36(2), 2473–2480.
- Access: `ucimlrepo.fetch_ucirepo(id=350)` (automatic), or download manually from the UCI page and save as
  `data/taiwan_default.csv`. A Kaggle mirror also exists
  (https://www.kaggle.com/datasets/uciml/default-of-credit-card-clients-dataset); `src/data.py` also accepts
  its column names.

## Secondary dataset (robustness / recourse) — Statlog German Credit

- Source: https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data (CC BY 4.0), 1,000 applicants,
  20 attributes, good/bad credit risk. Cite: Hofmann, H. (1994), DOI 10.24432/C5NC77.
- Access: `ucimlrepo.fetch_ucirepo(id=144)`.
- The UCI page states that this dataset **requires a cost matrix** (check the exact values on the page).
- Known issue: Grömping (2019) documents coding errors in the original file and provides a corrected version,
  "South German Credit": https://archive.ics.uci.edu/dataset/573/south+german+credit+update
  (`fetch_ucirepo(id=573)`). Consider using it and say so in the report.

## Other datasets you could use instead (not used by the default code)

| Dataset | Access | Note |
|---|---|---|
| FICO HELOC (Explainable ML Challenge, 2018) | Request form at https://community.fico.com/s/explainable-machine-learning-challenge | ~10k HELOC applications; built for XAI; requires accepting terms |
| Home Credit Default Risk | https://www.kaggle.com/competitions/home-credit-default-risk/data | Multi-table, large; Kaggle login + rules acceptance |
| Give Me Some Credit (2011) | https://www.kaggle.com/c/GiveMeSomeCredit | ~150k borrowers, target `SeriousDlqin2yrs`; Kaggle login |
