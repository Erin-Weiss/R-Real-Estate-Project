# 🏠 R Real Estate Project

**Author:** Erin Weiss  
**View the full report:** [https://erin-weiss.github.io/R-Real-Estate-Project/](https://erin-weiss.github.io/R-Real-Estate-Project/)

---

## 📘 Overview

This project explores **U.S. real estate trends** from 2016–2022 using data from **Realtor.com’s Research Data Center**.  
The goal was to understand how factors such as **region, season, square footage, and market activity** influence housing prices across states and over time.

---

## ⚙️ Approach

Using **R** and **Quarto**, I performed a full exploratory analysis and built a multiple linear regression model to explain variation in housing prices.  
Key steps included:

- Cleaning and transforming Realtor.com’s state-level dataset  
- Exploring trends by **region, season, month, year, and state**  
- Visualizing relationships between **price, square footage, listings, and days on market**  
- Testing nine hypotheses using regression analysis  

---

## 📊 Key Insights

- **Prices have risen consistently** each year since 2016.  
- The **West** and **Northeast** regions had the **highest housing prices**.  
- Homes in **summer** months and **faster-moving markets** (fewer days on market) tend to be more expensive.  
- **Pending listings** and **square footage** were strong positive predictors of price.  
- **Active** and **new listings** showed little impact on price.  
- The regression model explained **~95% of price variation (Adjusted R² = 0.95)**.

---

## 🧰 Tools Used

- **Language:** R  
- **Libraries:** `tidyverse`, `ggplot2`, `lubridate`, `summarytools`, `DT`, `ggpubr`, `HydroTSM`, `descr`, `SemTools`  
- **Reporting:** Quarto (`.qmd`) → HTML  

---

## 🌐 View the Full Analysis

👉 [**R Real Estate Project (Interactive HTML Report)**](https://erin-weiss.github.io/R-Real-Estate-Project/)
