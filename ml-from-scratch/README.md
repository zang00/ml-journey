# ML From Scratch

## Task

Implement binary logistic regression with NumPy and compare its predictions with scikit-learn.

## Notebook and approach

[`logistic-regression.ipynb`](./logistic-regression.ipynb) uses scikit-learn's built-in breast cancer dataset, scales the features, and implements the sigmoid, gradient updates, and prediction threshold directly with NumPy. It then fits scikit-learn's `LogisticRegression` on the same split for comparison.

The saved outputs report accuracy **0.974**, precision **0.986**, recall **0.972**, and F1 **0.979** for the NumPy implementation; scikit-learn's corresponding values are **0.974**, **0.972**, **0.986**, and **0.979**. The notebook currently covers logistic regression; it does not contain a linear regression notebook.

## Open and run

Open the notebook in JupyterLab or Google Colab. Install NumPy, scikit-learn, and matplotlib if needed, then run the cell. The dataset is bundled with scikit-learn and is downloaded automatically with that package.

The earlier extensionless source file from this repository is retained as [logistic-regression-previous-source.py](./logistic-regression-previous-source.py); the notebook is the primary walkthrough.
