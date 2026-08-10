#  Wine Quality Prediction

### Data Analytics Internship — Oasis Infobyte | Task 4

---

##  Overview

Can the chemical properties of red wine be used to predict whether a wine is considered good?

This project applies machine learning classification techniques to the **Red Wine Quality dataset**. The goal is to predict whether a wine belongs to the **Good** or **Not Good** category based on its physicochemical properties, including alcohol content, acidity, sulphates, density, pH, and other chemical characteristics.

Three classification models were trained and compared:

- Random Forest Classifier
- Stochastic Gradient Descent (SGD) Classifier
- Support Vector Classifier (SVC)

The models were evaluated using accuracy, precision, recall, F1-score, classification reports, and confusion matrices.

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

The original wine quality score was converted into a binary classification target:

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

The dataset is therefore imbalanced, with significantly more wines classified as **Not Good** than **Good**.

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
🔍 Exploratory Data Analysis

## Exploratory Data Analysis (EDA) was performed to understand the structure and characteristics of the dataset.

The analysis included:

Dataset structure and data types
Statistical summary
Missing-value analysis
Duplicate-value analysis
Wine quality score distribution
Chemical feature distributions
Correlation analysis
Class imbalance analysis
Correlation Analysis

A correlation heatmap was created to examine relationships between the physicochemical properties and wine quality.

The analysis showed that alcohol had the strongest positive correlation with wine quality, while volatile acidity showed a relatively strong negative correlation.

Correlation does not necessarily imply causation, but these relationships provide useful information for the machine learning models.

## 🤖 Machine Learning Models

Three classification algorithms were trained and compared.

1. Random Forest Classifier

Random Forest is an ensemble learning algorithm that combines multiple decision trees to produce predictions.

It was selected because it can capture non-linear relationships between physicochemical properties and wine quality.

2. Stochastic Gradient Descent Classifier

The Stochastic Gradient Descent (SGD) Classifier is a linear classification algorithm that uses iterative optimization to learn patterns from the training data.

Feature scaling was applied before training the SGD model.

3. Support Vector Classifier

The Support Vector Classifier (SVC) attempts to find an optimal decision boundary between the Good and Not Good classes.

Feature scaling was applied before training the SVC model.

## ⚙️ Model Training

The dataset was divided into training and testing sets using an 80/20 stratified split.

Training Set: 80%
Testing Set: 20%

Stratification was used to preserve the proportion of Good and Not Good wines in both the training and testing datasets.

For SGD and SVC, the features were standardized using StandardScaler.

## 📈 Model Evaluation

The models were evaluated using several performance metrics:

Accuracy
Precision
Recall
F1 Score
Classification Report
Confusion Matrix
🏆 Best Model

Based on the current experiment, Random Forest Classifier achieved the best overall performance.

Metric	Random Forest
Accuracy	94.38%
Precision	93.10%
Recall	62.79%
F1 Score	75.00%

The model achieved high accuracy and precision. However, the recall score indicates that some wines belonging to the Good class were classified as Not Good.

Because the dataset is imbalanced, accuracy alone should not be considered sufficient for evaluating the model.

🌟 Random Forest Feature Importance

Feature importance was calculated using the trained Random Forest model to identify which physicochemical properties contributed most to its predictions.

Rank	Feature	Importance
1	Alcohol	0.173564
2	Sulphates	0.111345
3	Density	0.102920
4	Volatile acidity	0.102421
5	Citric acid	0.093135
6	Total sulfur dioxide	0.078180
7	Fixed acidity	0.076296
8	Residual sugar	0.069652
9	Chlorides	0.068110
10	pH	0.065280
11	Free sulfur dioxide	0.059096
Key Feature

Alcohol was the most important feature in the Random Forest model, followed by:

Sulphates
Density
Volatile acidity
Citric acid

Feature importance indicates how useful a feature was to the model's predictions. It does not necessarily mean that a feature directly causes higher or lower wine quality.

💡 Key Insights
The dataset contains 1,599 red wine samples.
There are 11 physicochemical features used for prediction.
No missing values were identified in the dataset.
Most wines have quality scores of 5 or 6.
Very few wines have extremely low or high quality scores.
The original quality score was converted into a binary classification problem.
Wines with a quality score of 7 or higher were classified as Good.
Wines with a quality score below 7 were classified as Not Good.
The dataset contains 1,382 Not Good wines and 217 Good wines.
The dataset is therefore significantly imbalanced.
Random Forest achieved 94.38% accuracy in the current experiment.
Alcohol was the most important feature according to the Random Forest feature-importance analysis.
Sulphates, density, volatile acidity, and citric acid were also among the most influential features.
The lower recall for the Good class indicates that identifying minority-class wines remains challenging.
🚀 Recommendations

Several approaches could be explored to improve the model further.

1. Handle Class Imbalance

Techniques such as SMOTE (Synthetic Minority Oversampling Technique) could be used to increase the representation of the minority Good class.

Class weighting could also be tested to give greater importance to minority-class samples.

2. Hyperparameter Tuning

The models could be further optimized using:

GridSearchCV
RandomizedSearchCV
Cross-validation

This could potentially improve model performance.

3. Cross-Validation

Cross-validation could provide a more reliable estimate of model performance and reduce dependence on a single train/test split.

4. Focus on Multiple Evaluation Metrics

Since the dataset is imbalanced, future experiments should consider:

Precision
Recall
F1 Score
Confusion Matrix
ROC-AUC

rather than relying only on accuracy.

📂 Project Structure
Task4_Wine_Quality_Prediction/
│
├── Wine Quality Prediction Task 4.ipynb
├── Wine Quality Red.csv
└── README.md
▶️ How to Run
1. Clone the Repository
git clone https://github.com/sonali-0973/OIBSIP.git
2. Navigate to the Project Folder
cd OIBSIP/Task4_Wine_Quality_Prediction
3. Install Required Libraries
pip install pandas numpy matplotlib seaborn scikit-learn
4. Open the Jupyter Notebook

Open:

Wine Quality Prediction Task 4.ipynb
5. Run the Notebook

Run all cells from top to bottom.

Make sure the dataset file:

Wine Quality Red.csv

is located in the same project folder as the notebook.

📓 Notebook Contents

The Jupyter Notebook contains:

Library imports
Dataset loading
Dataset inspection
Statistical analysis
Missing-value checking
Duplicate checking
Quality distribution analysis
Feature distribution plots
Correlation heatmap
Binary target creation
Class imbalance analysis
Stratified train/test splitting
Feature scaling
Random Forest training
SGD Classifier training
SVC training
Model predictions
Performance comparison
Classification reports
Confusion matrices
Random Forest feature importance
Final conclusion and recommendations
📝 Conclusion

This project demonstrates how machine learning classification techniques can be used to predict red wine quality from physicochemical properties.

Three classification models were trained and compared: Random Forest, SGD Classifier, and Support Vector Classifier.

Among the tested approaches, Random Forest achieved the best overall performance with an accuracy of 94.38%.

The feature-importance analysis showed that alcohol was the most influential feature, followed by sulphates, density, volatile acidity, and citric acid.

However, the dataset contains a significant imbalance between Good and Not Good wines. The Random Forest model achieved high accuracy and precision but had lower recall for the Good class.

Future improvements could include SMOTE, class weighting, hyperparameter tuning, and cross-validation to improve the model's ability to identify high-quality wines.

Author

Zin Nwe Moe

Computer Science Undergraduate
Global Academy at Siam University, Thailand

📧 sonali.kdk@gmail.com

GitHub: sonali-0973

🎓 Internship

This project was completed as part of the:

Oasis Infobyte Data Analytics Internship

Project: Wine Quality Prediction — Task 4
