# Алфавитный + тематический индекс

Все понятия курса в одном списке. Каждый термин — кликабельная ссылка на карточку.

## По темам курса

### hw1 — [[01_pandas|Pandas]]
- [[Series]], [[DataFrame]], [[Groupby]]

### hw2 — [[02_data_cleaning|Очистка данных]]
- [[Outliers]], [[IQR]], [[Z-score]]

### hw3 — [[03_eda|EDA]]
- [[Correlation]], [[Skewness-Kurtosis]]

### hw4 — [[04_visualization|Визуализация]]
- [[Distributions]], [[BG-NBD]]

### hw5 — [[05_dynamic_visualization|Динамическая визуализация]]
- [[Moving-average]], [[Decomposition]], [[Cross-filtering]], [[MASE]]

### hw6 — [[06_ml_basics|ML основы]]
- **Препроцессинг:** [[One-hot-encoding]], [[Ordinal-encoding]], [[Normalization]], [[Pipeline]], [[Data-leakage]]
- **Модели:** [[Linear-regression]], [[Logistic-regression]], [[Random-Forest]], [[CatBoost]], [[K-Means]]
- **Метрики регрессии:** [[MAE]], [[RMSE]], [[R2]]
- **Метрики классификации:** [[Confusion-matrix]], [[Precision-Recall]], [[F1-score]], [[ROC-AUC]]
- **Метрика кластеризации:** [[Silhouette]]

### hw7 — [[07_feature_importance|Feature Importance]]
- [[Train-Valid-Test]], [[Statistical-tests]], [[Feature-importance]], [[Lasso]]

### hw8 — [[08_dim_reduction|Понижение размерности]]
- [[PCA]], [[t-SNE]], [[UMAP]]

### hw9 — [[09_tokenization|Токенизация]]
- [[BPE]]

### hw10 — [[10_embeddings|Эмбеддинги]]
- [[Embedding]], [[BoW]], [[TF-IDF]], [[Word2Vec]], [[GloVe]], [[FastText]], [[Cosine-similarity]]

### hw11 — [[11_geo_data|Геоданные]]
- [[Geopandas]]

---

## Алфавитный индекс

### A — D
- [[BG-NBD]] — Beta-Geometric / NBD модель «жизни» пользователя (hw4)
- [[BPE]] — Byte-Pair Encoding, субсловная токенизация (hw9)
- [[BoW]] — Bag of Words, мешок слов (hw10)
- [[CatBoost]] — градиентный бустинг (hw6, hw7)
- [[Confusion-matrix]] — матрица ошибок (hw6)
- [[Correlation]] — корреляция Пирсона и Спирмена (hw3)
- [[Cosine-similarity]] — косинусное сходство (hw10)
- [[Cross-filtering]] — связанные интерактивные графики (hw5, hw11)
- [[Data-leakage]] — утечка данных (hw6, hw7)
- [[DataFrame]] — двумерная таблица pandas (hw1)
- [[Decomposition]] — декомпозиция временного ряда (hw5)
- [[Distributions]] — распределения в `scipy.stats` (hw4)

### E — K
- [[Embedding]] — векторное представление токенов (hw10)
- [[F1-score]] — баланс Precision и Recall (hw6)
- [[FastText]] — эмбеддинги через подслова (hw10)
- [[Feature-importance]] — важность признаков (hw7)
- [[Geopandas]] — работа с геоданными (hw11)
- [[GloVe]] — глобальные векторы (hw10)
- [[Groupby]] — агрегация по группам (hw1)
- [[IQR]] — межквартильный размах (hw2)
- [[K-Means]] — алгоритм кластеризации (hw6)

### L — P
- [[Lasso]] — L1-регуляризация (hw7, hw8)
- [[Linear-regression]] — линейная регрессия / SGDRegressor (hw6)
- [[Logistic-regression]] — логистическая регрессия (hw6, hw8, hw9, hw10)
- [[MAE]] — Mean Absolute Error (hw6)
- [[MASE]] — Mean Absolute Scaled Error (hw5 бонус)
- [[Moving-average]] — скользящее среднее (hw5)
- [[Normalization]] — нормализация / StandardScaler (hw6)
- [[One-hot-encoding]] — кодирование «один из N» (hw6)
- [[Ordinal-encoding]] — порядковое кодирование (hw6)
- [[Outliers]] — выбросы и аномалии (hw2)
- [[PCA]] — метод главных компонент (hw8)
- [[Pipeline]] — Pipeline и ColumnTransformer (hw6)
- [[Precision-Recall]] — точность и полнота (hw6)

### Q — Z
- [[R2]] — коэффициент детерминации (hw6)
- [[Random-Forest]] — случайный лес (hw6, hw7)
- [[RMSE]] — Root Mean Squared Error (hw6)
- [[ROC-AUC]] — площадь под ROC-кривой (hw9)
- [[Series]] — одномерный массив pandas (hw1)
- [[Silhouette]] — silhouette score (hw6)
- [[Skewness-Kurtosis]] — асимметрия и эксцесс (hw3)
- [[Statistical-tests]] — статистические тесты (hw7)
- [[t-SNE]] — нелинейное снижение размерности (hw8)
- [[TF-IDF]] — Term Frequency–IDF (hw10)
- [[Tokenization]] — токенизация текста (hw9)
- [[Train-Valid-Test]] — разбиение выборки (hw7)
- [[UMAP]] — нелинейное снижение размерности (hw8)
- [[Word2Vec]] — обучаемые эмбеддинги слов (hw10)
- [[Z-score]] — z-оценка / стандартизация (hw2)

---

## По типу понятия

### Метрики
- Регрессия: [[MAE]], [[RMSE]], [[R2]]
- Классификация: [[Confusion-matrix]], [[Precision-Recall]], [[F1-score]], [[ROC-AUC]]
- Кластеризация: [[Silhouette]]
- Временные ряды: [[MASE]]

### Модели
- Регрессия: [[Linear-regression]], [[Random-Forest]], [[CatBoost]]
- Классификация: [[Logistic-regression]], [[Random-Forest]], [[CatBoost]]
- Кластеризация: [[K-Means]]
- Снижение размерности: [[PCA]], [[t-SNE]], [[UMAP]]

### Обработка данных
- [[One-hot-encoding]], [[Ordinal-encoding]], [[Normalization]], [[Pipeline]]
- [[Outliers]], [[IQR]], [[Z-score]]
- [[Train-Valid-Test]], [[Data-leakage]]

### Статистика
- [[Distributions]], [[Skewness-Kurtosis]], [[Correlation]], [[Statistical-tests]]

### NLP
- [[BPE]], [[BoW]], [[TF-IDF]]
- [[Embedding]], [[Word2Vec]], [[GloVe]], [[FastText]], [[Cosine-similarity]]

### Временные ряды
- [[Moving-average]], [[Decomposition]]

### Прочее
- [[BG-NBD]], [[Cross-filtering]], [[Geopandas]]
- [[Feature-importance]], [[Lasso]]
