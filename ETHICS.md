# ETHICS.md — Análisis Ético, Sesgos y Transparencia

## Introducción

Este documento describe las consideraciones éticas, posibles sesgos y limitaciones identificadas en el proyecto de Machine Learning para predicción de Churn utilizando el dataset **Telco Customer Churn**.

El objetivo es promover un uso responsable, transparente y justo del modelo desarrollado.

---

# 1. Variables Sensibles

El dataset contiene variables que podrían considerarse sensibles o generar sesgos indirectos en el modelo.

## Variables sensibles identificadas

- gender
- SeniorCitizen
- Partner
- Dependents

Estas variables representan características personales o demográficas de los clientes.

---

## Riesgos asociados

El modelo podría aprender patrones que favorezcan o perjudiquen ciertos grupos de personas.

Ejemplos:
- Clasificar incorrectamente a adultos mayores.
- Asociar mayor churn a ciertos géneros.
- Generar decisiones automáticas injustas.

Por ello, estas variables deben analizarse cuidadosamente durante el entrenamiento y evaluación del modelo.

---

# 2. Sesgos del Dataset

## Posible subrepresentación de grupos

El dataset podría no representar de manera equilibrada a toda la población de clientes.

Ejemplos:
- Diferencias entre clientes jóvenes y adultos mayores.
- Diferencias entre clientes con y sin internet.
- Diferencias entre tipos de contrato.

Esto puede provocar que el modelo tenga mejor desempeño en algunos grupos que en otros.

---

## Sesgos históricos

Las etiquetas del dataset reflejan decisiones y comportamientos reales de clientes en el pasado.

Esto significa que:
- algunos patrones pueden estar influenciados por estrategias comerciales anteriores,
- cambios de precios,
- calidad del servicio,
- o condiciones económicas específicas.

El modelo podría aprender estos patrones históricos y replicarlos automáticamente.

---

# 3. Limitaciones del Modelo

## El modelo no entiende contexto humano

El algoritmo únicamente identifica patrones matemáticos en los datos.

No comprende:
- razones emocionales,
- satisfacción real,
- problemas personales,
- ni factores externos que influyen en el abandono del servicio.

---

## Riesgo de falsos positivos y falsos negativos

El modelo puede equivocarse.

### Falso positivo
Predecir que un cliente abandonará el servicio cuando realmente no lo hará.

### Falso negativo
No detectar a un cliente que sí abandonará el servicio.

Ambos errores pueden afectar decisiones empresariales.

---

## Dependencia de la calidad de los datos

Si los datos contienen:
- errores,
- valores faltantes,
- información desactualizada,
- o sesgos,

el rendimiento del modelo también se verá afectado.

---

# 4. Transparencia y Explicabilidad

Para mantener transparencia en el proyecto:

- El código fuente es modular y accesible.
- Los parámetros del modelo están documentados en `params.yaml`.
- Las métricas utilizadas son:
  - Accuracy
  - Recall
  - F1-Score

Además, el sistema registra resultados experimentales para facilitar reproducibilidad y auditoría.

---

# 5. Uso Responsable del Modelo

Este modelo debe utilizarse únicamente como herramienta de apoyo para análisis de churn.

No debe utilizarse para:
- discriminar clientes,
- negar servicios automáticamente,
- ni tomar decisiones críticas sin supervisión humana.

Las predicciones deben complementarse con análisis de negocio y revisión humana.

---

# 6. Consideraciones de Equidad

Para mejorar equidad y reducir sesgos, se recomienda:

- Evaluar métricas separadas por grupos demográficos.
- Revisar balance de clases y representación de usuarios.
- Evitar decisiones automatizadas basadas únicamente en variables sensibles.
- Monitorear continuamente el comportamiento del modelo.

---

# 7. Conclusión

El proyecto demuestra cómo aplicar Machine Learning en un problema real de negocio, pero también evidencia la importancia de considerar ética, sesgos y transparencia en sistemas de inteligencia artificial.

Un modelo técnicamente correcto no siempre garantiza decisiones justas o responsables, por lo que la supervisión humana sigue siendo fundamental.