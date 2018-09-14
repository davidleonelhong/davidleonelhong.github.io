---
title: "Introduccion al Data Science"
layout: post
mathjax: true
date: 2018-09-14
tag:
- Data Science
- Analisis de Datos
category: blog
author: David Leonel Hong
description: Introduccion al analisis de datos.
---
# FRAMEWORK BASICO EN UN PROYECTO DE DATA SCIENCE

**1. Adquisicion de Datos:** Importar datos crudos a la plataforma de analisis.

**2. Preparacion:** Explorar y visualizar. Limpieza y transformacion de datos.

**3. Analizar:** Seleccionar Caracteristica, Seleccionar Modelos y Analizar los Resultados.

**4. Reportar:** Presentar los hallazgos.

**5. Actuar:** Utilizar los datos, aplicarlos.

### 1. ADQUIRIR DATOS:
Adquirir datos antes de analizar o actuar sobre los mismos. El primer paso para esta fase es determinar que los datos esten disponibles. Se pueden obtener bajando archivos, accediendo a APIs, hurgando paginas webs o combinando datos de diferentes formatos.

### 2. PREPARACION DE DATOS:
Explorar datos(A) para identificar los metodos a utilizar en un analisis preliminar. Esto se realiza para poder entender los datos que posteriormente van a ser analizados. En esta fase se intenta encontrar correlaciones, tendencias generales, outliers y estadisticas (media, moda, mediana, rango, desvio estandar).
La segunda parte del proceso es la Limpieza y transformacion de datos (B) para poder usar observaciones de calidad, ya que si ingreso datos truchos, obtengo resultados mediocres. Esto se debe a valores incosistentes, duplicados, informacion faltante, etc. Este proceso se lo conoce como Data Wrangling, Data Preprocessing o Data Munging.

### 3. ANALISIS DE DATOS:
Seleccionar tecnicas de analisis y crear modelos a partir de los datos ingresados para obtener resultados. Existen varias tecnicas para analizar pero las mas conocidas son las de clasificacion (predecir una categoria Ej. La accion sube o baja mañana), regresion (predecir valores numericos Ej. La accion va a valer $35), clustering (organizar items similiares en grupos Ej. Conservadores, Riesgo Medio y Riesgosos), analisis de asociaciones (Encontrar reglas para capturar asociaciones entre items Ej. Que la gente que licita LEBACS es mas propensa a invertir en otros activos financieros) y graficos analiticos (para encontrar conexiones Ej. Expansion de una crisis sistemica). A partir de una de ellas, se crea el modelo y se evalua su eficiencia. Para ello, se divie la serie de datos en 2 partes: la 1ra se utiliza para construir el modelo y la 2da para evaluar si funciona el mismo. 

### 4. REPORTAR:
Presentar los resultados, se suelen utilizar graficos y tablas para comunicar. 

### 5. ACTUAR:
Utilizar el analisis y el reporte para aplicar las ideas/conclusiones del modelo a nuestro favor.





