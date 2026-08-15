#  Wine Quality Prediction

### Data Analytics Internship — Oasis Infobyte | Task 4

---

## 📌 Overview

Can the chemical properties of red wine be used to predict whether a wine is considered good?

This project applies machine learning classification techniques to the **Red Wine Quality dataset**. The goal is to predict whether a wine belongs to the **Good** or **Not Good** category based on its physicochemical properties, including alcohol content, acidity, sulphates, density, pH, and other chemical characteristics.

Three classification models were trained and compared:

- Random Forest Classifier
- Stochastic Gradient Descent (SGD) Classifier
- Support Vector Classifier (SVC)

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- Classification Report
- Confusion Matrix

---

## 📊 Dataset

| Property | Details |
|---|---|
| **Source** | UCI Machine Learning Repository — Red Wine Quality |
| **File** | `Wine Quality Red.csv` |
| **Total Samples** | 1,599 wines |
| **Features** | 11 physicochemical properties |
| **Original Target** | Wine quality score |
| **Quality Range** | 3–8 |
| **Classification Target** | Good vs Not Good |

### Features

The dataset contains the following chemical properties:

- Fixed acidity
- Volatile acidity
- Citric acid
- Residual sugar
- Chlorides
- Free sulfur dioxide
- Total sulfur dioxide
- Density
- pH
- Sulphates
- Alcohol

---

## 🎯 Target Variable

The original wine quality score was converted into a binary classification target.

| Quality Score | Classification | Label |
|---|---|---:|
| `< 7` | Not Good | 0 |
| `≥ 7` | Good | 1 |

### Class Distribution

| Class | Number of Wines |
|---|---:|
| Not Good | 1,382 |
| Good | 217 |
| **Total** | **1,599** |

The dataset is significantly imbalanced because the **Not Good** class contains considerably more samples than the **Good** class.

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **Python** | Core programming language |
| **Pandas** | Data loading and manipulation |
| **NumPy** | Numerical operations |
| **Matplotlib** | Data visualization |
| **Seaborn** | Statistical visualization |
| **Scikit-learn** | Machine learning and model evaluation |
| **Jupyter Notebook** | Development and analysis environment |

---

## 🔄 Project Workflow

```text
1. Load Wine Quality Dataset
        ↓
2. Inspect Dataset Structure
        ↓
3. Check Missing Values & Duplicates
        ↓
4. Exploratory Data Analysis
        ↓
5. Analyze Quality Score Distribution
        ↓
6. Feature Distribution Analysis
        ↓
7. Correlation Heatmap
        ↓
8. Convert Quality into Binary Classes
        ↓
9. Stratified Train/Test Split
        ↓
10. Feature Scaling
        ↓
11. Train Three Classification Models
        ↓
12. Evaluate Model Performance
        ↓
13. Compare Models
        ↓
14. Random Forest Feature Importance
        ↓
15. Draw Conclusions & Recommendations
```

---

## 🔍 Exploratory Data Analysis

Exploratory Data Analysis (EDA) was performed to understand the structure, distribution, and characteristics of the dataset.

The analysis included:

- Dataset structure and data types
- Statistical summary
- Missing-value analysis
- Duplicate-value analysis
- Wine quality score distribution
- Chemical feature distributions
- Correlation analysis
- Class imbalance analysis

### Dataset Quality

The dataset contains **1,599 wine samples** and **11 physicochemical features**.

No missing values were identified in the dataset, so no missing-value imputation was required.

---

## 📈 Quality Score Distribution

The original wine quality variable contains scores ranging from **3 to 8**.

Most wines are concentrated around quality scores of **5 and 6**, while very few wines receive extremely low or high quality scores.

Because the higher quality classes contain fewer samples, the dataset becomes imbalanced after converting the target into Good and Not Good categories.

---

## 🔗 Correlation Analysis

A correlation heatmap was created to examine relationships between the physicochemical properties and wine quality.

The analysis showed that:

- **Alcohol** had the strongest positive correlation with wine quality.
- **Volatile acidity** showed a relatively strong negative correlation with wine quality.
- **Citric acid** showed a positive relationship with quality.
- Several chemical features also showed relationships with one another.

Correlation does not necessarily imply causation. These relationships were used as exploratory information to better understand the dataset and support the machine learning analysis.

---

## 🤖 Machine Learning Models

Three classification algorithms were trained and compared.

### 1. Random Forest Classifier

Random Forest is an ensemble learning algorithm that combines multiple decision trees to make predictions.

It was selected because it can capture non-linear relationships between physicochemical properties and wine quality.

---

### 2. Stochastic Gradient Descent Classifier

The **Stochastic Gradient Descent (SGD) Classifier** is a linear classification algorithm that uses iterative optimization to learn patterns from the training data.

Feature scaling was applied before training the SGD model.

---

### 3. Support Vector Classifier

The **Support Vector Classifier (SVC)** attempts to find an optimal decision boundary between the Good and Not Good classes.

Feature scaling was applied before training the SVC model.

---

## ⚙️ Model Training

The dataset was divided into training and testing sets using an **80/20 stratified split**.

| Dataset | Samples |
|---|---:|
| Training Set | 1,279 |
| Testing Set | 320 |
| Total | 1,599 |

Stratification was used to preserve the proportion of Good and Not Good wines in both the training and testing datasets.

### Feature Scaling

`StandardScaler` was used to standardize the numerical features.

Scaling was particularly important for the:

- SGD Classifier
- Support Vector Classifier

The Random Forest model does not require feature scaling, but the same prepared dataset was used consistently for the experiment.

---

## 📈 Model Evaluation

The models were evaluated using multiple performance metrics:

- Accuracy
- Precision
- Recall
- F1 Score
- Classification Report
- Confusion Matrix

Because the dataset is imbalanced, accuracy alone does not provide a complete picture of model performance.

---

## 🏆 Model Performance Comparison

The following results were obtained from the final experiment:

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---:|---:|---:|---:|
| **Random Forest** | **94.38%** | **93.10%** | **62.79%** | **75.00%** |
| Support Vector Classifier | 90.00% | 76.19% | 37.21% | 50.00% |
| SGD Classifier | 86.88% | 51.28% | 46.51% | 48.78% |

### 🥇 Best Model: Random Forest

Based on the current experiment, **Random Forest Classifier achieved the best overall performance**.

Its results were:

| Metric | Random Forest |
|---|---:|
| **Accuracy** | **94.38%** |
| **Precision** | **93.10%** |
| **Recall** | **62.79%** |
| **F1 Score** | **75.00%** |

Random Forest achieved the highest accuracy, precision, recall, and F1 score among the three tested models.

However, its **62.79% recall for the Good class** shows that some high-quality wines were still classified as Not Good.

This is partly related to the significant class imbalance in the dataset.

---

## 📊 Classification Performance

### Random Forest

| Class | Precision | Recall | F1 Score | Support |
|---|---:|---:|---:|---:|
| Not Good | 0.95 | 0.99 | 0.97 | 277 |
| Good | 0.93 | 0.63 | 0.75 | 43 |
| **Overall Accuracy** | | | **0.94** | **320** |

The Random Forest model performs very well at identifying Not Good wines, while identifying Good wines is more challenging.

---

## 🌟 Random Forest Feature Importance

Feature importance was calculated using the trained Random Forest model to identify which physicochemical properties contributed most to the model's predictions.

| Rank | Feature | Importance |
|---:|---|---:|
| 1 | **Alcohol** | **0.173564** |
| 2 | **Sulphates** | **0.111345** |
| 3 | **Density** | **0.102920** |
| 4 | **Volatile acidity** | **0.102421** |
| 5 | **Citric acid** | **0.093135** |
| 6 | Total sulfur dioxide | 0.078180 |
| 7 | Fixed acidity | 0.076296 |
| 8 | Residual sugar | 0.069652 |
| 9 | Chlorides | 0.068110 |
| 10 | pH | 0.065280 |
| 11 | Free sulfur dioxide | 0.059096 |

### 🔑 Key Feature

**Alcohol** was the most important feature in the Random Forest model, with an importance score of **0.173564**.

The next most important features were:

1. Sulphates
2. Density
3. Volatile acidity
4. Citric acid

Feature importance indicates how useful a feature was to the model's predictions. It does **not** necessarily mean that the feature directly causes higher or lower wine quality.

---

## 💡 Key Insights

1. The dataset contains **1,599 red wine samples** with **11 physicochemical features**.

2. No missing values were identified in the dataset.

3. Most wines have quality scores of **5 or 6**.

4. Very few wines have extremely low or high quality scores.

5. The original quality score was converted into a binary classification problem.

6. Wines with a quality score of **7 or higher** were classified as **Good**.

7. Wines with a quality score below **7** were classified as **Not Good**.

8. The dataset contains **1,382 Not Good wines** and **217 Good wines**, creating a significant class imbalance.

9. **Random Forest achieved the highest accuracy at 94.38%**.

10. Random Forest also achieved the highest F1 score at **75.00%**.

11. **Alcohol** was the most important feature according to the Random Forest feature-importance analysis.

12. **Sulphates, density, volatile acidity, and citric acid** were also among the most influential features.

13. The lower recall for the Good class indicates that identifying minority-class wines remains challenging.

---

## 🚀 Recommendations

Several approaches could be explored to improve the model further.

### 1. Handle Class Imbalance

Techniques such as **SMOTE (Synthetic Minority Oversampling Technique)** could be used to increase the representation of the minority Good class.

Class weighting could also be tested to give greater importance to minority-class samples.

### 2. Hyperparameter Tuning

The models could be further optimized using:

- GridSearchCV
- RandomizedSearchCV
- Cross-validation

This could potentially improve model performance.

### 3. Cross-Validation

Cross-validation could provide a more reliable estimate of model performance and reduce dependence on a single train/test split.

### 4. Focus on Multiple Evaluation Metrics

Since the dataset is imbalanced, future experiments should consider:

- Precision
- Recall
- F1 Score
- Confusion Matrix
- ROC-AUC

rather than relying only on accuracy.

---

## 📂 Project Structure

```text
Task4_Wine_Quality_Prediction/
│
├── Wine Quality Prediction Task 4.ipynb
├── Wine Quality Red.csv
└── README.md
```

---

## ▶️ How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/sonali-0973/OIBSIP.git
```

### 2. Navigate to the Project Folder

```bash
cd OIBSIP/Task4_Wine_Quality_Prediction
```

### 3. Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### 4. Open the Jupyter Notebook

Open:

```text
Wine Quality Prediction Task 4.ipynb
```

### 5. Run the Notebook

Run all cells from top to bottom.

Make sure the dataset file:

```text
Wine Quality Red.csv
```

is located in the same project folder as the notebook.

---

## 📓 Notebook Contents

The Jupyter Notebook contains:

- Library imports
- Dataset loading
- Dataset inspection
- Statistical analysis
- Missing-value checking
- Duplicate checking
- Quality distribution analysis
- Feature distribution plots
- Correlation heatmap
- Binary target creation
- Class imbalance analysis
- Stratified train/test splitting
- Feature scaling
- Random Forest training
- SGD Classifier training
- SVC training
- Model predictions
- Performance comparison
- Classification reports
- Confusion matrices
- Random Forest feature importance
- Final conclusion and recommendations

---

## 📝 Conclusion

This project demonstrates how machine learning classification techniques can be used to predict red wine quality from physicochemical properties.

Three classification models were trained and compared: **Random Forest, SGD Classifier, and Support Vector Classifier**.

Among the tested approaches, **Random Forest achieved the best overall performance**, with an accuracy of **94.38%**, precision of **93.10%**, recall of **62.79%**, and F1 score of **75.00%**.

The feature-importance analysis showed that **alcohol** was the most influential feature, followed by **sulphates, density, volatile acidity, and citric acid**.

However, the dataset contains a significant imbalance between Good and Not Good wines. Although Random Forest achieved high accuracy and precision, its recall for the Good class was lower at **62.79%**.

Therefore, accuracy alone should not be used to judge the model. Future improvements could include **SMOTE, class weighting, hyperparameter tuning, and cross-validation** to improve the model's ability to identify high-quality wines.

---

##  Author

**Zin Nwe Moe**

Computer Science Undergraduate  
Global Academy at Siam University, Thailand

📧 **sonali.kdk@gmail.com**

GitHub: **sonali-0973**

---

## 🎓 Internship

This project was completed as part of the:

**Oasis Infobyte Data Analytics Internship**

**Project:** Wine Quality Prediction — Task 4
