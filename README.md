📌
## DESCRIPCIÓN

Este laboratorio implementa el analisis estadistico de señales , donde se abordaran los conceptos de **convolución** , **correlación** y **transformada de Fourier** 

## REQUISITOS

Este laboratorio requiere las siguientes librerias:

- import numpy as np
- import matplotlib.pyplot as plt
- import wfdb
- from scipy.signal import welch (para estimar el contenido espectral de una señal, útil en el análisis de frecuencias)

## OBJETIVOS

- Reconocer la convolución como operación entre señal y sistema
- Aplicar la correlación
- Utilizar la transformada de Fourier para el analisis en el dominio de la frecuencia

## ESTRUCTURA 

 🔬 **FUNDAMENTO TEORICO**

 En el análisis de señales biomédicas, es fundamental comprender ciertos estadísticos descriptivos que permiten resumir y caracterizar el comportamiento de la señal. Estos estadísticos ayudan a identificar patrones, tendencias y variaciones que podrían no ser evidentes a simple vista. 

A continuación, se explican los principales estadísticos utilizados en esta práctica:

## MEDIA :  
La media es una medida de tendencia central que representa el valor promedio de una señal. Se calcula sumando todos los valores de la señal y dividiendo entre el número total de muestras. La media también se conoce como media aritmética o promedio. Además, la media de una distribución estadística es equivalente a su esperanza matemática.

  ![](https://github.com/Nupan07/procesamiento/blob/main/MEDIA.png)

  Donde:

**𝑁: N es el número total de muestras.**

**X_i: representa cada uno de los valores de la señal.**

## DESVIACIÓN ESTANDAR 

Es una medida de dispersión estadística que indica cuánto se alejan los valores de un conjunto de datos respecto a su media. En otras palabras, refleja el grado de variabilidad o dispersión de los datos: 

  ![](https://github.com/Nupan07/procesamiento/blob/main/Desviaci%C3%B3n.png)

Cuanto mayor sea la desviación estándar de un conjunto de datos, significa que más lejos están los datos de la media. Y la interpretación también se puede hacer al revés, si la desviación estándar es baja quiere decir que en general los datos están muy cerca de su media.

La **desviación estándar** (σ) se calcula con la siguiente fórmula:

Donde:
- \( σ ) es la desviación estándar.
- \( N ) es el número total de observaciones.
- \( x_i ) representa cada valor del conjunto de datos.
- \( mu ) es la media de los datos.

## COEFICIENTE DE VARIACIÓN 

El coeficiente de variación es una medida estadística que sirve para determinar la dispersión de un conjunto de datos respecto a su media. El coeficiente de variación se calcula dividiendo la desviación típica de los datos entre su promedio.

El coeficiente de variación se expresa en forma de porcentaje y suelen utilizarse las siglas CV como símbolo de esta métrica estadística.

![](https://github.com/Nupan07/procesamiento/blob/main/Coeficiente.png)

El **coeficiente de variación** (CV) se calcula con la siguiente fórmula:

Donde:

- \( \sigma \): desviación estándar.
- \( \mu \): media de los datos

## INICIO LABORATORIO
