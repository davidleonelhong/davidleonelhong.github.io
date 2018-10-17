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

## Testeando Reversion a la Media:
**Reversión a la media** es el proceso referido a una **serie de tiempo que dispone una tendencia de reversión hacia el valor histórico de la media**. La idea verificar que una serie de tiempo es revertible a su media es a traves de pruebas estadisticas para observar si difiere de una random walk. El **random walk** es una serie de tiempo donde **el proximo movimiento direccional es completamente independiente de cualquier movimiento pasado**, es decir, la serie de tiempo no tiene memoria. Por el otro lado, en la serie con **reversion a la media**, el cambio en el valor de la serie en **el proximo periodo es proporcional al valor corriente**. Especialmente, es proporcional a la diferencia entre el precio medio historico y el precio corriente. Matematicamente, este proceso continuo de reversion en la serie de tiempo se lo conoce como **proceso de Ornstein-Uhlenbeck**.

## Augmented Dickey-Fuller (ADF) Test
La prueba ADF hace uso del supuesto de que si los precios poseen reversion a la media, entonces el proximo nivel de precio deberian ser proporcionales al precio de nivel actual. Matematicamente, el ADF esta basado en la idea de testear la presencia de raices unitarias en una muestra de serie de tiempo autoregresiva.

Output de Python:
1.	Prueba estadística calculada
2.	P-Value
3.	–
4.	Numero de data points en la muestra
5.	El diccionario contiene valores críticos de la prueba estadística en valores de 1, 5 y 10 porciento.

> Si el valor de test estadístico calculado es mayor a cualquier valor critico a niveles de 1%, 5% y 10%, no podemos rechazar la hipótesis nula y por eso no encontramos una serie de tiempo con reversión a la media, es decir se comporta como Geometric Brownian Motion (GBM), random walk.

**LINK DEL ANALISIS EN PYTHON:** [Analisis de Series de Tiempo Aplicado al MERVAL]
