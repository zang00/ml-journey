# ML Journey

A portfolio of hands-on machine learning and data analysis projects. The notebooks cover customer churn, credit risk, data cleaning, and a logistic regression implementation from scratch.

## Projects

- [Credit Default Risk](./credit-default-risk/) — data cleaning, feature engineering, cross-validation, and class-balanced logistic regression on the Give Me Some Credit dataset.
- [Telecom Churn](./telecom-churn/) — exploratory analysis and logistic regression and random forest models for customer churn.
- [ML From Scratch](./ml-from-scratch/) — a NumPy implementation of logistic regression, compared with scikit-learn.
- [Loan Data Cleaning](./loan-data-cleaning/) — missing-value handling, categorical encoding, and baseline classifiers for a loan dataset.
- [SQL E-commerce Analytics](./sql-ecommerce-analytics/) — a relational schema and SQL analysis exercises.

## Tools used

Python, pandas, NumPy, scikit-learn, XGBoost, matplotlib, and seaborn are imported in the notebooks. SQL files define an e-commerce schema and queries. Some notebooks require dataset files that are not included in this repository; see each project README for expected inputs.

## Repository structure

```text
credit-default-risk/       Credit default notebook and notes
telecom-churn/             Telecom churn notebook and notes
ml-from-scratch/           Logistic regression notebook
loan-data-cleaning/        Loan data preparation and classifier notebook
sql-ecommerce-analytics/   SQL schema and query exercises
```

Open a notebook in JupyterLab or Google Colab. The notebooks may require installing the packages they import and supplying the referenced input data. Datasets and generated model artifacts are intentionally kept out of Git.
