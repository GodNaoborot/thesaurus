---
tags: [topic, hw5, visualization, time-series]
hw: "05. Dynamic visualization"
---

# 05. Динамическая визуализация и временные ряды

> Библиотеки: **plotly** , **bokeh** .
> Датасет курса: финансовые данные **AAPL, GOOGL, MSFT, AMZN, TSLA, ^GSPC** за 2021–2024.

**Важно**: GitHub **не отображает** интерактивные графики. Нужно сохранять в формате HTML: `fig.write_html("plot.html")` + скрины в README.

## Когда использовать

- Дашборды для бизнес-пользователей
- EDA для внешних пользователей
- Презентации с глубоким погружением
- Веб-публикации

---

## Plotly — основные виды графиков

| График | Для чего |
|--------|----------|
| **Candlestick** | цены акций/аблигаций и тд |
| **Scatter** | Линии, точки (`mode='lines'/'markers'/'lines+markers'`) |
| **Bar** | Столбчатые (объём торгов) |

```python
import plotly.graph_objects as go
from plotly.subplots import make_subplots

fig = make_subplots(rows=2, cols=1, shared_xaxes=True,
 row_heights=[0.7, 0.3])
fig.add_trace(go.Candlestick(x=df.Date, open=df.Open, high=df.High,
 low=df.Low, close=df.Close), row=1, col=1)
fig.add_trace(go.Bar(x=df.Date, y=df.Volume), row=2, col=1)
fig.write_html("dashboard.html")
```

### Интерактивные элементы

| Возможность | Метод |
|-------------|-------|
| **Range Slider** | `update_xaxes(rangeslider=...)` |
| **Range Selector** (кнопки 1M/3M/6M/1Y/All) | `update_xaxes(rangeselector=...)` |
| **Hover** | `update_layout(hovermode=...)` |
| **Аннотации** | `fig.add_annotation(...)` |

---

## [[Cross-filtering]]

Когда взаимодействие с одним графиком обновляет другие.

| Тип | Что делает |
|-----|------------|
| **Shared Axes** | Общая ось X/Y, общий zoom |
| **Legend Toggle** | Клик по легенде → показать/скрыть серию |
| **Brushing** | Выделение области → фильтр |
| **Click Events** | Клик по точке → действие |
| **Dropdown (updatemenus)** | Выбор в меню → обновление |

См. [[Cross-filtering]].

---

## Bokeh — кратко

| Функционал | Метод |
|-----------|-------|
| `figure()` | Создаёт холст |
| Glyphs | `line()`, `circle()`, `bar()` |
| `ColumnDataSource` | Источник данных |
| Widgets | `Select()`, `Slider()`, `CheckboxGroup()` |
| Callbacks | `js_on_change()`, `on_change()` |
| Layouts | `column()`, `row()`, `gridplot()` |

---

## Временные ряды

### [[Moving-average|Скользящее среднее (SMA)]]

$$SMA_t = \frac{1}{n}\sum_{i=0}^{n-1} p_{t-i}$$

```python
df['MA20'] = df['Close'].rolling(window=20).mean()
```

- **MA5** — краткосрочный сигнал, быстро реагирует
- **MA20** — общий тренд, сглаживает шум

### [[Decomposition|Декомпозиция]]

$$y_t = \text{Trend}_t + \text{Seasonality}_t + \text{Residual}_t$$

```python
from statsmodels.tsa.seasonal import seasonal_decompose, STL
result = seasonal_decompose(df['Close'], model='additive', period=251)
# STL — более «умная», устойчивая
stl = STL(df['Close'], period=251).fit()
```
Декомпозиция **позволяет** разбить временной ряд на **тренд** (общую тенденцию изменений при продолжительном времени), **сезонность** (повторяющиеся с фиксированным периодом изменения) и **случайный шум**

---

**До:** [[04_visualization]] · **После:** [[06_ml_basics]]
