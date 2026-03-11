**Telecom X – Parte 2: Predicción de Cancelación (Churn)**

📣 Historia del Desafío

¡Felicidades! 🎉 Has sido promovido después de tu excelente desempeño en el análisis exploratorio de la cancelación de clientes en Telecom X. Tu dedicación, claridad al comunicar los datos y visión estratégica marcaron la diferencia.
Ahora, ¡has sido invitado oficialmente a formar parte del equipo de Machine Learning de la empresa!

🎯 Misión
Tu nueva misión es desarrollar modelos predictivos capaces de prever qué clientes tienen mayor probabilidad de cancelar sus servicios.
La empresa quiere anticiparse al problema de la cancelación, y te corresponde a ti construir un pipeline robusto para esta etapa inicial de modelado.

🧠 Objetivos del Desafío
Preparar los datos para el modelado (tratamiento, codificación, normalización).
Realizar análisis de correlación y selección de variables.
Entrenar dos o más modelos de clasificación.
Evaluar el rendimiento de los modelos con métricas.
Interpretar los resultados, incluyendo la importancia de las variables.
Crear una conclusión estratégica señalando los principales factores que influyen en la cancelación.

🧰 Lo que vas a practicar**
✅ Preprocesamiento de datos para Machine Learning 
✅ Construcción y evaluación de modelos predictivos 
✅ Interpretación de resultados y entrega de insights 
✅ Comunicación técnica con enfoque estratégico

    **FASES DEL PROYECTO**
1. Exploración y Limpieza de Datos
   
   Análisis del Dataset: Se revisaron los 7,043 registros y las variables clave (Tenencia, Cargos Mensuales, Contrato, etc.).
   Limpieza: Identificamos y corregimos valores nulos o formatos incorrectos (como la conversión de tipos de datos).
   Visualización: Usé gráficos (boxplots, barras) para entender cómo se comportan los clientes que se van frente a los que se quedan.
   
2. Preparación de los Datos
   
Transformamos los datos "crudos" en algo que el algoritmo pueda entender.
Codificación (Encoding): Conversión de variables categóricas (como "Tipo de Contrato") en números.
División (Split): Separé los datos en un conjunto de Entrenamiento (para que el modelo aprenda) y uno de Prueba (para ver si realmente aprendió).
Balanceo de Clases: Como suele haber menos clientes que cancelan que los que se quedan, usé técnicas (_res) para equilibrar la balanza y que el modelo no ignore a la minoría.

3. Ingeniería de Modelos y Normalización

Creé dos arquitecturas con filosofías distintas:
•	Modelo de Optimización (Regresión Logística): Aquí apliqué Normalización con StandardScaler. Esto fue vital para que las variables con números grandes no sesgaran los coeficientes y el algoritmo convergiera correctamente.
•	Modelo de Ensamble (Random Forest): Este modelo no necesitó normalización porque se basa en particiones binarias (umbrales) y no en distancias.

4. Evaluación de Métricas

Se puso a prueba ambos modelos usando el set de datos que el modelo "no conocía".
•	Métricas de Clasificación: Se calculó la Exactitud (Accuracy), Precisión, Recall y F1-score.
•	Matrices de Confusión: Visualización mediante mapas de calor cuántas veces el modelo acertó y dónde se equivocó (Falsos Positivos vs. Falsos Negativos).

5- Análisis Crítico y Diagnóstico

Interpretación de los resultados para tomar decisiones de negocio.
•	Detección de Ajuste: Se analizó si los modelos sufrían de Overfitting (aprender de memoria) o Underfitting (ser demasiado simples).
•	Comparativa: Se determinó que el Random Forest fue ligeramente superior en equilibrio general, aunque la Regresión Logística fue mejor capturando el Recall (casos positivos).


📈 Resultados y Análisis del Proyecto

 Random Forest:

Reducción de Impureza (Gini Importance) A diferencia de la regresión, el Random Forest no usa una fórmula lineal. Su métrica de importancia se basa en cuánta "limpieza" aporta cada variable al separar los datos.

Interpretación: Si una variable como Tenure (Tenencia) aparece arriba, significa que el modelo la usó constantemente en la parte superior de sus árboles para tomar las decisiones más importantes.

Ventaja: Detecta relaciones no lineales. Por ejemplo, puede descubrir que los "Cargos Mensuales" solo son un problema si el cliente no tiene "Fibra Óptica".

Gracias al uso de StandardScaler, se puede identificar que el tipo de contrato y la antigüedad del cliente son los factores con mayor peso estadístico. Mientras que los cargos elevados actúan como un impulsor de la cancelación, la estabilidad de los contratos a largo plazo funciona como el principal factor de protección contra la fuga de clientes."

📊 Resumen de Conclusiones del Proyecto

El los cálculos de los modelos se puede determinar quien tuvo el mejor desempeño

El ganador técnico es Random Forest, pero por un margen muy estrecho.

F1-Score: El Random Forest (0.58) supera ligeramente a la Regresión Logística (0.57). Dado que el F1-Score es la media armónica entre precisión y recall, este es el mejor indicador de equilibrio.

Precisión vs. Recall: La Regresión Logística tiene un mejor Recall (0.63). Esto significa que es mejor encontrando los casos positivos, pero a costa de equivocarse más (muchos falsos positivos).

El Random Forest tiene mejor Precisión (0.57). Es más "cuidadoso"; cuando dice que algo es positivo, tiene más probabilidad de acertar que la regresión.

Conclusión: Si el objetivo es detectar la mayor cantidad de casos posibles (aunque nos equivoquemos un poco), gana la Regresión Logística. Si el objetivo es no dar falsas alarmas, gana el Random Forest.

El Análisis de Overfitting y Underfitting Regresión Logística: Tendencia al Underfitting (Subajuste)

Diagnóstico: Sus métricas son bajas en general (especialmente la precisión de 0.52).

Causa: Al ser un modelo lineal, probablemente la relación entre tus variables es demasiado compleja para ser explicada por una simple línea recta. El modelo es "demasiado simple" para el problema.

Random Forest: Sospecha de Overfitting (Sobreajuste)

Diagnóstico: Aunque supera a la regresión, una precisión de 0.57 y un recall de 0.58 sugieren que el modelo está sufriendo para generalizar. En Random Forest, es muy común que en el set de entrenamiento los resultados sean cercanos al 1.00, y al ver estos números en test, confirmamos que el modelo no está capturando el patrón real de forma sólida.

**Tecnologías Utilizadas**

Herramienta	          Uso
☁️ Google Colab	Entorno de ejecución en la nube
🐙 GitHub	          Control de versiones
🐍 Python 3.10+	Lenguaje principal
🐼 Pandas	          Manipulación y análisis de datos
📊 Matplotlib	     Visualización estática
🎨 Seaborn	     Visualización estadística avanzada
🌐 Requests	     Consumo de API REST


**USO Y EJECUCIÓN**

1. Opción — Google Colab (Recomendado)
   
   a. Abre Google Colab
   b. Ve a Archivo → Abrir cuaderno → GitHub
   c. Pega la URL de este repositorio
   c. Selecciona TELECOMX_2PARTE.ipynb
   d. Ejecuta las celdas en orden ▶️
   
2. Opción — Local
 
   a. Clonar el Repositorio:      
Estructura del Repositorio **Challenge_3_TELECOM_X_parte**
-README.md
-TelecomX_2PARTE.ipynb

**Autor: Yanucelly Moreira. Alura Latam + Oracle Next Education**

https://github.com/YANUMORE/CHALLENGE_3_TELECOM_X_2_parte.git

yanu.moreira@gmail.com 

