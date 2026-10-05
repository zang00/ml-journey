# ML From Scratch

Classical ML algorithms implemented from scratch using NumPy — without 
scikit-learn for the actual training — to build deep understanding of 
gradient descent mechanics, loss functions, and weight updates.

## Files

### `linear-regression.ipynb`
Linear regression on the California Housing dataset.
- Full gradient descent cycle implemented manually: forward pass, 
  MSE loss, gradient computation, weight updates
- Results benchmarked against sklearn.LinearRegression — metrics 
  are nearly identical

### `logistic-regression.ipynb`
Logistic regression on the Breast Cancer dataset (binary classification).
- Sigmoid function and Binary Cross-Entropy (Log Loss) implemented from scratch
- Same gradient descent pattern as linear regression — demonstrates that 
  the gradient formula for MSE and Log Loss is mathematically equivalent
- Result: Accuracy 0.974, F1 0.979 — nearly identical to 
  sklearn.LogisticRegression on the same data

## Why this matters
Understanding what happens "under the hood" when calling `.fit()` — 
builds intuition for debugging models on real tasks and deeper 
understanding of hyperparameters (learning rate, number of iterations).

## Technologies used
Python, NumPy, matplotlib (for visualization), scikit-learn (comparison only)

---

# ML с нуля

Реализация классических ML-алгоритмов с нуля на NumPy — без использования 
scikit-learn для самого обучения — с целью глубокого понимания механики 
градиентного спуска, функций потерь и обновления весов.

## Файлы

### `linear-regression.ipynb`
Линейная регрессия на датасете California Housing.
- Реализован полный цикл градиентного спуска вручную: forward pass, 
  MSE loss, вычисление градиента, обновление весов
- Результат сравнён с sklearn.LinearRegression — метрики практически совпадают

### `logistic-regression.ipynb`
Логистическая регрессия на датасете Breast Cancer (бинарная классификация).
- Реализованы sigmoid-функция и Binary Cross-Entropy (Log Loss) с нуля
- Тот же паттерн градиентного спуска, что и в линейной регрессии — 
  показывает, что формула градиента для MSE и Log Loss математически 
  эквивалентна
- Результат: Accuracy 0.974, F1 0.979 — практически идентично 
  sklearn.LogisticRegression на тех же данных

## Зачем это нужно
Понимание того, что происходит "под капотом" при вызове `.fit()` — 
даёт интуицию для отладки моделей в реальных задачах и более глубокое 
понимание гиперпараметров (learning rate, количество итераций).

## Использованные технологии
Python, NumPy, matplotlib (для визуализации), scikit-learn (только для сравнения)
