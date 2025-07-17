# Analyzing-Customer-Purchase-Patterns-and-Marketing-Effectiveness-in-E-Commerce


## Overview

This project analyzes customer behavior using transaction data, demographics, marketing spend, and discount history to:
- Segment customers with RFM and K-Means
- Predict customer lifetime value (CLV)
- Forecast the timing of next purchases

![ecommerce](https://github.com/user-attachments/assets/3e23bd1a-6756-4f22-8014-2004f7b8f852)


---

## Objectives

- Segment customers into Premium, Gold, Silver, and Standard tiers
- Predict customer lifetime value (LTV)
- Forecast likelihood of next purchase (0–30 days, 30–60, >60 days)

---

## Data Sources

| File                  | Description                                 |
|-----------------------|---------------------------------------------|
| `Online_Sales.csv`    | Product-level transactions                  |
| `Customers_Data.csv`  | Customer demographics                       |
| `Discount_Coupon.csv` | Discounts and redemptions                   |
| `Marketing_Spend.csv` | Daily online & offline marketing spend      |
| `Tax_Amount.csv`      | Product-level tax information               |

---

## Methodology

### Data Preparation
- Merged multiple data sources on customer/product/date keys
- Handled missing values, removed duplicates, and converted dates

### Feature Engineering
- RFM metrics for segmentation
- CLV = Revenue × Tenure
- Transaction revenue calculation
- Monthly acquisition and retention tracking

### Modeling
- RFM + K-Means for segmentation (Elbow method to determine K)
- Random Forest for purchase prediction
- Evaluation metrics: Accuracy, Precision, Recall, F1, AUC

---

## Results & Insights

### Marketing Effectiveness

| Channel          | Coefficient | Significance |
|------------------|-------------|--------------|
| Online Marketing | 0.65        | p < 0.01     |
| Offline Marketing| 0.34        | p < 0.05     |

- Online marketing showed higher ROI
- Adjusted R² = 0.78

### Segmentation Summary

| Cluster | Frequency | Value | Profile Description         |
|---------|-----------|--------|------------------------------|
| 0       | High      | Low    | Bargain Seekers              |
| 1       | Low       | High   | Occasional High-Spenders     |
| 2       | High      | High   | Premium Customers (45% Rev)  |
| 3       | Low       | Low    | Low Engagement Customers     |

### Other Key Takeaways

- Premium customers show highest tenure (avg. 24 months)
- Revenue spikes in Q1 and Q4 → strong seasonality
- Apparel & Electronics discounts yield 15% redemption vs. 8% in books/groceries
- Online marketing should be prioritized in future budget planning

---

## Visualizations Excerpt

<img width="884" height="523" alt="Screenshot 2025-07-16 at 21 13 35" src="https://github.com/user-attachments/assets/3175b93e-cecf-4e89-a3b2-504fb5a58c3d" />
<img width="884" height="525" alt="Screenshot 2025-07-16 at 21 13 44" src="https://github.com/user-attachments/assets/1f51faa1-64f4-4e71-84a2-05240999904a" />
<img width="554" height="468" alt="Screenshot 2025-07-16 at 21 13 59" src="https://github.com/user-attachments/assets/09f57b9f-e7df-4f58-99e0-e7381f758d69" />



---

## Experimental Setup

- Dataset timeframe: Jan 1, 2019 – Dec 31, 2019
- Total records: ~52,000 transactions
- 80/20 train-test split for modeling
- Cross-validation applied
