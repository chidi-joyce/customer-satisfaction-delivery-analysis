# Customer Satisfaction & Delivery Performance Analysis

**Olist Brazilian E-Commerce Dataset | Python, Tableau**

## Project Overview

This project analyzes customer satisfaction on the Olist e-commerce platform and investigates the impact of delivery performance on customer reviews. The objective is to identify the factors influencing customer satisfaction and provide actionable recommendations for improving the overall customer experience.

## Business Problem

Customer satisfaction is critical to customer retention, loyalty, and long-term business success. As delivery is one of the most visible stages of the customer journey, this project seeks to understand whether delivery performance influences customer satisfaction and to identify opportunities for improvement.

## Goal

To determine the impact of delivery performance on customer satisfaction and identify opportunities to enhance the customer experience.

## Dataset

The analysis uses data from the [Brazilian Olist e-commerce dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) (public, via Kaggle), including:

- Customers
- Orders
- Order Reviews
- Order Items
- Products

## Data Preparation

### Data Cleaning

- Missing value assessment
- Duplicate record checks
- Data type validation
- Datetime conversion and validation
- Investigation of invalid or unusual records
- Initial outlier analysis

### Feature Engineering

| Feature | Description |
|---|---|
| `delivery_days` | Total days from purchase to delivery |
| `delivery_delay_days` | Days late (or early) relative to the estimated delivery date |
| `delivery_status` | Late vs. on-time/early classification |
| `delivery_outlier` | Flag for deliveries falling outside the normal IQR range |
| `delay_band` | Delay severity bucket (1–3, 4–7, 8–14, 15–30, 30+ days late) |

## Analytical Techniques

- Descriptive statistics
- Distribution analysis
- Outlier detection (IQR method)
- Comparative analysis
- Segmentation analysis
- Correlation analysis

## Key Findings

**1. Overall customer satisfaction is high.**
Most customers gave ratings of 4 or 5 stars, indicating generally positive experiences overall.

**2. Delivery performance is strongly associated with customer satisfaction.**
Orders delivered within the normal delivery range received an average review score of 4.18, compared to 2.33 for delivery outliers.

**3. Late deliveries significantly increase customer dissatisfaction.**
- 62.40% of late deliveries received ratings of 1–2 stars.
- Only 11.39% of on-time or early deliveries received ratings of 1–2 stars.
- Customers experiencing late deliveries were over five times more likely to leave a poor review.

**4. Satisfaction declines sharply once delays pass a threshold, then levels off.**
Average review scores dropped from 3.29 (1–3 days late) to roughly 1.6–2.1 for longer delays, with the steepest drop occurring in the first week of delay.

**5. Correlation analysis.**
A correlation coefficient of -0.267 was observed between delivery delay days and review scores, which is a weak-to-moderate negative relationship. While delay isn't the only factor behind a review score, the categorical comparisons above (62.40% vs. 11.39%) show the practical effect is substantial, even where the linear correlation itself is modest.

## Dashboard

An interactive Tableau dashboard was built to let users explore:
- Customer satisfaction levels
- Delivery performance
- Late delivery patterns
- Delay severity impacts

**Interactive filters:** Customer State · Delivery Status · Review Score

🔗 **[View the live dashboard on Tableau Public](https://public.tableau.com/app/profile/chidiogo.ezeugwu/viz/CustomerSatisfactionDeliveryPerformanceAnalysis/Dashboard1)**

## Recommendations

1. **Reduce the frequency and severity of delivery delays.** Delayed orders are strongly linked to dissatisfaction, 62.40% of late deliveries received 1–2 star ratings, versus 11.39% for on-time/early orders, making delay reduction a high-leverage lever for improving overall satisfaction.
2. **Prioritize orders experiencing extended delays.** Focus operational effort on orders showing signs of significant delay, particularly those exceeding three days, since that's where satisfaction drops fastest.
3. **Investigate the 30+ day delay segment.** Satisfaction in this segment was slightly higher than the trend would predict. It's worth investigating whether customer service, operational, or seller-led interventions helped mitigate dissatisfaction, and whether those practices can be applied more broadly.

*Further investigation: identifying which specific factors (e.g., seller processing time, carrier transit patterns, product category) predict delay risk, in advance, was out of scope for this phase and is a natural next step.*

## Tools Used

- **Python**, Pandas, NumPy, Matplotlib, Seaborn
- **Tableau**, interactive dashboard

## Repository Contents

- `notebook/`, full analysis notebook (data cleaning, feature engineering, EDA, correlation analysis)
- `dashboard/`, Tableau workbook (`.twbx`)
- `presentation/`, summary slide deck
- `data/`, cleaned, feature-engineered dataset (CSV) used as the Tableau data source

## How to Reproduce Locally

The raw Olist CSVs aren't included in this repo (they're a public dataset, not mine to redistribute, and one file alone is ~60MB, too large for a clean git repo).

1. Download the dataset from Kaggle: [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
2. Extract the CSVs into a folder named `Olist Tables/` in the same directory as the notebook
3. Open `notebook/` and run all cells, the notebook reads the CSVs using a relative path, so no path changes are needed as long as the folder structure above is kept

## Author

**Chidiogo Joyce Ezeugwu**
Data Analyst | [LinkedIn](https://www.linkedin.com/in/chidiogo-ezeugwu)
