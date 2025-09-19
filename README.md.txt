# Creditworthiness Prediction Project

## Overview
This project addresses the problem of predicting whether a credit applicant is creditworthy or not based on available applicant and loan data. It supports financial institutions in making lending decisions and managing credit risk by assessing the likelihood that an individual will be a good (creditworthy) or bad (non-creditworthy) credit risk.

## Objective
- Formulate the problem as a supervised binary classification task.
- Predict the binary target variable:
  - 1: Applicant is creditworthy (good credit risk)
  - 2: Applicant is not creditworthy (bad credit risk)
- Utilize applicant characteristics and loan details as features.

## Dataset
The dataset contains 1000 samples with 20 feature columns representing:
- Applicant attributes such as age, employment, marital status, etc.
- Loan details such as credit amount, duration, installment rates, etc.

Example features include:
- checking account status
- credit history
- purpose of loan
- credit amount
- savings account
- employment duration
- installment rate
- personal status and sex
- age in years
- number of existing credits
- foreign worker status
- and more

The target variable is `creditworthy` with values 1 (good) or 2 (bad).

## Data Preprocessing
- Handling missing values for certain categorical features.
- Encoding categorical variables using one-hot encoding.
- Standardization of numerical features using z-score normalization.

## Models and Methods
- Baseline model using majority class prediction.
- Decision tree classifiers.
- Random forest classifiers with nested cross-validation for hyperparameter tuning.
- Support Vector Machine (SVM) with polynomial and RBF kernels evaluated.
- Evaluation metrics include accuracy, precision, recall, ROC-AUC, and a custom project cost model.

## Project Cost Model
The evaluation incorporates a cost-sensitive metric where:
- False Positives (predicting creditworthy when actually not) have a higher penalty (cost = 5).
- False Negatives (predicting not creditworthy when actually creditworthy) have a lower penalty (cost = 1).

This reflects the real-world cost impact of credit decisions.

## Evaluation
- Nested cross-validation with 5 outer folds and 3 inner folds to tune hyperparameters.
- Performance reported includes average accuracy, precision, recall, AUC, and cost across folds.
- Baseline model yields 70% accuracy but random ROC-AUC (0.5) and a high average cost of 150.
- Tuned Random Forest model achieves improved discrimination with AUC ~0.79 and significantly reduces project cost.
- Precision-recall and ROC curves are plotted for detailed analysis.

## Results Summary
- Best Random Forest models provide balanced trade-offs between recall and precision, reducing costly false positives.
- Polynomial SVM kernel outperforms RBF in cost-sensitive evaluation despite slightly lower recall.
- Overall, the tuned models provide more informed creditworthiness predictions compared to the majority baseline.

## Usage
- The notebook is organized into sections: data loading, preprocessing, baseline evaluation, model training, nested cross-validation, and result visualization.
- Metrics and costs guide model selection aligned to the project's financial risk considerations.
- The approach can be adapted or extended for different lending datasets or alternative cost models.

## Requirements
- Python 3.x
- Libraries: numpy, pandas, seaborn, matplotlib, scikit-learn

---

For detailed code and analysis, please refer to the `Credit.ipynb` notebook included.
