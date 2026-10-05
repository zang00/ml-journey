# Loan Data Cleaning & Model Comparison

## Task
A practice project focused on data cleaning and feature engineering on a 
synthetically generated "messy" dataset — designed to simulate common 
real-world data quality issues. Binary classification target.

## Dataset
Synthetically generated dataset (1,515 rows, 9 columns) intentionally 
containing typical data quality problems:
- Missing values in both numeric and categorical columns
- Inconsistent category labels (e.g. 'M', 'F', 'male', 'female' for the 
  same gender field)
- Outliers (extreme income values)
- Duplicate rows

## What was done
- Missing value handling: numeric columns filled with mean, categorical 
  columns filled with 'Unknown'
- Standardized inconsistent categorical labels (e.g. unified gender values)
- Removed duplicate rows
- One-Hot Encoding for categorical features (city, gender, education, 
  has_loan) using pd.get_dummies()
- Trained and compared three models: Logistic Regression, Random Forest, 
  and XGBoost

## Results
| Model | Accuracy | F1 |
|---|---|---|
| Logistic Regression | 0.71 | 0.823 |
| Random Forest | 0.71 | 0.823 |
| XGBoost | 0.657 | 0.774 |

## Key takeaway
A more advanced model (XGBoost) does not automatically outperform simpler 
models — on this dataset, both Logistic Regression and Random Forest 
outperformed XGBoost with default hyperparameters. This highlights the 
importance of comparing multiple models rather than assuming the most 
sophisticated one is always best, especially without hyperparameter tuning.

## Technologies used
Python, pandas, numpy, scikit-learn, xgboost

---

# Очистка данных по кредитам и сравнение моделей

## Задача
Тренировочный проект, сфокусированный на очистке данных и feature engineering 
на синтетически сгенерированном "грязном" датасете — созданном для имитации 
типичных проблем качества реальных данных. Целевая переменная — бинарная 
классификация.

## Датасет
Синтетически сгенерированный датасет (1515 строк, 9 колонок), намеренно 
содержащий типичные проблемы качества данных:
- Пропуски как в числовых, так и в категориальных колонках
- Неконсистентные значения категорий (например, 'M', 'F', 'male', 'female' 
  для одного и того же поля пол)
- Выбросы (аномально высокие значения дохода)
- Дублирующиеся строки

## Что сделано
- Обработка пропусков: числовые колонки заполнены средним значением, 
  категориальные — значением 'Unknown'
- Приведение неконсистентных категориальных значений к единому формату 
  (например, унификация значений пола)
- Удаление дублирующихся строк
- One-Hot Encoding для категориальных признаков (city, gender, education, 
  has_loan) через pd.get_dummies()
- Обучены и сравнены три модели: Logistic Regression, Random Forest и XGBoost

## Результаты
| Модель | Accuracy | F1 |
|---|---|---|
| Logistic Regression | 0.71 | 0.823 |
| Random Forest | 0.71 | 0.823 |
| XGBoost | 0.657 | 0.774 |

## Ключевой вывод
Более продвинутая модель (XGBoost) не гарантирует автоматически лучший 
результат — на этом датасете и Logistic Regression, и Random Forest 
показали себя лучше, чем XGBoost с дефолтными гиперпараметрами. Это 
подчёркивает важность сравнения нескольких моделей, а не предположения, 
что самая сложная модель всегда лучшая, особенно без тюнинга гиперпараметров.

## Использованные технологии
Python, pandas, numpy, scikit-learn, xgboost
