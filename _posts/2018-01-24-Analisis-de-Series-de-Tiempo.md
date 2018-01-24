---
title: "Analisis de Series de Tiempo"
layout: post
mathjax: true
date: 2018-01-24
tag:
- Trading
- Finance
- Quant
- Quantitative finance
- Quantitative analysis
category: blog
author: David Leonel Hong
description: Time Series en Python
---
# Análisis de Series de tiempo:

Se busca identificar series de precios que posean tendencia o comportamiento de reversión hacia la media. Si logramos identificarlas, podemos capitalizar mediante estrategias de momentum o mean-reversion. 

## Testeando Mean Reversión

Reversión a la media es el proceso referido a una serie de tiempo que dispone una tendencia de reversión hacia el valor histórico de la media, cuando se presentan divergencias de la misma, es donde se toman posiciones para obtener profits cuando posteriormente convergan. Se utilizan pruebas estadísticas para confirmar si difiere de un comportamiento random walk (el próximo movimiento direccional es completamente independiente de cualquier movimiento pasado). Matemáticamente dicha serie de tiempo continua se denomina **Ornstein-Uhlenbeck process**. 

####  Augmented Dickey-Fuller (ADF) Test:

La prueba de **ADF** busca la presencia de raíz unitaria en una muestra de serie de tiempo autorregresiva. Si la serie de precios posee reversión a la media, entonces el nivel de precio siguiente va a ser proporcional al precio actual.

Output de Python:
1.	Prueba estadística calculada
2.	P-Value
3.	–
4.	Numero de data points en la muestra
5.	El diccionario contiene valores críticos de la prueba estadística en valores de 1, 5 y 10 porciento.

> Si el valor de test estadístico calculadpo es mayor a cualquier valor critico a niveles de 1, 5 y 10 porciento, no podemos rechazar la hipótesis nula y por eso no encontramos una serie de tiempo con reversión a la media, es decir se comporta como Geometric Brownian Motion (GBM), random walk.

Existen métodos alternativos para detectar reversión a la media, particularmente a través del concepto de **estacionariedad**. 

## Testeando la estacionariedad:
 
En una serie estacionaria, la media y varianza del proceso no cambia según tiempo y espacio (se mantienen constantes) y cada una no sigue tendencia alguna. Una característica de las series de precios estacionarias es que sus precios se dispersan de su valor inicial a un ritmo más lento que la del GBM. Calculando esta **diffuse rate**, podemos intendificar la naturaleza de la serie de tiempo y detectar si hay reversión a la media.

#### Hurst Exponent 

Mediante el HE vamos a poder se va a poder identificar si la serie tiene reversión a la media, random walk o tendencia. Se utiliza la varianza de una serie de tiempo logarítmica para evaluar la tasa del comportamiento dispersivo. 

* H > 0.5 -- Serie de tiempo es Mean Reverting
* H = 0.5 -- Serie de tiempo es GBM
* H < 0.5 -- Serie de tiempo tiene tendencia.
* H cercano a 0 tiene mucha reversión a la media, mientras que H cercano a 1 tiene una fuerte tendencia.

> Output Python: dependiendo de lo que de Hurst (ticker), vamos a ver si es GBM, MR o TR.

## Cointegración:

El comportamiento de los equities se asemeja generalmente al GBM, por eso lo mas conveniente es crear un portfolio de series de precios estacionarios, donde podemos aplicar estrategias de trading de reversión a la media al portfolio. Las estrategias más simples de reversión a la media son los **pairs trade**, que incluyen al `dollar-neutral long-short pair of equities`. Esto se debe a que probablemente 2 compañías en el mismo sector estén expuestas a los mismos factores de mercado, que afecten a sus negocios. Ocasionalmente sus precios relativos van a divergir por diferentes eventos, pero convergerán en un futuro a su media de largo plazo.

#### Cointegrated Augmented Dickey-Fuller (CADF)

Se utiliza para determiner el **hedge ratio** óptimo realizando una regresión linear entre 2 series de tiempo, para luego testear su estacionariedad bajo la combinación linear.

Python: hay que crear un archivo nuevo cadf.py e importar las librerías necesarias (numpy, matplotlib, pandas & statsmodels). Primero bajamos los datos para ambas series de tiempo, creamos un DataFrame separado para almacenar los valores de los precios ajustados por cierre, ploteamos la serie de precios y el scatter plot. Por ultimo obtenemos los residuales para calcular el hedge ratio y también los ploteamos para luego aplicar sobre ellos el test de ADF.

> Si el test estadístico es mejor a alguno de los valores críticos de 1, 5 o 10%, rechazamos la hipótesis nula de que no hay una relación cointegral en el X% level. 
