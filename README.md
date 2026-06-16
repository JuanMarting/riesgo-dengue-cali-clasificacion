# Sistema de Categorización Espacio-Temporal del Riesgo Semanal de Dengue a Nivel de Comuna en Cali, Colombia 🦟📊

Este repositorio contiene el código fuente para el desarrollo de un sistema basado en Machine Learning diseñado para categorizar el riesgo epidemiológico del dengue en la ciudad de Cali. Este proyecto se desarrolla en el marco de la Maestría en Ciencia de Datos de la Universidad Icesi.

El objetivo principal es integrar datos epidemiológicos, factores ambientales y variables satelitales para predecir el riesgo de brotes a nivel de comuna, proporcionando una herramienta analítica robusta para la toma de decisiones en salud pública.

## 🛠️ Metodología

El desarrollo del proyecto sigue la metodología **CRISP-DM** (Cross-Industry Standard Process for Data Mining), abarcando desde la comprensión del problema de salud pública hasta la evaluación de los modelos. 

Para garantizar la generalización del modelo en el tiempo y el espacio, se implementan esquemas de validación rigurosos como **Leave-One-Year-Out (LOYO)**, y se utiliza la teoría de juegos (valores **SHAP**) para interpretar el impacto de las variables ambientales y espaciales en las predicciones.

## 📂 Estructura de los Notebooks

El análisis está dividido de manera secuencial en cuatro notebooks principales:

* **`01-data_nivel_comuna.ipynb`:** Integración de fuentes de datos. Realiza las uniones espaciales (spatial joins) necesarias para transicionar la información desde una resolución de píxel hasta el nivel administrativo de comuna.
* **`02-preparar_data.ipynb`:** Limpieza y preprocesamiento de datos. Manejo de valores nulos, ingeniería de características (feature engineering) y preparación de la estructura temporal-espacial.
* **`03-EDA - VF.ipynb`:** Análisis Exploratorio de Datos (EDA). Visualización de patrones temporales, distribución espacial del dengue y correlación entre las variables climáticas y los casos reportados.
* **`04-modelado-v3.ipynb`:** Entrenamiento y evaluación de algoritmos de Machine Learning (XGBoost, LightGBM, CatBoost, Random Forest). Incluye la optimización de hiperparámetros, validación LOYO y el análisis de explicabilidad con SHAP.

## 📊 Resultados y Métricas

En la raíz del repositorio se incluyen los resultados consolidados de los modelos evaluados:
* `metricas_por_comuna.csv`: Desempeño detallado de las predicciones en cada zona de la ciudad.
* `shap_ranking_global.csv`: Importancia global de las características que más influyen en el aumento del riesgo de dengue.

> **Nota sobre los datos y modelos:** Por motivos de privacidad y tamaño de almacenamiento, la carpeta con los datos crudos (`data/`) y los modelos binarios serializados (`.pkl`) no están incluidos en este repositorio.

## 💻 Requisitos del Entorno

Para replicar este entorno, se recomienda utilizar las siguientes librerías principales:
* `pandas` y `numpy`
* `geopandas`
* `scikit-learn`
* `xgboost`, `lightgbm`, `catboost`
* `shap`
* `matplotlib` y `seaborn`