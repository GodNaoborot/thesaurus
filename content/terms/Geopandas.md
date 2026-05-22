---
tags: [term, geodata, library, hw11]
aliases: [geopandas, GeoDataFrame]
---

# GeoPandas

## Что это

Библиотека для работы с **геоданными** в Python. По сути расширение pandas — добавляет к [[DataFrame|DataFrame]] колонку `geometry` (точки, линии, полигоны) и пространственные операции типа `sjoin`.

## Создание GeoDataFrame

```python
import geopandas as gpd
gdf = gpd.GeoDataFrame(
 df,
 geometry=gpd.points_from_xy(df.lon, df.lat),
 crs="EPSG:4326" # WGS84 — стандартные lat/lon
)
# Из shape-файла / GeoJSON
districts = gpd.read_file("Borough_Boundaries_nyc.geojson")
```

## Расстояния

**Важно**: евклидово расстояние **некорректно** для координат — Земля не плоская. Для честных расстояний — `geopy.distance.geodesic`:

```python
from geopy.distance import geodesic
distance_miles = geodesic((lat1, lon1), (lat2, lon2)).miles
```

На NYC Taxi через `sjoin` соединял точки поездок с полигонами районов, чтобы получить `pickup_district` и `dropoff_district`, а через `geodesic` считал `distance_between_points`.

**Тема:** [[11_geo_data]]
