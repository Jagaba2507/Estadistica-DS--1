1. Adquisición de Datos: descarga el conjunto de datos "Heart Disease UCI" desde el repositorio de Kaggle, que es una versión limpia y accesible del original.
Enlace: https://www.kaggle.com/datasets/redwankarimsony/heart-disease-data
Deberás crear una cuenta en Kaggle si no tienes una. La descarga es gratuita.

2. Configuración del entorno: prepara tu ambiente de trabajo en R (usando RStudio) o Python (usando Jupyter Notebook). Carga las librerías necesarias para la manipulación de datos (dplyr o pandas), visualización (ggplot2 o matplotlib/seaborn) y análisis.

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
