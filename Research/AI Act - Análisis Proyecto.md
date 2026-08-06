---
tags:
  - AI-Act
  - regulación
  - requisitos
  - proyecto
  - emprendimiento
  - deep-learning
related:
  - "[[Equipo 4 - Deep Learning]]"
  - "[[DL - Usos y Aplicaciones]]"
---

# 🏛️ Análisis del AI Act (EU) 2024/1689 para el Proyecto "Recomendador de Cursos"

Este documento analiza el Reglamento de Inteligencia Artificial de la Unión Europea (AI Act) y lo vincula con nuestro proyecto de emprendimiento: una plataforma de venta de cursos (B2C y B2B) que utiliza un modelo de Deep Learning para recomendar contenido educativo a los usuarios.

El objetivo es identificar las obligaciones legales y regulatorias que condicionarán el diseño, desarrollo e implementación de nuestro modelo de calidad, para así derivar requisitos funcionales y no funcionales claros.

---

## 📌 1. Clasificación de Riesgo de nuestro Sistema de Recomendación

El AI Act se basa en un **enfoque de riesgos**. Para saber qué obligaciones nos aplican, primero debemos clasificar nuestro sistema de IA.

### 1.1. ¿Es un sistema de "Riesgo Inaceptable" (Artículo 5)?
**No.** Nuestro sistema no realiza prácticas prohibidas como:
- Manipulación subliminal.
- Explotación de vulnerabilidades.
- Puntuación social (social scoring).
- Identificación biométrica en tiempo real.

### 1.2. ¿Es un sistema de "Alto Riesgo" (Artículo 6 y Anexo III)?
**Probablemente NO**, pero hay que analizarlo con cuidado.

El Anexo III define áreas de alto riesgo. La que más se acerca a nuestro caso es el **Punto 5: "Acceso a servicios privados y públicos esenciales"**, específicamente el **apartado 5(b)**, que menciona:
> "Sistemas de IA destinados a evaluar la solvencia de personas físicas o a establecer su puntuación crediticia..."

**Análisis:**
- Nuestro sistema recomienda cursos, no concede créditos ni servicios de subsistencia (vivienda, electricidad). Su impacto, aunque importante para la formación profesional, **no es comparable** a la denegación de un préstamo o una prestación social. No se considera esencial para el sustento vital de una persona.
- Sin embargo, la clasificación depende de si **"influye materialmente en el resultado de la toma de decisiones"** (Artículo 6.3). Si nuestra plataforma es la única vía de acceso a ciertos cursos críticos para la empleabilidad de un colectivo vulnerable, el riesgo podría ser mayor.

**Conclusión preliminar:** Nuestro sistema es de **"Riesgo Limitado"** o **"Riesgo Mínimo"**, lo cual es una gran ventaja, ya que las obligaciones son mucho menores que para un sistema de alto riesgo. Esto no nos exime de cumplir con las obligaciones de transparencia.

---

## ⚖️ 2. Obligaciones Clave para Nuestro Sistema (Capítulo IV)

Aunque nuestro sistema sea de bajo riesgo, el **Artículo 50** (Transparencia) nos impone obligaciones irrenunciables:

### 2.1. Informar de la Interacción con una IA (Artículo 50.1)
> *"Los proveedores garantizarán que los sistemas de IA destinados a interactuar directamente con personas físicas estén diseñados y desarrollados de forma que dichas personas sean informadas de que están interactuando con un sistema de IA..."*

**Implicación para nuestro proyecto:**
- **Requisito Funcional:** Debemos implementar un mensaje claro que indique que las recomendaciones son generadas por un sistema de IA. Ejemplo: "Estas recomendaciones se basan en un análisis de tu perfil mediante inteligencia artificial".

### 2.2. Deber de Información para Contenido Sintético (Artículo 50.2)
> *"Los proveedores de sistemas de IA... que generen contenido sintético de audio, imagen, vídeo o texto garantizarán que los resultados del sistema de IA estén marcados en un formato legible por máquina y sean detectables como generados o manipulados artificialmente."*

**Implicación para nuestro proyecto:**
- Nuestro sistema no genera contenido, **solo recomienda** cursos existentes. Por lo tanto, **esta obligación no aplica directamente** al sistema de recomendación. Aplicaría si usáramos IA para crear descripciones de cursos, pero no es el caso.

### 2.3. Transparencia en el Empleo (Artículo 50.3 y 50.4)
Estos apartados aplican a sistemas de reconocimiento de emociones o *deepfakes*, que no son nuestro caso, pero debemos tenerlos en cuenta para futuros desarrollos (ej. evaluar el compromiso del empleado en un curso).

---

## ⚙️ 3. Requisitos para Sistemas de Propósito General (GPAI) (Capítulo V)

Nuestro modelo de Deep Learning para recomendaciones no es un modelo de propósito general (como GPT). Es un modelo **específico** entrenado para recomendar cursos. Por lo tanto, **las obligaciones del Capítulo V no nos aplican directamente**. Sin embargo, si en el futuro usáramos un modelo base (LLM) para enriquecer la recomendación, entonces sí deberíamos cumplir con:
- **Artículo 53:** Proporcionar documentación técnica y un resumen del contenido de entrenamiento.
- **Artículo 53.1(c):** Tener una política para cumplir con la ley de derechos de autor.

---

## 📊 4. Requisitos Aplicables a Sistemas de "Riesgo Mínimo" (Capítulo III, Sección 2)

Aunque no estemos obligados a cumplir todos los requisitos de la Sección 2 (Artículos 8-15), es una **mejor práctica** y una ventaja competitiva (especialmente para el mercado B2B) adoptarlos voluntariamente, como indica el Artículo 95 (Códigos de conducta).

Los siguientes requisitos son especialmente relevantes para nuestro modelo de calidad:

### 4.1. Gobernanza de Datos (Artículo 10)
> *"Los conjuntos de datos de entrenamiento, validación y prueba serán pertinentes, suficientemente representativos y, en la mayor medida posible, estarán exentos de errores y serán completos en función de la finalidad prevista. Se tendrán especialmente en cuenta la posible existencia de sesgos..."*

**Requisitos para nuestro modelo:**
- **Requisito Funcional:** El sistema debe documentar el origen de los datos de entrenamiento (interacciones de usuarios, compras, valoraciones).
- **Requisito No Funcional:** El modelo debe ser evaluado periódicamente para detectar sesgos (ej. recomendar menos cursos técnicos a mujeres o menos cursos de arte a hombres).
- **Requisito No Funcional:** El dataset debe ser representativo de nuestra base de usuarios (B2C y B2B).

### 4.2. Documentación Técnica y Registros (Artículo 11 y 12)
> *"La documentación técnica se elaborará antes de que el sistema se comercialice o se ponga en servicio..."* y *"Los sistemas de IA de alto riesgo permitirán técnicamente el registro automático de eventos (registros) durante todo el ciclo de vida del sistema."*

**Requisitos para nuestro modelo:**
- **Requisito Funcional:** Debemos mantener un registro de auditoría (logs) de las recomendaciones hechas y las interacciones de los usuarios.
- **Requisito No Funcional:** Debemos tener un sistema de versionado del modelo y documentación clara de su arquitectura, hiperparámetros y métricas de rendimiento (ej. precisión, tasa de conversión).

### 4.3. Transparencia e Información (Artículo 13)
> *"Los sistemas de IA de alto riesgo irán acompañados de instrucciones de uso..."*

**Requisitos para nuestro modelo:**
- **Requisito Funcional:** Crear un "Manual de Usuario" o documentación para los administradores de la plataforma (y para los clientes B2B) donde se explique cómo funciona el sistema de recomendación, sus limitaciones y cómo interpretar sus salidas.

### 4.4. Robustez y Precisión (Artículo 15.1 y 15.3)
> *"Los sistemas de IA de alto riesgo se diseñarán y desarrollarán de forma que alcancen un nivel adecuado de precisión, robustez y ciberseguridad..."*

**Requisitos para nuestro modelo:**
- **Requisito Funcional:** El modelo debe alcanzar una precisión (ej. *Mean Average Precision*) mínima definida en los requisitos del producto.
- **Requisito No Funcional:** El sistema debe ser robusto ante cambios en el comportamiento de los usuarios (ej. *cold start* para nuevos usuarios). Debe tener mecanismos para evitar el *feedback loop* (reforzar sesgos continuamente).
- **Requisito No Funcional:** El sistema debe estar protegido contra ataques adversariales (ej. un usuario malicioso que intenta distorsionar las recomendaciones).

### 4.5. Supervisión Humana (Artículo 14)
> *"Los sistemas de IA de alto riesgo se diseñarán y desarrollarán de forma... que puedan ser supervisados eficazmente por personas físicas durante el período en que estén en uso."*

**Requisito para nuestro modelo:**
- **Requisito Funcional:** Implementar un panel de control para administradores donde puedan revisar las recomendaciones más populares, intervenir manualmente y ajustar el peso de ciertos criterios si es necesario (ej. priorizar cursos de una categoría específica por campaña de marketing).

---

## 🎯 5. Resumen de Requisitos para el Modelo de Calidad

| Categoría | Tipo | Requisito | Fuente en AI Act |
| :--- | :--- | :--- | :--- |
| **Ética y Transparencia** | Funcional | Mostrar mensaje "Recomendado por IA" al usuario. | Art. 50.1 |
| **Ética y Transparencia** | No Funcional | Documentar el origen de los datos de entrenamiento y posibles sesgos. | Art. 10 |
| **Calidad de Datos** | No Funcional | Asegurar datasets representativos y sin sesgos significativos. | Art. 10 |
| **Documentación** | No Funcional | Crear y mantener documentación técnica del modelo (arquitectura, entrenamiento, métricas). | Art. 11 |
| **Auditoría** | Funcional | Implementar sistema de logs de recomendaciones, interacciones y versiones del modelo. | Art. 12 |
| **Transparencia B2B** | Funcional | Proveer manual de uso del sistema para clientes empresariales. | Art. 13 |
| **Rendimiento** | No Funcional | Definir y alcanzar métricas de precisión y robustez (ej. MAP@K). | Art. 15 |
| **Seguridad** | No Funcional | Proteger el sistema contra ataques adversariales y fugas de datos. | Art. 15.5 |
| **Supervisión** | Funcional | Crear un panel de administración para revisar y ajustar recomendaciones manualmente. | Art. 14 |

---

## 📚 6. Conclusión y Siguientes Pasos

1.  **Clasificación:** Nuestro sistema es de **riesgo mínimo/limitado**, lo que simplifica el cumplimiento normativo.
2.  **Obligaciones Clave:** Debemos enfocarnos en la **transparencia** (Art. 50) y en adoptar **mejores prácticas** de gobernanza de datos, documentación y robustez (Art. 10-15), lo cual es esencial para la confianza del usuario y para competir en el mercado B2B.
3.  **Siguientes Pasos:**
    - **Definir KPIs del modelo:** Precisión, tasa de conversión, diversidad de las recomendaciones.
    - **Diseñar la UI/UX:** Incluir el mensaje de transparencia y un enlace a la política de privacidad donde se explique el uso de IA.
    - **Planificar la documentación:** Redactar guías para el equipo de desarrollo y para los clientes.
    - **Implementar un sistema de monitoreo:** Para auditar el rendimiento del modelo y detectar desviaciones (sesgos) a tiempo.

Este análisis sienta las bases para que, como equipo de Deep Learning, podamos definir requisitos funcionales y no funcionales de nuestro modelo de calidad alineados con la regulación europea.

---

[[Equipo 4 - Deep Learning|← Volver al índice principal]]]