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

 **convolucion de Nupan**
![](https://github.com/Nupan07/Laboratorio2/blob/main/ConvolucionNupan.jpg)


Se hizo una convolucion discreta de dos secuencias x[n] y h[n] se define como una suma:    
                
               y[n]=∑ x[K]*h[n-k]
                
- x[k] es la señal de entrada.
- h[k] es la respuesta del sistema.
- y[n] es la señal de salida resultante.

 Se dieron dos secuencias numericas: 
 
**Señal de entrada (cedula)**

x[n] = {1, 1, 9, 3, 5, 6, 3, 2, 6, 1}

Respuesta del sistema(codigo de estudiante) 

h[n] = {5, 6, 0, 0, 5, 5, 7}

Para calcular la convolución, usamos la fórmula de la convolución discreta, sumando los productos de los valores correspondientes mientras desplazamos una de las secuencias.

donde:

- h[n]={5,6,0,0,5,5,7} (Código 5600557, longitud M=7)
- x[n]={1,1,9,3,5,6,3,2,6,1} (Cédula 1193563261, longitud N=10)
- La salida  y[n] tendrá una longitud de L=N+M−1=10+7−1=16.

Ahora calculamos los valores de y[n] manualmente:

- **Para y[0]**:

y[0]=h[0]x[0]=5(1)=5

- **Para y[1]**:

y[1]=h[0]x[1]+h[1]x[0]=5(1)+6(1)=5+6=11

- **Para y[2]**:

y[2]=h[0]x[2]+h[1]x[1]+h[2]x[0]=5(9)+6(1)+0(1)=45+6+0=51

- **Para y[3]**:

y[3]=h[0]x[3]+h[1]x[2]+h[2]x[1]+h[3]x[0]=5(3)+6(9)+0(1)+0(1)=15+54+0+0=69

- **Para y[4]**:

y[4]=h[0]x[4]+h[1]x[3]+h[2]x[2]+h[3]x[1]+h[4]x[0]=5(5)+6(3)+0(9)+0(1)+5(1)=25+18+0+0+5=48

- **Para y[5]**:

y[5]=h[0]x[5]+h[1]x[4]+h[2]x[3]+h[3]x[2]+h[4]x[1]+h[5]x[0]=5(6)+6(5)+0(3)+0(9)+5(1)+5(1)=30+30+0+0+5+5=70

- **Para y[6]**:

y[6]=h[0]x[6]+h[1]x[5]+h[2]x[4]+h[3]x[3]+h[4]x[2]+h[5]x[1]+h[6]x[0]=5(3)+6(6)+0(5)+0(3)+5(9)+5(1)+7(1)=15+36+0+0+45+5+7=108
    
Continuamos de la misma manera para los siguientes valores hasta y[15]:

Por lo tanto, el resultado final de la convolución es:

**y[n]={5,11,51,69,48,70,108,95,145,117,86,67,61,49,47,7}**

Ya obteniendo la convulcion podemos porseguir con el codigo para poder hallar la representacionde grafica de la convolucion y[n] 

En este código se calcula la convolución discreta entre dos secuencias h[n] y x[n] usando la función np.convolve() de NumPy. 

-**Paso 1: Definir las secuencias h[n] y x[n]**

    h_new = np.array([5, 6, 0, 0, 5, 5, 7])  # Código 5600557
    x_new = np.array([1, 1, 9, 3, 5, 6, 3, 2, 6, 1])  # Cédula 1193563261
Aquí estamos creando dos arreglos NumPy (np.array), que contienen los valores de las secuencias 
h[n] y x[n].

-h[n] representa la respuesta del sistema (como un filtro).

-x[n] es la señal de entrada (datos de la cédula).

-**Paso 2: Calcular la convolución con np.convolve()**
          
          y_new = np.convolve(x_new, h_new)
np.convolve(x_new, h_new) multiplica y suma los valores de 
x[n] y h[n] de manera desplazada, siguiendo la fórmula matemática:

y[n]= ∑ x[k]⋅h[n−k]

Esto nos da la respuesta del sistema a la entrada dada.
Ya con el codigo de la convolucion y el resultado dado el siguiente paso es contruir la grafica.

import matplotlib.pyplot as plt

                       # Valores de nimport matplotlib.pyplot as plt
                      n_values = np.arange(len(y_new))

                       # Crear la gráfica de stem (señal discreta)
                       plt.figure(figsize=(10, 5))
                       plt.stem(n_values, y_new, use_line_collection=True)
                       plt.xlabel('n')
                       plt.ylabel('y[n]')
                       plt.title('Representación Gráfica de la Convolución y[n]')
                       plt.grid()
                       plt.show()
                       
Este código genera una representación gráfica de la señal resultante de la convolución 
y[n] utilizando la función stem(), que es ideal para señales discretas. Primero, importamos matplotlib.pyplot para poder graficar. Luego, creamos un arreglo n_values con valores desde 0 hasta el tamaño de 
y[n], lo que nos da los índices en el eje horizontal. Después, usamos plt.figure(figsize=(10, 5)) para definir el tamaño de la figura y plt.stem(n_values, y_new, use_line_collection=True) para graficar 
y[n], donde use_line_collection=True mejora la visualización de las líneas verticales. Añadimos etiquetas con plt.xlabel('n') y plt.ylabel('y[n]') para indicar qué representan los ejes.

![](https://github.com/Nupan07/Laboratorio2/blob/main/ConvolucionNu.png)


La gráfica nos muestra cómo la señal cambia al pasar por el sistema, destacando qué partes tienen mayor respuesta y dónde la señal pierde fuerza.

**convolucion de olfred**

![](https://github.com/Nupan07/Laboratorio2/blob/main/ConvolucionOlfred.jpg)

Se hizo una convolucion discreta de dos secuencias x[n] y h[n] se define como una suma:    
                
                y[n]=∑ x[K]*h[n-k]
                
- x[k] es la señal de entrada.
- h[k] es la respuesta del sistema.
- y[n] es la señal de salida resultante.

 Se dieron dos secuencias numericas: 
 
**Señal de entrada (#cedula)**

x[n] = {1, 0, 3, 1, 6, 4, 4, 1, 2, 4}

Respuesta del sistema(codigo de estudiante) 

h[n] = {5, 6, 0, 0, 6, 3, 5}

Para calcular la convolución, usamos la fórmula de la convolución discreta, sumando los productos de los valores correspondientes mientras desplazamos una de las secuencias.

Donde:

- h[n]={5,6,0,0,6,3,5} (Código 5600635, longitud M=7)
- x[n]={1,0,3,1,6,4,4,1,2,4} (Cédula 1031644124, longitud N=10)
- La salida  y[n] tendrá una longitud de L=N+M−1=10+7−1=16.

Ahora calculamos los valores de y[n] manualmente:

- **Para y[0]:**

y[0]=h[0]x[0]=5(1)=5

- **Para y[1]:**

y[1]=h[0]x[1]+h[1]x[0]=5(0)+6(1)=6

- **Para y[2]:**

y[2]=h[0]x[2]+h[1]x[1]+h[2]x[0]=5(3)+6(0)+0(1)=15

- **Para y[3]:**

y[3]=h[0]x[3]+h[1]x[2]+h[2]x[1]+h[3]x[0]=5(1)+6(3)+0(0)+0(1)=5+18=23

Siguiendo esta metodología, podemos calcular todos los valores hasta y[15].
Por lo tanto, el resultado final de la convolución es:

**y[n]={5,6,15,23,42,59,67,44,70,79,90,38,35,35,22,20}**

Ya obteniendo la convulcion podemos porseguir con el codigo para poder hallar la representacionde grafica de la convolucion y[n] 

En este código se calcula la convolución discreta entre dos secuencias h[n] y x[n] usando la función np.convolve() de NumPy. 

-**Paso 1: Definir las secuencias h[n] y x[n]**

    h_new = np.array([5, 6, 0, 0, 6, 3, 5])  # Código 5600557
    x_new = np.array([1, 0, 3, 1, 6, 4, 4, 1, 2, 4])  # Cédula 1193563261
Aquí estamos creando dos arreglos NumPy (np.array), que contienen los valores de las secuencias 
h[n] y x[n].

-h[n] representa la respuesta del sistema (como un filtro).

-x[n] es la señal de entrada (datos de la cédula).

-**Paso 2: Calcular la convolución con np.convolve()**
          
          y_new = np.convolve(x_new, h_new)
np.convolve(x_new, h_new) multiplica y suma los valores de 
x[n] y h[n] de manera desplazada, siguiendo la fórmula matemática:

y[n]= ∑ x[k]⋅h[n−k]

Esto nos da la respuesta del sistema a la entrada dada.
Ya con el codigo de la convolucion y el resultado dado el siguiente paso es contruir la grafica.

import matplotlib.pyplot as plt

                       # Valores de nimport matplotlib.pyplot as plt
                      n_values = np.arange(len(y_new))

                       # Crear la gráfica de stem (señal discreta)
                       plt.figure(figsize=(10, 5))
                       plt.stem(n_values, y_new, use_line_collection=True)
                       plt.xlabel('n')
                       plt.ylabel('y[n]')
                       plt.title('Representación Gráfica de la Convolución y[n]')
                       plt.grid()
                       plt.show()
                       
Este código genera una representación gráfica de la señal resultante de la convolución 
y[n] utilizando la función stem(), que es ideal para señales discretas. Primero, importamos matplotlib.pyplot para poder graficar. Luego, creamos un arreglo n_values con valores desde 0 hasta el tamaño de 
y[n], lo que nos da los índices en el eje horizontal. Después, usamos plt.figure(figsize=(10, 5)) para definir el tamaño de la figura y plt.stem(n_values, y_new, use_line_collection=True) para graficar 
y[n], donde use_line_collection=True mejora la visualización de las líneas verticales. Añadimos etiquetas con plt.xlabel('n') y plt.ylabel('y[n]') para indicar qué representan los ejes.

![](https://github.com/Nupan07/Laboratorio2/blob/main/ConvolucionOl.png)

La gráfica nos muestra cómo la señal cambia al pasar por el sistema, destacando qué partes tienen mayor respuesta y dónde la señal pierde fuerza.

**Correlación Cruzada entre señales sinusoidales**

Ahora analizamos la correlación entre dos señales:

x1[n]=cos [n]=cos(2π100nT)
x2[n]=sin [n]=sin(2π100nT)

**codigo:**

             fs = 1 / (1.25e-3)  # Frecuencia de muestreo (1/Ts)
             Ts = 1 / fs
             n = np.arange(0, 9)
             f = 100  # Frecuencia de la señal en Hz

             x1 = np.cos(2 * np.pi * f * n * Ts)
             x2 = np.sin(2 * np.pi * f * n * Ts)

             correlation = np.correlate(x1, x2, mode='full')
             lags = np.arange(-len(n) + 1, len(n))

             plt.figure(figsize=(12, 5))
             plt.stem(lags, correlation, use_line_collection=True)
             plt.xlabel('Desplazamiento (lags)')
             plt.ylabel('Correlación')
             plt.title('Correlación entre x1[n] y x2[n]')
             plt.grid()
             plt.show()
             
1️⃣ Definir parámetros:

fs = 1 / (1.25e-3): Calcula la frecuencia de muestreo a partir del período de muestreo  =1.25 ms.
Ts = 1 / fs: Obtiene el valor de 
n = np.arange(0, 9): Genera un vector de índices 
n desde 0 hasta 8 (9 muestras en total).
f = 100: Define la frecuencia de las señales en 100 Hz.

2️⃣ Generar señales:

x1 = np.cos(2 * np.pi * f * n * Ts): Genera una onda coseno de 100 Hz.
x2 = np.sin(2 * np.pi * f * n * Ts): Genera una onda seno de 100 Hz.

3️⃣ Calcular la correlación cruzada:

np.correlate(x1, x2, mode='full'): Calcula la similitud entre x1 y x2 a medida que una se desplaza sobre la otra.
lags = np.arange(-len(n) + 1, len(n)): Define los desplazamientos posibles para la correlación.

![](![image](https://github.com/user-attachments/assets/0c4be0a7-6e39-4839-896e-ff6c56cd9d5e)

La correlación cruzada indica cómo varía la similitud entre x1 y x2 en función del desplazamiento. Dado que coseno y seno están desfasados 90° (π/2 radianes), la correlación será máxima en un desplazamiento específico y disminuirá en otros puntos. La gráfica muestra esta variación y ayuda a identificar el punto donde ambas señales están más alineadas.
