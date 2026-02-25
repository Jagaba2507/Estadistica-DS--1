1. Adquisición de Datos: 
  El conjunto de datos utilizado es "UCI Heart Disease Data", el cual involucra cierta cantidad de variables matematicas o estadisticas. Compuesto de 14 atributos como edad, sexo, tipo de dolor en el pecho, presión arterial en reposo, colesterol sérico, nivel de azúcar en sangre en ayunas, resultados electrocardiográficos en reposo, frecuencia cardíaca máxima alcanzada, angina inducida por el ejercicio, oldpeak (depresión del segmento ST inducida por el ejercicio en relación con el reposo), pendiente del segmento ST en el punto máximo del ejercicio, número de vasos principales y talasemia.

  Una de las principales tareas de este dataset es predecir, apartir de los atributos dados por los pacientes, si esa persona presenta o no enfermedad cardiaca. Además el análisis experimental para diagnosticar y extraer hallazgos del conjunto de datos, lo que puede contribuir a una mejor comprensión del problema.

2. Configuración del entorno: prepara tu ambiente de trabajo en R (usando RStudio) o Python (usando Jupyter Notebook). Carga las librerías necesarias para la manipulación de datos (dplyr o pandas), visualización (ggplot2 o matplotlib/seaborn) y análisis.
  El análisis fue desarrollado en Python utilizando Jupyter Notebook como entorno de trabajo, desde Visual Studio Code con la extensión oficial de Jupyter.


3. Análisis descriptivo y exploratorio (EDA): siguiendo la metodología de Tukey, realiza un EDA completo:
• Carga los datos y realiza una inspección inicial (estructura, nombres de variables, tipos de datos).
• Identifica y clasifica las variables en categóricas (nominales, ordinales) y cuantitativas (discretas, continuas).
• Calcula medidas de resumen para las variables numéricas clave (e.g., age, trestbps, chol, thalach):
• Tendencia central: media, mediana.
• Dispersión: desviación estándar, rango intercuartílico (IQR), coeficiente de variación.
• Interpreta las diferencias de estas medidas al agrupar los datos por la variable objetivo (target, presencia o no de enfermedad).

4. Análisis de asociación y probabilidad:
• Calcula la matriz de correlación de Pearson entre las variables numéricas para identificar posibles relaciones lineales. Visualízala con un mapa de calor.
• Calcula probabilidades condicionales relevantes para el problema. Por ejemplo: P(target=1 | sex=1) o P(target=1 | cp > 0).

5. Visualización exploratoria de datos: crea un conjunto de gráficos para comunicar tus hallazgos de manera efectiva:
• Histogramas: para visualizar la distribución de variables continuas como age y chol.
• Diagramas de barras: para comparar frecuencias de variables categóricas como sex, cp (tipo de dolor de pecho) y target.
• Diagramas de caja (Boxplots): Para comparar la distribución de una variable numérica entre diferentes categorías. Por ejemplo, la distribución de la frecuencia cardíaca máxima (halach) para pacientes con y sin enfermedad cardíaca.
• Gráficos de dispersión (Scatter plots): para visualizar la relación entre dos variables numéricas, como age vs. chol.

6. Elaboración del informe: Consolida todo tu análisis en un único documento (Jupyter Notebook o R Markdown). El informe debe ser auto-contenido y reproducible. Incluye:
• El código utilizado en bloques claramente definidos.
• Los resultados numéricos (tablas de resumen) y gráficos generados.
• Interpretaciones escritas: Debajo de cada tabla o gráfico, añade un párrafo explicando qué muestra el resultado en el contexto del problema de salud, respondiendo a las preguntas orientadoras.


## Análisis de Asociación y Probabilidad

### Matriz de correlación

Se calculó la matriz de correlación de Pearson entre variables numéricas y se visualizó mediante un mapa de calor.

**Hallazgos principales:**

- `ca` y `oldpeak` muestran correlación positiva moderada con la severidad.
- `thalach` presenta correlación negativa moderada con la enfermedad.
- `chol` y `trestbps` muestran correlaciones débiles.

Esto indica que algunas variables funcionales tienen mayor asociación lineal con la enfermedad que otras variables tradicionales como el colesterol.

---

### Probabilidades Condicionales

Se calcularon probabilidades condicionales relevantes, tales como:

- P(target = 1)
- P(target = 1 | sex = Male)
- P(target = 1 | oldpeak > 1)
- P(target = 1 | thalach < 120)
- P(target = 1 | ca ≥ 1)

**Hallazgos clave:**

- La probabilidad general de enfermedad es aproximadamente 55%.
- En hombres, la probabilidad es significativamente mayor.
- Valores altos de `oldpeak`, menor `thalach` y presencia de vasos afectados (`ca ≥ 1`) incrementan notablemente la probabilidad de enfermedad.
- El colesterol elevado no mostró un aumento marcado en la probabilidad en esta muestra.

Este análisis permitió evaluar factores de riesgo desde una perspectiva probabilística.

---

## Visualización Exploratoria

Se generaron los siguientes gráficos:

### Histogramas

Para visualizar la distribución de:

- Edad (`age`)
- Colesterol (`chol`)

Se observó que la mayoría de pacientes se concentran entre 45 y 65 años.  
El colesterol presenta algunos valores elevados, aunque la mayor concentración se encuentra entre 180 y 300.

---

### Diagramas de Barras

Para variables categóricas:

- `sex`
- `cp`
- `target`

Se evidenció predominancia de hombres en la muestra y una ligera mayoría de pacientes con enfermedad.

---

### Diagramas de Caja (Boxplots)

Se compararon las distribuciones de:

- `thalach`
- `age`
- `oldpeak`
- `chol`

entre pacientes con y sin enfermedad.

Se observó que:

- Los pacientes con enfermedad tienden a tener menor `thalach`.
- Presentan mayor `oldpeak`.
- Son, en promedio, mayores.
- `chol` no muestra una separación tan clara entre grupos.

---

### Scatterplots

Se analizaron relaciones entre variables como:

- `age` vs `thalach`
- `oldpeak` vs `thalach`
- `age` vs `chol`

Se observó mayor diferenciación visual en combinaciones que incluyen `thalach` y `oldpeak`, mientras que la relación entre edad y colesterol muestra alta superposición entre grupos.

---

## Conclusión General

El análisis exploratorio permitió identificar variables con mayor poder discriminativo para la presencia de enfermedad cardíaca, especialmente:

- `oldpeak`
- `ca`
- `thalach`
- `age`

El colesterol, aunque clínicamente relevante, no mostró una diferenciación fuerte en esta muestra específica.

El informe presentado es reproducible, contiene código claramente estructurado, resultados numéricos y gráficos acompañados de interpretaciones contextualizadas dentro del problema de salud.
