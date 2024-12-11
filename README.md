# CEIA2024- Procesamiento de Lenguaje Natural

# Desafíos propuestos

En este repositorio se encuentran los desafíos resueltos del curso Procesamiento de lenguaje natural de la Especialización en Inteligencia Artificial (CEIA - FIUBA).

## Desafío 1: Análisis de similitud entre documentos

Se implementa un análisis de textos basado en técnicas de PNL y algoritmos de clasificación para resolver un desafío de clasificación de documentos y análisis de palabras. Está dividido en tres partes principales:

1. **Análisis de similitud entre documentos:** Implementación de un modelo para identificar documentos similares utilizando TF-IDF y métricas de similitud coseno.
2. **Entrenamiento y ajuste de modelos Naive Bayes:** Desarrollo y optimización de modelos de clasificación (MultinomialNB y ComplementNB) para maximizar el F1-Score macro.
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

## Desafío 2: Vectores con Gensim

Se desarrolla un análisis de texto basado en embeddings generados con Word2Vec de Gensim. Se utiliza el texto de La Odisea de Homero como dataset para explorar relaciones semánticas entre palabras, probar analogías y visualizar agrupamientos en el espacio de vectores.

El código aborda los siguientes objetivos:

- **Generación de embeddings personalizados:** Creación de representaciones vectoriales para las palabras en el texto.
- **Exploración de relaciones semánticas:** Evaluación de términos relevantes en el espacio vectorial mediante pruebas de similitud y analogías.
- **Visualización de vectores:** Reducción de dimensionalidad y gráficos 2D/3D para interpretar el espacio de embeddings.

#### Características principales

- **Preprocesamiento de texto:**
    - Tokenización con text_to_word_sequence de Keras.
    - Generación de embeddings con Word2Vec en modo Skip-Gram, con parámetros ajustados:
        - Dimensionalidad: 300.
        - Contexto: 10 palabras antes y después.
        - Frecuencia mínima: 10 ocurrencias.

- **Pruebas semánticas:**
     - **Similitud entre palabras:** Identificación de los términos más y menos relacionados con palabras clave como "nave" y "viaje".

- **Pruebas de analogías:**
    - Ejemplo: ``mar + orilla - tierra → playa.``
    - Ejemplo: ``Odiseo + Calipso - esposa → ninfa.``

- **Visualización de vectores:** 
    - Gráficos 2D y 3D utilizando técnicas como Incremental PCA y t-SNE para interpretar agrupamientos y relaciones en el espacio de vectores.
    - Ejemplo: Relación entre "Odiseo", "Telemaco" y "Atenea".

El notebook con la solución se encuentra en [Desafío 2](https://github.com/dieguearau/CEIA2024-PNL/blob/main/Desaf%C3%ADo%202/Soluci%C3%B3n_Desafio_2.ipynb).

## Desafío 3: Modelado de Lenguaje con RNN

En este proyecto se implementa un modelo de generación de lenguaje natural utilizando redes neuronales recurrentes (RNN) para explorar el comportamiento del modelo al generar texto y evaluar su capacidad para aprender patrones lingüísticos.

El código aborda los siguientes objetivos principales:

1. **Entrenamiento de un modelo de lenguaje:** 
    - Basado en RNNs o sus variantes.
    - Optimización para minimizar la perplejidad, una métrica que mide la calidad de predicción del modelo.
2. **Generación de texto:**
    - Producción de secuencias de palabras utilizando el modelo entrenado.
    - Ajuste de hiperparámetros como temperatura y métodos de búsqueda (beam search, muestreo aleatorio) para controlar la diversidad de texto.
3. **Visualización del rendimiento:**
    - Análisis de la perplejidad durante el entrenamiento para evaluar el aprendizaje y la generalización del modelo.

#### Características principales

- **Preprocesamiento de texto:**
    - Tokenización y secuenciación de datos de texto.
    - Codificación y padding para normalizar las entradas del modelo.

- **Entrenamiento del modelo:**
     - Optimización para minimizar la pérdida y la perplejidad en los conjuntos de entrenamiento y validación.
     - Estrategia de early stopping para evitar sobreajuste.

- **Generación de texto**
    - **Ajuste de temperatura:** Control de la aleatoriedad en las palabras generadas.
    - **Beam search:** Implementación de búsquedas determinísticas y con muestreo aleatorio para explorar mejores secuencias.

- **Evaluación de resultados:** 
    - Análisis de coherencia y diversidad en las secuencias generadas.
    - Comparación del impacto de los hiperparámetros en las salidas del modelo.

El notebook con la solución se encuentra en [Desafío 3](https://github.com/dieguearau/CEIA2024-PNL/blob/main/Desaf%C3%ADo%203/Soluci%C3%B3n_Desafio_3.ipynb).

## Desafío 4: Traducción Automática y Chatbot

Este proyecto implementa un sistema de traducción automática y generación de respuestas utilizando una arquitectura de codificador-decodificador (Encoder-Decoder) basada en redes LSTM. El enfoque principal es entrenar un modelo para generar respuestas contextualmente apropiadas a preguntas en lenguaje natural.

El código aborda los siguientes objetivos principales:

1. **Entrenamiento de un modelo de traducción:** 
    - Uso de redes LSTM con embeddings de palabras para codificación y decodificación de secuencias.
    - Optimización para minimizar la pérdida categórica.
2. **Inferencia para generación de respuestas:**
    - Uso de un modelo codificador para generar representaciones vectoriales de las preguntas.
    - Generación de respuestas token por token mediante el modelo decodificador.
3. **Evaluación de respuestas generadas:**
    - Análisis cualitativo de las respuestas obtenidas y ajustes al modelo.

#### Características principales

- **Preprocesamiento de texto:**
    - Tokenización y mapeo de palabras a índices.
    - Alineación de secuencias de entrada y salida mediante padding para normalización.

- **Construcción del modelo:**
    - Arquitectura de codificador con una capa LSTM para capturar contextos.
    - Decodificador con LSTM para generar secuencias de salida.
    - Capa densa con activación softmax para la predicción de palabras.

- **Entrenamiento del modelo:**
    - Ajuste de pesos en 50 épocas utilizando un 20% de los datos para validación.
    - Métricas de desempeño: pérdida categórica y precisión.

- **Inferencia de respuestas**
    - Respuesta generada palabra por palabra, comenzando con un token de inicio (<sos>) y terminando con un token de fin (<eos>).
    - Implementación de una función para procesar preguntas y generar respuestas.

#### Ejemplo de resultados
1.  Pregunta: "How are you?"
    Respuesta generada: "i m fine"

2.  Pregunta: "Do you read?"
    Respuesta generada: "i love to read"

3.  Pregunta: "Where are you from?"
    Respuesta generada: "i am in the army"


El notebook con la solución se encuentra en [Desafío 4](https://github.com/dieguearau/CEIA2024-PNL/blob/main/Desaf%C3%ADo%204/Soluci%C3%B3n_desaf%C3%ADo_4.ipynb).








