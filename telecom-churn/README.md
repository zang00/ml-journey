# Telecom Churn

## Task

Explore telecom customer data and build classifiers for the `Churn` target.

## Notebook and approach

[`notebook.ipynb`](./notebook.ipynb) explores the target and feature relationships, creates a stratified 80/20 train/test split, standardizes features, and fits logistic regression and random forest classifiers. It displays random-forest feature importances. The saved output includes the ranked importances, but the notebook does not print test-set classification metrics.

The notebook expects a file named `telecom_churn.csv` at `/content/telecom_churn.csv` (as commonly used in Colab). The dataset is not included.

## Open and run

Open the notebook in JupyterLab or Google Colab, place the dataset at the path used in the notebook, and install pandas, NumPy, scikit-learn, matplotlib, and seaborn if needed. Run the cells in order.
