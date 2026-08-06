---
tags: [deep-learning, definicion, historia, fundamentos]
related: [[Equipo 4 - Deep Learning]]
---

# 📜 Definición y Origen del Deep Learning

## 1. ¿Qué es el Deep Learning?

El **Deep Learning** (DL) o **aprendizaje profundo** es un subconjunto del Machine Learning que utiliza **redes neuronales artificiales con múltiples capas** (de ahí el término "profundo") para aprender patrones y representaciones a partir de grandes volúmenes de datos.

A diferencia de la programación tradicional, donde las reglas son escritas explícitamente por desarrolladores, los sistemas de Deep Learning **aprenden esas reglas automáticamente** al ser expuestos a datos. Cuanto más datos procesan, más refinada se vuelve su comprensión.

### 1.1. Estructura básica de una red neuronal profunda

Una red neuronal profunda típica está compuesta por **tres tipos de capas**:

| Capa | Función |
|------|---------|
| **Capa de entrada (Input Layer)** | Recibe los datos brutos (píxeles de una imagen, palabras de una frase, lecturas de sensores) y los distribuye a la siguiente capa. |
| **Capas ocultas (Hidden Layers)** | Transforman la información aplicando funciones no lineales (activación). Aprenden representaciones cada vez más abstractas de los datos. Un modelo se considera "profundo" cuando tiene **al menos 4 capas**, aunque las arquitecturas modernas suelen ser mucho más profundas. |
| **Capa de salida (Output Layer)** | Produce el resultado final: una clasificación, una predicción o una respuesta generada. |

> 📌 **Concepto clave**: El término "profundo" hace referencia al **número de capas** de la red neuronal. Estas capas permiten que el modelo aprenda representaciones cada vez más abstractas de la entrada, lo que da al Deep Learning su poder distintivo.

---

## 2. Origen e historia del Deep Learning

### 2.1. Los fundamentos (décadas de 1940-1950)

Los primeros teóricos que concibieron los fundamentos de la computación neuronal fueron **Warren McCulloch** (neurofisiólogo) y **Walter Pitts** (matemático), quienes en **1943** propusieron el primer modelo de neurona artificial.

En **1958**, **Frank Rosenblatt** presentó públicamente el **perceptrón**, un desarrollo que sentó las bases para las redes neuronales modernas. Rosenblatt es ampliamente reconocido como uno de los padres fundadores del Deep Learning.

### 2.2. El "invierno de la IA" y el resurgimiento (décadas de 1970-1990)

Durante las décadas de 1970 y 1980, el interés por las redes neuronales decayó debido a limitaciones computacionales y teóricas. Sin embargo, en los **años 80**, **Geoffrey Hinton**, junto con otros investigadores como **Yoshua Bengio**, **Yann LeCun** y **Jürgen Schmidhuber**, desarrollaron una versión moderna más simple y eficiente de las redes neuronales.

Hinton inventó el método moderno de entrenamiento de redes neuronales conocido como **backpropagation** (retropropagación del error), que permitió superar las limitaciones de los modelos anteriores.

### 2.3. El punto de inflexión: 2012 y AlexNet

El **verdadero despegue** del Deep Learning ocurrió en **2012**, cuando Geoffrey Hinton y su equipo publicaron **AlexNet**, una red neuronal convolucional que logró una precisión sin precedentes en el reconocimiento de objetos en imágenes, venciendo con amplia ventaja en competiciones internacionales.

Este hito demostró que las redes neuronales profundas, entrenadas con grandes cantidades de datos y potentes GPUs, podían superar a cualquier otro enfoque de Machine Learning en tareas de visión por computadora.

### 2.4. Hitos recientes

- **2006**: Geoffrey Hinton y su equipo revivieron el interés por las redes neuronales profundas al mostrar que podían entrenarse eficazmente usando un enfoque jerárquico llamado **preentrenamiento capa por capa**.
- **2024**: Geoffrey Hinton fue galardonado con el **Premio Nobel de Física** por su trabajo fundacional en aprendizaje automático con redes neuronales artificiales.

---

[[Equipo 4 - Deep Learning|← Volver al índice principal]]