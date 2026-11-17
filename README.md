Overview
ML Championship — Competencia crediticia

LA COMPETENCIA TERMINA EL 17 A LAS 11:30 PM

¿Puedes predecir quién enfrentará dificultades financieras?

Una de las aplicaciones más importantes del Machine Learning en la industria financiera es la estimación del riesgo crediticio.

En esta competencia, el objetivo será construir un modelo de clasificación capaz de estimar la probabilidad de que una persona experimente dificultades financieras graves durante los próximos dos años, utilizando información sobre su historial crediticio y situación financiera.

Los datos son reales y son una recopilación anonimizada de información de performance crediticio de 150,000 individuos y contienen variables relacionadas con utilización de crédito, edad, endeudamiento, ingresos, número de créditos y comportamiento de pago.

El reto

Cada equipo deberá desarrollar un pipeline de Machine Learning que transforme los datos disponibles en una estimación de:

P(SeriousDlqin2yrs = 1)

No existe una única estrategia correcta.

Durante la competencia podrán experimentar con:

Análisis exploratorio de datos.
Tratamiento de valores faltantes y valores atípicos.
Ingeniería y selección de variables.
Diferentes algoritmos de clasificación.
Regularización.
Validación cruzada.
Selección de hiperparámetros.
Ensambles de modelos.
El objetivo no es solamente entrenar modelos más complejos, sino encontrar información útil en los datos y construir una estrategia de modelado que generalice correctamente a observaciones nunca vistas.

Evaluación

Las predicciones serán evaluadas utilizando Area Under the ROC Curve (AUC-ROC).

Por lo tanto, la submission deberá contener la probabilidad predicha para cada observación del conjunto de prueba, y no únicamente una clasificación binaria de 0 o 1.

Durante la competencia podrán observar su desempeño en el Public Leaderboard. Sin embargo, la clasificación definitiva será determinada por el Private Leaderboard al finalizar la competencia.

¿El mejor modelo ganará?

Tal vez.

Un modelo sofisticado no necesariamente supera a un modelo sencillo con buenas variables.

Exploren los datos. Construyan hipótesis. Validen correctamente. Iteren.

Que gane el mejor modelo.

Description
link
keyboard_arrow_up
Descripción del problema

Contexto

La evaluación del riesgo crediticio es uno de los problemas clásicos de clasificación en Machine Learning.

Antes de otorgar un crédito, una institución financiera necesita estimar el riesgo asociado a cada solicitante. Una buena estimación permite tomar mejores decisiones, administrar el riesgo de la cartera y reducir pérdidas derivadas del incumplimiento.

En esta competencia trabajaremos con datos basados en riesgo crediticio, un problema de riesgo crediticio en el que cada observación representa a una persona y contiene información sobre su situación financiera y comportamiento crediticio.

Variable objetivo

La variable que queremos predecir es:

SeriousDlqin2yrs

Esta variable indica si una persona experimentó dificultades financieras graves durante los siguientes dos años.

SeriousDlqin2yrs = 1: presentó dificultades financieras graves.
SeriousDlqin2yrs = 0: no presentó dificultades financieras graves.
El objetivo no es simplemente determinar una clase, sino estimar para cada observación:



donde $X$ representa la información disponible sobre cada individuo.

Datos disponibles

La competencia proporciona dos conjuntos principales:

train.csv

Contiene las observaciones que podrán utilizar para desarrollar y entrenar sus modelos.

Incluye las variables predictoras y la variable objetivo SeriousDlqin2yrs.

test.csv

Contiene nuevas observaciones para las cuales deberán generar predicciones.

La variable SeriousDlqin2yrs no está disponible en este conjunto.

Su objetivo será estimar la probabilidad de SeriousDlqin2yrs = 1 para cada una de estas observaciones.

El desafío

Los datos del mundo real rara vez están listos para introducirse directamente en un algoritmo.

Durante el análisis encontrarán decisiones que deberán resolver como equipo:

¿Cómo tratar los valores faltantes?
¿Existen observaciones atípicas?
¿Todas las variables contienen información útil?
¿Es necesario transformar algunas variables?
¿Pueden construirse nuevas variables a partir de las existentes?
¿Qué modelo generaliza mejor?
¿Cómo deben seleccionar sus hiperparámetros?
¿Cómo pueden estimar el desempeño de su modelo antes de realizar una submission?
Parte importante del reto consiste precisamente en descubrir qué características de los datos son relevantes para mejorar la capacidad predictiva del modelo.

Formato de la predicción

Para cada observación del conjunto test.csv deberán producir una probabilidad entre 0 y 1.

Conceptualmente, el archivo de submission tendrá la siguiente estructura:

Id	Probability
1	0.0832
2	0.7415
3	0.2157
…	…
Las probabilidades deberán corresponder exactamente a las observaciones proporcionadas en test.csv.

Métrica

El desempeño será evaluado mediante Area Under the ROC Curve (AUC-ROC).

$$ AUC = P(\hat{p}{+} > \hat{p}{-}) $$

Intuitivamente, el AUC mide qué tan bien el modelo es capaz de ordenar observaciones de mayor a menor riesgo.

Un valor cercano a 0.5 representa un modelo sin capacidad discriminatoria, mientras que valores más cercanos a 1.0 representan una mejor capacidad para distinguir entre ambas clases.

Por esta razón, deberán enviar probabilidades, no únicamente predicciones binarias de 0 y 1.

Recomendación

No confíen únicamente en el resultado del leaderboard.

Construyan primero una estrategia de validación local que les permita evaluar sus decisiones antes de realizar una submission.

El leaderboard es la evaluación final. La experimentación ocurre antes.

Evaluación
link
keyboard_arrow_up
Las submissions serán evaluadas utilizando Area Under the ROC Curve (AUC-ROC).

El AUC mide la capacidad del modelo para asignar un mayor riesgo a las observaciones que pertenecen a la clase positiva (SeriousDlqin2yrs = 1) que a aquellas que pertenecen a la clase negativa (SeriousDlqin2yrs = 0).

$$ AUC = P(\hat{p}{+} > \hat{p}{-}) $$

donde $\hat{p}{+}$ representa la probabilidad predicha para una observación positiva y $\hat{p}{-}$ la probabilidad predicha para una observación negativa.

Un AUC de 0.5 corresponde aproximadamente a una clasificación aleatoria, mientras que un valor de 1.0 representa una discriminación perfecta.

Un mayor AUC representa un mejor desempeño.

Submission File

Para cada observación de test.csv, deberán generar la probabilidad estimada de que SeriousDlqin2yrs = 1.

No deberán enviar predicciones binarias (0 o 1), sino probabilidades entre 0 y 1.

El archivo deberá:

Estar en formato .csv.
Contener exactamente una predicción por cada observación de test.csv.
Mantener los identificadores del conjunto de prueba.
Utilizar exactamente los mismos nombres de columnas que sample_submission.csv.
No contener columnas adicionales.
El formato esperado es:

```csv Id,Probability 1,0.0832 2,0.7415 3,0.2157 4,0.0371

Se proporciona el archivo sample_submission.csv como referencia del formato exacto requerido.
