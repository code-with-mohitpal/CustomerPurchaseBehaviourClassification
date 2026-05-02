# 🛍️ Customer Purchase Behaviour Prediction System

## 📋 Project Overview

A comprehensive machine learning system that analyzes customer purchase behavior and predicts:
1. **Whether a customer will make a purchase** (Binary Classification)
2. **Expected spending amount** (Regression)

This system helps businesses understand customer behavior, identify high-value customers, and optimize marketing strategies.

---

## 🎯 Project Objectives

### Primary Goals
- **Predict purchase likelihood** for each customer
- **Forecast spending amount** for customers who are likely to purchase
- **Identify key factors** influencing purchase decisions
- **Segment customers** based on purchase probability
- **Provide actionable insights** for marketing optimization

### Business Value
- Increase marketing ROI by targeting right customers
- Reduce customer acquisition costs
- Improve customer retention strategies
- Optimize inventory based on demand prediction
- Personalize customer experience

---

## 📊 Dataset Information

### Source
Marketing campaign dataset containing customer demographic and behavioral data

### Features (24+ attributes)

| Category | Features |
|----------|----------|
| **Demographics** | Age, Income, Education, Marital Status |
| **Family** | Kidhome, Teenhome, Total Children |
| **Purchase History** | Wine, Meat, Fish, Fruits, Sweet, Gold Products |
| **Campaign Data** | AcceptedCmp1-5, Response, Complain |
| **Engagement** | Web Visits, Web Purchases, Store Purchases, Catalog Purchases |
| **Temporal** | Recency, Customer Tenure, Dt_Customer |

### Target Variables
- **Classification**: `Response` (0 = No Purchase, 1 = Purchase)
- **Regression**: `Total_Spending` (Sum of all product purchases)

### Dataset Statistics
- Total Samples: ~2,240 customers
- Response Rate: ~15% (imbalanced dataset)
- Features: 24 original + 10 engineered features

---

## 🏗️ System Architecture

---
┌─────────────────────────────────────────────────────────────┐
│ INPUT DATA │
│ (Customer Demographics + Behavioral Data) │
└─────────────────────────────────────────────────────────────┘
│
▼
┌─────────────────────────────────────────────────────────────┐
│ DATA PREPROCESSING │
│ • Missing Value Handling • Encoding • Scaling │
│ • Feature Engineering • Feature Selection │
└─────────────────────────────────────────────────────────────┘
│
▼
┌─────────────────────────────────────────────────────────────┐
│ EXPLORATORY DATA ANALYSIS │
│ • Correlation Analysis • Pattern Discovery │
│ • Visualization Dashboard │
└─────────────────────────────────────────────────────────────┘
│
┌───────────────┴───────────────┐
▼ ▼
┌─────────────────────────┐ ┌─────────────────────────┐
│ CLASSIFICATION │ │ REGRESSION │
│ (Purchase Prediction) │ │ (Spending Prediction) │
├─────────────────────────┤ ├─────────────────────────┤
│ • Logistic Regression │ │ • Linear Regression │
│ • Naive Bayes │ │ • Gradient Boosting │
│ • XGBoost │ │ │
│ • Gradient Boosting │ │ │
│ • Random Forest │ │ │
└─────────────────────────┘ └─────────────────────────┘
│ │
└───────────────┬───────────────┘
▼
┌─────────────────────────────────────────────────────────────┐
│ MODEL EVALUATION & OPTIMIZATION │
│ • Hyperparameter Tuning • Cross-Validation │
│ • Performance Metrics • Model Selection │
└─────────────────────────────────────────────────────────────┘
│
▼
┌─────────────────────────────────────────────────────────────┐
│ BUSINESS INSIGHTS │
│ • Customer Segmentation • Marketing Strategies │
│ • ROI Projections • Recommendations │
└─────────────────────────────────────────────────────────────┘
......
customer-purchase-prediction/
│
├── data/
│ └── marketing_campaign.csv # Dataset
│
├── notebooks/
│ ├── 01_data_preprocessing.ipynb # Data cleaning & preparation
│ ├── 02_exploratory_analysis.ipynb # EDA & Visualizations
│ ├── 03_model_building.ipynb # Classification & Regression
│ ├── 04_model_evaluation.ipynb # Performance analysis
│ └── 05_business_insights.ipynb # Recommendations
│
├── src/
│ ├── preprocess.py # Data preprocessing functions
│ ├── models.py # Model definitions
│ ├── evaluate.py # Evaluation metrics
│ └── visualize.py # Visualization utilities
│
├── outputs/
│ ├── figures/ # Generated plots
│ ├── reports/ # Performance reports
│ └── models/ # Saved models
│
├── README.md # Project documentation
├── requirements.txt # Dependencies
└── presentation.pptx # Class presentation
.....

---

## 🔧 Technologies Used

### Core Libraries
| Library | Version | Purpose |
|---------|---------|---------|
| Python | 3.8+ | Base language |
| Pandas | 1.3+ | Data manipulation |
| NumPy | 1.21+ | Numerical operations |
| Scikit-learn | 1.0+ | ML models & preprocessing |
| XGBoost | 1.5+ | Gradient boosting |
| Matplotlib | 3.4+ | Visualizations |
| Seaborn | 0.11+ | Statistical visualizations |

### Additional Libraries
- `imbalanced-learn`: Handling imbalanced dataset
- `joblib`: Model serialization
- `warnings`: Suppress unnecessary warnings

---

## 📈 Methodology

### 1. Data Preprocessing

#### Steps Performed:
```python
✓ Missing value imputation (median for numeric, mode for categorical)
✓ Outlier removal (Income, Year_Birth)
✓ Label encoding for categorical variables
✓ StandardScaler for feature normalization
✓ Feature engineering (10 new features)

