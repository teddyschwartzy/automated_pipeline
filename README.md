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

### Modification 1: Adaptive Imputation Logic

The original workflow used a fixed median-imputation strategy.

The notebook was modified to automatically select either mean or median imputation based on the overall proportion of missing data in the training set. This extends the notebook's conditional decision-making process and makes preprocessing more adaptive.

### Modification 2: Random Forest Classification Model

A Random Forest classifier was added to the existing machine learning workflow.

This provided an additional supervised learning model for comparison against Logistic Regression and Decision Tree models and allowed evaluation of ensemble-based classification performance.

### Modification 3: ROC Curve Comparison Visualization

A comparative ROC visualization was added to display the predictive performance of all models on the same figure.

This enhancement improves interpretability and simplifies model comparison.

---

## Key Findings

Several variables demonstrated meaningful relationships with diabetes status, particularly:

- Glucose
- BMI
- Insulin
- Age

Among the evaluated models, Logistic Regression produced the strongest overall performance, achieving the highest ROC AUC and better overall classification metrics than the Decision Tree model.

Feature importance analysis from the tuned Decision Tree identified:

1. Glucose
2. BMI
3. Age

as the most influential predictors within the model.

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

### Option 1: Google Colab

Click the badge below:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svgHERE)

1. Open the notebook in Colab.
2. Upload the dataset when prompted.
3. Run all notebook cells from top to bottom.
4. Review generated outputs, visualizations, and model results.

### Option 2: Local Execution

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
```

Navigate to the project folder:

```bash
cd YOUR_REPOSITORY
```

Install required dependencies:

```bash
pip install pandas numpy matplotlib seaborn scipy statsmodels scikit-learn phik
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open the notebook and execute all cells sequentially.

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
