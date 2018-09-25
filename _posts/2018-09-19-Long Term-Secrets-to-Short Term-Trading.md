---
title: "Long-Term Secrets to Short-Term Trading by Larry Williams"
layout: post
mathjax: true
date: 2018-09-19
tag:
- Trading
- Finance
- Quant
- Quantitative finance
- Quantitative analysis
category: blog
author: David Leonel Hong
description: Resumen del libro
---
# RESUMEN:
> Contabiliza porcentualmente las veces que el close > open si compramos a la apertura y vendemos al cierre.

> Nro de veces que el $ cerro arriba despues de 2 dias de baja

## Short-Term Low y Short-Term High:
* STL: daily low con higher lows on the side
* STH: daily high con lower highs on the side
* Podemos aplicar los mismo para timeframes intermedios (como fractales, usar STL o STH) y de largo plazo (usar ITL o ITH).

## Tipos de dias de trading:
* Inside day: opera dentro del rango del dia anterior (lower daily high y higher daily low).
* Outside day: higher high & lower low comparado al dia anterior.

> Contabiliza de los datos historicos el % de inside days y outside days.

## Ciclos:
* Rangos chicos producen rangos grandes. Rangos grandes producen rangos chicos.
* Large Range Up days (LRUD) suelen abrir cerca de los minimos y cerrar cerca de los maximos.
* Large Range Down days (LRDD) suelen abrir cerca de los maximos y cerrar cerca de los minimos.
* Cuanto mayor es la variacion ente el Open respecto al low (LRUD) o high (LRDD), mas se reduce la probabilidad de que sea uno de estos dias.

## Volatility Breakouts:
* Si los precios tienen un movimiento explosivo para arriba o abajo, el mercado va a continuar esa tendencia hasta qye haya un movimiento explosivo opuesto de mayor o igual magnitud.

> Daily Range Values: High-Low

* El DRV mide la volatilidad diaria, cuando esto aumenta, implica un posible cambio de tendencia.
* Utiliza el daily range de t-1.
* Para los entry usa los volatility breakouts, experimenta con un % del DRV de t-1 sumado al Open de t0. Ej. Si el DRV(t-1)=$0.12 y hoy abre a $10, entra en $10+(X% de $0.12). Para vender es lo mismo usa el $Open - un % del DRV(t-1) como entry de venta. 
* Stop Loss = Experimenta con valores fijos o % del Rango del DRV(t-1). Ej. 50% del DRV(t-1) abajo del precio que entre.
* Trading Day of the Week o Trading Day of the Month: utilizarlos para ver si pueden optimizar las estrategias.

> TDOW: compro en la apertura y vendo al cierre. Me fijo por dia (L, M, M, J, V, S, D) que que predomina por dia, si tiende a BAJAR o SUBIR. Calculo tmb el promedio de ganancias segun lo que prevalece ese dia segun el TDOW. Ej. Miercoles 57% +8 = el 57% de las veces los miercoles cierra positivo, en promedio +8.

> Ejemplo de entry que uso para estrategia: comprar en la apertura del TDOW + %X del DRV(t-1). Estrategia: holdear por 3 dias.

> Si el precio (t0) es mayor al precio (t-30), precio (t0) menor al precio (t-9). Compro al Open t+1 y vendo al close de t+2. Ademas 
combino con TDOW o TDOM.

## Estrategias Bullish:

Buy signal: Outside Day a la baja = high (t0) > high (t-1) & low (t0) es < low(t-1) ademas de que el cierre (t0) es menor al low (t-1).
* Si el dia siguiente abre menos que el close del outside down day, compro.
* Stop de 2K y Take profit en el 1rst profitable opening.
* Tambien se puede combinar con el TDOW.

Estrategia bullish #2: busco un dia que haya cerrado arriba del close (t-1) y sea precedido por 2 dias de up close (siendo este el 3er up close)

## Smash days:

1. Smash Day Buy Setup (SDBS): cierre t0 < low (t-1). (Reversal)

> En t+1 compro si el precio se mueve arriba del high de t0 

2. Smash Day Sell Setup (SDSS): cierre t0 > high (t-1)

> En t+1 vendo si el precio se mueve abajo del low de t0. (Reversal)

3. Hidden Buy Smash Day (HBSD): Dia con up close (t0), no tiene que ser mayor al high de t-1. Ademas de cerrar < al open y en el 25% inferior del Daily Range. 

> En t+1 compro si supera el high de t0. (Reversal)

4. Hidden Sell Smash Day (HSSD): Dia con down close (t0), no tiene que ser menor al low en (t-1). Ademas de cerrar > al open y en el 25%
superior del Daily Range.

> En t+1 vendo si rompe el low de t0. (Reversal)
