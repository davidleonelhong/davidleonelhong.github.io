---
title: "Test de Normalidad (CSV) [Python]"
layout: post
mathjax: true
date: 2018-10-05
tag:
- Data Science
- Analisis de Datos
- Estadistica
- Test de Normalidad
- Python
category: blog
author: David Leonel Hong
description: Test de normalidad a un CSV.
---
# Testeando la Normalidad de una Serie

Las **Pruebas de Normalidad** se utilizan para determinar si un conjunto de datos está bien modelado por una distribución normal y para calcular la probabilidad de que una variable aleatoria subyacente al conjunto de datos se distribuya normalmente.

Una basta cantidad de modelos financieros, como el **Mean-Variance Portfolio Theory**, el **Capital Asset Pricing Model (CAPM)**, la **Hipotesis de Mercados Eficientes** y el **Option Pricing Theory** (Geometric Brownian Motion) se basan en el supuesto de que los retornos de los activos estan normalmente distribuidos. Por eso, acontinuacion se presentaran enfoques para testear la normalidad de los retornos dada la serie de tiempo pertinente.

En este caso, se van a utilizar datos del indice **MERVAL** desde octubre 1996 hasta septiembre 2018. De esta manera, se va a buscar estudiar la distribucion de los retornos del indice MERVAL. **Tener en cuenta que los datos fueron obtenidos de Yahoo Finance y pueden tener errores debido a que no pasaron por un proceso de control y limpieza riguroso.**

**LINK DEL ANALISIS EN PYTHON:** [Test de Normalidad](https://github.com/davidleonelhong/Normality-Test-CSV/blob/master/Normality%20Test%20CSV.ipynb)
