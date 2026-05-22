# Тезаурус курса «Анализ данных»

> **Автор:** Рубанов Михаил
> **Семестр:** весна 2026
> **Формат:** Obsidian vault

---

## Структура

| Папка / файл | Что содержит |
|--------------|--------------|
| `README.md` | Этот файл — как читать |
| `00_index.md` | Алфавитный + тематический индекс всех терминов |
| `GRAPH.md` | Mermaid-граф связей (рендерится прямо на GitHub) |
| `topics/` | **11 тематических блоков** курса (по одному на каждое hw) |
| `terms/` | **49 карточек терминов** с определениями, формулами, кодом, плюсами/минусами |
| `images/` | Картинки, встраиваемые в карточки |
| `THESAURUS.html` | Стилизованный HTML всего тезауруса (для печати в PDF) |
| `THESAURUS_combined.md` | Единый markdown (для Obsidian → Export to PDF) |

## Как читать

Возможны два сценария:

1. **Освежить тему целиком** → стоит открыть соответствующий файл в `topics/`, оттуда ссылки приведут в `terms/`.
2. **Найти конкретный термин** → тогда стоит использовать [[index]] или открыть файл напрямую в `terms/`.

---

## Содержание курса

| № | Блок курса | Файл | Главные термины |
|---|------------|------|-----------------|
| 1 | Pandas | [[01_pandas]] | [[Series]], [[DataFrame]], [[Groupby]] |
| 2 | Очистка данных | [[02_data_cleaning]] | [[Outliers]], [[IQR]], [[Z-score]] |
| 3 | EDA | [[03_eda]] | [[Correlation]], [[Skewness-Kurtosis]] |
| 4 | Визуализация и распределения | [[04_visualization]] | [[Distributions]], [[BG-NBD]] |
| 5 | Динамическая визуализация и временные ряды | [[05_dynamic_visualization]] | [[Moving-average]], [[Decomposition]], [[Cross-filtering]], [[MASE]] |
| 6 | Данные в ML | [[06_ml_basics]] | [[Linear-regression]], [[Logistic-regression]], [[Random-Forest]], [[CatBoost]], [[K-Means]], метрики |
| 7 | Feature Importance | [[07_feature_importance]] | [[Train-Valid-Test]], [[Statistical-tests]], [[Lasso]] |
| 8 | Понижение размерности | [[08_dim_reduction]] | [[PCA]], [[t-SNE]], [[UMAP]] |
| 9 | Токенизация | [[09_tokenization]] | [[BPE]] |
| 10 | Эмбеддинги | [[10_embeddings]] | [[BoW]], [[TF-IDF]], [[Word2Vec]], [[GloVe]], [[FastText]] |
| 11 | Геоданные | [[11_geo_data]] | [[Geopandas]] |

---

## Сборка PDF

В корне vault'а лежат собранные файлы:

| Файл | Что |
|------|-----|
| `THESAURUS_combined.md` | Весь тезаурус в одном markdown |
| `THESAURUS.html` | Стилизованная HTML-версия с поддержкой формул (MathJax) |
