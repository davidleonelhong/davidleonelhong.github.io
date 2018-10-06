---
title: "Modern Portfolio Theory y Optimizacion (Yahoo Finance) [Python]"
layout: post
mathjax: true
date: 2018-10-08
tag:
- Data Science
- Analisis de Datos
- Estadistica
- Test de Normalidad
- Modern Portfolio Theory
- Optimization
- Python
category: blog
author: David Leonel Hong
description: MPT y Optimizacion + Test de Normalidad. Datos sacados del Yahoo Finance.
---
# Teoria Moderna de Portfolio y Optimizacion
La **teoría moderna del portafolio** (Modern portfolio theory) examina cómo inversores conservadores pueden construir carteras de activos para optimizar o maximizar su retorno esperado en función del nivel de riesgo de mercado que estén dispuestos a asumir. Bajo este punto de vista una alta rentabilidad va necesariamente acompañada de un nivel más alto de riesgo.

En este caso utilizamos datos de varios activos que conforman el indice **MERVAL** y tomamos como fecha de inicio el 01/01/2014 hasta octubre 2018. Las acciones consideradas fueron ALUA, APBR, BMA, COME, CRES, DGCU2, EDN, GGAL, METR, MIRG, PAMP, TECO2, TGNO4, TGSU2, TRAN, TS, TXAR e YPFD. **Tener en cuenta que los datos fueron obtenidos del Yahoo Finance y pueden estar sujetos a errores debido a que no pasaron por un proceso de limpieza riguroso.**

Ademas de obtener carteras eficientes segun media-varianza y optimizarlas segun **mayor Sharpe Ratio** y **menor varianza**, tambien se realizara un test de normalidad (a diferencia del otro archivo, estos datos seran importados desde un API y no un CSV).

Que se obtuvo mediante el analisis:
* Prueba de Normalidad para los retornos.
* Retornos logaritmicos anualizados por accion y cartera.
* Covarianza anualizada entre activos de la cartera.
* Optimizacion de cartera para obtener el mayor Sharpe Ratio.
* Optimizacion de cartera para obtener la minima varianza absoluta.
* Retorno Esperado Anualizado y Volatilidad Esperada Anualizada por cada optimizacion. Ademas del Sharpe Ratio para c/u.

LINK DEL ANALISIS EN PYTHON: [Teoria Moderna de Cartera y Optimizaciones para el MERVAL](https://github.com/davidleonelhong/MPT-y-Optimizacion/blob/master/%5BYahoo%20Finance%5D%20Normality%20Test%2C%20MPT%2C%20Portfolio%20Optimization.ipynb)]
