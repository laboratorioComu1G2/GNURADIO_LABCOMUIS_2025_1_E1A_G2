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
En los sistemas de comunicaciones modernas, la caracterización y análisis de señales es fundamental para garantizar un desempeño adecuado y eficiente en la transmisión de información. Para ello, es indispensable comprender cómo influyen los parámetros de las fuentes de señal, las formas de onda y el entorno de transmisión tanto en el dominio del tiempo como en el de la frecuencia. Este informe tiene como objetivo analizar experimentalmente diversos aspectos relacionados con la generación, transmisión y medición de señales utilizando el USRP 2920 y equipos complementarios como el analizador de espectros y el osciloscopio. A través de una serie de preguntas clave, se exploran conceptos como la potencia, el ancho de banda, la relación señal a ruido (SNR), la respuesta en frecuencia y las pérdidas en canales inalámbricos. Además, se evalúan las limitaciones de los instrumentos empleados y se identifican aplicaciones prácticas dentro de los sistemas de comunicaciones reales, resaltando la importancia de una correcta configuración y análisis para optimizar la calidad de la señal y la robustez del enlace.

En los sistemas de comunicación de la actualidad se hace necesario un correcto análisis de las señales para garantizar que la información se transmita de manera adecuada, por lo cual es impresindible comprender cómo afecta a la señal sus distintos parámetros tales como: las formas de onda, las fuentes de la señal y el entorno en el cual se está transmitiendo, además de considerar sus efectos en el tiempo y la frecuencia. A lo largo de este informe  

### Procedimiento
Debe basarse en las acciones efectivamente realizadas durante el laboratorio, describiendo los procesos realizados y los resultados obtenidos. Para cada práctica se pueden brindar preguntas orientadoras o pasos a seguir para establecer lo que se espera lograr/estudiar/analizar/obtener/comparar. Por ejemplo:
- Describa los procesos realizados en el laboratorio  y los resultados obtenidos.
- ¿Cómo se alcanza el límite de Nyquist y que pasa cuando se disminuye de este?
- ¿Por qué al interpolar una señal en GNURADIO su frecuencia disminuye?
- ¿Por qué al diezmar una señal en GNURADIO su frecuencia aumenta?
- ¿Cómo se puede determinar la frecuencia máxima de una señal desde lo experimental?
- ¿Qué le sucede a una señal de audio cuando no se respeta el teorema de Nyquist?
- Describa las funciones logradas con el Ecualizador desarrollado con GNURadio.

### Conclusiones
Se sintetizan los principales aportes y puntos relevantes de la práctica, evitando repetir lo ya consignado en las otras secciones del informe. 

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
