# 📊 Customer Churn Prediction & Analysis

> **A data-driven approach to identifying and reducing customer churn in the telecommunications industry**

![Project Status](https://img.shields.io/badge/Status-Complete%20EDA-green)
![Python](https://img.shields.io/badge/Python-3.11-blue)
![License](https://img.shields.io/badge/License-MIT-yellow)

---

## 🎯 Project Overview

**Business Problem:**  
StreamTech, a telecommunications company, is experiencing a **26.54% customer churn rate**, resulting in approximately **$1.46M in annual revenue loss**. This project analyzes customer data to identify the key drivers of churn and provides actionable recommendations to reduce customer attrition.

**Analysis Objective:**  
Identify which customer segments are most likely to churn and why, enabling targeted retention strategies that maximize ROI.

**Key Achievement:**  
Identified retention strategies with potential to save **$1.1M annually** by targeting high-risk customer segments.

---

## 📁 Project Structure
```
user-churn-prediction/
│
├── data/
│   ├── raw/                          # Original dataset
│   │   └── Telco-Customer-Churn.csv
│   └── processed/                    # Processed data for ML
│       ├── X_train.csv
│       ├── X_test.csv
│       ├── y_train.csv
│       └── y_test.csv
│
├── notebooks/
│   ├── 01_exploratory_data_analysis.ipynb    # EDA with visualizations
│   ├── 02_feature_engineering.ipynb          # Data preprocessing
│   └── 03_predictive_modeling.ipynb          # ML models & evaluation
│
├── results/                          # Visualizations and outputs (future)
│
├── requirements.txt                  # Python dependencies
└── README.md                         # Project documentation
```

## 🔍 Key Findings

### Overall Churn Status
- **26.54% churn rate** - approximately 1 in 4 customers are leaving
- **1,869 customers** churned out of 7,043 total
- **Assessment:** CRISIS LEVEL (industry standard: 5-10%)

### Top Churn Drivers (Ranked by Impact)

| Rank | Factor | High Risk | Churn Rate | Low Risk | Churn Rate | Gap |
|------|--------|-----------|------------|----------|------------|-----|
| 🥇 | **Contract Type** | Month-to-month | 42.71% | Two-year | 2.83% | **39.88%** |
| 🥈 | **Customer Tenure** | 0-12 months | 47.44% | 25+ months | 14.04% | **33.40%** |
| 🥉 | **Payment Method** | Electronic check | 45.29% | Credit card | 15.24% | **30.05%** |
| 4 | **Age Group** | Seniors | 41.68% | Non-seniors | 23.61% | 18.07% |
| 5 | **Monthly Charges** | High ($74 avg) | Higher | Low ($61 avg) | Lower | $13 |
| 6 | **Partner Status** | No partner | 32.96% | Has partner | 19.66% | 13.30% |

### Critical Insights

🔴 **High-Risk Customer Profile**
- Month-to-month contracts
- Electronic check payment
- Tenure < 12 months
- Higher monthly charges ($70+)
- Senior citizens without partners
- **Estimated churn probability: 60-70%**

🟢 **Low-Risk Customer Profile**
- Two-year contracts
- Automatic payments
- Tenure > 25 months
- Moderate charges ($60-65)
- Non-seniors with partners
- **Estimated churn probability: 5-10%**

---

## 💡 Key Insights

### 1. Contract Type is the Dominant Factor
Month-to-month customers churn at **15x the rate** of two-year contract customers. 55% of the customer base (3,875 customers) are on this high-risk contract type.

### 2. The First Year is Make-or-Break
New customers face a **47.44% churn rate** in their first 12 months. After 25 months, churn drops dramatically to **14.04%**.

### 3. Payment Method Reflects Customer Commitment
Electronic check users pay **$77/month** (highest) and churn at **45.29%**. In contrast, mailed check users pay only **$42/month** with just **19% churn**.

### 4. Factors are Interconnected
Churn results from **combinations** of risk factors:
- Month-to-month + E-check + New customer = ~60% churn
- Two-year + Autopay + Veteran = ~5% churn

---

## 🤖 Machine Learning Results

### Model Performance

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| **Logistic Regression** | **80.4%** | **65.4%** | **55.6%** | **60.1%** |
| Random Forest | 78.9% | 62.7% | 50.3% | 55.8% |

**Winner:** Logistic Regression outperformed Random Forest on all metrics.

### Key Insights from Modeling

**Top 5 Most Important Features:**
1. **TotalCharges** (18.6%) - Lifetime customer value
2. **MonthlyCharges** (17.3%) - Monthly payment amount  
3. **Tenure** (15.2%) - Customer age/loyalty
4. **Contract_Month-to-month** (6.3%) - Contract flexibility
5. **InternetService_Fiber optic** (3.5%) - Service type

**Model validates EDA findings:** The features we identified in exploratory analysis as most important for churn (contract type, tenure, charges) are also what the ML model considers most predictive.

### Confusion Matrix Results
- **Correctly identified 925/1035 customers who stayed** (89% accuracy on retention)
- **Correctly identified 208/374 customers who churned** (56% catch rate)
- **166 churners missed** (opportunity for model improvement)

### Business Value
The model can identify 56% of at-risk customers before they churn, enabling proactive retention efforts worth an estimated **$13,520/month** in saveable revenue.


## 🎯 Business Recommendations

### Priority 1: Contract Strategy (Highest Impact)
**Target:** Convert 50% of month-to-month customers to annual contracts
- Make two-year contracts the default during signup
- Offer 20-30% discounts for annual commitments
- Proactive upgrade campaigns for existing customers
- **Expected savings: $365,400 annually**

### Priority 2: Payment Method Migration
**Target:** Migrate electronic check users to automatic payments
- 10% discount for enabling autopay
- Add manual processing fee for e-check
- Simplify autopay setup process
- **Expected savings: $213,240 annually**

### Priority 3: First-Year Retention Program
**Target:** Reduce new customer churn from 47% to 30%
- Enhanced onboarding (days 1-30)
- Proactive engagement (months 1-6)
- Contract upgrade offers (month 6-12)
- **Expected savings: $273,000 annually**

### Combined Impact
**Total estimated annual savings: $1,097,400**  
**Implementation cost: $450,000**  
**Net benefit Year 1: $647,400 (144% ROI)**  
**3-year value: $3.29M**

---

## 🛠️ Technologies Used

- **Python 3.11** - Primary programming language
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computations
- **Matplotlib & Seaborn** - Data visualization (future)
- **Jupyter Notebook** - Interactive development environment
- **Scikit-learn** - Machine learning (future)

---

## 📊 Dataset

**Source:** [Kaggle - Telco Customer Churn Dataset](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

**Size:** 7,043 customers, 21 features

**Features Include:**
- Demographics (gender, senior citizen status, partner, dependents)
- Services (phone, internet, streaming, security)
- Account information (tenure, contract, payment method, charges)
- Target variable (Churn: Yes/No)

---

### Clone the repository

bash git clone [github](https://github.com/emiataehi/user-churn-prediction.git)
cd user-churn-prediction


### Install 

**Clone the repository**


git clone [github](https://github.com/emiataehi/user-churn-prediction.git)
cd user-churn-prediction

**Install dependencies**

bash pip install -r requirements.txt


**Download the dataset**

Download from Kaggle
Place Telco-Customer-Churn.csv in data/raw/ folder


**Run the analysis**

bashjupyter notebook notebooks/01_exploratory_data_analysis.ipynb

---

## 📈 Project Roadmap

- [x] **Phase 1:** Exploratory Data Analysis ✅ COMPLETE
  - [x] Data loading and quality assessment
  - [x] Univariate and bivariate analysis
  - [x] Customer segmentation analysis
  - [x] Business insights and recommendations
  - [x] 5 professional visualizations

- [x] **Phase 2:** Feature Engineering ✅ COMPLETE
  - [x] Handle categorical variables (18 columns encoded)
  - [x] Fix data types (TotalCharges conversion)
  - [x] Feature scaling (StandardScaler)
  - [x] Train/test split (80/20)
  - [x] Created 26 ML-ready features

- [x] **Phase 3:** Predictive Modeling ✅ COMPLETE
  - [x] Train/test split
  - [x] Model training (Logistic Regression, Random Forest)
  - [x] Model evaluation and comparison
  - [x] Feature importance analysis
  - [x] Performance visualization



## 💼 Business Impact
**Problem Quantified**

1,869 customers churning annually
Average customer value: $65/month
Total annual revenue at risk: $1,457,580

**Solution Proposed**
Targeted retention strategies focusing on:

Contract conversions (month-to-month → annual)
Payment method improvements (e-check → autopay)
First-year customer engagement

**Expected Outcomes**

Reduce overall churn from 26.54% → 18% within 12 months
Save 1,597 customers annually
ROI: 144% in Year 1, increasing thereafter

### Model Deployment Value

**Current State:**
- Reactive approach: Only know customers churned after they leave
- No early warning system
- Miss opportunities to save customers

**With ML Model:**
- **Proactive approach:** Score all customers monthly for churn risk
- **Target top 20% highest risk** (can save ~56% of them)
- **Estimated impact:** 
  - Save 208 of 374 monthly churners
  - Revenue saved: $162,240 annually (208 × $65 × 12)
  - Combined with contract/payment strategies: **$1.26M total annual impact**

**ROI:** Implementing this model pays for itself in the first month.


## 📝 Key Learnings & Skills Demonstrated

Through this end-to-end project, I demonstrated:

### Technical Skills
- ✅ **Python Programming:** Pandas, NumPy, scikit-learn, matplotlib, seaborn
- ✅ **Data Cleaning:** Handled missing values, data type conversions, outlier detection
- ✅ **Feature Engineering:** Encoded 18 categorical variables, scaled features, created 26 ML-ready features
- ✅ **Machine Learning:** Built and compared classification models (Logistic Regression, Random Forest)
- ✅ **Model Evaluation:** Accuracy, precision, recall, F1-score, confusion matrix analysis
- ✅ **Data Visualization:** Created 5+ professional visualizations to communicate insights

### Analytical Skills
- ✅ **Exploratory Data Analysis:** Analyzed 8 customer factors, identified patterns and correlations
- ✅ **Statistical Thinking:** Evaluated factor significance and interaction effects
- ✅ **Feature Importance:** Identified top predictive features matching business insights
- ✅ **Problem Solving:** Identified root causes of churn, not just symptoms

### Business Skills
- ✅ **Business Acumen:** Translated data insights into $1.26M in actionable strategies
- ✅ **ROI Analysis:** Quantified financial impact of recommendations
- ✅ **Communication:** Presented technical findings in business-friendly language
- ✅ **Strategic Planning:** Prioritized recommendations by impact and feasibility

### Project Management
- ✅ **End-to-End Workflow:** Completed full data science pipeline from raw data to deployment recommendations
- ✅ **Documentation:** Professional README, clear code comments, reproducible analysis
- ✅ **Version Control:** Organized project structure on GitHub


👤 Author
**IGEIN EMIATAEHI HOPE**

- LinkedIn: [My LinkedIn](https://www.linkedin.com/in/emi-igein-b024a8147/)
- GitHub: [emiataehi](https://github.com/emiataehi)
- Email: emi.igein@gmail.com


📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

🙏 Acknowledgments

Dataset provided by IBM Sample Datasets
Available on Kaggle: Telco Customer Churn
Inspired by real-world telecom industry challenges



📫 Contact
Questions or suggestions? Feel free to reach out!

- Open an issue in this repository
- Connect with me on [My LinkedIn](https://www.linkedin.com/in/emi-igein-b024a8147/)
- Email: emi.igein@gmail.com

⭐ If you found this project helpful, please consider giving it a star!








