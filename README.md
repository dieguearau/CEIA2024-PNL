# CEIA2024- Procesamiento de Lenguaje Natural

# Desafíos propuestos

En este repositorio se encuentran los desafíos resueltos del curso Procesamiento de lenguaje natural de la Especialización en Inteligencia Artificial (CEIA - FIUBA).

## Desafío 1: Análisis de similitud entre documentos

Este proyecto implementa un análisis de textos basado en técnicas de PNL y algoritmos de clasificación para resolver un desafío de clasificación de documentos y análisis de palabras. Está dividido en tres partes principales:

1. **Análisis de similitud entre documentos:** Implementación de un modelo para identificar documentos similares utilizando TF-IDF y métricas de similitud coseno.
2. **Entrenamiento y ajuste de modelos Naive Bayes:** Desarrollo y optimización de modelos de clasificación (MultinomialNB y ComplementNB) para maximizar el F1-Score.
3. **Análisis de similitud entre palabras:** Identificación de palabras más similares a partir de una matriz término-documento generada mediante TF-IDF.

#### Características principales
- **Preprocesamiento de texto:** utiliza técnicas como vectorización con TF-IDF para extraer características del texto.
- **Clasificación supervisada:** 
    - Modelos implementados: MultinomialNB y ComplementNB.
    - Optimización de hiperparámetros usando Optuna para maximizar el rendimiento en un conjunto de prueba.
- **Análisis de palabras:**
    - Transposición de la matriz documento-término para analizar similitudes entre palabras.
    - Selección manual de términos relevantes para evitar términos irrelevantes en la comparación.

El notebook con la solución se encuentra en [Desafío 1](https://github.com/dieguearau/CEIA2024-PNL/blob/main/Desaf%C3%ADo%201/Soluci%C3%B3n_Desafio_1.ipynb).


