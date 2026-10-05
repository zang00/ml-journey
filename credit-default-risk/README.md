# Credit Default Risk Prediction

## Task
Predicting the probability of serious delinquency on a loan within 2 years 
(binary classification) based on the borrower's financial characteristics.

## Dataset
Give Me Some Credit (Kaggle) — 150,000 records, 10 features.
Strong class imbalance: ~93.3% reliable borrowers, ~6.7% defaults.

## What was done
- Data cleaning: handled missing values (MonthlyIncome, NumberOfDependents),
  removed anomalous outliers (age=0, placeholder codes of 98 in delinquency 
  counts, extreme RevolvingUtilization values)
- Feature Engineering: created new features — TotalPastDue (total number 
  of delinquencies), IncomePerDependent (income per dependent)
- 5-Fold cross-validation for honest model evaluation
- Class balancing via class_weight='balanced' — critical due to the 
  strong imbalance

## Key insight: Precision/Recall trade-off
Without class balancing, the model showed high accuracy (93.8%), but 
recall of only 16% — meaning it missed 84% of actual defaults. 
After class_weight='balanced': recall rose to 74%, at the cost of lower 
precision and accuracy. For credit scoring, this is a justified trade-off — 
the cost of a missed default is usually higher than the cost of excess caution.

## Results (test set)
| Metric | Value |
|---|---|
| Accuracy | 0.804 |
| Precision | 0.213 |
| Recall | 0.738 |
| F1 | 0.331 |

## Technologies used
Python, pandas, numpy, scikit-learn, matplotlib, seaborn

---

# Предсказание риска дефолта по кредиту

## Задача
Предсказание вероятности серьёзной просрочки по кредиту в течение 2 лет 
(бинарная классификация) на основе финансовых характеристик заёмщика.

## Датасет
Give Me Some Credit (Kaggle) — 150 000 записей, 10 признаков.
Сильный дисбаланс классов: ~93.3% надёжных заёмщиков, ~6.7% дефолтов.

## Что сделано
- Очистка данных: обработка пропусков (MonthlyIncome, NumberOfDependents),
  удаление аномальных выбросов (age=0, коды-заглушки 98 в просрочках,
  экстремальные значения RevolvingUtilization)
- Feature Engineering: созданы новые признаки — TotalPastDue (суммарное 
  количество просрочек), IncomePerDependent (доход на иждивенца)
- Кросс-валидация (5-Fold) для честной оценки модели
- Балансировка классов через class_weight='balanced' — критично из-за
  сильного дисбаланса

## Ключевой инсайт: компромисс Precision/Recall
Без балансировки классов модель показывала высокую accuracy (93.8%), 
но recall всего 16% — то есть пропускала 84% реальных дефолтов.
После class_weight='balanced': recall вырос до 74%, ценой снижения 
precision и accuracy. Для задачи кредитного скоринга это оправданный 
компромисс — цена пропущенного дефолта обычно выше цены излишней 
осторожности.

## Результаты (test set)
| Метрика | Значение |
|---|---|
| Accuracy | 0.804 |
| Precision | 0.213 |
| Recall | 0.738 |
| F1 | 0.331 |

## Использованные технологии
Python, pandas, numpy, scikit-learn, matplotlib, seaborn
