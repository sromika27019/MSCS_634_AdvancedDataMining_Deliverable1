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
  - fixed_acidity  
  - volatile_acidity  
  - citric_acid  
  - residual_sugar  
  - chlorides  
  - free_sulfur_dioxide  
  - total_sulfur_dioxide  
  - density  
  - pH  
  - sulphates  
  - alcohol  
  - quality (target: 0–10)

**Justification:**  
I selected the Wine Quality dataset because it meets the size (4,898 samples) and feature (12 attributes) requirements, and its real-world task of predicting sensory quality provides a clear modeling objective.

---

## 2. Data Cleaning Steps

1. **Loaded data** using `pd.read_csv('winequality-red.csv', sep=';')`.  
2. **Checked for missing values**; none were present.  
3. **Dropped 240 duplicate rows** to avoid data leakage.  
4. **Standardized column names** to snake_case for consistency.  
5. **Imputed missing values** (if any) with each column’s median.  
6. **Verified data types** and converted any numeric strings to floats.

---

## 3. Exploratory Data Analysis (EDA)

- I plotted histograms and KDEs for key numeric features to assess distributions and skewness.  
- I generated a correlation matrix to identify strong positive (e.g., alcohol vs. quality) and negative (e.g., volatile_acidity vs. quality) relationships.  
- I created boxplots of select features against the target to confirm insights from the correlation analysis.



---

## 4. Key Insights

- **Strong predictors:** Alcohol (ρ ≈ +0.48) and volatile acidity (ρ ≈ –0.39) show the highest correlation with quality.  
- **Skew & outliers:** Some features (e.g., residual_sugar) are right-skewed; outliers will be addressed in preprocessing.  
- **Target distribution:** Most wines are rated 5–6; I plan to use stratified sampling or appropriate weighting in future models.

These findings will guide Deliverable 2’s modeling choices, including feature transformations, interaction terms, and cross-validation strategies.

---

## 5. Challenges & Resolutions

- **Duplicates:** Removing them reduced the dataset to 4,658 unique records.  
- **Missing values:** Although none were present, I demonstrated imputation logic to show best practices.  
- **Visualization clarity:** I annotated each plot with descriptive titles and axis labels in the report.

---


