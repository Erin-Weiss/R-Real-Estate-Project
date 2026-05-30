# U.S. Real Estate Market Analysis Using Multiple Linear Regression in R

**Author:** Erin Weiss  
[Portfolio](https://erin-weiss.github.io/index.html) | [LinkedIn](https://www.linkedin.com/in/erinweiss3/) | [GitHub](https://github.com/Erin-Weiss)

[View the Full Interactive Report](https://erin-weiss.github.io/articles/Real-Estate.html) | [Live GitHub Page](https://erin-weiss.github.io/R-Real-Estate-Project/)

---

## Objective

Analyze U.S. real estate trends from 2016–2022 using state-level data from Realtor.com's Research Data Center. The goal was to identify how region, season, square footage, market activity, and time influence median housing prices, and to build a multiple linear regression model that explains variation in listing prices across states and over time.

---

## Business Relevance

Understanding which factors drive housing prices, and by how much, has direct value across several industries. Real estate investment firms and REITs use models like this to identify undervalued markets, time acquisitions, and allocate capital to regions with the strongest price trajectories. Mortgage lenders rely on accurate price drivers to assess collateral value, calibrate loan-to-value ratios, and flag markets where prices may be overextended relative to fundamentals. For developers and brokers, the finding that seasonal timing and days-on-market significantly predict price translates into actionable guidance on when to list properties or launch new inventory. A model that explains 95% of price variance provides a strong analytical foundation for any of these decision-making pipelines, reducing reliance on intuition and supporting data-driven strategy at scale.

---

## Dataset

| Property | Detail |
|----------|--------|
| Source | [Realtor.com Research Data Center](https://www.realtor.com/research/data/) |
| File | RDC_Inventory_Core_Metrics_State_History.csv |
| Granularity | State-level, monthly observations |
| Time Period | 2016–2022 |
| Key Features | Median Listing Price, Active Listings, New Listings, Pending Listings, Median Days on Market, Median Square Feet, Region, Season, State, Year |

---

## Methodology

1. **Data Ingestion & Cleaning** — Read the Realtor.com CSV, converted date fields, recoded categorical variables, and adjusted weekly new listing counts to monthly units for consistency.
2. **Exploratory Data Analysis** — Examined price distributions by region, season, month, year, and state using box plots, bar charts, histograms, and time-series line plots.
3. **Correlation Analysis** — Visualized bivariate relationships between price and continuous predictors (pending listings, days on market, square footage) using scatterplots.
4. **Regression Modeling** — Fit a multiple linear regression with nine predictor variables and applied backward elimination using p-values, removing insignificant predictors while monitoring Adjusted R².
5. **Hypothesis Testing** — Evaluated nine formal hypotheses on whether each predictor significantly influences median listing price.

---

## Results

| Predictor | Significant? | Direction |
|-----------|-------------|-----------|
| Region | Yes (p < .001) | West and Northeast highest |
| Season | Yes (p < .001) | Summer prices highest |
| Pending Listings | Yes (p < 2e-16) | Positive |
| Days on Market | Yes (p < 2e-16) | Negative (faster markets = higher prices) |
| Year | Yes (p < .001) | Prices rising since 2016 |
| State | Yes (p < .001) | Significant variation across states |
| Median Square Feet | Yes (p < 2e-16) | Positive |
| Active Listings | No (p = 0.43) | Removed during elimination |
| New Listings (Monthly) | No (p = 0.15) | Removed during elimination |

**Final Model:** Adjusted R² = **0.9542**, indicating the model explains approximately 95% of the variance in median listing price. The overall F-statistic was significant (p < 2.2e-16).

**Key Findings:**

- Median listing prices have risen consistently each year since 2016.
- The West and Northeast regions had the highest housing prices.
- Homes in summer months and in faster-moving markets (fewer days on market) tend to be more expensive.
- Pending listings and square footage were strong positive predictors of price.
- Active and new listing counts showed no statistically significant impact on price after controlling for other variables.

---

## Tech Stack

| Category | Tool |
|----------|------|
| Language | R |
| Core Libraries | `tidyverse`, `ggplot2`, `lubridate`, `ggpubr` |
| Data Summaries | `summarytools`, `DT`, `descr` |
| Additional | `HydroTSM`, `SemTools` |
| Reporting | Quarto (`.qmd`) rendered to HTML |

---

## Repository Structure

```
R-Real-Estate-Project/
├── data/
│   └── RDC_Inventory_Core_Metrics_State_History.csv   # Source dataset
├── real-estate-r-project.qmd                          # Quarto analysis notebook
├── docs/
│   ├── real-estate-r-project_files/                   # Rendered figures and assets
│   └── index.html                                     # Rendered HTML report (GitHub Pages)
└── README.md
```

---

## How to Reproduce

```bash
git clone https://github.com/Erin-Weiss/R-Real-Estate-Project.git
cd R-Real-Estate-Project
```

Open `real-estate-r-project.qmd` in RStudio and render with Quarto. The notebook contains the full analysis pipeline including data cleaning, exploratory visualizations, regression modeling, and hypothesis testing. Requires R with the `tidyverse`, `lubridate`, `ggpubr`, `summarytools`, `DT`, `descr`, `HydroTSM`, and `SemTools` packages installed.

---

## Future Work

- Incorporate external economic indicators (mortgage rates, inflation, unemployment) to improve model explanatory power.
- Apply time-series forecasting methods (ARIMA, Prophet) to predict future median listing prices.
- Explore interaction effects between region and season or region and year.
- Compare linear regression performance with tree-based models (random forest, gradient boosting) for price prediction.
