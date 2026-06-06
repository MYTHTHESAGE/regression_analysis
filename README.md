# Marketing ROI Analysis - Simple Linear Regression

A data science project that uses Python and statsmodels to identify the marketing channel with the greatest impact on Sales and quantifies that relationship through an OLS regression model.

---

## Regression Equation

Sales = 3.5615 * TV - 0.1325
(or y = 3.5615x - 0.1325)

*Units: $000s (e.g., a TV budget of $10,000 [TV = 10] predicts Sales of 35.4825 [$35,482.50]).*

---

## Project Structure

```text
├── regression_analysis.ipynb   # Main analysis notebook (ASCII-only, fully executed)
├── marketing_data.csv          # Raw dataset (TV, Radio, Social_Media, Sales)
└── README.md                   # This file
```

---

## Key Findings

| Metric | Value | Business Meaning |
|---|---|---|
| Best Predictor | TV (r = 0.9995) | TV advertising budget has an extremely strong linear correlation with Sales. |
| R-squared (R^2) | 0.998995 (99.90%) | TV budget explains 99.90% of the variance in Sales. |
| TV Coefficient (Slope) | 3.561514 | Each additional $1,000 spent on TV ads yields $3,561.51 in Sales. |
| Estimated Gross ROI | ~256% | Return of $3.56 for every $1.00 invested. |

---

## Detailed Statistical Results

### OLS Regression Coefficients
- **TV Coefficient (Slope)**: 3.561514
  - **p-value**: 0.0000 (highly statistically significant, p < 0.001)
  - **95% Confidence Interval**: [3.558229, 3.564799]
- **Intercept (c)**: -0.132493
  - **p-value**: 0.1879 (p > 0.05, not statistically significant; baseline sales are statistically indistinguishable from zero)
  - **95% Confidence Interval**: [-0.329727, 0.064742]
- **Model F-statistic**: 4,516,779.38
  - **Prob (F-statistic)**: 0.0000 (overall model is highly significant, p < 0.001)

### Residual Assumption Tests
- **Normality (Jarque-Bera Test)**:
  - **JB Statistic**: 0.031087
  - **p-value**: 0.9846
  - **Verdict**: Fail to reject null hypothesis (p > 0.05). Residuals are normally distributed.
- **Homoscedasticity (Breusch-Pagan Test)**:
  - **LM Statistic**: 0.000059
  - **p-value**: 0.9939
  - **Verdict**: Fail to reject null hypothesis (p > 0.05). Residuals exhibit constant variance (homoscedasticity).

---

## Environment Setup

### Install Dependencies
```bash
pip install pandas numpy matplotlib seaborn statsmodels scipy jupyter
```

### Run the Notebook
```bash
jupyter notebook regression_analysis.ipynb
```

---

## Outputs

| File | Description |
|---|---|
| `distributions.png` | Histogram grid of TV, Radio, Social Media, and Sales |
| `scatter_plots.png` | Scatter plots with OLS fit lines for each channel |
| `correlation_heatmap.png` | Pearson correlation matrix heatmap |
| `regression_line.png` | TV spend vs Sales regression line plot |
| `diagnostic_plots.png` | Residual plots (Normality & Homoscedasticity) |
| `roi_comparison.png` | Bar chart comparing correlations with Sales |

---

## Author
Samuel Oladipupo
