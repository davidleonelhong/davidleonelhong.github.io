---
title: "Trading Day Of the Week (TDOW) en Bitcoin (CSV) [Python]"
layout: post
mathjax: true
date: 2018-10-22
tag:
- Data Science
- Analisis de Datos
- Estadistica
- Trading Day Of the Week
- Python
category: blog
author: David Leonel Hong
description: BTC TDOW importado a traves de un CSV, .
---
# Trading Day Of the Week (TDOW) en BTC

En este analisis, se va a realizar el TDOW aplicado al BTC, importando la serie historica de 5 años por medio de un CSV. El TDOW calcula la **probabilidad (comprar en la apertura y vender al cierre del dia) que BTC cierre en positivo discerniendo a traves del dia de la semana.** Aparte de eso, calcula el **retorno promedio para cada dia**. Esto permite analizar que dias son los que historicamente estan predispuestos a cerrar al alza o a la baja, asi como su retorno pertinente. Mediante esto, podemos determinar que dias nos conviene ir long o short, asi como crear estrategias para trading. El TDOW en BTC, demuestra que los precios no se mueven como un random walk, refutando la teoria de eficiencia de mercado.

En este caso, se van a utilizar datos del **BITCOIN** desde abril de 2013 hasta inicios de abril de 2018. **Tener en cuenta que los datos fueron obtenidos de internet. A pesar de realizar los procedimientos necesarios de limpieza, pueden estar sujetos de errores.**

**LINK DEL ANALISIS EN PYTHON:** [TDOW Aplicado al BTC](https://github.com/davidleonelhong/BTC-TDOW/blob/master/TDOW%20BTC%20(CSV).ipynb)
