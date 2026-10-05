# Telecom Customer Churn Prediction

## Task
Predicting telecom customer churn based on usage behavior and plan 
characteristics. Binary classification: will the customer leave (1) 
or stay (0).

## Dataset
Telecom Churn (Kaggle) — 3,333 rows, 11 features, no missing values.

## Key EDA findings
- Class imbalance: ~85.5% of customers stay, ~14.5% churn
- Customers with more frequent support calls statistically churn more often
- All features are numeric, no missing data

## Approach
1. Exploratory Data Analysis (EDA): distributions, group comparisons, correlations
2. Stratified train/test split (stratify=y) — preserving class balance
3. Feature scaling (StandardScaler)
4. Training two models: Logistic Regression and Random Forest
5. Evaluation via precision/recall/f1 (accuracy is not reliable due to imbalance)
6. Feature importance analysis

## Feature importance (Random Forest)

Strongest predictors of churn:
1. DayMins (daytime call minutes)
2. MonthlyCharge (monthly bill)
3. CustServCalls (customer service calls)

## Conclusions
Churn is most strongly linked to service usage intensity and customer 
experience quality (frequency of support calls). The business should 
prioritize monitoring customers with high DayMins/MonthlyCharge and 
frequent support calls as a churn risk group.

## Technologies used
Python, pandas, numpy, scikit-learn, matplotlib, seaborn

---

# Предсказание оттока клиентов телеком-компании

## Задача
Предсказание оттока клиентов телеком-компании на основе их поведения, 
использования услуг и характеристик тарифа. Бинарная классификация: 
уйдёт клиент (1) или останется (0).

## Датасет
Telecom Churn (Kaggle) — 3333 строки, 11 признаков, без пропущенных значений.

## Ключевые находки EDA
- Дисбаланс классов: ~85.5% клиентов остаются, ~14.5% уходят
- Клиенты, обращавшиеся в поддержку чаще, статистически чаще уходят
- Все признаки числовые, пропусков в данных нет

## Подход
1. Разведочный анализ данных (EDA): распределения, групповые сравнения, корреляции
2. Train/test split со стратификацией (stratify=y) — сохранение баланса классов
3. Масштабирование признаков (StandardScaler)
4. Обучение двух моделей: Logistic Regression и Random Forest
5. Оценка через precision/recall/f1 (accuracy не показательна из-за дисбаланса)
6. Анализ важности признаков (Feature Importance)

## Важность признаков (Random Forest)

Наибольшее влияние на предсказание оттока:
1. DayMins (минуты дневных разговоров)
2. MonthlyCharge (ежемесячный платёж)
3. CustServCalls (звонки в поддержку)

## Выводы
Отток клиентов сильнее всего связан с интенсивностью использования услуг 
и качеством клиентского опыта (частота обращений в поддержку). 
Бизнесу стоит в первую очередь отслеживать клиентов с высокими значениями 
DayMins/MonthlyCharge и частыми звонками в поддержку как группу риска оттока.

## Использованные технологии
Python, pandas, numpy, scikit-learn, matplotlib, seaborn
