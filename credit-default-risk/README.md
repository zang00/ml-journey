# Credit Default Risk

## Task

Estimate whether a borrower will experience serious delinquency within two years, using the Give Me Some Credit data.

## Notebook and approach

[`notebook.ipynb`](./notebook.ipynb) inspects the data, handles missing values, filters several anomalous/sentinel values, adds `TotalPastDue` and `IncomePerDependent`, and compares logistic regression evaluation with and without class balancing. The notebook uses five-fold cross-validation on the training data before evaluating a class-balanced logistic regression on a holdout split.

The notebook reads the CSV from a public raw GitHub URL. It does not require a local dataset file when that URL is available.

## Results recorded in the notebook

For the final holdout evaluation, the saved notebook output reports accuracy **0.804**, precision **0.213**, recall **0.738**, and F1 **0.331**. The notebook also reports mean five-fold recall of about **0.159** for the unbalanced model and **0.741** for the class-balanced model. These are the recorded outputs; results can vary if the data or execution environment changes.

## Open and run

Open `notebook.ipynb` in JupyterLab or Google Colab. Install pandas, NumPy, scikit-learn, matplotlib, and seaborn if needed, then run the notebook cells in order. Internet access is needed to load the CSV.
