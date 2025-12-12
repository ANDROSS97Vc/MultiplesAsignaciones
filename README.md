Validación de Estabilidad del Modelo Mediante Monte Carlo (100 Iteraciones)

Este script implementa un proceso de validación de estabilidad utilizando 100 particiones aleatorias (Monte Carlo Cross-Validation) con un modelo de Regresión Logística aplicado al dataset datasetFINALFINAL1.csv.
El objetivo principal es evaluar la variabilidad del modelo midiendo métricas clave como F1-Score y ROC AUC a lo largo de múltiples ejecuciones con diferentes semillas aleatorias.

Descripción General

El código realiza los siguientes pasos:

Carga del dataset almacenado en Google Drive.

Separación entre variables predictoras (X) y variable objetivo (y = cardio).

Configuración de un pipeline con un clasificador LogisticRegression usando:

solver = liblinear

class_weight = balanced

random_state = 42

Ejecución de 100 iteraciones Monte Carlo, donde en cada una:

Se realiza un train-test split del 80/20 con una semilla distinta.

Se entrena el modelo.

Se generan probabilidades de predicción.

Se aplica un threshold fijo de 0.4.

Se calculan F1-score y ROC AUC.

Finalmente, se calcula:

Mediana del F1-score

Mediana del ROC AUC

Desviación estándar del F1-score

Rango total de valores obtenidos

Tiempo total de ejecución

Este procedimiento permite analizar cuán estable es el modelo bajo diferentes asignaciones de datos.
