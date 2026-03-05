# 📊✨ Análisis de Cancelación de Clientes en Telecom (Telecom x - parte 2)

Proyecto Final -- Alura Latam | Programa: Oracle ONE 9 - Argentina

## 🎯 Propósito del Proyecto

El objetivo principal de este proyecto es desarrollar modelos predictivos capaces de predecir la cancelación (churn) de clientes en la empresa Telecom X, utilizando variables demográficas, contractuales y de consumo.
La finalidad estratégica es anticipar la pérdida de clientes para permitir a la empresa implementar acciones de retención basadas en datos.

## 🧠 Objetivo Analítico

1) Identificar los factores más influyentes en la cancelación.

2)  Construir al menos dos modelos de clasificación.

3) Comparar el desempeño de los modelos.

4)  Generar insights estratégicos para la toma de decisiones.

## 🛠 Preparación de los Datos

1️⃣ Clasificación de Variables

Las variables fueron clasificadas en:

Variables categóricas: tipo de contrato, método de pago, servicios contratados, etc.

Variables numéricas: tenure, MonthlyCharges, TotalCharges.

2️⃣ Transformación de Variables

🔹 Codificación de Variables Categóricas

Se utilizó One-Hot Encoding para convertir variables categóricas en variables numéricas binarias, permitiendo su uso en algoritmos de Machine Learning.

🔹 Transformación de la Variable Objetivo

La variable Churn fue transformada a formato binario:

0 → No canceló

1 → Sí canceló

3️⃣ Separación en Entrenamiento y Prueba
Se utilizó una división:

70% entrenamiento

30% prueba

Aplicando stratify=y para mantener la proporción original de cancelación (~26.5%).

4️⃣ Normalización

Se aplicó StandardScaler únicamente para modelos sensibles a la escala (Regresión Logística).

## 💡 Modelos Implementados

🔹 Modelo 1: Regresión Logística

Requiere normalización

Interpretabilidad mediante coeficientes

🔹 Modelo 2: Random Forest

Modelo basado en árboles

No requiere normalización

Permite analizar importancia de variables

No se aplicó normalización para modelos basados en árboles (Random Forest), ya que no son sensibles a la escala de los datos.


##📈 Métricas de Evaluación
Se evaluaron ambos modelos utilizando:

1) Accuracy
2) Precision
3) Recall
4) F1-score
5) Matriz de Confusión
6) ROC-AUC
   
Se realizó además análisis de:

* Overfitting (comparación train vs test)
* Underfitting
* Capacidad de generalización

##🔎 Insights Relevantes del EDA

Algunos hallazgos importantes:

* Clientes con contrato Month-to-Month presentan mayor probabilidad de cancelación.

* El servicio Fiber Optic está fuertemente asociado al churn.

* Menor antigüedad (tenure) aumenta significativamente el riesgo de cancelación.

* Clientes con débito automático tienden a cancelar menos.

* Estos hallazgos permiten diseñar estrategias específicas de retención.


# ✅ Conlusión

El análisis de la Regresión Logística muestra que la antigüedad del cliente (tenure) es uno de los factores más importantes para reducir la cancelación: cuanto más tiempo lleva un cliente, menos probable es que abandone el servicio.

También se observa que los contratos de mayor duración ayudan a disminuir el churn, mientras que los contratos mensuales presentan mayor riesgo de cancelación. Por otro lado, los cargos mensuales altos y el uso de fibra óptica se asocian con una mayor probabilidad de baja.

Finalmente, contar con servicios adicionales como soporte técnico o seguridad en línea reduce la probabilidad de cancelación, lo que indica que el valor del servicio y la atención al cliente influyen en la permanencia de los usuarios.

