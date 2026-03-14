# OECD FDI Income Analysis by Economic Activity

> **Status: 🔄 Work in Progress** — Pre-analysis complete; EDA and modeling in progress.

This project conducts a comprehensive statistical analysis of **Foreign Direct Investment (FDI) income flows** across OECD member countries, broken down by economic sector. The goal is to uncover structural patterns in global investment activity and build predictive models for investment behavior.

**Data Source:** [OECD Data Explorer — FDI Income by Industry (BMD4)](https://data-explorer.oecd.org/vis?lc=en&df[ds]=dsDisseminateFinalDMZ&df[id]=DSD_FDI%40DF_FDI_INC_IND&df[ag]=OECD.DAF.INV&dq=.T_D4P_F.USD_EXC......W.IMC._T%2BA_B%2BC%2BC10T12%2BC13T18X15%2BC19T22%2BC24T28X27%2BC29_30%2BC15_23_27_31T33%2BD%2BE%2BF%2BGTU%2BG%2BH%2BI%2BJ%2BK%2BL%2BM%2BN%2BO_T_U%2BP%2BQ%2BR%2BS%2B_X.A.&lom=LASTNPERIODS&lo=2&to[TIME_PERIOD]=false)

---

## Dataset Overview

| Property | Value |
|---|---|
| Source | OECD (Organisation for Economic Co-operation and Development) |
| Standard | BMD4 (Benchmark Definition of FDI, 4th Edition) |
| Observations | 10,344 |
| Variables | 24 (18 analytical, 6 structural/dropped) |
| Coverage | 38 OECD member countries |
| Sectors | 18+ economic activity categories (ISIC Rev. 4) |
| Frequency | Annual |
| Unit | USD millions |

---

## Research Questions

1. Which countries and sectors attract the largest FDI income flows, and how has this changed over time?
2. What structural relationships exist between investment type, sector, and country characteristics?
3. Can FDI income reliability (observation status) be predicted from available features?
4. What investment patterns and country clusters emerge from the data?

---

## Analysis Workflow

### Phase 1 — Pre-Analysis & Data Understanding ✅
- Variable taxonomy: defined types, roles, and quality flags for all 24 variables
- Identified 6 structural/redundant variables for exclusion (STRUCTURE, ACTION, CONF_STATUS, etc.)
- Flagged OBS_STATUS as a key data quality indicator for modeling
- Designed full analysis and modeling roadmap

### Phase 2 — Data Cleaning & Preparation 🔄
- SQL-based preprocessing: filtering, deduplication, variable selection
- Handling missing values and inconsistent encodings
- Feature engineering: country groupings, sector aggregations, time-based features

### Phase 3 — Exploratory Data Analysis (EDA) 🔄
- Descriptive statistics for all analytical variables
- Normality testing (Shapiro-Wilk, Q-Q plots)
- Distribution visualization: histograms, box plots, violin plots
- Dependency analysis:
  - Categorical × Categorical → Chi-square test
  - Categorical × Numerical → ANOVA
  - Numerical × Numerical → Pearson / Spearman correlation
- Hypothesis testing based on findings

### Phase 4 — Statistical Modeling ⏳
| Method | Target |
|---|---|
| **Regression** | Predict FDI income volume (OBS_VALUE) |
| **Classification** | Predict observation reliability (OBS_STATUS) |
| **Clustering** | Identify country/sector investment profiles |
| **Time Series** | Model FDI trends and forecast future flows |
| **Panel Data** | Analyze cross-country, cross-time investment patterns |

### Phase 5 — Reporting & Visualization ⏳
- Interactive Power BI dashboard
- Key findings report

---

## Repository Structure

```
OECD-FDI-Income-Analysis/
│
├── data/
│   └── raw/                  # Original OECD dataset (CSV)
│
├── reports/                  # Pre-analysis report and findings
│
├── requirements.txt          # Python dependencies
├── LICENSE
└── README.md
```

> Notebooks will be added as each analysis phase is completed.

---

## Technologies

| Tool | Purpose |
|---|---|
| Python (Jupyter Notebook) | EDA, statistical testing, modeling |
| SQL | Data preprocessing and querying |
| Power BI | Dashboard and reporting |
| Pandas, NumPy | Data manipulation |
| SciPy, Statsmodels | Statistical tests and panel modeling |
| Scikit-learn | Classification and clustering |
| Matplotlib, Seaborn | Visualization |

---

## Author

**Yusuf Onur Şimşek**
- GitHub: [@yusufosimsek](https://github.com/yusufosimsek)
- LinkedIn: [yusuf-onur-şimşek](https://linkedin.com/in/yusuf-onur-simsek-702241224)
