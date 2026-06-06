# Marketing ROI Analysis — Simple Linear Regression

A data science project that uses Python and statsmodels to identify the marketing
channel with the greatest impact on Sales and quantifies that relationship through
an OLS regression model.

---

## Project Structure

```
├── regression_analysis.ipynb   # Main analysis notebook (all cells executed)
├── marketing_data.csv          # Raw dataset (TV, Radio, Social_Media, Sales)
└── README.md                   # This file
```

## Dataset

| Column | Description | Units |
|---|---|---|
| `TV` | TV advertising budget | $000s |
| `Radio` | Radio advertising budget | $000s |
| `Social_Media` | Social media advertising budget | $000s |
| `Sales` | Revenue generated | $000s |

4,572 rows · 4 columns · minimal missing values (< 0.3 % per column, dropped).

---

## Key Findings

| Metric | Value |
|---|---|
| Best predictor | TV (r = 0.9995) |
| R² | ≈ 0.9990 |
| TV coefficient | ≈ 3.56 |
| Estimated ROI | ~256 % per $1,000 invested |

**Recommendation:** Prioritise TV spend. Every additional $1,000 allocated to TV
advertising is associated with approximately $3,560 in incremental Sales revenue.

---

## Environment Setup

### Prerequisites
- Python 3.8 or higher
- pip

### Install dependencies

```bash
pip install pandas numpy matplotlib seaborn statsmodels scipy
```

Or install from a requirements file:

```bash
pip install -r requirements.txt
```

**requirements.txt**
```
pandas>=1.5
numpy>=1.23
matplotlib>=3.6
seaborn>=0.12
statsmodels>=0.13
scipy>=1.9
jupyter>=1.0
```

### Run the notebook

```bash
jupyter notebook regression_analysis.ipynb
```

Run all cells with **Kernel → Restart & Run All** to reproduce results.

---

## Analysis Steps

1. **Load & explore** the dataset; audit and handle missing values
2. **EDA** — distributions, scatter plots, and correlation heat-map
3. **Variable selection** — identify the channel most correlated with Sales
4. **OLS regression** — fit model with statsmodels, print full summary
5. **Diagnostic plots** — Residuals vs Fitted, Q-Q, Scale-Location, histogram
6. **Statistical tests** — Jarque-Bera (normality), Breusch-Pagan (homoscedasticity)
7. **Business interpretation** — translate coefficients to ROI language
8. **Recommendation** — data-driven budget allocation advice

---

## Outputs

| File | Description |
|---|---|
| `distributions.png` | Histogram grid of all four variables |
| `scatter_plots.png` | Each channel vs Sales with OLS trendline |
| `correlation_heatmap.png` | Pearson correlation matrix |
| `regression_line.png` | TV vs Sales with fitted regression line |
| `diagnostic_plots.png` | Four-panel assumption diagnostics |
| `roi_comparison.png` | Bar chart of channel correlations with Sales |

---

## Author

Samuel Oladipupo
