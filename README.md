# ML EDA - Adult Income

## Descripción

Este proyecto realiza un análisis exploratorio de datos (EDA) sobre el dataset Adult Income.

El objetivo es comprender la estructura y calidad de los datos antes de realizar procesos de limpieza o modelado.

## Dataset

El dataset contiene información demográfica y laboral de personas, con el objetivo de analizar su nivel de ingresos.

- Filas: 32,561
- Columnas: 15
- Variable objetivo: `income`

### Variables

El dataset contiene variables numéricas y categóricas.

Variables numéricas principales:

- `age`
- `fnlwgt`
- `education-num`
- `capital-gain`
- `capital-loss`
- `hours-per-week`

Variables categóricas:

- `workclass`
- `education`
- `marital-status`
- `occupation`
- `relationship`
- `race`
- `sex`
- `native-country`
- `income`

## Análisis exploratorio

Durante el EDA se revisaron:

- Dimensiones del dataset
- Tipos de datos
- Valores faltantes
- Duplicados
- Estadísticas descriptivas
- Distribución de la variable objetivo
- Problemas de calidad de datos

## Hallazgos

### 1. Valores faltantes representados como `?`

Aunque `df.isna().sum()` no detecta valores faltantes, se encontraron registros con `?` en variables categóricas.

- `workclass`: 1,836 registros (5.64%)
- `occupation`: 1,843 registros (5.66%)
- `native-country`: 583 registros (1.79%)

Estos valores representan información faltante codificada como texto.

### 2. Registros duplicados

Se encontraron:

- 24 duplicados exactos.

Esto representa aproximadamente el 0.07% del dataset.

### 3. Inconsistencias de formato

Se revisaron las variables categóricas para detectar posibles espacios iniciales en los valores.

Los resultados de esta revisión se encuentran documentados en el notebook.

## Distribución del objetivo

La variable objetivo es `income`.

| Categoría | Registros | Porcentaje |
| ---------- | --------: | ---------: |
| `<=50K`  |    24,720 |     75.92% |
| `>50K`   |     7,841 |     24.08% |

Se observa que las categorías del objetivo no están distribuidas de manera uniforme.

## Resumen estadístico

Algunas estadísticas relevantes:

- Edad promedio: 38.58 años
- Edad mínima: 17 años
- Edad máxima: 90 años
- Horas trabajadas por semana promedio: 40.44
- Mediana de horas trabajadas por semana: 40
- `education-num` promedio: 10.08

## Hipótesis

Se plantea como hipótesis que las variables relacionadas con educación, edad, ocupación y horas trabajadas por semana podrían estar asociadas con el nivel de ingresos (`income`).

Esta hipótesis deberá ser analizada posteriormente mediante técnicas estadísticas y/o modelos de Machine Learning.

## Estructura del proyecto

```text
ml-eda-dirty-data/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── models/
│
├── notebooks/
│   └── 01_eda_adult_income.ipynb
│
├── src/
│
├── .gitignore
├── README.md
└── requirements.txt
```
