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
user-churn-prediction/
│
├── data/
│   ├── raw/                          # Original dataset
│   └── processed/                    # Cleaned data (future)
│
├── notebooks/
│   └── 01_exploratory_data_analysis.ipynb    # Main EDA notebook
│
├── results/                          # Visualizations and outputs (future)
│
├── requirements.txt                  # Python dependencies
└── README.md                         # Project documentation

---

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

## 🚀 Getting Started

### Prerequisites
```bash
Python 3.11+
pip
Installation

Clone the repository

bashgit clone https://github.com/[your-username]/user-churn-prediction.git
cd user-churn-prediction

Install dependencies

bashpip install -r requirements.txt

Download the dataset


Download from Kaggle
Place Telco-Customer-Churn.csv in data/raw/ folder


Run the analysis

bashjupyter notebook notebooks/01_exploratory_data_analysis.ipynb

📈 Project Roadmap

 Phase 1: Exploratory Data Analysis

 Data loading and quality assessment
 Univariate and bivariate analysis
 Customer segmentation analysis
 Business insights and recommendations


 Phase 2: Feature Engineering (Coming Soon)

 Handle categorical variables
 Create interaction features
 Feature scaling and transformation


 Phase 3: Predictive Modeling (Coming Soon)

 Train/test split
 Model training (Logistic Regression, Random Forest, XGBoost)
 Model evaluation and comparison
 Feature importance analysis


 Phase 4: Deployment & Monitoring (Coming Soon)

 Model deployment strategy
 Real-time churn prediction system
 Monitoring dashboard




💼 Business Impact
Problem Quantified

1,869 customers churning annually
Average customer value: $65/month
Total annual revenue at risk: $1,457,580

Solution Proposed
Targeted retention strategies focusing on:

Contract conversions (month-to-month → annual)
Payment method improvements (e-check → autopay)
First-year customer engagement

Expected Outcomes

Reduce overall churn from 26.54% → 18% within 12 months
Save 1,597 customers annually
ROI: 144% in Year 1, increasing thereafter


📝 Key Learnings
Through this project, I demonstrated:

✅ Business Acumen: Translated data insights into actionable business strategies
✅ Data Analysis: Conducted comprehensive EDA to identify patterns and relationships
✅ Statistical Thinking: Evaluated factor significance and interaction effects
✅ Communication: Presented technical findings in business-friendly language
✅ Problem Solving: Identified root causes, not just symptoms
✅ Strategic Planning: Prioritized recommendations by impact and feasibility

👤 Author
**IGEIN EMIATAEHI HOPE**

- LinkedIn: [linkedin.com/in/emi-igein-b024-8147](https://www.linkedin.com/in/emi-igein-b024-8147)
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
- Connect with me on [LinkedIn](https://www.linkedin.com/in/emi-igein-b024-8147)
- Email: emi.igein@gmail.com

⭐ If you found this project helpful, please consider giving it a star!