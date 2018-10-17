---
title: "Time Series Analysis [Python]"
layout: post
mathjax: true
date: 2018-10-10
tag:
- Data Science
- Analisis de Datos
- Estadistica
- Time Series
- Python
category: blog
author: David Leonel Hong
description: Analis de Series de Tiempo al MERVAL.
---
# Analisis de Series de Tiempo Aplicado al MERVAL:

En este articulo se van a realizar pruebas estadisticas para identificar si el indice MERVAL tiene un comportamiento de **reversion a la media, tendencia o random walk** Dicho analisis se puede aplicar a cualquier serie de tiempo y el objetivo del mismo es capitalizar mediante estrategias de momentum o de reversion a la media, dependiendo del caso.

### Testeando Reversion a la Media:
**Reversión a la media** es el proceso referido a una **serie de tiempo que dispone una tendencia de reversión hacia el valor histórico de la media**. La idea verificar que una serie de tiempo es revertible a su media es a traves de pruebas estadisticas para observar si difiere de una random walk. El **random walk** es una serie de tiempo donde **el proximo movimiento direccional es completamente independiente de cualquier movimiento pasado**, es decir, la serie de tiempo no tiene memoria. Por el otro lado, en la serie con **reversion a la media**, el cambio en el valor de la serie en **el proximo periodo es proporcional al valor corriente**. Especialmente, es proporcional a la diferencia entre el precio medio historico y el precio corriente. Matematicamente, este proceso continuo de reversion en la serie de tiempo se lo conoce como **proceso de Ornstein-Uhlenbeck**.

#### Augmented Dickey-Fuller (ADF) Test
La prueba ADF hace uso del supuesto de que si los precios poseen reversion a la media, entonces el proximo nivel de precio deberian ser proporcionales al precio de nivel actual. Matematicamente, el ADF esta basado en la idea de testear la presencia de raices unitarias en una muestra de serie de tiempo autoregresiva.

Output de Python:
1.	Prueba estadística calculada
2.	P-Value
3.	–
4.	Numero de data points en la muestra
5.	El diccionario contiene valores críticos de la prueba estadística en valores de 1, 5 y 10 porciento.

> Si el valor de test estadístico calculado no es mayor a cualquier valor critico a niveles de 1%, 5% y 10%, no se rechaza la hipótesis nula y por eso la serie se comporta como random walk (Geometric Brownian Motion). En otras palabras, no tiene reversion a la media.

### Testeando Estacionariedad:
En una serie estacionaria, la media y varianza del proceso no cambia según tiempo y espacio (se mantienen constantes) y cada una no sigue tendencia alguna. Una característica de las series de precios estacionarias es que sus precios se dispersan de su valor inicial a un ritmo más lento que la del GBM. Calculando esta **diffuse rate**, podemos intendificar la naturaleza de la serie de tiempo y detectar si hay reversión a la media.

#### Hurst Exponent 

Mediante el HE vamos a poder obtener un valor escalar que va a permitir identificar si la serie tiene una conducta de reversión a la media, random walk o tendencia. Se utiliza la varianza de una serie de tiempo logarítmica para evaluar la tasa del comportamiento difusivo. 

* H < 0.5 -- Serie de tiempo es Mean Reverting
* H = 0.5 -- Serie de tiempo es GBM
* H > 0.5 -- Serie de tiempo tiene tendencia.
* H cercano a 0 tiene mucha reversión a la media, mientras que H cercano a 1 tiene una fuerte tendencia.

> Output Python: dependiendo de lo que de Hurst (ticker), vamos a ver si es GBM, MR o TR.

**LINK DEL ANALISIS EN PYTHON:** [Analisis de Series de Tiempo Aplicado al MERVAL]
