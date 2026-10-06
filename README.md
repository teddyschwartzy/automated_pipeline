# Diabetes Prediction and Automated Analysis Pipeline

## Overview

This project explores an automated analytical workflow using the Pima Indians Diabetes Database. The notebook demonstrates how statistical analysis and machine learning workflows can be automated through conditional logic that adapts preprocessing, analysis, visualization, and modeling decisions based on dataset characteristics and user-defined settings.

The project was completed as part of a Health Data Science and AI Analytics assignment focused on understanding automated analytical pipelines, reproducible workflows, inferential statistics, and supervised machine learning.

---

## Dataset

The analysis uses the Pima Indians Diabetes Database, a publicly available dataset originally collected by the National Institute of Diabetes and Digestive and Kidney Diseases (NIDDK).

### Dataset Characteristics

- 768 observations
- 9 variables
- Binary classification outcome
- Diabetes outcome coded as:
  - 0 = No Diabetes
  - 1 = Diabetes

### Variables

| Variable | Description |
|-----------|------------|
| Pregnancies | Number of pregnancies |
| Glucose | Plasma glucose concentration |
| D_BP | Diastolic blood pressure |
| Skin_Thickness | Triceps skin fold thickness |
| Insulin | Serum insulin level |
| BMI | Body mass index |
| Pedigree | Diabetes pedigree function |
| Age | Age in years |
| Outcome | Diabetes status |

---

## Project Objectives

This notebook demonstrates:

- Automated data ingestion
- Data validation and cleaning
- Missing-value detection and handling
- Exploratory data analysis (EDA)
- Inferential statistical testing
- Machine learning model training
- Model performance evaluation
- Threshold optimization
- Automated analytical decision-making through conditional logic

---

## Automated Pipeline Workflow

The workflow follows the structure below:

1. Data Import
   - Automatically detects file format
   - Loads CSV, Excel, JSON, or Parquet files

2. Data Inspection
   - Reviews variable types
   - Evaluates dataset dimensions
   - Generates descriptive statistics

3. Data Cleaning
   - Identifies invalid values
   - Replaces impossible measurements with missing values

4. Missing Data Handling
   - Detects missing observations
   - Applies automated imputation procedures

5. Exploratory Data Analysis
   - Summary statistics
   - Correlation analysis
   - Heatmaps
   - Distribution plots
   - Comparative visualizations

6. Inferential Statistics
   - One-sample t-test
   - Independent-samples t-test
   - One-way ANOVA
   - Chi-square test

7. Machine Learning
   - Logistic Regression
   - Decision Tree
   - Random Forest (added modification)

8. Model Evaluation
   - Confusion matrices
   - Accuracy
   - Precision
   - Recall
   - F1 Score
   - ROC AUC

9. Threshold Optimization
   - Cross-validation
   - Youden's J statistic
   - ROC curve analysis

---

## Assignment Modifications

To demonstrate understanding of the automated workflow, the following modifications were implemented:

- Automated Data Validation: Added a guardrail to verify that all required columns are present upon upload, preventing runtime errors.
- Feature Correlation Analysis: Integrated a correlation heatmap to visualize the relationship between biological markers (e.g., Glucose, BMI) and the target outcome.
- Adaptive Imputation Strategy: Implemented conditional logic that automatically switches between Mean and Median imputation based on the dataset's missingness rate.
- Random Forest Addition: Expanded the ML suite by adding a Random Forest Classifier to compare ensemble performance against linear and single-tree models.
- Consolidated Performance Benchmarking: Created a unified comparison table sorted by ROC AUC for efficient model selection.
- Model Diagnostics (ROC Curves): Integrated ROC curve visualizations to evaluate the trade-off between sensitivity and specificity across all classification thresholds.

---

## Key Findings

### Predictor Analysis
Through a combination of correlation heatmaps and model feature importance analysis, several variables were identified as having a strong relationship with diabetes status:
- Glucose: The most significant predictor across all models.
- BMI & Age: Demonstrated strong positive correlations with the outcome.
- Insulin: Showed meaningful influence, although it had a higher rate of missing values.

### Model Performance
The pipeline compared three different architectural approaches: Linear (Logistic Regression), Non-Linear Single Tree (Decision Tree), and Non-Linear Ensemble (Random Forest).

#### Top Performer: The Random Forest Classifier produced the strongest overall performance, achieving the highest ROC AUC and the best balance between Precision and Recall.
#### Comparative Insight: While Logistic Regression provided a strong baseline, the Random Forest's ability to handle non-linear relationships resulted in a curve that bowed furthest toward the top-left of the ROC plot, indicating superior sensitivity and specificity.
#### Model Stability: The Decision Tree showed the highest variance, confirming that an ensemble approach (Random Forest) is necessary to reduce overfitting for this specific clinical dataset.

---

## Required Libraries

The notebook uses the following Python packages:

```python
pandas
numpy
matplotlib
seaborn
scipy
statsmodels
scikit-learn
phik
```

---

## Running the Analysis

### Open the Notebook: Click the link below or open the .ipynb file in Google Colab.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1-owFIoktTtmlKcHyTtSQpGGmBgiMvVSe?usp=sharing)

### Execute Cells: Run the cells sequentially from top to bottom.

### Upload Data: When prompted by the upload widget in the first block, upload the diabetes data .CSV file.

### Review Outputs: The pipeline will automatically handle cleaning, imputation, training, and evaluation, ending with the Comparison Table and ROC Curve.

---

## Repository Structure

├── Automated_Analysis_Pipeline_Notebook.ipynb
├── Example+Dataset_Diabetes.csv
└── README.md

---

## Reproducibility

The notebook was designed to execute from start to finish without requiring manual intervention beyond dataset upload. Random seeds are specified where applicable to support reproducibility of model results.

---

## Assumptions and Limitations

### Assumptions

- Uploaded datasets are correctly formatted.
- Outcome variable represents a binary classification problem.
- Predictor variables are primarily numeric.

### Limitations

- Results are specific to the Pima Indians Diabetes dataset.
- Dataset size is relatively small compared to many modern machine learning applications.
- Performance estimates may vary with alternate train/test splits.
- Feature importance does not imply causation.

---

## Author

Hunter Schwarz

MS Health Data Science

Dartmouth College - Geisel School of Medicine
