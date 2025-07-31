# Customer Personality Analysis

> A comprehensive data science project analyzing customer behavior and segmentation to help businesses understand their customers better and optimize marketing strategies.

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://python.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0%2B-green.svg)](https://scikit-learn.org)
[![Pandas](https://img.shields.io/badge/Pandas-1.3%2B-lightblue.svg)](https://pandas.pydata.org)

## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [Dataset Information](#-dataset-information)
- [Key Findings & Insights](#-key-findings--insights)
- [Visualizations](#-visualizations)
- [Methodology](#-methodology)
- [Installation & Usage](#-installation--usage)
- [Results & Conclusions](#-results--conclusions)
- [Technologies Used](#-technologies-used)
- [Future Improvements](#-future-improvements)

## 🎯 Project Overview

Customer Personality Analysis is a detailed analysis of a company's ideal customers. This project helps businesses better understand their customers and makes it easier for them to modify products according to specific needs, behaviors, and concerns of different customer segments.

### Business Value
- **Targeted Marketing**: Instead of marketing to all customers, identify which segments are most likely to purchase specific products
- **Product Optimization**: Modify products based on customer segment preferences
- **Resource Allocation**: Focus marketing budgets on high-value customer segments
- **Customer Retention**: Understand factors that influence customer loyalty

## 📊 Dataset Information

The dataset contains **2,240 customers** with **29 features** across multiple categories:

### 👥 Customer Demographics
- **ID**: Customer's unique identifier
- **Year_Birth**: Customer's birth year
- **Education**: Customer's education level (5 categories)
- **Marital_Status**: Customer's marital status (8 categories)
- **Income**: Customer's yearly household income
- **Kidhome**: Number of children in customer's household
- **Teenhome**: Number of teenagers in customer's household
- **Dt_Customer**: Date of customer's enrollment with the company
- **Recency**: Number of days since customer's last purchase
- **Complain**: 1 if customer complained in the last 2 years, 0 otherwise

### 🛒 Product Purchase Behavior
- **MntWines**: Amount spent on wine in last 2 years
- **MntFruits**: Amount spent on fruits in last 2 years
- **MntMeatProducts**: Amount spent on meat in last 2 years
- **MntFishProducts**: Amount spent on fish in last 2 years
- **MntSweetProducts**: Amount spent on sweets in last 2 years
- **MntGoldProds**: Amount spent on gold in last 2 years

### 🎯 Campaign Response
- **NumDealsPurchases**: Number of purchases made with a discount
- **AcceptedCmp1-5**: Response to marketing campaigns 1-5 (1 if accepted, 0 otherwise)
- **Response**: Response to the last campaign (1 if accepted, 0 otherwise)

### 🛍️ Purchase Channels
- **NumWebPurchases**: Number of purchases made through the company's website
- **NumCatalogPurchases**: Number of purchases made using a catalogue
- **NumStorePurchases**: Number of purchases made directly in stores
- **NumWebVisitsMonth**: Number of visits to company's website in the last month

## 🔍 Key Findings & Insights

### 📈 Demographic Insights
- **Average Customer Age**: 54 years (ranging from 27 to 130 years)
- **Income Distribution**: Mean income ~$52,247 with significant outliers up to $666,666
- **Education Impact**: Postgraduate customers have significantly higher income than undergraduate customers
- **Family Structure**: 
  - 50%+ of customers have children
  - Most customers have 0-2 children or teenagers at home

### 💰 Spending Patterns
- **Total Customer Spending**: More than 50% of customers spend less than $1,000 annually
- **Product Preferences**: 
  - **Wine** is the highest spending category
  - **Meat products** are the second most popular
  - **Fruits** have the lowest spending amounts
- **Distribution**: All product spending shows right-skewed (positive) distributions

### 🛒 Purchase Behavior
- **Channel Preference**: Most purchases are made through **stores** and **websites**
- **Campaign Response**: 
  - 79.3% of customers accepted 0 campaigns
  - 14.6% accepted 1 campaign
  - Only 3.7% accepted 2 campaigns
- **Customer Complaints**: 99% of customers have not complained in the past two years

### 👨‍👩‍👧‍👦 Marital Status Impact
- **Married customers** spend significantly more money than single customers
- **Couples** show higher engagement across all product categories
- **Family size** negatively correlates with luxury spending

### 🎓 Education & Income Correlation
- **Strong correlation** between education level and annual income
- **Postgraduate customers** consistently show higher spending patterns
- **Education** is a key predictor for customer lifetime value

### 📅 Temporal Patterns
- **2013** was the peak year for customer acquisition
- **Seasonal variations** exist in customer spending patterns
- **Customer tenure** affects loyalty and spending behavior

## 📊 Visualizations

The analysis includes comprehensive visualizations:

### 📈 Distribution Analysis
- Age distribution histograms
- Income distribution by education level
- Product spending distributions
- Campaign acceptance rates

### 🔗 Correlation Analysis
- Income vs Age scatter plots
- Education vs Income relationships
- Marital status vs spending patterns
- Product category correlations

### 📋 Categorical Analysis
- Purchase channel preferences
- Campaign response rates
- Customer demographic breakdowns
- Complaint analysis

### 🎯 Segmentation Visualizations
- Customer clustering results
- Segment characteristics
- Purchase behavior by segment

## 🔬 Methodology

### 1. **Data Preprocessing**
- **Missing Value Treatment**: Income column filled using median by education level
- **Feature Engineering**: 
  - Created Age from Year_Birth
  - Combined spending across all products
  - Calculated customer seniority
  - Simplified categorical variables
- **Data Cleaning**: Handled outliers and inconsistent data

### 2. **Exploratory Data Analysis (EDA)**
- **Univariate Analysis**: Distribution analysis for all features
- **Bivariate Analysis**: Correlation and relationship exploration
- **Multivariate Analysis**: Complex relationship patterns

### 3. **Feature Engineering**
- **New Features Created**:
  - `Age`: Current age of customers
  - `Spending`: Total spending across all products
  - `Seniority`: Years as a customer
  - `Children`: Total number of children
  - `Has_child`: Binary indicator for having children
  - `Campaigns_accepted`: Total campaigns accepted

### 4. **Machine Learning Models**
- **Classification Models**:
  - Decision Tree Classifier
  - Random Forest Classifier
  - Logistic Regression
- **Model Evaluation**: Accuracy scores and error analysis
- **Feature Importance**: SHAP values for model interpretability

### 5. **Explainable AI (XAI)**
- **SHAP (SHapley Additive exPlanations)**: Global feature importance
- **LIME (Local Interpretable Model-agnostic Explanations)**: Local explanations
- **Feature importance visualization** for business insights

## 🚀 Installation & Usage

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn plotly scikit-learn yellowbrick shap lime
```

### Running the Analysis
1. **Clone the repository**:
   ```bash
   git clone https://github.com/iamaber/customer-personality-analysis.git
   cd customer-personality-analysis
   ```

2. **Launch Jupyter Notebook**:
   ```bash
   jupyter notebook customer-personality-analysis.ipynb
   ```

3. **Run all cells** to reproduce the complete analysis

### File Structure
```
customer-personality-analysis/
├── customer-personality-analysis.ipynb    # Main analysis notebook
├── marketing_campaign.csv                 # Dataset
├── README.md                              # This file
└── requirements.txt                       # Python dependencies
```

## 📈 Results & Conclusions

### 🎯 Business Recommendations

1. **Targeted Marketing Strategy**:
   - Focus on **married, educated customers** with higher disposable income
   - Develop **premium wine and meat product campaigns** for high-value segments
   - Create **family-oriented marketing** for customers with children

2. **Product Strategy**:
   - **Expand wine portfolio** as it's the highest-spending category
   - **Improve fruit marketing** to increase engagement in this category
   - **Bundle products** for cross-selling opportunities

3. **Channel Optimization**:
   - **Strengthen store and web presence** as preferred purchase channels
   - **Reduce catalog marketing** costs due to lower engagement
   - **Optimize website** for increased monthly visits

4. **Customer Retention**:
   - **Maintain low complaint rates** through quality service
   - **Develop loyalty programs** for long-tenure customers
   - **Create age-specific offerings** for different demographic segments

### 📊 Model Performance
- **Random Forest**: Highest accuracy for campaign response prediction
- **Feature Importance**: Income, spending, and education are top predictors
- **Model Interpretability**: SHAP and LIME provide actionable insights

## 🛠️ Technologies Used

- **Python 3.8+**: Core programming language
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computing
- **Matplotlib & Seaborn**: Statistical visualizations
- **Plotly**: Interactive visualizations
- **Scikit-learn**: Machine learning models
- **SHAP**: Model interpretability
- **LIME**: Local model explanations
- **Jupyter Notebook**: Development environment

## 🚀 Future Improvements

1. **Advanced Segmentation**:
   - Implement **K-means clustering** for customer segmentation
   - **RFM (Recency, Frequency, Monetary) analysis**
   - **Cohort analysis** for customer lifetime value

2. **Predictive Analytics**:
   - **Customer churn prediction** models
   - **Lifetime value estimation**
   - **Next purchase prediction**

3. **Deep Learning**:
   - **Neural networks** for complex pattern recognition
   - **Ensemble methods** for improved accuracy
   - **Time series analysis** for seasonal patterns

4. **Business Intelligence**:
   - **Real-time dashboard** development
   - **A/B testing framework** for campaign optimization
   - **Automated reporting** system

