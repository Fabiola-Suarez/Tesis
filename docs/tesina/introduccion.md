# CAPÍTULO 1. INTRODUCCIÓN

## 1.1. Contextualización

Las bases de datos relacionales constituyen un componente fundamental de numerosos sistemas informáticos, ya que permiten almacenar, organizar, consultar y modificar información estructurada. Su utilización se encuentra presente en aplicaciones empresariales, plataformas educativas, sistemas administrativos y otros entornos que requieren gestionar grandes volúmenes de datos (Elmasri & Navathe, 2016; Silberschatz et al., 2019).

El funcionamiento de estos sistemas depende, entre otros factores, de la capacidad del motor de base de datos para procesar las operaciones solicitadas. Las consultas, inserciones, actualizaciones y eliminaciones de registros requieren recursos computacionales y pueden presentar diferentes tiempos de ejecución dependiendo de las características de la información almacenada y de las estrategias utilizadas para su procesamiento.

El rendimiento de una base de datos adquiere especial importancia cuando aumenta el volumen de información o cuando se ejecutan operaciones que involucran múltiples tablas, filtros, agrupamientos y cálculos de agregación. En estos escenarios, los tiempos de respuesta pueden incrementarse y afectar el funcionamiento general de las aplicaciones que dependen de dichos procesos.

Entre los sistemas gestores de bases de datos relacionales de código abierto se encuentran PostgreSQL y MariaDB. Ambos permiten implementar estructuras relacionales y ejecutar operaciones mediante el lenguaje SQL (Structured Query Language). Sin embargo, poseen mecanismos propios de almacenamiento, planificación y optimización de consultas, lo que puede producir diferencias en sus tiempos de ejecución (MariaDB, 2026; PostgreSQL Global Development Group, 2026).

La evaluación de estas diferencias requiere considerar múltiples factores, entre ellos el volumen de registros, la utilización de índices, las características de las consultas y la configuración del entorno de ejecución.

En este contexto, el presente trabajo propone realizar un análisis comparativo de los tiempos de ejecución de distintas operaciones SQL sobre PostgreSQL y MariaDB, mediante la implementación de escenarios de prueba equivalentes que permitan observar su comportamiento y analizar los factores asociados a las diferencias de rendimiento.

## 1.2. Planteamiento del problema

El rendimiento de las operaciones ejecutadas sobre una base de datos relacional constituye un aspecto relevante para el funcionamiento de los sistemas informáticos. Una misma operación SQL puede presentar diferentes tiempos de ejecución dependiendo del motor utilizado, del volumen de información, de los índices disponibles y de las estrategias de procesamiento seleccionadas.

Cuando una consulta presenta tiempos de respuesta elevados, identificar su causa puede resultar complejo, debido a que intervienen diferentes componentes del sistema. Entre ellos se encuentran la estructura de las tablas, los mecanismos de acceso a los datos, los planes de ejecución y la utilización de los recursos disponibles.

Por otra parte, comparar el rendimiento de dos motores de bases de datos no consiste únicamente en ejecutar una consulta y registrar el tiempo obtenido. Para que los resultados sean comparables, es necesario establecer condiciones de prueba equivalentes, utilizar conjuntos de datos comunes y repetir las mediciones para reducir la influencia de variaciones ocasionales.

La ausencia de una metodología de comparación controlada puede conducir a interpretaciones incorrectas sobre el comportamiento de los motores, especialmente cuando no se consideran las características particulares de las operaciones realizadas.

En consecuencia, resulta necesario estudiar cómo se comportan PostgreSQL y MariaDB frente a diferentes escenarios de procesamiento, identificando no solamente las variaciones en sus tiempos de ejecución, sino también los posibles factores que contribuyen a dichas diferencias.

A partir de esta problemática, se plantea la siguiente pregunta de investigación:

¿Cómo varían los tiempos de ejecución de operaciones SQL equivalentes entre PostgreSQL y MariaDB cuando cambian el volumen de datos, la utilización de índices y las estrategias de procesamiento?

De manera complementaria, se buscará analizar qué factores pueden explicar las diferencias observadas y qué técnicas de optimización permiten reducir los tiempos de ejecución en los escenarios evaluados.

## 1.3. Justificación de la investigación

El estudio del rendimiento de los motores de bases de datos relacionales resulta relevante debido a la importancia que tiene el procesamiento de información en los sistemas informáticos actuales.

Las operaciones realizadas sobre una base de datos pueden influir directamente en los tiempos de respuesta de las aplicaciones. Por este motivo, comprender los factores que afectan su ejecución permite contar con mayores herramientas para identificar problemas de rendimiento y evaluar alternativas de optimización.

La presente investigación se justifica desde una perspectiva técnica y metodológica.

Desde el punto de vista técnico, permitirá analizar el comportamiento de PostgreSQL y MariaDB frente a un conjunto de operaciones SQL equivalentes. La comparación buscará identificar cómo influyen determinadas variables, como el volumen de datos y la presencia de índices, en los tiempos registrados por cada motor.

Asimismo, se pretende profundizar en el análisis de las posibles causas de las diferencias observadas, considerando las estrategias de ejecución empleadas y las características de las operaciones evaluadas.

Desde el punto de vista metodológico, el trabajo propone establecer un procedimiento de pruebas controladas y reproducibles. Para ello, se diseñará una estructura de datos común, se automatizará la ejecución de operaciones y se registrarán los resultados obtenidos mediante mediciones repetidas.

Este enfoque permitirá construir un conjunto de resultados que facilite el análisis comparativo y reduzca la dependencia de observaciones aisladas.

Finalmente, la investigación buscará contribuir a la identificación de criterios de diagnóstico y patrones de optimización aplicables a situaciones similares a las estudiadas. De esta manera, los resultados podrán servir como referencia para comprender determinados problemas de rendimiento y evaluar posibles mejoras en operaciones SQL.

## 1.4. Objetivos de la investigación

### 1.4.1. Objetivo general

Comparar los tiempos de ejecución de operaciones SQL equivalentes en los motores de bases de datos relacionales PostgreSQL y MariaDB, mediante pruebas realizadas sobre conjuntos de datos comunes y bajo condiciones controladas, con el propósito de analizar las diferencias de rendimiento, identificar posibles factores que las originan y evaluar alternativas de optimización.

### 1.4.2. Objetivos específicos

1. Diseñar un modelo de datos relacional y conjuntos de datos de prueba que permitan evaluar operaciones SQL bajo diferentes volúmenes de información.
2. Implementar estructuras de bases de datos equivalentes en PostgreSQL y MariaDB, procurando mantener condiciones comparables para la ejecución de las pruebas.
3. Desarrollar scripts que automaticen la generación y carga de datos, la ejecución de operaciones SQL y el registro de los tiempos obtenidos.
4. Evaluar los tiempos de ejecución de operaciones de inserción, consulta, filtrado, unión entre tablas, agrupamiento, agregación, actualización y eliminación de registros.
5. Analizar el comportamiento de ambos motores ante el incremento del volumen de datos y la incorporación de índices.
6. Ejecutar mediciones repetidas de cada escenario y organizar los resultados en un conjunto de datos que permita realizar comparaciones.
7. Examinar los resultados obtenidos para identificar posibles causas de las diferencias de rendimiento, considerando las estrategias de procesamiento utilizadas por cada motor.
8. Evaluar alternativas de optimización en los escenarios que presenten tiempos de ejecución elevados y proponer criterios o patrones que contribuyan al diagnóstico y mejora del rendimiento.

## 1.5. Hipótesis de investigación

La investigación parte de la hipótesis de que los tiempos de ejecución de operaciones SQL equivalentes presentan diferencias entre PostgreSQL y MariaDB, y que dichas diferencias varían en función del volumen de información procesada, la utilización de índices y las estrategias de ejecución empleadas por cada motor.

Se considera, además, que el análisis de los planes de ejecución y de las características de las operaciones permitirá identificar posibles causas de las diferencias observadas y evaluar técnicas de optimización capaces de reducir los tiempos de procesamiento en determinados escenarios.

Esta hipótesis será contrastada mediante pruebas experimentales y el análisis de los resultados obtenidos.

## 1.6. Alcance y limitaciones

La investigación se centrará en el análisis comparativo de los tiempos de ejecución de PostgreSQL y MariaDB.

Para desarrollar las pruebas, se implementará un esquema relacional común en ambos motores y se utilizarán conjuntos de datos de diferentes tamaños, con cantidades crecientes de registros.

Las operaciones evaluadas comprenderán consultas simples, búsquedas con filtros, consultas sobre columnas indexadas y no indexadas, uniones entre tablas, agrupamientos, funciones de agregación, inserciones, actualizaciones y eliminaciones.

Las pruebas serán ejecutadas bajo condiciones controladas, procurando mantener recursos y configuraciones comparables. Asimismo, se realizarán mediciones repetidas para facilitar el análisis de los resultados.

El estudio se enfocará principalmente en los tiempos de ejecución de las operaciones SQL. Otros aspectos de los sistemas gestores, como la seguridad, la alta disponibilidad, la facilidad de administración o la compatibilidad con aplicaciones específicas, quedarán fuera del alcance de la investigación.

De igual manera, no se buscará establecer que un motor es superior al otro en términos generales. Las conclusiones estarán limitadas a los escenarios experimentales definidos y a las condiciones en las cuales se realicen las mediciones.

El análisis de los problemas de rendimiento se concentrará en las operaciones estudiadas, sin pretender desarrollar un método universal que permita resolver cualquier problema de ejecución lenta.

Como resultado complementario, se procurará identificar criterios de diagnóstico y patrones de optimización cuya efectividad pueda ser observada a partir de las pruebas realizadas.

## 1.7. Metodología general

El trabajo se desarrollará mediante un enfoque cuantitativo, basado en la ejecución de pruebas experimentales y en el análisis de los tiempos registrados.

En una primera etapa, se definirá el entorno de evaluación y se establecerán las condiciones necesarias para realizar comparaciones entre ambos motores. Posteriormente, se diseñará un modelo de datos relacional común y se generarán conjuntos de datos con volúmenes crecientes de registros.

Una vez implementadas las bases de datos, se desarrollarán scripts destinados a automatizar la carga de información, la ejecución de las operaciones SQL y la recopilación de las mediciones.

Cada escenario de prueba será ejecutado repetidamente, con el propósito de registrar múltiples observaciones y disminuir la influencia de resultados aislados. Los tiempos obtenidos serán almacenados y organizados para su posterior procesamiento.

El análisis contemplará la comparación de los tiempos de ejecución entre PostgreSQL y MariaDB, considerando las características de cada operación, el volumen de información y la utilización de índices.

En aquellos escenarios donde se observen diferencias relevantes o tiempos de procesamiento elevados, se examinarán posibles causas mediante herramientas de análisis de ejecución proporcionadas por los motores.

Finalmente, cuando corresponda, se aplicarán modificaciones orientadas a optimizar las operaciones evaluadas y se repetirán las pruebas para determinar si las mejoras propuestas producen reducciones medibles en los tiempos de ejecución.

Los resultados serán presentados mediante tablas, gráficos y análisis comparativos que permitan interpretar el comportamiento registrado en cada escenario.
