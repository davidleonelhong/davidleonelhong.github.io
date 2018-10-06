---
title: "Modern Portfolio Theory y Optimizacion (Yahoo Finance) [Python]"
layout: post
mathjax: true
date: 2018-10-05
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
La teoría moderna del portafolio (Modern portfolio theory) examina cómo inversores conservadores pueden construir carteras de activos para optimizar o maximizar su retorno esperado en función del nivel de riesgo de mercado que estén dispuestos a asumir. Bajo este punto de vista una alta rentabilidad va necesariamente acompañada de un nivel más alto de riesgo.

En este caso utilizamos datos de varios activos que conforman el indice MERVAL y tomamos como fecha de inicio el 01/01/2014. Tener en cuenta que los datos fueron obtenidos del Yahoo Finance y pueden estar sujetos a errores debido a que no pasaron por un proceso de limpieza riguroso.

Ademas de obtener carteras eficientes segun media-varianza y optimizarlas segun mayor Sharpe Ratio y menor varianza, tambien se realizara un test de normalidad (a diferencia del otro archivo, estos datos seran importados desde un API y no un CSV).
