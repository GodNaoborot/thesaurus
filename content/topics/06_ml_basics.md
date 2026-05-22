---
tags: [topic, hw6, machine-learning]
hw: "06. Data in machine learning"
---

# 06. Данные в машинном обучении

> Три типа задач: **регрессия**, **классификация**, **кластеризация**. Цель — понять, как данные влияют на предсказание.

## Типы задач

| Тип | Что предсказываем | Датасет в курсе | Модели в курсе | Метрики |
|-----|-------------------|-----------------|----------------|---------|
| **Регрессия** | Непрерывная величина | `diamonds` | `SGDRegressor`, `RandomForestRegressor` | [[MAE]], [[RMSE]], [[R2]] |
| **Классификация** | Класс | `Telco-Customer-Churn` | [[Logistic-regression]], [[Random-Forest]], [[CatBoost]] | [[Precision-Recall]], [[F1-score]], [[ROC-AUC]] |
| **Кластеризация** | Скрытые группы (unsupervised) | `Mall_Customers` | [[K-Means]] | [[Silhouette]], inertia |

---

## Подготовка категориальных признаков

| Метод | Когда |
|-------|-------|
| [[One-hot-encoding]] | Категории **без** порядка (color, country) |
| [[Ordinal-encoding]] | Категории **с** порядком (clarity, cut) |

**Важно**: Применить ordinal к не-упорядоченным → модель «увидит» искусственный порядок, что испортит обучение.
**Важно**: `handle_unknown` — для категорий, которых не было в train.

---

## [[Normalization|Нормализация]]

`StandardScaler`: $(x - \mu) / \sigma$ → среднее 0, std 1.

Зачем для линейных моделей:
1. Градиентный спуск работает быстрее
2. Коэффициенты становятся сравнимыми
3. Регуляризация работает корректно

- Для [[K-Means]] и алгоритмов на **расстояниях** — обязательна, иначе признак с большим масштабом доминирует.
- Для деревьев и бустингов — не нужна (они инвариантны к скейлингу).

---

## [[Pipeline|Pipeline]]

Контейнер шагов: препроцессоры + модель в одном объекте.

```python
from sklearn.pipeline import Pipeline
from sklearn.compose import ColumnTransformer

preproc = ColumnTransformer([
 ('num', StandardScaler(), num_cols),
 ('ord', OrdinalEncoder(), ord_cols),
 ('ohe', OneHotEncoder(handle_unknown='ignore'), nom_cols),
])
pipe = Pipeline([('prep', preproc), ('model', SGDRegressor())])
pipe.fit(X_train, y_train)
```

**Важно**: **`fit()` только на train**, к test — `transform()` с теми же параметрами. Иначе → [[Data-leakage]].

---

## Метрики

### Регрессия
- [[MAE]] — средняя абсолютная ошибка
- [[RMSE]] — корень из MSE, сильнее штрафует большие отклонения
- [[R2]] — доля дисперсии, объяснённая моделью

### Классификация
- **Accuracy**:
	 -`Accuracy=(TP+TN)/(TP+TN+FP+FN)`— бесполезна при дисбалансе классов
- [[Confusion-matrix]] — матрица, состоящая из TN / FP / FN / TP
- [[Precision-Recall]]:
 - `Precision = TP/(TP+FP)` — когда дороги ложные срабатывания
 - `Recall = TP/(TP+FN)` — когда дорог пропуск
- [[F1-score]] — гармоническое среднее между `Precision` и `Recall`
- [[ROC-AUC]] — устойчива к дисбалансу

### Кластеризация
- [[Silhouette]] — насколько объект «свой» в своём кластере
- `inertia_` — сумма квадратов расстояний до центроида (метод локтя)

---

## Дисбаланс классов и порог

При дисбалансе:
- `class_weight='balanced'` — обратные веса по частоте
- Подбор **порога классификации** (по умолчанию 0.5) под бизнес-задачу

---

**До:** [[05_dynamic_visualization]] · **После:** [[07_feature_importance]]
