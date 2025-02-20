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

## MEDIANA 

La mediana es el valor del medio de todos los datos ordenados de menor a mayor. Es decir, la mediana divide todo el conjunto de datos ordenados en dos partes iguales.

## TRANSFORMA DE FOURIER

![](https://github.com/Nupan07/Laboratorio2/blob/main/Transformada%20fourier.png)


Esto se hace sumando los productos de los valores de la señal por senos y cosenos de distintas frecuencias.

- **Densidad espectral de potencia:**

Se obtiene elevando al cuadrado la magnitud de la transformada de Fourier y normalizando.

## CONVOLUCIÓN 

La convolución entre dos señales discretas se hace con la fórmula:

![](https://github.com/Nupan07/Laboratorio2/blob/main/Convolucion.png)


Para cada punto de la nueva señal 𝑦[𝑛], desplazamos la secuencia ℎ[𝑘] sobre 𝑥[𝑛] y realizamos productos y sumas. Esto se puede hacer en una tabla escribiendo los valores de ℎ[𝑘]
en diferentes desplazamientos sobre 𝑥[𝑛], multiplicando y sumando los resultados.

## CORRELACIÓN 

La correlación cruzada mide la similitud entre dos señales desplazadas en el tiempo. Se calcula con:

![](https://github.com/Nupan07/Laboratorio2/blob/main/Correlaci%C3%B3n.png)

Para calcularla manualmente:

1. Se toma una de las señales y se va desplazando sobre la otra.
2. Se multiplican los valores correspondientes.
3. Se suman los productos para cada desplazamiento.
4. Se obtiene una tabla de valores y se grafica.








 

## INICIO LABORATORIO
