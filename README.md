# Examen práctico – Ingeniero de Datos (20 min)

Con el archivo `Grocery_Inventory new v1.csv` (en la raíz del repositorio) arma un **mini modelo dimensional** (esquema estrella) listo para ser consultado por un analista o una herramienta de BI.

No buscamos un modelo perfecto, sino ver cómo razonas sobre los datos.

## Qué hacer
1. **Revisa los datos:** tipos, nulos, formatos y claves. Anota los problemas que encuentres.
2. **Define el grano** de la tabla de hechos (qué representa una fila).
3. **Construye** con Python (o SQL):
   - Una tabla de **hechos** con sus medidas.
   - Las **dimensiones** que consideres necesarias.
   - Una **`dim_fecha`** diaria, sin huecos, que cubra el rango de fechas del modelo, con al menos: `date_id`, `date`, `year`, `quarter`, `month`, `month_name`, `day_name`.
4. **Valida el modelo:** usando tus tablas (no el CSV), calcula el valor de inventario (`Stock_Quantity × Unit_Price`) por categoría.

## Entregables
- Código reproducible (scripts o notebook, sin rutas absolutas).
- Tablas modeladas en la carpeta `output/` (formato libre: CSV, Parquet, DuckDB, etc.).
- Un párrafo breve (en el código o en un `.md`) con el grano, las tablas creadas y las decisiones principales.

## Reglas
- Puedes utilizar cualquier modelo de IA para el análisis. 
- Puedes usar Pandas, Polars, DuckDB o SQL.
- Las medidas principales son `Stock_Quantity` y `Unit_Price`. El resto de columnas numéricas puedes incluirlas o descartarlas.
- Algunas columnas necesitan limpieza o parseo antes de usarse.
- Si haces algún supuesto sobre los datos, anótalo; lo conversaremos en la entrevista.
