# Proyecto Final 2 — Predicción de enfermedad cardíaca con Machine Learning

## Descripción

Este proyecto desarrolla un pipeline completo de Machine Learning para predecir la presencia de enfermedad cardíaca a partir de variables clínicas.

El trabajo incluye:

- formulación del problema;
- análisis exploratorio de datos;
- validación y limpieza del dataset;
- tratamiento de valores clínicamente inválidos;
- ingeniería de atributos;
- preprocesamiento con pipelines;
- entrenamiento de múltiples modelos;
- validación cruzada;
- optimización de hiperparámetros;
- evaluación final;
- análisis de umbrales;
- explicabilidad con SHAP;
- conclusiones, limitaciones y criterios de reproducibilidad.

> Este proyecto tiene fines educativos y no debe utilizarse como herramienta de diagnóstico médico.

## Objetivo

Construir un modelo de clasificación binaria capaz de estimar si un paciente presenta enfermedad cardíaca.

La variable objetivo es:

- `HeartDisease = 1`: presencia de enfermedad cardíaca.
- `HeartDisease = 0`: ausencia de enfermedad cardíaca.

## Métricas utilizadas

La métrica principal es:

- **ROC-AUC**

También se utilizan:

- Recall
- Precision
- F1-score
- Accuracy
- Matriz de confusión
- Curva ROC

En este contexto, el recall es especialmente relevante porque un falso negativo implica no detectar a un paciente que sí presenta enfermedad.

## Dataset

El archivo utilizado es:

```text
heart.csv
```

El dataset contiene variables clínicas y demográficas como:

- edad;
- sexo;
- tipo de dolor de pecho;
- presión arterial;
- colesterol;
- glucemia en ayunas;
- electrocardiograma en reposo;
- frecuencia cardíaca máxima;
- angina inducida por ejercicio;
- depresión del segmento ST;
- pendiente del segmento ST;
- presencia o ausencia de enfermedad cardíaca.

## Estructura del repositorio

```text
proyecto-final-ml/
├── README.md
├── ProyectoFinal2-Martinelli.ipynb
├── requirements.txt
├── heart.csv
└── .gitignore
```

## Modelos evaluados

Se comparan los siguientes modelos:

- Regresión logística
- Árbol de decisión
- Random Forest
- XGBoost

La comparación se realiza mediante validación cruzada estratificada.

## Optimización

Se utilizan técnicas de optimización de hiperparámetros:

- `GridSearchCV`
- `RandomizedSearchCV`

La métrica utilizada durante la optimización es ROC-AUC.

## Ingeniería de atributos

El proyecto incorpora nuevas variables derivadas:

- grupos de edad;
- relación entre frecuencia cardíaca máxima y edad;
- relación entre colesterol y edad.

También se tratan valores clínicamente inválidos:

- `RestingBP = 0`
- `Cholesterol = 0`

Estos valores se reemplazan por datos faltantes y se imputan dentro del pipeline para evitar fuga de información.

## Explicabilidad

Se utiliza SHAP para interpretar el modelo final.

El notebook incluye:

- importancia global de variables;
- gráfico SHAP de impacto y dirección;
- explicación individual de una predicción.

## Requisitos

Las dependencias están definidas en:

```text
requirements.txt
```

Instalación:

```bash
pip install -r requirements.txt
```

## Ejecución

1. Clonar o descargar el repositorio.
2. Instalar las dependencias.
3. Verificar que `heart.csv` esté junto al notebook o dentro de una carpeta `data/`.
4. Abrir `ProyectoFinal2-Martinelli.ipynb`.
5. Ejecutar todas las celdas desde cero.

En Jupyter:

```text
Kernel → Restart Kernel and Run All Cells
```

En Google Colab:

```text
Entorno de ejecución → Reiniciar sesión y ejecutar todo
```

## Reproducibilidad

El proyecto utiliza una semilla fija:

```python
SEED = 42
```

Esto permite reproducir:

- división de datos;
- validación cruzada;
- entrenamiento;
- optimización;
- resultados.

## Limitaciones

- El dataset es relativamente pequeño.
- Algunos valores faltantes están codificados como cero.
- No existe validación externa.
- Puede haber sesgos asociados a la población original.
- Las asociaciones encontradas no implican causalidad.
- El modelo no sustituye una evaluación médica.

## Autora

**Mariana Martinelli**

Proyecto final de Data Science y Machine Learning.
