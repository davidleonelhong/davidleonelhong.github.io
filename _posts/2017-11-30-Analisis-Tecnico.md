---
title: "Financial Data Storage"
layout: post
mathjax: true
date: 2018-01-23
tag:
- Trading
- Finance
- Quant
- Quantitative finance
- Quantitative analysis
category: blog
author: David Leonel Hong
description: Analisis de equity segun indicadores tecnicos
---

# FINANCIAL DATA STORAGE

## 1. Securities Master Database

Un `securities master database` es una base de datos que guarda datos fundamentales,
de precios y transaccionales para una variedad de instrumentos financieros. Provee acceso a esta informacion de una manera consisitente
para ser usada por otros departamentos como Risk Management. Alguno de los instrumentos de los SMD son acciones, opciones, indices, forex, tasas de interes, futuros, commodities, bonos y derivados.

## 2. Financial Datasets

Para los fondos cuantitativos chicos y los algorithmic traders independientes, 
los datasets mas comunes son `end-of-day` y el `intraday` de precios historicos para acciones, indices, futuros y forex.
Lo recomendado es obtener la mayor cantidad de data posible, especialmente para los datos EOD que su almacenamiento es barato.

## 3. Storage Formats

Existen 3 maneras de almacenar data financiera, todas poseen diferentes
grados de acceso, rendimiento y capacidades estructurales.

#### 3.1 Flat-File Storage

La mas sencilla para almacenar data financiera y probablemente la manera en que recibas los datos de cualquier proveedor de datos. 
Por lo general vienen en el formate de `Comma Separated Variable (CVS)`.
La ventaja de los flat-files es la facilidad de comprimir los archivos para guardarlos o bajarlos.

#### 3.2 Document Stores/NoSQL

Son colecciones y documentos. Los `Document stores`, en aplicaciones financieras, son adecuados para data fundamental o meta data.
La data fundamental para activos financieros vienen en muchas formas como `corporate actions, earnings
statements, SEC filings etc`. La desventaja del NoSQL DBs  es que no esta diseñada para series de tiempo como high-resolution pricing data.

#### 3.3 Relational Database Management Systems

Los RDBMS usan modelos de relacion para almacenar informacion. Estos databases son adecuados para los datos financieros debido a que diferentes _objetos_ (como exchanges, data sources, precios) pueden estar separados en tables con relaciones definidas entre ellos.
RDBMS hace uso de Structured Query Language (SQL) y sus ventajas son su simpleza para la instalacion, platform-independence,
facilidad de querying, facilidad de integrarlas con softwares de backtesting y altas capacidad de rendimiento a grandes escalas.
Sus desventajas son su complejidad para customizar y dificultad de alcanzar dicho performance sin tener conocimiento de los datos almacenados. Es gratis, open-source, cross-platform y escalable, lo que lo hace una buena opction para quant work.

## 4. Historical Data Structure

Acontinuacion les voy a presentar un patron comun para la construccion de un equity security master, el cual podran modificar para que encaje con sus propias comodidades. La primer tarea es definir nuestras entidades, que son los elementos de la data financiera que van a transformarse en tablas de la base de datos. Para el equity master databse:
* Exchanges - Cual es la fuente original de data?
* Vendor - De donde es obtenido un data point particular?
* Instrumento/Ticker - El ticker/simbolo para la accion o indice, junto con informacion corporativa de la firma o fondo.
* Precio - El precio actual de un instrumento e un dia particular.
* Acciones corporativas - Lista de todos los splits o ajustes de dividendos, necesarios para ajustar la pricing data.
* Feriados Nacionales - Para que los dias que no se tradea no sean contados como errores por falta de datos.

