# 📊 Customer Segmentation Analysis

### Data Analytics Internship — Oasis Infobyte (OIBSIP) | Task 2

---

## 📌 Project Overview

This project was completed as part of the **Data Analytics Internship at Oasis Infobyte (OIBSIP)**.

The objective of this project is to perform **customer segmentation analysis** using the **K-Means clustering algorithm**. The analysis groups mall customers into different segments based on their **annual income and spending behavior**.

Customer segmentation can help businesses understand different types of customers and develop more targeted and effective marketing strategies.

---

## 🎯 Project Objectives

The main objectives of this project are:

- Explore and understand the customer dataset
- Check the dataset for missing values and duplicates
- Perform descriptive statistical analysis
- Analyze customer age, income, and spending behavior
- Select suitable features for clustering
- Standardize the selected features
- Determine the appropriate number of clusters using the Elbow Method
- Apply K-Means clustering
- Visualize the resulting customer segments
- Analyze the characteristics of each cluster
- Develop marketing recommendations for each customer segment

---

## 📂 Dataset

The project uses the **Mall Customer Segmentation Dataset**.

The dataset contains **200 customer records** with the following variables:

| Column | Description |
|---|---|
| `CustomerID` | Unique identification number of each customer |
| `Gender` | Gender of the customer |
| `Age` | Age of the customer |
| `Annual Income (k$)` | Annual income in thousands of dollars |
| `Spending Score (1-100)` | Spending score assigned to the customer based on purchasing behavior |

### Dataset File

```text
Mall Customers Segmentation.csv
```

---

## 🛠️ Technologies & Libraries

| Technology / Library | Purpose |
|---|---|
| **Python** | Core programming language |
| **Pandas** | Data loading and manipulation |
| **NumPy** | Numerical operations |
| **Matplotlib** | Data visualization |
| **Seaborn** | Statistical visualization |
| **Scikit-learn** | Feature scaling and K-Means clustering |
| **Jupyter Notebook** | Development and analysis environment |

---

## 🔄 Project Workflow

```text
1. Load Customer Dataset
        ↓
2. Inspect Dataset Structure
        ↓
3. Check Missing Values & Duplicates
        ↓
4. Perform Descriptive Statistics
        ↓
5. Exploratory Data Analysis
        ↓
6. Analyze Age Distribution
        ↓
7. Analyze Annual Income Distribution
        ↓
8. Analyze Spending Score Distribution
        ↓
9. Select Clustering Features
        ↓
10. Standardize Features
        ↓
11. Apply Elbow Method
        ↓
12. Determine Optimal Number of Clusters
        ↓
13. Apply K-Means Clustering
        ↓
14. Visualize Customer Segments
        ↓
15. Analyze Cluster Sizes
        ↓
16. Profile Customer Segments
        ↓
17. Develop Marketing Recommendations
        ↓
18. Draw Conclusions
```

---

## 🔍 Exploratory Data Analysis

Before applying the clustering algorithm, exploratory data analysis was performed to understand the characteristics of the customer dataset.

The analysis included:

- Dataset structure
- Data types
- Missing-value checking
- Duplicate checking
- Descriptive statistics
- Gender distribution
- Age distribution
- Annual income distribution
- Spending score distribution

These analyses helped provide an initial understanding of the customer population before applying machine learning.

### 👥 Gender Distribution

A count plot was used to visualize the distribution of customers by gender.

This provides an overview of the demographic composition of the customer dataset.

### 🎂 Age Distribution

The age distribution was visualized using a histogram.

This helped identify the range and general distribution of customer ages within the dataset.

### 💰 Annual Income Distribution

Annual income was analyzed using a histogram to understand the income levels of the customers.

The variable is measured in thousands of dollars (`k$`).

### 🛍️ Spending Score Distribution

The Spending Score ranges from **1 to 100** and represents the customer's purchasing behavior.

A higher spending score indicates stronger spending activity, while a lower score indicates weaker spending activity.

---

## 🎯 Feature Selection

For customer segmentation, the following two features were selected:

```python
X = df[
    [
        "Annual Income (k$)",
        "Spending Score (1-100)"
    ]
]
```

### Why These Features?

**Annual Income** provides an indication of the customer's financial capacity, while **Spending Score** provides an indication of their purchasing behavior.

Together, these features allow customers to be grouped according to different combinations of income and spending behavior.

---

## ⚖️ Feature Scaling

Before applying K-Means clustering, the selected features were standardized using `StandardScaler`.

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()

X_scaled = scaler.fit_transform(X)
```

Standardization was performed so that the features were placed on a comparable scale during clustering.

---

## 📐 Elbow Method

The **Elbow Method** was used to determine the appropriate number of clusters.

K-Means was tested using different values of `K`, ranging from 1 to 10.

The inertia decreased significantly as the number of clusters increased. The improvement began to level off around **K = 5**.

Therefore, the project selected:

```text
Optimal Number of Clusters = 5
```

---

## 🤖 K-Means Clustering

The K-Means clustering algorithm was applied using five clusters.

```python
from sklearn.cluster import KMeans

kmeans = KMeans(
    n_clusters=5,
    init="k-means++",
    random_state=42,
    n_init=10
)

df["Cluster"] = kmeans.fit_predict(X_scaled)
```

The algorithm assigned all 200 customers to one of five customer segments.

---

## 📊 Cluster Distribution

The resulting clusters contained the following number of customers:

| Cluster | Customers | Percentage |
|---|---:|---:|
| Cluster 0 | 81 | 40.5% |
| Cluster 1 | 39 | 19.5% |
| Cluster 2 | 22 | 11.0% |
| Cluster 3 | 35 | 17.5% |
| Cluster 4 | 23 | 11.5% |
| **Total** | **200** | **100%** |

### Key Observation

**Cluster 0 is the largest segment**, containing 81 customers, or approximately **40.5% of the customer base**.

---

## 📋 Cluster Profile

The average characteristics of each customer segment are:

| Cluster | Customers | Average Age | Average Income (k$) | Average Spending Score |
|---:|---:|---:|---:|---:|
| 0 | 81 | 42.72 | 55.30 | 49.52 |
| 1 | 39 | 32.69 | 86.54 | 82.13 |
| 2 | 22 | 25.27 | 25.73 | 79.36 |
| 3 | 35 | 41.11 | 88.20 | 17.11 |
| 4 | 23 | 45.22 | 26.30 | 20.91 |

---

# 👤 Customer Segment Analysis

## 🟦 Cluster 0 — Moderate Engagement Customers

**Customers:** 81  
**Average Age:** 42.72 years  
**Average Income:** $55.30k  
**Average Spending Score:** 49.52

Cluster 0 is the largest customer group.

These customers have moderate income and moderate spending behavior. They represent a broad customer segment with potential to increase their engagement and spending.

### Marketing Recommendation

Recommended strategies include:

- Loyalty rewards
- Personalized offers
- Bundle promotions
- Limited-time discounts
- Repeat-purchase incentives

The goal is to encourage these customers to become more engaged with the business.

---

## 🟢 Cluster 1 — High Value Customers

**Customers:** 39  
**Average Age:** 32.69 years  
**Average Income:** $86.54k  
**Average Spending Score:** 82.13

Cluster 1 has both **high income and high spending behavior**.

This makes it the most valuable customer segment identified in the analysis.

### Marketing Recommendation

The business should prioritize:

- VIP loyalty programs
- Premium products
- Exclusive offers
- Personalized recommendations
- Early access to new products
- Special customer benefits

The main goal should be to retain these customers and maximize their long-term value.

---

## 🟡 Cluster 2 — Young Big Spenders

**Customers:** 22  
**Average Age:** 25.27 years  
**Average Income:** $25.73k  
**Average Spending Score:** 79.36

Cluster 2 contains relatively young customers with lower average income but a very high spending score.

This is an interesting segment because the customers demonstrate strong spending behavior despite their lower average income.

### Marketing Recommendation

Recommended strategies include:

- Affordable and trendy products
- Student-friendly discounts
- Social media campaigns
- Influencer marketing
- Limited-time offers
- Mobile-focused promotions

The goal is to maintain engagement and encourage repeat purchases.

---

## 🟣 Cluster 3 — Untapped Potential

**Customers:** 35  
**Average Age:** 41.11 years  
**Average Income:** $88.20k  
**Average Spending Score:** 17.11

Cluster 3 has the **highest average income among all customer segments** but a very low spending score.

This makes it an important growth opportunity.

These customers have strong purchasing capacity but currently demonstrate low spending activity.

### Marketing Recommendation

Recommended strategies include:

- Personalized promotions
- Targeted product recommendations
- Exclusive offers
- Re-engagement campaigns
- Personalized communication
- Special incentives

The business should investigate why these customers are not spending more and use targeted marketing to increase engagement.

---

## 🟠 Cluster 4 — Low Engagement Customers

**Customers:** 23  
**Average Age:** 45.22 years  
**Average Income:** $26.30k  
**Average Spending Score:** 20.91

Cluster 4 has relatively low income and low spending behavior.

This segment has lower current purchasing activity compared with the other groups.

### Marketing Recommendation

Recommended strategies include:

- Value-based promotions
- Discounts
- Affordable products
- Bundle offers
- Occasional promotions
- Repeat-purchase incentives

Marketing spending should remain cost-effective for this segment.

---

# 📈 Visualizations

The project includes several visualizations to support the customer segmentation analysis.

### 1. Gender Distribution

A count plot showing the distribution of customers by gender.

### 2. Age Distribution

A histogram showing the distribution of customer ages.

### 3. Annual Income Distribution

A histogram showing the distribution of annual income.

### 4. Spending Score Distribution

A histogram showing the distribution of spending scores.

### 5. Elbow Method

A line chart showing the inertia values for different numbers of clusters.

### 6. Annual Income vs Spending Score

A scatter plot showing the five customer segments and K-Means centroids.

### 7. Age vs Spending Score

A scatter plot showing the relationship between age and spending behavior across the identified customer segments.

### 8. Customer Count by Cluster

A bar chart showing the number of customers in each cluster.

### 9. Customer Segment Heatmap

A heatmap showing the average characteristics of each customer segment.

---

# 💡 Key Insights

The K-Means clustering analysis identified five meaningful customer segments.

### 1. Largest Customer Segment

Cluster 0 contains **81 customers**, representing approximately **40.5% of the customer base**.

These customers have moderate income and moderate spending behavior.

### 2. Highest-Value Customer Segment

Cluster 1 contains customers with:

- Average income: **$86.54k**
- Average spending score: **82.13**

This makes Cluster 1 the most valuable segment based on the combination of income and spending.

### 3. Young High-Spending Customers

Cluster 2 has:

- Average age: **25.27 years**
- Average income: **$25.73k**
- Average spending score: **79.36**

These customers have relatively low income but demonstrate high spending behavior.

### 4. High-Income Low-Spending Customers

Cluster 3 has:

- Average income: **$88.20k**
- Average spending score: **17.11**

This segment represents a significant opportunity for customer re-engagement and targeted marketing.

### 5. Low-Engagement Customers

Cluster 4 has:

- Average income: **$26.30k**
- Average spending score: **20.91**

This segment demonstrates relatively low purchasing activity and should be approached using cost-effective marketing strategies.

---

# 📌 Business Recommendations

| Customer Segment | Recommended Strategy |
|---|---|
| **Moderate Engagement Customers** | Loyalty rewards, personalized offers, and bundle promotions |
| **High Value Customers** | VIP programs, premium products, and exclusive offers |
| **Young Big Spenders** | Trendy products, student discounts, and social-media campaigns |
| **Untapped Potential** | Personalized promotions and targeted re-engagement |
| **Low Engagement Customers** | Discounts, affordable products, and value bundles |

---

# 🧠 Conclusion

The customer segmentation analysis successfully divided the **200 mall customers into five distinct groups** using the **K-Means clustering algorithm**.

The results demonstrate that customers should not be treated as a single homogeneous group. Customers with similar income levels can have very different spending behaviors, while customers with lower income can sometimes demonstrate significantly higher spending activity.

The analysis identified five useful customer segments:

- **Moderate Engagement Customers** — the largest customer group with moderate income and spending.
- **High Value Customers** — high-income customers with high spending behavior.
- **Young Big Spenders** — younger customers with lower income but high spending scores.
- **Untapped Potential** — high-income customers with low spending activity.
- **Low Engagement Customers** — customers with relatively low income and low spending.

Among these groups, **High Value Customers should receive the highest retention priority**, while the **Untapped Potential segment represents an important opportunity for increasing customer engagement and revenue**.

Overall, this project demonstrates how **K-Means clustering can transform customer data into meaningful business segments** and support more targeted, data-driven marketing decisions.

---

# 🚀 How to Run

## 1. Clone the Repository

Clone the project repository to your local machine.

```bash
git clone <your-repository-url>
```

## 2. Navigate to the Project Folder

```bash
cd Task2_Customer_Segmentation
```

## 3. Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

## 4. Open the Notebook

Open:

```text
Task2_Customer_Segmentation.ipynb
```

You can run the notebook using:

- Jupyter Notebook
- JupyterLab
- Visual Studio Code
- Google Colab

## 5. Add the Dataset

Make sure the dataset is available in the same folder as the notebook:

```text
Mall Customers Segmentation.csv
```

## 6. Run the Notebook

Run all cells from **top to bottom**.

---

# 📁 Project Structure

```text
Task2_Customer_Segmentation/
│
├── Mall Customers Segmentation.csv
├── Task2_Customer_Segmentation.ipynb
└── README.md
```

---

# 👩‍💻 About Me

## Zin Nwe Moe

🎓 **Computer Science Undergraduate**  
🏫 **Global Academy at Siam University, Thailand**

### Interests

- 🤖 Artificial Intelligence
- 📊 Data Science
- 🧠 Machine Learning
- 🔬 Deep Learning
- 🐍 Python
- 📈 Data Analytics

I am currently developing my skills in Python, data analysis, machine learning, and artificial intelligence through academic projects, internships, and practical work.

---

# 📫 Contact

📧 **Email:** sonali.kdk@gmail.com

💻 **GitHub:** `sonali-0973`

---

# 🎓 Internship

This project was completed as part of the:

**Oasis Infobyte Data Analytics Internship Program (OIBSIP)**

**Task:** Customer Segmentation Analysis — Task 2

---

This project helped strengthen my practical understanding of:

- Exploratory Data Analysis
- Data Visualization
- Feature Selection
- Feature Scaling
- K-Means Clustering
- Customer Segmentation
- Data Interpretation
- Business Recommendation Development

---

# ⭐ Project Summary

| Category | Result |
|---|---|
| **Dataset** | Mall Customer Segmentation |
| **Total Customers** | 200 |
| **Features Used** | Annual Income + Spending Score |
| **Algorithm** | K-Means Clustering |
| **Optimal K** | 5 |
| **Largest Cluster** | Cluster 0 — 81 customers |
| **Highest-Value Segment** | Cluster 1 |
| **Young High-Spending Segment** | Cluster 2 |
| **Untapped Potential Segment** | Cluster 3 |
| **Low Engagement Segment** | Cluster 4 |

---

⭐ **Thank you for visiting this project!**