# 📊 MACHINE LEARNING: EVALUACIÓN DE MODELOS

[![Python](https://img.shields.io/badge/Python-3670A0?style=flat&logo=python&logoColor=ffdd54)](https://www.python.org/)  
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)  
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)](https://pandas.pydata.org/)

Este proyecto es esencial en el flujo de trabajo de Machine Learning, centrándose en la **Evaluación de Modelos** para asegurar su fiabilidad y capacidad de generalización. Se explora cómo la **aleatoriedad inicial** afecta el rendimiento del modelo y se introducen técnicas avanzadas como la **Validación Cruzada (K-Fold)** y el uso de **Pipelines** para lograr una evaluación robusta y objetiva.

---

## 🧠 Contenido del Proyecto

### 1️⃣ La Influencia de la Aleatoriedad
- **Problema:** La división inicial de los datos en conjuntos de entrenamiento y prueba es un proceso aleatorio, lo que significa que el **Accuracy** (o métrica de rendimiento) del modelo puede variar significativamente cada vez que se ejecuta el proceso.
- **Solución:** Se demuestra que fijar el parámetro `random_state` es crucial para garantizar la **reproducibilidad** de los resultados.

### 2️⃣ Evaluación Robusta: Validación Cruzada (Cross-Validation)
Para obtener una métrica de rendimiento más estable y objetiva, se utiliza la técnica de Validación Cruzada:

- **K-Fold Cross-Validation:** El dataset se divide en *K* subconjuntos (o *folds*). El modelo se entrena *K* veces, utilizando *K-1* *folds* para entrenamiento y el *fold* restante para prueba. La métrica final es el promedio de los *K* resultados.
- **Group K-Fold:** Se utiliza una versión avanzada (`GroupKFold`) que es vital cuando hay **datos con correlación interna** (ej. varios registros de un mismo cliente o, en el ejemplo, diferentes "modelos de carro"). Esta técnica asegura que las muestras de un mismo grupo **nunca** estén en los conjuntos de entrenamiento y prueba simultáneamente, evitando así la fuga de información.

### 3️⃣ Estandarización del Flujo de Trabajo (Pipelines)
- **Necesidad:** En modelos complejos (como la Regresión Lineal), a menudo se requieren pasos previos al entrenamiento (ej. transformaciones, escalado de variables).
- **Pipeline de Scikit-learn:** Se introduce el uso de `Pipeline` como una solución elegante para encadenar estos pasos de preprocesamiento con el modelo final. Esto garantiza que la validación cruzada aplique correctamente las transformaciones en **cada uno de los *folds***, manteniendo la integridad del proceso de evaluación.

---

## 🛠️ Librerías Utilizadas

| Librería | Uso principal |
|:---:|:---:|
| **Scikit-learn** | Implementación de la Validación Cruzada (`KFold`, `GroupKFold`) y la construcción de `Pipeline`|
| **Pandas** | Carga y manipulación del dataset de vehículos|

---

## 🎯 Objetivo del Proyecto
Capacitar al usuario para evaluar de manera **sólida, objetiva y reproducible** cualquier modelo de Machine Learning, superando las limitaciones de la simple división `train_test_split`. El proyecto garantiza que el usuario pueda utilizar técnicas avanzadas como `GroupKFold` y `Pipeline` para manejar situaciones complejas en la evaluación.

---

## 📈 Resultados Clave
- Se demuestra cómo la **Validación Cruzada** produce una **métrica de rendimiento más estable y representativa** que una única división aleatoria.
- Se utiliza `GroupKFold` para simular la **entrada de datos nuevos o no disponibles** durante el entrenamiento, obteniendo una evaluación más realista del modelo en producción.
- Se implementa el **Pipeline** para encapsular y ejecutar correctamente los pasos de preprocesamiento, asegurando un proceso de entrenamiento y validación eficiente.

