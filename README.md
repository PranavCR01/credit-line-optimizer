# Credit Line Optimization Framework


This repository presents a machine learning framework for credit line management using anonymized customer data provided by \*\*Synchrony\*\*. It predicts future spending, segments accounts by credit risk, and recommends personalized credit line adjustments to balance business growth with risk exposure.



---



## Project Structure


```

credit-line-optimizer/
│
├── credit\_line\_analysis.ipynb # Full modeling notebook
├── screenshots # Visuals used in README
└── README.md # This file

```

---



## Overview

### Business Objectives:

1. **Predict Customer Spend** – Estimate Q4 2025 spending using historical and behavioral features.

2. **Segment Accounts** – Classify accounts into groups for credit line decision-making.

3. **Recommend Adjustments** – Suggest personalized credit line increases for eligible customers.



---



## Key Results



### 1. Q4 Spend Forecasting  

- **Model:** GradientBoostingRegressor  

- **Performance:** R² = 0.9985  

- **Validation Proxy:** Q4 2024 Spend



<div align="center">
&nbsp; <img src="screenshots\ss_1.png" width="500"/>
</div>


---



### 2. Customer Segmentation  

- **Model:** XGBoost + SMOTE  

- **Classes:**

&nbsp; - No Increase Required
&nbsp; - Eligible (Safe / Risky)
&nbsp; - High Risk  

- **Accuracy:** 88%


<div align="center">
&nbsp; <img src="screenshots\ss_2.png" width="400"/>
&nbsp; <br/>

&nbsp; <img src="screenshots\ss_3.png" width="430"/>
</div>


---



### 3. Credit Line Recommendation  

- **Model:** RandomForestRegressor  
- **Mean Absolute Error (MAE):** $3.38  
- **Criteria:** Utilization, spend-to-limit ratio, risk flags

---

## Exploratory Insights

### Delinquency vs Credit Line

<div align="center">
&nbsp; <img src="screenshots\ss_4.png" width="450"/>
</div>

- Accounts with more delinquencies in the past 6 months tend to have lower credit lines.
- As delinquency counts increase, both the median and variability in credit lines decrease—supporting its use as a risk signal.


---

### Behavioral Score vs Credit Line

<div align="center">
&nbsp; <img src="screenshots\ss_5.png" width="450"/>
</div>

- Higher behavioral scores are strongly associated with higher credit limits.
- This correlation supports their use in segmentation and credit line adjustment models.


---

### Average Spend Over Time

<div align="center">
&nbsp; <img src="screenshots\ss_6.png" width="450"/>
</div>

- Spending dropped in 2023 but recovered steadily through 2024 and early 2025.
- These patterns were used to improve Q4 2025 spending forecasts.


---

## Features Engineered

- Credit Utilization (Current, 3M, 6M)
- Avg Quarterly Spend (Q2 2023 to Q1 2025)
- Behavioral \& Bureau Scores
- Fraud \& Delinquency Metrics
- Open-to-Buy (OTB) Ratios

---

## Impact

- Identifies high-value accounts for strategic credit growth
- Flags high-risk accounts for exclusion
- Enables data-backed, fair credit decisions






