# TP1 - Análisis exploratorio de datos sobre abandono estudiantil

**Autor:** José Ignacio Pedretti  
**Repositorio:** diploup2026

## Objetivo

Realizar un análisis exploratorio de datos (EDA) para identificar qué variables académicas, laborales y económicas tienen relación con el abandono estudiantil.

Mi objetivo es analizar las características de los alumnos que abandonan y compararlas con las de quienes continúan, buscando resultados que puedan servir para mejorar el seguimiento de los estudiantes desde la universidad.

## Dataset

Utilicé el archivo `academic_survival_longitudinal.csv`, que contiene **79.239 registros y 22 columnas** con información académica, económica y personal de estudiantes.

El dataset incluye datos sobre rendimiento académico, horas de trabajo, asistencia, accesos al campus virtual, estrés financiero y situación académica.

Cada registro corresponde a la información de un estudiante en un semestre, por lo que la cantidad de registros no necesariamente equivale a la cantidad de alumnos únicos.

Para analizar el abandono utilicé principalmente `Target_Dropout_Next_Sem`, donde:

- **0:** el estudiante no abandona en el semestre siguiente.
- **1:** el estudiante abandona en el semestre siguiente.

También utilicé `End_of_Semester_Status` para conocer la situación académica de los estudiantes al finalizar cada semestre.

## Diccionario de datos

Estas son las principales variables utilizadas en el análisis:

| Variable | Descripción |
|---|---|
| Student_ID | Identificador del estudiante |
| Semester | Semestre que cursa |
| Work_Hours | Horas de trabajo semanales |
| Sem_GPA | Promedio académico del semestre |
| Attendance | Porcentaje de asistencia |
| LMS_Logins | Cantidad de accesos al campus virtual |
| Course_Load | Cantidad de materias cursadas |
| Financial_Stress | Nivel de estrés financiero |
| Family_Income | Ingreso familiar |
| Advising_Visits | Visitas de asesoramiento académico |
| Housing_Status | Situación de vivienda del estudiante |
| Target_Dropout_Next_Sem | Indica si abandona en el semestre siguiente |
| End_of_Semester_Status | Estado del estudiante al finalizar el semestre |

## Metodología

Realicé el trabajo en Python, utilizando principalmente Pandas, NumPy, Matplotlib y Seaborn.

Primero exploré el dataset para conocer sus variables, dimensiones y posibles problemas en los datos.

Después realicé la limpieza:

- Revisé los valores nulos y los registros duplicados.
- Reemplacé los valores faltantes de `Family_Income` y `LMS_Logins` utilizando la mediana.
- Corregí 249 valores inconsistentes de asistencia, reemplazándolos por la mediana.
- Analicé los valores atípicos de `Family_Income` mediante el método IQR. Identifiqué 4.002 registros (5,05%) que decidí conservar, ya que no encontré evidencia suficiente para considerarlos errores.

Para el análisis utilicé histogramas con KDE, boxplots, scatterplots, gráficos de barras, líneas y una matriz de correlaciones.

También comparé grupos de estudiantes según sus horas de trabajo, rendimiento académico y estrés financiero para identificar diferencias en las tasas de abandono.

## Cómo ejecutar el análisis
El análisis se encuentra en el notebook DiploUP_TP1_9449.ipynb y fue desarrollado en Google Colab utilizando Python.

## Principales hallazgos

### 1. Rendimiento académico

Los estudiantes que abandonan tienen un GPA más bajo que los que continúan, con medianas de 2,40 y 2,72 respectivamente.

Esto podría servir para identificar alumnos que necesitan mayor seguimiento e incentivar las visitas de asesoramiento académico (`Advising_Visits`).

### 2. Horas de trabajo y rendimiento

Los estudiantes que abandonan trabajan en promedio 21,29 horas semanales, frente a 16,52 de los que continúan.

Al combinar trabajo y rendimiento, el abandono llega al **17,07%** entre quienes trabajan muchas horas y tienen un GPA bajo, frente al **3,28%** de quienes trabajan menos y tienen mejor rendimiento.

Considero que se podrían evaluar alternativas de cursada más flexibles o asincrónicas para acompañar a estos estudiantes.

### 3. Estrés financiero y trabajo

Los estudiantes con mayor estrés financiero y más horas de trabajo presentan un **14,97% de abandono**, frente al **4,13%** de quienes tienen menor estrés y trabajan menos.

Estos resultados podrían ayudar a identificar alumnos que necesitan apoyo económico y evaluar mayores oportunidades de acceso a becas y beneficios.

### 4. Asistencia y campus virtual

Los estudiantes que abandonan tienen menos accesos al campus virtual (62,85 frente a 66,71) y una asistencia algo menor (83,26% frente a 85,32%).

Considero que ambas variables podrían servir como señales para hacer un seguimiento de los alumnos, aunque por sí solas no indican que vayan a abandonar.

### 5. Abandono según el semestre

La tasa de abandono es menor en el primer semestre (6,7%), aumenta en los siguientes y después se mantiene cerca del 9% y 10%.

Esto muestra que el seguimiento de los alumnos no debería concentrarse solamente en los ingresantes, sino también en quienes están más avanzados en la carrera.

### 6. Correlaciones

El rendimiento académico (-0,25) y el estrés financiero (0,22) son las variables que presentan mayor correlación con el abandono entre las analizadas, aunque los valores no son muy altos.

También encontré que los estudiantes que trabajan más horas tienden a tener menor asistencia (-0,30).

Estos resultados muestran que el abandono podría estar relacionado con distintos factores académicos, laborales y económicos.

## Variables que decidí no profundizar

Durante el análisis también revisé otras variables, como la situación de vivienda, pero no encontré diferencias importantes en la asistencia según esta variable.

Por eso decidí concentrarme en los resultados que consideré más relevantes para analizar el abandono estudiantil.

Esto no significa que las variables que dejé de lado no tengan relación con el abandono, sino que no profundicé en ellas dentro de este trabajo.

## Conclusión general

A través del análisis pude encontrar relaciones entre el abandono estudiantil y factores como el rendimiento académico, las horas de trabajo, el estrés financiero y la participación académica.

Uno de los principales resultados que encontré es que **los alumnos que trabajan muchas horas y tienen bajo rendimiento presentan mayores porcentajes de abandono**. Algo similar ocurre cuando se combinan muchas horas de trabajo y estrés financiero elevado.

Considero que estos resultados podrían ayudar a la universidad a identificar perfiles que necesitan mayor acompañamiento y pensar acciones para mejorar la permanencia de los alumnos.

De todas formas, se trata de un análisis exploratorio, por lo que pude identificar relaciones entre variables, pero no asegurar que sean las causas del abandono.
