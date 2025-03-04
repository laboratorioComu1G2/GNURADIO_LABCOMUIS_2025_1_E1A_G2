# Laboratorio de Comunicaciones
## Universidad Industrial de Santander

# Práctica 1C. Mediciones de potencia y frecuencia

### Integrantes
- **Duban Andretti Gutierrez Leon** - 2220396
- **Juan José De la Rosa Medina** - 2202810

Escuela de Ingenierías Eléctrica, Electrónica y de Telecomunicaciones  
Universidad Industrial de Santander

### Fecha
5 de marzo de 2025

---

## Declaración de Originalidad y Responsabilidad
Los autores de este informe certifican que el contenido aquí presentado es original y ha sido elaborado de manera independiente. Se han utilizado fuentes externas únicamente como referencia y han sido debidamente citadas.

Asimismo, los autores asumen plena responsabilidad por la información contenida en este documento. 

Uso de IA:

---
## Contenido

### Resumen
Descripción en no más de 150 palabras del contenido de la práctica. Debe ser conciso y brindar una idea clara sobre el trabajo realizado y sus conclusiones.

**Palabras clave:** Analizador de espectros, mediciones, GNU radio, Mediciones. 

### Introducción
En los sistemas de comunicación de la actualidad se hace necesario un correcto análisis de las señales para garantizar que la información se transmita de manera adecuada, por lo cual es imprescindible comprender cómo afecta a la señal sus distintos parámetros tales como: las formas de onda, las fuentes de la señal y el entorno en el cual se está transmitiendo, además de considerar sus efectos en el tiempo y la frecuencia. A lo largo de este informe se tiene como objetivo analizar el comportamiento de una señal al implementarle ciertos cambios, entre estos la amplitud, la frecuencia, el ruido, la fase y su offset; todos estos cambios se podrán medir utilizando el USRP 2920 y equipos complementarios como el analizador de espectros y el osciloscopio.

### Procedimiento
### Actividad 1: Revisión de Especificaciones de los Equipos
   ## 1. Seleccionar Especificaciones Relevantes:
    USRP 2920: Las especificaciones seleccionadas se muestran a continuación
            1. Rango de frecuencia de 50 Mhz a 2.2 Ghz.
            2. Precisión de frecuencia 2.5 ppm.
            3. Pasos de ganancia 1.0 db.
            4. Rango de ganancias de 0 db a 31 db.
            5. Pasos de frecuencia menores a 1 kHz.
            
    Osciloscopio R&S RTB2004: Las especificaciones seleccionadas se muestran a continuación
            1. Cantidad de canales: 4 canales analógicos.
            2. Frecuencia de muestreo: Hasta 2.5 GSa/s.
            3. Pantalla: Táctil capacitiva de 10.1 pulgadas, resolución 1280 x 800 píxeles.
            4. Interfaces: USB, LAN, salida de disparo.
            5. Ancho de banda: 70 MHz, 100 MHz, 200 MHz, hasta 300 MHz.

    Analizador de Espectros R&S FPC1000: Las especificaciones seleccionadas se muestran a continuación
            1. Rango de frecuencia: 5 kHz a 1 GHz.
            2. Rango de atenuación 0 db a 40 db.
            3. La entrada RF con una impedancia de 50 Ω le permite conectar un DUT al R&S FPC1000.
            4. Precisión de frecuencia: 0.5 ppm.
            5. Nivel de ruido de fondo (DANL): -150 dBm.
En esta fase de la práctica se analizó el comportamiento de los dispositivos y las diferentes configuraciones que poseian, se logró determinar que para el USRP 2920 su rango de frecuencias va desde 50 Mhz hasta 2.2 Ghz mientras que para el analizador de espectros va desde 5 kHz a 1 GHz, por lo que podemos decir que el analizador de espectros nos permite trabajar con frecuencias mucho menores a las que el USRP 2920 nos permite hacerlo, por otro lado se analizó como medir la amplitud y frecuencia en el osciloscopio, esto se logra mediante los siguientes pasos, primero se ingresa la señal que se quiere analizar, luego se ajusta la división de la señal para que ésta se muestre según lo que se quiera analizar, evitando así visualizar posibles saturaciones, luego se establece en el osciloscopio los valores que se quieren medir en este caso la amplitud y frecuencia para finalmente tomar los datos requeridos.
### Actividad 2: Simulación de Señales en GNU Radio
En esta fase se visualizaron los cambios ocurridos a una señal de entrada elegida por cada grupo al alterar varios de sus parametros de manera individual, a continuación se muestra cada uno de los cambios con respecto a la imagen original y se hace una breve explicacioón de cada fenomeno ocurrido.
### Señal Original: 
En un inicio se tiene una señal coseno con amplitud de 1V y una frecuencia de 1kHz dicha señal se representa con la sigueinte ecuación $cos((2\pi )1000t)$
<div align="center">
  <img src="https://github.com/user-attachments/assets/8a1ef106-7307-4d43-96f4-98cbdbd73400" title="señal original" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal Con Amplitud De 4V:
Al realizar el aumento en la amplitud se puede ver como la señal cosenoidal aumenta tanto en su parte real como en su componente imaginaria, además la ganancia de potencia en el espectro de la frecuencia aumenta de manera considerable.
<div align="center">
  <img src="https://github.com/user-attachments/assets/dd62690e-d5bc-4325-92d2-31e8384a0041" title="señal Modificada En Amplitud" alt="Texto alternativo" width="600" height="400"/>
</div>



#################################################################
### Actividad 3: Transmisión y Medición de Señales con el USRP 2920

En la primera parte de esta actividad, se indicó que reconociéramos el bloque de frecuencia de muestreo y observáramos el impacto de alterar o cambiar su valor, que en un principio se establecía en 32 kHz, pero luego fue disminuido a 10 kHz para observar las variaciones en su señal.
Se observó que, al reducir la frecuencia de muestreo, disminuyó el ancho de banda que se podía analizar, pasando de 16 kHz a 5 kHz. Esto nos restringía el efecto de las frecuencias que se podían percibir, pero al mismo tiempo mejoró la resolución de la frecuencia en este espectro.

<img src="" title="señal Modificada En Amplitud" alt="Texto alternativo" width="600" height="400"/>
</div>




### Referencias

Ejemplo de referencia:

- [Proakis, 2014] J. Proakis, M. Salehi. Fundamentals of communication systems. 2 ed. England: Pearson Education Limited, 2014. p. 164-165, 346. Chapter 5 In: [Biblioteca UIS](https://uis.primo.exlibrisgroup.com/permalink/57UIDS_INST/63p0of/cdi_askewsholts_vlebooks_9781292015699)

---
# Ejemplos usando Markdown

Volver al [INICIO](#laboratorio-de-comunicaciones)

## Inclusión de Imágenes
### Imagen de referencia dentro del repositorio:
![Networking](my%20file/test.png)

### Imagen de fuente externa
![GNU Radio logo](https://kb.ettus.com/images/thumb/5/50/gnuradio.png/600px-gnuradio.png)

### Uso de html para cambiar escala de la imagen
<img src="https://kb.ettus.com/images/thumb/5/50/gnuradio.png/600px-gnuradio.png" alt="GNU Radio Logo" width="300">

## Creación de hipevínculos 
- [Aprende Markdown](https://markdown.es/)
- [Más acerca de Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- [Abrir documento en el repositorio](my%20file/test_file.txt). Si hay espacios en la ruta de su archivo, reemplácelos por `%20`.
- Ir a una sección de este documento. Por ejemplo: [Ir a Contenido](#contenido) Tenga en cuenta escribir el título de la sección en minúsculas y los espacios reemplazarlos por guiones.
## Uso de Expresiones Matemáticas
Se pueden incluir ecuaciones en el archivo `README.md` utilizando sintaxis similar a [LaTeX](https://manualdelatex.com/tutoriales/ecuaciones):

### Ecuaciones en Línea
```
La energía de una señal exponencial es $E = \int_0^\infty A^2 e^{-2t/\tau} dt$.
```
**Salida renderizada:**
La energía de una señal exponencial es $E = \int_0^\infty A^2 e^{-2t/\tau} dt$.

### Ecuaciones en Bloque
```
$$E = \int_0^\infty A^2 e^{-2t/\tau} dt = \frac{A^2 \tau}{2}$$
```
**Salida renderizada**
$$E = \int_0^\infty A^2 e^{-2t/\tau} dt = \frac{A^2 \tau}{2}$$

## Creación de Tablas

**Tabla 1.** Ejemplo de tabla en Markdown.

| Parámetro | Valor |
|-----------|-------|
| Frecuencia (Hz) | 1000 |
| Amplitud (V) | 5 |
| Ciclo útil (%) | 50 |

## Inclusión de código

```python
def hello_world():
    print("Hello, World!")
```

También es posible resaltar texto tipo código como `print("Hello, World!")`.

---

Volver al [INICIO](#laboratorio-de-comunicaciones)
