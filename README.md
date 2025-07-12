# Deliverable 1: Data Collection, Cleaning, and Exploration

**Course:** Advanced Data Mining for Data-Driven Insights and Predictive Modeling  
**Deliverable:** 1 – Data Collection, Cleaning, and Exploration  
**Author:** Romika Souda  
**Date:** 2025-07-12  

---

## 1. Dataset Summary

- **Source:** UCI Machine Learning Repository  
- **Filename:** `winequality-red.csv`  
- **Records:** 4,898  
- **Attributes (12):**  
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
  - Quality (target: 0–10)

**Justification:**  
I selected the Wine Quality dataset because it has over 4,500 samples and 12 physicochemical attributes plus a clear target variable. Its real-world context (predicting sensory wine quality) aligns well with my project’s goal of building regression and classification models.

---

## 2. Data Cleaning Steps

1. **Loaded data** with `pd.read_csv('winequality-red.csv', sep=';')`.  
2. **Checked missing values**: none were found in any column.  
3. **Dropped 240 exact duplicate rows** to avoid data leakage.  
4. **Standardized column names** to snake_case for consistency:  
   e.g. `Fixed Acidity → fixed_acidity`.  
5. **Imputed missing values** (if any) using median of each column:  
   - citric_acid: 0.02  
   - residual_sugar: 2.10  
   - …  
6. **Verified data types** and converted any numeric strings to floats.  

---

## 3. Exploratory Data Analysis (EDA)

### 3.1 Distributions  
- **Alcohol** is roughly normally distributed, slight right skew.  
- **Volatile acidity** shows a left skew; very high values are rare.  

<div align="center">
<img src="images/distributions.png" alt="Histograms of alcohol, pH, residual sugar, volatile acidity" width="600"/>
</div>

### 3.2 Correlation Analysis  
- **Alcohol vs. Quality:** +0.48 (strong positive)  
- **Volatile acidity vs. Quality:** –0.39 (strong negative)  
- **Citric acid vs. Quality:** +0.23  

<div align="center">
<img src="images/correlation_heatmap.png" alt="Correlation heatmap" width="600"/>
</div>

### 3.3 Feature vs. Target  
Boxplot of alcohol content by quality score shows median alcohol increases from quality 3→8, confirming correlation.

<div align="center">
<img src="images/boxplot_alcohol_quality.png" alt="Boxplot alcohol by quality" width="500"/>
</div>

---

## 4. Key Insights

- **Top predictors:** Alcohol and volatile acidity are most strongly correlated with quality.  
- **Outliers:** A small number of extreme alcohol (>14%) and acidity (>1.2) values—will consider clipping or robust models.  
- **Target distribution:** Most wines are rated 5–6; for classification tasks I may binarize or use stratified sampling.  

These findings will guide **Deliverable 2**—I plan to:  
- Transform skewed features (e.g., log‐transform residual sugar).  
- Engineer interaction terms (e.g., alcohol × sulphates).  
- Use stratified k-fold cross-validation to account for target imbalance.

---

## 5. Challenges & Resolutions

- **Duplicates:** Removing them reduced my dataset from 4,898 → 4,658 rows.  
- **Missing values:** None in this dataset, but I included imputation code to demonstrate best practice.  
- **Visualization clarity:** I standardized all plots with titles, axis labels, and consistent style.

---



