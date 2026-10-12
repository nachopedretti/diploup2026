# diploup2026
# TP1 - Análisis exploratorio de datos sobre abandono estudiantil

**Autor:** José Ignacio Pedretti

## Objetivo

Realizar un análisis exploratorio de datos (EDA) para identificar qué variables académicas, laborales y económicas tienen relación con el abandono estudiantil.

La idea es analizar las características de los alumnos que abandonan y compararlas con las de quienes continúan, buscando resultados que puedan servir para mejorar el seguimiento de los estudiantes desde la universidad.

## Dataset

Se utiliza el archivo `academic_survival_longitudinal.csv`, que contiene **79.239 registros y 22 columnas** con información académica, económica y personal de estudiantes.

El dataset incluye datos sobre rendimiento académico, horas de trabajo, asistencia, accesos al campus virtual, estrés financiero y situación académica.

Para analizar el abandono se utiliza principalmente `Target_Dropout_Next_Sem`, donde:

- **0:** el estudiante no abandona en el semestre siguiente.
- **1:** el estudiante abandona en el semestre siguiente.

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
| Target_Dropout_Next_Sem | Indica si abandona en el semestre siguiente |
| End_of_Semester_Status | Estado del estudiante al finalizar el semestre |

## Metodología

El trabajo se realizó en Python, utilizando principalmente Pandas, NumPy, Matplotlib y Seaborn.

Primero se exploró el dataset para conocer sus variables, dimensiones y posibles problemas en los datos.

Después se realizó la limpieza:
- Se revisaron valores nulos y registros duplicados.
- Se reemplazaron valores faltantes de `Family_Income` y `LMS_Logins` utilizando la mediana.
- Se corrigieron 249 valores inconsistentes de asistencia.
- Se analizaron valores atípicos en `Family_Income` mediante el método IQR. Se identificaron 4.002 registros (5,05%), que se conservaron al no contar con evidencia de que fueran errores.

Finalmente, se utilizaron histogramas, boxplots, scatterplots, gráficos de barras, líneas y una matriz de correlaciones para analizar las relaciones entre variables y el abandono.

También se compararon grupos de estudiantes según sus horas de trabajo, rendimiento académico y estrés financiero.

## Principales hallazgos

**Rendimiento académico:** los estudiantes que abandonan tienen un GPA menor que quienes continúan, con medianas de 2,40 y 2,72.

**Horas de trabajo:** quienes abandonan trabajan en promedio 21,29 horas semanales, frente a 16,52 de quienes continúan.

**Trabajo y rendimiento:** los estudiantes que trabajan muchas horas y tienen un GPA bajo presentan un 17,07% de abandono, frente al 3,28% de quienes trabajan menos y tienen mejor rendimiento.

**Estrés financiero:** los alumnos con mayor estrés financiero y muchas horas de trabajo presentan un 14,97% de abandono, frente al 4,13% de quienes tienen menor estrés y trabajan menos.

**Asistencia y campus virtual:** los estudiantes que abandonan presentan una asistencia y una cantidad de accesos al campus virtual ligeramente inferiores.

**Correlaciones:** el rendimiento académico (-0,25) y el estrés financiero (0,22) son las variables con mayor correlación absoluta con el abandono entre las analizadas.

## Conclusión

El análisis permitió encontrar relaciones entre el abandono estudiantil y variables como el rendimiento académico, las horas de trabajo y el estrés financiero.

Uno de los principales resultados es que los alumnos que combinan muchas horas de trabajo con bajo rendimiento académico presentan mayores porcentajes de abandono.

Estos resultados podrían ayudar a la universidad a identificar alumnos que necesitan mayor acompañamiento y evaluar acciones como asesoramiento académico, alternativas de cursada más flexibles y acceso a becas o beneficios.

Se trata de un análisis exploratorio. Los resultados muestran relaciones entre variables, pero no permiten asegurar que sean las causas del abandono.
