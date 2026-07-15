# Predicción de cancelaciones y análisis de reservas hoteleras

Proyecto académico de Minería de Datos desarrollado para analizar patrones de reservas hoteleras, predecir cancelaciones y segmentar clientes mediante técnicas de Machine Learning.

## Objetivo

El proyecto busca responder tres preguntas principales:

1. ¿Es posible predecir la cancelación de una reserva?
2. ¿Qué variables influyen más en el precio promedio diario de una reserva?
3. ¿Existen grupos de reservas con características similares?

## Dataset

Se utilizó el dataset `hotel_bookings`, que contiene aproximadamente **86.940 registros** y 30 variables.

Entre las variables más relevantes se encuentran:

- `is_canceled`
- `lead_time`
- `adr`
- `customer_type`
- duración total de la estadía
- mes de llegada
- tipo de hotel
- canal de distribución

El dataset incluye reservas de dos tipos de hoteles:

- Resort Hotel
- City Hotel

## Problema 1 — Predicción de cancelaciones

Se desarrollaron modelos de clasificación para predecir si una reserva sería cancelada.

### Modelos utilizados

- Regresión Logística
- Random Forest

### Variables principales

- mes de llegada
- tipo de cliente
- anticipación de la reserva
- duración total de la estadía

### Métricas

- ROC-AUC
- Matriz de confusión
- Precisión de clasificación

Random Forest alcanzó un ROC-AUC aproximado de **0,82**, superando al modelo de Regresión Logística.

## Problema 2 — Análisis de atributos asociados al ADR

Se utilizó un modelo Lasso para analizar la importancia de las variables asociadas al valor `ADR`.

### Preprocesamiento

- `StandardScaler` para variables numéricas
- `OneHotEncoder` para variables categóricas
- expansión desde 28 a 191 variables

### Resultados

- R² aproximado: **0,816**
- MAE aproximado: **19,47**
- Lasso redujo 191 variables a 87 coeficientes relevantes
- mejora aproximada del 50 % frente al modelo baseline

El análisis mostró que la estacionalidad, especialmente los meses de julio y agosto, tiene una influencia importante en el ADR.

## Problema 3 — Segmentación de reservas

Se aplicó K-Means para identificar grupos de reservas con características similares.

### Variables utilizadas

- anticipación de la reserva
- ADR
- noches totales
- cantidad de adultos
- variables categóricas codificadas

### Evaluación

- método del codo
- Silhouette Score
- visualización mediante PCA
- análisis de medianas y proporciones por cluster

El número óptimo identificado fue de **3 clusters**.

## Tecnologías

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook
- Google Colab
- Machine Learning
- Data Mining
- Git
- GitHub

## Archivos

- `Hito2_informe_final.ipynb`: notebook con preprocesamiento, modelos, métricas y visualizaciones.
- `Prediccion_de_cancelaciones_y_Analisis_de_reservas.pdf`: presentación final del proyecto.

## Integrantes

Proyecto grupal desarrollado para el curso de Minería de Datos.

## Contexto académico

Proyecto desarrollado en la Universidad de Chile para el curso de Minería de Datos.
