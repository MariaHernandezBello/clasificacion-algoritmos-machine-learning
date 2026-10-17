# Clasificación de IPS en Colombia mediante algoritmos de Machine Learning

## Descripción del proyecto

Este proyecto tiene como objetivo comparar diferentes algoritmos de aprendizaje automático para clasificar las Instituciones Prestadoras de Servicios de Salud (IPS) en Colombia, utilizando la variable `ese` para distinguir entre las categorías **SI** y **NO**.

El análisis se desarrolla en Python mediante Google Colab y la biblioteca Scikit-learn. Incluye exploración de datos, preparación de variables, entrenamiento de modelos, evaluación de resultados y visualización de métricas.

## Objetivo general

Evaluar y comparar el desempeño de cinco algoritmos de clasificación para identificar cuál presenta mejores resultados en la predicción de la variable `ese` dentro del conjunto de datos analizado.

## Base de datos

Se utiliza el conjunto de datos **Listado de IPS en Colombia según su nivel de complejidad**, que contiene información sobre instituciones prestadoras de servicios de salud en el país.

- **Archivo:** `ips_colombia.csv`
- **Registros originales:** 11.466
- **Columnas originales:** 27
- **Registros utilizados en el modelado:** 3.501, correspondientes a observaciones con etiqueta conocida en la variable objetivo `ese`.
- **Variable objetivo:** `ese` (`SI` o `NO`).

Los registros sin etiqueta conocida en la variable objetivo se excluyeron del entrenamiento supervisado.

## Tecnologías utilizadas

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## Algoritmos implementados

1. **Árbol de Decisión:** permite construir reglas de clasificación a partir de las variables predictoras.
2. **Random Forest:** combina múltiples árboles de decisión para mejorar el desempeño predictivo.
3. **Máquinas de Soporte Vectorial (SVM):** busca separar las clases mediante fronteras de decisión.
4. **K-Nearest Neighbors (K-NN):** clasifica los registros según la proximidad entre observaciones.
5. **Naive Bayes:** utiliza probabilidades para estimar la clase de cada registro.

## Metodología

El proyecto se desarrolló mediante las siguientes etapas:

1. Carga y exploración inicial de la base de datos.
2. Identificación de valores faltantes y revisión de la variable objetivo.
3. Selección y preparación de las variables predictoras.
4. Transformación de fechas y codificación de variables categóricas.
5. Imputación de valores faltantes y escalado cuando corresponde.
6. División de los datos en entrenamiento (80 %) y prueba (20 %), con estratificación.
7. Entrenamiento de los cinco algoritmos.
8. Evaluación mediante métricas de clasificación y matrices de confusión.
9. Análisis de la importancia de las variables y elaboración de conclusiones.

## Resultados

Los resultados obtenidos en el conjunto de prueba fueron los siguientes:

| Modelo | Exactitud | F1-score para la clase SI |
|---|---:|---:|
| Random Forest | 89,59 % | 80,64 % |
| Árbol de Decisión | 86,73 % | 76,34 % |
| SVM | 82,74 % | 72,93 % |
| K-NN | 83,17 % | 60,93 % |
| Naive Bayes | 73,75 % | 15,60 % |

Random Forest obtuvo la mayor exactitud y el mejor F1-score para la clase `SI`. Por su parte, SVM presentó el mayor recall para esa clase, con un 87,17 %.

## Conclusiones

La comparación muestra que Random Forest presentó el mejor equilibrio general entre las métricas evaluadas para este conjunto de datos. Sin embargo, el desempeño de cada algoritmo depende de la métrica priorizada y de las características de los datos.

Es importante considerar que la variable objetivo solo cuenta con etiquetas conocidas para una parte de los registros originales y que existe un desequilibrio entre las clases. Por esta razón, los resultados deben interpretarse con precaución y validarse con nuevos datos antes de considerar cualquier aplicación práctica.

Las predicciones del modelo tienen fines académicos y analíticos; no sustituyen la verificación de la información en fuentes oficiales.

## Estructura del repositorio

- `Clasificacion_Algoritmos_Machine_Learning.ipynb`: notebook con el análisis, preparación de datos, entrenamiento y evaluación de los modelos.
- `ips_colombia.csv`: conjunto de datos utilizado en el proyecto.
- `README.md`: documentación general del repositorio.

## Cómo ejecutar el proyecto

1. Descarga o clona este repositorio.
2. Abre el notebook en Google Colab.
3. Carga el archivo `ips_colombia.csv` cuando el notebook lo solicite.
4. Ejecuta las celdas en orden.
5. Revisa las métricas, las gráficas y las conclusiones generadas.

## Autora

**María Isabel Hernández Bello**  
Universidad de Cundinamarca  
Asignatura: Introducción a Machine Learning
