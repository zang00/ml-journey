# Loan Data Cleaning

## Task

Prepare a loan dataset for binary classification and compare baseline classifiers.

## Notebook and approach

[`notebook.ipynb`](./notebook.ipynb) inspects missing values, standardizes some categorical labels, imputes missing values, removes duplicate rows, one-hot encodes selected columns, scales the features, and fits logistic regression, random forest, and XGBoost classifiers. Its saved output reports accuracy and F1 for each model: logistic regression **0.710 / 0.823**, random forest **0.710 / 0.823**, and XGBoost **0.657 / 0.774**.

The notebook expects `messy_loan_data.csv` in its current working directory. That input is not included, so the recorded outputs cannot be reproduced without obtaining the matching dataset. The notebook imports XGBoost and LightGBM; only XGBoost is used in the shown modeling cells.

## Open and run

Open the notebook in JupyterLab or Google Colab, put the dataset beside the notebook, install pandas, NumPy, scikit-learn, matplotlib, seaborn, and XGBoost if needed, then run the cell.
