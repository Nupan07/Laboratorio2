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

## ¿Que estamos resolviendo ?
Se realizo dos calculos principales siendo el primero la convolucion de dos secuencias numericas siendo una el codigo de estudiante y la otra en numero de cedula.

Lo segundo que se realizo fue la correlacion cruzada entre dos señales sinusidales para despues porder graficarlas y poder observar un dezplasiamiento y demostrar su desfases.

## Explicacion De La Convolucion 
**convolucion de valnetina**
Se hizo una convolucion discreta de dos secuencias x[n] y h[n] se define como una suma:    
                
                y[n]=∑ x[K]*h[n-k]
                
-x[k] es la señal de entrada.
-h[k] es la respuesta del sistema.
-y[n] es la señal de salida resultante.

 Se dieron dos secuencias numericas: 
 
Señal de entrada (#cedula)

x[n] = {1, 1, 9, 3, 5, 6, 3, 2, 6, 1}

Respuesta del sistema(codigo de estudiante) 

h[n] = {5, 6, 0, 0, 5, 5, 7}

Para calcular la convolución, usamos la fórmula de la convolución discreta, sumando los productos de los valores correspondientes mientras desplazamos una de las secuencias.

donde:
h[n]={5,6,0,0,5,5,7} (Código 5600557, longitud M=7)
x[n]={1,1,9,3,5,6,3,2,6,1} (Cédula 1193563261, longitud N=10)
La salida  y[n] tendrá una longitud de L=N+M−1=10+7−1=16.

Ahora calculamos los valores de y[n] manualmente:

Para y[0]:

y[0]=h[0]x[0]=5(1)=5

Para y[1]:

y[1]=h[0]x[1]+h[1]x[0]=5(1)+6(1)=5+6=11

Para y[2]:

y[2]=h[0]x[2]+h[1]x[1]+h[2]x[0]=5(9)+6(1)+0(1)=45+6+0=51

Para y[3]:

y[3]=h[0]x[3]+h[1]x[2]+h[2]x[1]+h[3]x[0]=5(3)+6(9)+0(1)+0(1)=15+54+0+0=69

Para y[4]:

y[4]=h[0]x[4]+h[1]x[3]+h[2]x[2]+h[3]x[1]+h[4]x[0]=5(5)+6(3)+0(9)+0(1)+5(1)=25+18+0+0+5=48

Para y[5]:

y[5]=h[0]x[5]+h[1]x[4]+h[2]x[3]+h[3]x[2]+h[4]x[1]+h[5]x[0]=5(6)+6(5)+0(3)+0(9)+5(1)+5(1)=30+30+0+0+5+5=70

Para y[6]:

y[6]=h[0]x[6]+h[1]x[5]+h[2]x[4]+h[3]x[3]+h[4]x[2]+h[5]x[1]+h[6]x[0]=5(3)+6(6)+0(5)+0(3)+5(9)+5(1)+7(1)=15+36+0+0+45+5+7=108
    
Continuamos de la misma manera para los siguientes valores hasta y[15]:

Por lo tanto, el resultado final de la convolución es:

y[n]={5,11,51,69,48,70,108,95,145,117,86,67,61,49,47,7}


