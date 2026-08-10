# 📊 Task 1: Exploratory Data Analysis (EDA) on Retail Sales Data

## Overview

This project is part of the Data Analytics Internship at Oasis Infobyte (OIBSIP). The goal of this project is to perform Exploratory Data Analysis (EDA) on a retail sales dataset to uncover sales patterns, analyze product and customer performance, evaluate profitability, and generate actionable business insights.

---

## Dataset

The dataset used in this project is the Superstore Sales dataset from Kaggle credit goes to original owner. It contains retail order information, including order dates, customer segments, product categories, sub-categories, product names, sales, quantity, discounts, and profit.

---

## Tools and Libraries Used

- Python
- Pandas (data loading, cleaning, and manipulation)
- NumPy (numerical operations)
- Matplotlib (data visualization)
- Seaborn (statistical visualization and correlation analysis)
- Jupyter Notebook

---

## Steps Performed

1. Loaded and inspected the dataset using `df.head()`, `df.info()`, and `df.shape`.
2. Checked for missing values and duplicate records.
3. Performed data cleaning and prepared the dataset for analysis.
4. Calculated descriptive statistics, including mean, median, mode, and standard deviation for numerical columns.
5. Converted the Order Date column into a proper datetime format.
6. Extracted Year, Month, and Quarter information for time-series analysis.
7. Analyzed monthly sales trends using a line chart.
8. Analyzed quarterly sales trends to identify changes in sales performance over time.
9. Compared total sales across product categories and sub-categories.
10. Analyzed total sales across Consumer, Corporate, and Home Office customer segments.
11. Compared profitability across product categories.
12. Created a correlation heatmap to examine relationships between numerical variables.
13. Identified the top 10 best-selling products using a horizontal bar chart.
14. Generated business insights and actionable recommendations based on the analysis.

---

## Key Insights

- Sales show noticeable fluctuations over time, with relatively weaker sales during several periods at the beginning of the year and stronger sales activity during some middle and later periods.

- Technology is the highest-performing category by total sales, followed by Furniture and Office Supplies.

- Machines, Chairs, and Phones are among the strongest-performing sub-categories based on total sales.

- The Consumer segment generates the highest total sales, significantly outperforming the Corporate and Home Office segments.

- Office Supplies generates the highest overall profit despite having lower total sales than Technology and Furniture.

- Furniture generates relatively strong sales but records an overall loss, indicating a significant profitability concern that requires further investigation.

- The correlation analysis shows a negative relationship between Discount and Profit, suggesting that higher discount levels may contribute to reduced profitability.

- Sales and Quantity have a positive but relatively weak relationship, indicating that quantity is not the only factor influencing total sales value.

- A small number of high-value products contribute significantly to overall product-level sales.

---

## Business Recommendations

- Investigate the Furniture category at the product and sub-category levels to identify the main sources of financial losses.

- Review the company's discount strategy and avoid excessive discounting on products with low profit margins.

- Use targeted discounts, promotional campaigns, and customer coupons during historically low-sales periods to stimulate demand.

- Increase inventory availability during high-demand periods to reduce the risk of stock shortages and missed sales opportunities.

- Continue focusing on high-performing categories such as Technology while monitoring profitability alongside sales performance.

- Strengthen engagement with the Consumer segment while exploring opportunities to increase sales from Corporate and Home Office customers.

- Use historical monthly and quarterly sales patterns to improve demand forecasting and inventory planning.

---

## How to Run

1. Clone or download this GitHub repository.
2. Open the Jupyter Notebook file in Jupyter Notebook, VS Code, or Google Colab.
3. Ensure that the Superstore dataset file is available in the same project directory.
4. Install the required Python libraries if necessary.
5. Run each notebook cell in order from top to bottom.

---

## Author

**Zin Nwe Moe(Sonali)** — Data Analytics Intern, Oasis Infobyte

---

## Acknowledgment

This project was completed as part of the Oasis Infobyte Data Analytics Internship Program (OIBSIP).
