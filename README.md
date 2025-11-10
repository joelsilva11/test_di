# Examen práctico – Ingeniero/a de Datos

Este práctico evalúa tu capacidad para ingerir datos, modelar una dimensión de fechas, generar salidas en formatos columnar (Parquet) y calcular métricas agregadas. Usa el archivo CSV provisto: `Grocery_Inventory new v1.csv`.

## Objetivos
- Leer y perfilar un CSV con Python.
- Identificar columna(s) de fecha y construir una tabla DIM_FECHA con atributos derivados (día, semana ISO, mes, trimestre, etc.).
- Exportar resultados a Parquet.
- Calcular una métrica agregada agrupada por una dimensión.

## Entregables
- Código Python reproducible (scripts o notebook), sin depender de rutas absolutas excepto la del CSV provisto.
- Carpeta `output/` con:
  - `dim_calendar.parquet` (dimensión de fechas).
  - `agg_metric.parquet` (resultado de la métrica agregada).

## Dataset
Archivo: `Grocery_Inventory new v1.csv` (en la raíz del repositorio).

## Reglas y supuestos
- Puedes usar Pandas y PyArrow. Se valora el uso opcional de Polars o PySpark (no obligatorio).
- El/los campo(s) de fecha pueden necesitar inferencia o parseo flexible.
- La DIM_FECHA debe cubrir al menos el rango mínimo–máximo de fechas presentes en la columna Date_Received dataset, a nivel de día.

## Atributos mínimos para DIM_FECHA
Incluye, como mínimo, estas columnas:
- `date` (YYYY-MM-DD)
- `year`, `quarter`, `month`, `month_name`
- `week_iso` (semana ISO), `iso_year`
- `day`, `day_of_week`, `day_name`

## Métrica agregada (ejemplo)
- Selecciona una columna numérica (p. ej., `Stock_Quantity`, `Sales_Volume`) y una dimensión (p. ej., una categoría o `month`).
- Calcula una agregación (por defecto `sum`). Resultado: dos o más columnas: `dimension`, `metric` (y opcionalmente `count`/`avg`).
