# Customer Shopping Behavior Analytics & ML

An end-to-end **Data Analytics + Machine Learning** project analyzing 3,900 retail customer transactions using **Python, SQL, Power BI, Scikit-learn, XGBoost, and SHAP**.

The project combines business analytics with machine learning to understand customer behavior, identify customer segments, classify subscription status, compare ML models, and explain model predictions.

> **Attribution:** This project is an extended version of an existing customer shopping behavior analytics project. The ML modeling, K-Means segmentation, SHAP explainability, and ML-focused Power BI dashboard were added in this version. Retain the original attribution and license terms if this repository was forked.

## Project Highlights

- Analyzed **3,900 customer transactions**
- Data cleaning and EDA with Python/Pandas
- Business analysis using SQL
- Interactive Power BI dashboards
- **K-Means** customer behavioral segmentation
- Subscription classification using **Logistic Regression, Random Forest, and XGBoost**
- Evaluation using Accuracy, Precision, Recall, F1-score, and ROC-AUC
- **SHAP** explainability for subscription predictions

## Business Problem

The project answers:

1. Who are the customers?
2. How do customer behaviors differ across segments?
3. Can subscription status be classified from observed shopping behavior?
4. Which ML model performs best?
5. Which factors contribute most to model predictions?
6. How can the findings support customer engagement decisions?

## Dataset

The dataset contains **3,900 records** and includes demographics, products, purchases, subscription status, shipping, discounts, payment methods, and purchase frequency.

Key fields include:

- Age
- Gender
- Category
- Purchase Amount
- Location
- Season
- Review Rating
- Subscription Status
- Shipping Type
- Discount Applied
- Previous Purchases
- Payment Method
- Frequency of Purchases

## Workflow

```text
Raw Data
   ↓
Data Cleaning & EDA
   ├──→ SQL Business Analysis
   ↓
Feature Engineering
   ├──→ K-Means Customer Segmentation
   └──→ Subscription Classification
             ├── Logistic Regression
             ├── Random Forest
             └── XGBoost
                     ↓
              Model Comparison
                     ↓
                  SHAP
                     ↓
               Power BI
```

## Customer Segmentation — K-Means

K-Means was applied using behavioral features including:

- Age
- Purchase Amount
- Review Rating
- Previous Purchases
- Purchase Frequency

The Elbow Method was used to evaluate cluster counts, with **4 clusters** selected based on the curve and business interpretability.

The resulting clusters were profiled using age, purchase history, ratings, purchase amount, and customer count. The clusters are primarily differentiated by **age and purchase history**, while average purchase amounts are relatively similar.

## Subscription Classification

Target:

```text
Subscription Status
Yes → 1
No  → 0
```

Categorical variables were encoded with `OneHotEncoder`, numerical variables were standardized with `StandardScaler`, and preprocessing was combined with model training using a Scikit-learn `Pipeline`.

### Models

| Model | Role |
|---|---|
| Logistic Regression | Interpretable baseline |
| Random Forest | Non-linear ensemble |
| XGBoost | Gradient boosting |

## Model Performance

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| **Logistic Regression** | **85.77%** | **68.38%** | **88.15%** | **0.7702** | **91.19%** |
| Random Forest | 85.00% | 66.32% | **90.52%** | 0.7655 | 91.12% |
| XGBoost | 83.97% | 66.93% | 80.57% | 0.7312 | 90.78% |

**Best overall model:** Logistic Regression, based on the highest Accuracy, Precision, F1-score, and ROC-AUC.

Random Forest produced slightly higher Recall, which can be useful when the business priority is to identify as many potential subscribers as possible.

## Explainable AI — SHAP

SHAP was used to explain the Logistic Regression classifier.

The analysis includes:

- Global feature importance
- Direction and magnitude of feature contributions
- SHAP summary visualizations
- Top subscription-related factors for Power BI

## Power BI Dashboard

### Page 1 — Customer Behavior Dashboard

- Total customers
- Average purchase amount
- Average review rating
- Subscription distribution
- Revenue and sales by category
- Revenue and sales by age group
- Interactive filters

### Page 2 — Customer Intelligence & ML

- Total customers
- Subscription rate
- Best model accuracy
- Best ROC-AUC
- Customer segment distribution
- Average purchase amount by segment
- K-Means segmentation
- Model accuracy comparison
- Model ROC-AUC comparison
- Top 10 SHAP factors

## Key Results

- **3,900** records analyzed
- **27%** subscription rate
- Approximately **$59.76** average purchase amount
- Approximately **3.75** average review rating
- **4** behavioral customer clusters
- **85.77%** best classification accuracy
- **91.19%** best ROC-AUC
- SHAP used for model explainability

## Repository Structure

```text
Customer-Shopping-Behavior/
│
├── notebooks/
│   └── customer-trends-organized.ipynb
│
├── README.md
│
└── ml_outputs/
    ├── customer_behavior_ml.csv
    ├── cluster_summary.csv
    ├── model_comparison.csv
    └── shap_feature_importance.csv
```

## Installation

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost shap jupyter
```

## Run

```bash
jupyter notebook
```

Open `notebooks/customer-trends-organized.ipynb` and run the sections in order:

```text
Data Loading
→ Data Cleaning
→ EDA
→ Feature Engineering
→ K-Means
→ Classification
→ Model Evaluation
→ SHAP
→ Export ML Results
```

## Future Improvements

- Hyperparameter tuning with cross-validation
- Probability calibration
- Better longitudinal customer data for true future-subscription prediction
- Model monitoring
- Automated Power BI refresh
- FastAPI model deployment
- Customer recommendation engine

## Author

**Yash Gupta**  
MCA | Data Analytics | Machine Learning | AI

GitHub: [yashguptak](https://github.com/yashguptak)

## License

See `LICENSE` for the applicable license and attribution terms.
