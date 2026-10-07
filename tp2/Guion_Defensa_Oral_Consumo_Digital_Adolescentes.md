# Defensa oral — Consumo digital en adolescentes

**Materia:** Aprendizaje Automático  
**Trabajo:** Grupo N.º 02 — Consumo digital en adolescentes (12 a 18 años)  
**Duración estimada:** 5 minutos  
**Alcance:** Análisis exploratorio de datos (EDA), limpieza y propuesta de clustering.

---

## Guion para la defensa oral (5 minutos)

Buenas tardes. Nosotros somos el grupo de trabajo n2, conformado por los siguientes colaboradores: Javier Carabajal, Gisela Martinez, Noelia Cualina y quien les habla Leonardo Carabajal.-

### 1. Introducción y problema de investigación — 0:00 a 0:50

Nuestro trabajo aborda el consumo digital en adolescentes de entre 12 y 18 años, desde una perspectiva de Aprendizaje Automático.

Partimos de una idea: hoy el uso de pantallas forma parte de la vida cotidiana de los adolescentes, pero no todos las utilizan de la misma manera.

Por ejemplo, dos adolescentes pueden pasar seis horas frente a una pantalla, pero uno dedicar principalmente ese tiempo a redes sociales y otro a videojuegos.

Si analizamos únicamente el tiempo total de exposición, ambos parecen tener el mismo comportamiento, cuando en realidad sus hábitos son diferentes.

Por eso, nuestra pregunta de investigación es: **¿Podemos identificar perfiles diferenciados de adolescentes según sus patrones de uso de pantallas y caracterizarlos a partir de sus hábitos y características?**

Para responderla, proponemos utilizar aprendizaje no supervisado, específicamente técnicas de clustering.

### 2. Comprensión del dataset y análisis exploratorio — 0:50 a 1:40

Para desarrollar el trabajo, comenzamos con un dataset de **4.115 registros y 125 variables**, que incluye información demográfica, consumo digital, hábitos de sueño, somnolencia y rendimiento académico.

El primer desafío fue comprender qué representaba cada variable y evaluar su calidad.

Encontramos variables originales, otras recodificadas y también versiones previamente tratadas, denominadas *trimmed*.

Mediante estadísticas descriptivas, histogramas y análisis de distribuciones, identificamos valores extremos, datos faltantes y posibles redundancias.

Uno de los hallazgos interesantes fue que el consumo digital no se distribuye de manera uniforme entre las actividades. Por ejemplo, observamos un promedio de aproximadamente 4,1 horas de redes sociales en la variable original, frente a 1,1 horas de videojuegos.

Esto refuerza la importancia de analizar **cómo se distribuye el tiempo de pantalla**, y no solamente cuánto tiempo se utiliza.

### 3. Calidad y limpieza de datos — 1:40 a 2:45

Una de las partes más importantes fue definir criterios de limpieza basados en la evidencia del EDA.

Primero, analizamos los valores faltantes. Por ejemplo, algunas variables académicas tenían alrededor de un 69 % de datos ausentes. En lugar de eliminar automáticamente esos registros, decidimos conservar esa información para una posible caracterización posterior.

También encontramos valores inconsistentes en algunas variables de sueño, incluso duraciones negativas, por lo que priorizamos las versiones previamente tratadas.

Para detectar valores extremos utilizamos el método del rango intercuartílico, o IQR. Sin embargo, **no consideramos que todos los outliers debieran eliminarse**, porque un consumo digital elevado puede representar un comportamiento real y relevante para la segmentación.

Otra decisión importante fue evitar variables redundantes. Comprobamos que el tiempo total de pantalla coincidía exactamente con la suma de sus componentes en los 4.115 registros analizados.

Por eso, priorizamos las actividades individuales sobre el total: queremos que el algoritmo distinga tipos de consumo y no cuente dos veces la misma información.

### 4. Dataset resultante y estrategia de segmentación — 2:45 a 3:40

Después del proceso de selección y filtrado, obtuvimos un dataset de **4.062 registros y 32 variables**, conservando las características relevantes para nuestro objetivo.

Acá hay una decisión metodológica que queremos destacar: separamos las variables en dos grupos según su función.

Por un lado, las variables que utilizaremos para construir los clusters, como las horas dedicadas a redes sociales, videojuegos, contenido audiovisual y la frecuencia de uso de dispositivos.

Por otro lado, conservamos variables demográficas, de sueño, somnolencia y rendimiento académico para caracterizar posteriormente los perfiles.

Esta separación es importante porque queremos descubrir grupos a partir del consumo digital y recién después investigar si esos grupos presentan diferencias en otros aspectos.

Así evitamos condicionar la segmentación con características externas al comportamiento que buscamos estudiar.

### 5. Elección del modelo de Aprendizaje Automático — 3:40 a 4:30

Para la siguiente etapa proponemos utilizar **K-Means**, un algoritmo de clustering no supervisado.

Elegimos este enfoque porque no contamos con etiquetas previas que indiquen a qué perfil pertenece cada adolescente. Lo que buscamos es que el algoritmo descubra similitudes entre los comportamientos.

K-Means nos permite agrupar observaciones y analizar posteriormente las características de cada segmento.

Sin embargo, sabemos que es sensible a la escala de las variables y a los valores extremos. Por eso resulta fundamental el análisis y la preparación que realizamos.

Antes de entrenarlo, todavía será necesario definir el tratamiento de los faltantes, estandarizar las variables de entrada y evaluar diferentes cantidades de clusters para determinar una segmentación adecuada.

### 6. Conclusión y cierre — 4:30 a 5:00

Como conclusión, este trabajo nos permitió comprender el dataset, detectar problemas de calidad y definir qué información necesitamos para construir perfiles de consumo digital.

Nuestro objetivo no es demostrar que las pantallas causan problemas de sueño o de rendimiento académico, sino identificar patrones y explorar posibles asociaciones.

Consideramos que este enfoque puede aportar información útil para comprender mejor los hábitos digitales de los adolescentes y, a futuro, orientar estrategias educativas y de concientización adaptadas a diferentes perfiles.

**En definitiva, buscamos pasar de analizar cuánto tiempo usan pantallas los adolescentes a comprender cómo las utilizan y qué características distinguen sus comportamientos.**

Muchas gracias.

---

## Los tres puntos más valiosos para destacar

### 1. Diferencia entre segmentar y caracterizar

Es probablemente la decisión metodológica más importante. Los clusters se construirán con variables de consumo digital; las variables de sueño, somnolencia, rendimiento académico y características demográficas servirán para caracterizar los perfiles después.

### 2. Limpiar no es simplemente eliminar datos

El tratamiento de faltantes, la revisión de outliers y la eliminación de redundancias respondieron al objetivo de investigación. No se aplicaron reglas automáticas indiscriminadamente.

### 3. La elección de K-Means está conectada con el EDA

El análisis previo mostró por qué hay que atender a los valores extremos, las escalas de medición y los faltantes antes de entrenar el algoritmo.

---

## Preguntas posibles del profesor y respuestas sugeridas

**¿Por qué eligieron aprendizaje no supervisado?**  
Porque no existe una etiqueta previa que indique a qué perfil de consumo pertenece cada adolescente. Buscamos descubrir agrupamientos basados en similitudes entre sus comportamientos, en lugar de predecir una categoría conocida.

**¿Por qué no utilizaron directamente el tiempo total de pantalla?**  
Porque el total resume la cantidad de consumo, pero pierde información sobre su composición. Además, comprobamos que era exactamente la suma de sus componentes, por lo que incorporarlo junto con ellos introduciría redundancia.

**¿Por qué conservaron registros con datos faltantes?**  
Porque no todas las variables cumplen la misma función. Un adolescente sin calificaciones académicas todavía puede aportar información valiosa sobre consumo digital. Los faltantes de las variables necesarias para K-Means deberán tratarse antes del entrenamiento.

**¿El dataset final está completamente limpio?**  
No en el sentido de estar completamente preparado para entrenar. Ya se realizó la selección de variables y el filtrado poblacional, pero persisten valores faltantes. Todavía resta definir su tratamiento y escalar las variables de entrada.

**¿Qué pasa con los adolescentes que no tienen edad informada?**  
El dataset resultante conserva 562 registros sin edad informada para no perder información potencialmente útil. Sus edades no están verificadas dentro del rango de 12 a 18 años; es una limitación que deberá considerarse en los análisis posteriores.

**¿Pueden concluir que usar más pantallas produce mayor somnolencia?**  
No. El estudio es exploratorio y descriptivo. Incluso si encontramos diferencias entre clusters, estas representarían asociaciones, no evidencia de causalidad.

---

## Recomendaciones para exponer

- No explicar línea por línea el código de Pandas ni los cálculos internos del IQR, salvo que lo pregunten.
- Fundamentar cada decisión de limpieza según el objetivo de segmentación.
- Hablar de K-Means como **modelo propuesto para la etapa siguiente**, sin afirmar que ya fue entrenado.
- Ensayar el guion en voz alta y ajustar las pausas para acercarse a los cinco minutos.

### Idea principal para memorizar

> No buscamos que el algoritmo agrupe adolescentes según sus problemas de sueño o sus calificaciones, sino descubrir primero cómo se diferencian sus patrones de consumo digital y luego analizar qué otras características presentan esos perfiles.

Esa idea conecta la pregunta de investigación, el EDA, la limpieza y el modelo elegido.
