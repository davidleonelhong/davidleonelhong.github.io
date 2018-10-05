---
title: "Test de Normalidad (CSV)"
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
# Testeando la Normalidad de una serie

Las **Pruebas de Normalidad** se utilizan para determinar si un conjunto de datos está bien modelado por una distribución normal y para calcular la probabilidad de que una variable aleatoria subyacente al conjunto de datos se distribuya normalmente.

Una basta cantidad de modelos financieros, como el **Mean-Variance Portfolio Theory**, el **Capital Asset Pricing Model (CAPM)**, la **Hipotesis de Mercados Eficientes** (los precios de las acciones fluctuan aleatoriamente y los retornos estan distribuidos normalmente) y el **Option Pricing Theory** (Geometric Brownian Motion) se basan en el supuesto de que los retornos de los activos estan normalmente distribuidos. Por eso, acontinuacion se presentaran enfoques para testear la normalidad de los retornos dada la serie de tiempo pertinente.

En este caso, utilizamos datos del indice **MERVAL** desde octubre 1996 hasta septiembre 2018. De esta manera, se buscara estudiar si los retornos del indice merval se distribuyen de manera normal o no. **Tener en cuenta que los datos fueron obtenidos de Yahoo Finance y pueden tener errores debido a que no pasaron por un proceso de control y limpieza riguroso.**

### Importo los paquetes y librerias necesarias

```import pandas as pd
import numpy as np
import scipy.stats as scs
import statsmodels.api as sm
import matplotlib.pyplot as plt
%matplotlib inline
```
### Importo el CSV y lo agrego a un dataframe llamado MERVAL

```MERVAL = pd.read_csv("MERV.csv")```

### Observo la forma de la serie (filas x columnas)

```MERVAL.shape```

### Busco si faltan valores, True=Si False=No

```MERVAL.isnull().any()```

### Analizo el typo del Dataframe

```type(MERVAL)```

### Creo un dataframe solo para los cierres ajustados y utilizo el dropna para descartar la fila con los NaN

```MERV = MERVAL['Adj Close'].dropna()```

### Comparo la cantidad de datos en la nueva serie sin NaN con la original, asi verifico si elimino las filas

```len(MERV), len(MERVAL)```

### Grafico los cierres del activo (normalizado) para que arranque de 100. Esto me permite graficar otros activos y compararlos ya que todos arrancarian del mismo punto.

```(MERV / MERV.loc[0] * 100).plot(figsize=(8, 6))```

![Alt text](http://localhost:8889/view/Desktop/retornos.png)
