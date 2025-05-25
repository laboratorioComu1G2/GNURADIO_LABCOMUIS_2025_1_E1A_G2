Laboratorio de Comunicaciones
## Universidad Industrial de Santander

# Práctica 5. Modulaciones Digitales Y De Pulsos

### Integrantes
- **Duban Andretti Gutierrez Leon** - 2220396
- **Juan José De la Rosa Medina** - 2202810

Escuela de Ingenierías Eléctrica, Electrónica y de Telecomunicaciones  
Universidad Industrial de Santander

### Fecha
21 de mayo de 2025

---

## Declaración de Originalidad y Responsabilidad
Los autores de este informe certifican que el contenido aquí presentado es original y ha sido elaborado de manera independiente. Se han utilizado fuentes externas únicamente como referencia y han sido debidamente citadas.

Asimismo, los autores asumen plena responsabilidad por la información contenida en este documento. 

Uso de IA: No se usó IA.
## Contenido

### Resumen
En esta práctica se analizó un modelo de canal para la transmisión de distintos tipos de señales, además de ver las afectaciones presentadas por la atenuación y el ruido, en un inicio se analizaron las señales mediante un flujograma, para posteriormente comparar los resultados obtenidos con el analizador de espectros, se estudiaron los efectos del ruido y la atenuación, todo esto bajo diferentes condiciones y para diferentes tipos de señales.

**Palabras clave:** Espectro en Frecuencia, GNU radio, Filtros, Ruido. 

### Introducción
En el mundo de las telecomunicaciones, cuando enviamos señales digitales por un canal, estas pueden verse afectadas por varias cosas, como el ruido, la atenuación y la dispersión. Estos factores pueden hacer que la señal llegue con errores o distorcionada, lo que afecta su calidad y la transmisión de la información.  

El objetivo de esta práctica es crear un modelo de canal que nos ayude a estudiar cómo se comporta la señal en distintas condiciones de transmisión. A través de simulaciones y analisis de los resultados, queremos entender mejor cómo estos factores afectan la señal y ver qué soluciones podrían mejorar su calidad. Este tipo de estudios es clave para diseñar sistemas de comunicación más eficientes y resistentes a las interferencias.

### Procedimiento
### Actividad 1
### Objetivo

### Figura 1. Señal Senoidal: 
En un inicio se tiene una señal senoidal con un ancho de pulso de 20 y una frecuencia de pulso de 1kHz.
En la figura 1 se puede observar una modulación de una señal senoidal mediante un tren de pulsos.  
Se buscó establecer un valor de `samprate`, por lo que sabiendo el valor de  
**F<sub>pulsos</sub> = 1000 Hz**, se estableció un `samprate = 100 kHz`.

Luego se estableció un ancho de pulso de **20 µs**, esto con el fin de permitirle al pulso funcionar durante este tiempo y establecer un ciclo útil bajo, para ver cómo se afectaba en el espectro de la frecuencia.  
En este se puede observar cómo la señal senoidal presenta dos impulsos centrados alrededor de la frecuencia del mensaje, concentrando toda la potencia en ese punto.

<div align="center">
  <img src="https://github.com/user-attachments/assets/364f9606-1386-4d8f-ade6-475a715357af" title="señal original" alt="Texto alternativo" width="600" height="400"/>
</div>

### Figura 2. Señal Cuadrada:
Para esta señal se usaron los mismos parámetros usados previamente para el análisis de la figura 1.  
El único cambio que se realizó fue su frecuencia del mensaje, la cual bajó de **240 Hz** a **100 Hz**.  
En el espectro se presenta una mayor dispersión y más armónicos, debido a la naturaleza discontinua de la señal cuadrada.  
Esto se refleja en un mayor ancho de banda comparado con la senoidal.

<div align="center">
  <img src="https://github.com/user-attachments/assets/d9186830-25a3-4003-a164-123daa17918b" title="Señal Modificada En Amplitud" alt="Texto alternativo" width="600" height="400"/>
</div>

### Figura 3. Señal Triangular
Para esta señal se usaron los parámetros del análisis de la figura 2.  
En el espectro de la señal podemos observar que la señal triangular genera un espectro más suave en comparación con la señal cuadrada.  
Además, se observan componentes en baja frecuencia con armónicos que decrecen de manera muy rápida.

<div align="center">
  <img src="https://github.com/user-attachments/assets/d34d1675-2122-4e42-8baa-b54283ce5125" title="Señal Modificada En Frecuencia" alt="Texto alternativo" width="600" height="400"/>
</div>

### Cálculo del Ciclo Útil
| Tipo de Señal | Frec. Mensaje (Hz) | Frec. Pulsos (Hz) | Ancho Pulso (μs) | Ciclo Útil (%) |
|---------------|--------------------|--------------------|-------------------|-----------------|
| Senoidal      | 240                | 1000               | 20                | 2               |
| Cuadrada      | 100                | 1000               | 20                | 2               |
| Triangular    | 100                | 1000               | 20                | 2               |

### Actividad 2:
En esta actividad se buscaba multiplexar 4 señales distintas y luego realizar la recuperación de cada una de estas, además se busca analizar qué sucede al agregar otra señal a la multiplexación.

Al momento de realizar una multiplexación se deben tener en cuenta los siguientes aspectos, primero el ancho del pulso, ya que éste depende del número de canales que esté usando, para el caso de 4, necesito un ancho del pulso de 25, pero para el caso de los 5 canales se necesita un ancho del pulso de 20, esto me permite evitar posibles interferencias entre canales; como segundo aspecto se tienen que tener en cuenta sus retardos los cuales están equiespaciados para evitar que un canal se sobreponga con otro, la distancia a la que están separados es del mismo valor que el ancho del pulso, ya por último se tiene en cuenta la señal de selección la cual tomará valores n*ancho del pulso para ir recuperando cada uno de los canales.

## Figura 4: Multiplexación Con 4 Canales:
<div align="center">
  <img src="https://github.com/user-attachments/assets/3d1c8633-827c-465e-9236-00c974f8dbf1" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 5: Recuperación de la señal coseno con Rx = 0
<div align="center">
  <img src="https://github.com/user-attachments/assets/95946569-8650-461a-a876-5935acc4e318" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 6: Recuperación de la señal dientes de sierra con Rx = 25
<div align="center">
  <img src="https://github.com/user-attachments/assets/7a5efb95-c974-4695-86e7-a56a1579172d" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 7: Recuperación de la señal triangular con Rx = 50
<div align="center">
  <img src="https://github.com/user-attachments/assets/fb4628b4-5da1-4a9c-b849-e5d296667a51" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 8: Recuperación de la señal cuadrada con Rx = 75
<div align="center">
  <img src="https://github.com/user-attachments/assets/b2dbcc1c-4280-4727-9685-b369408892ce" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 9: Multiplexación con 5 canales
<div align="center">
  <img src="https://github.com/user-attachments/assets/cda40712-b67c-4775-9feb-c3f0426e47e5" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Actividad 3
En esta actividad se busca analizar mediante el osciloscopio y el analizador de espectros la multiplexación de canales y las condiciones para recuperar los mismos.

El osciloscopio nos permite ver cada una de las formas de onda recuperadas mediante el parámetro Rx, no se tiene en cuenta el valor de D4 ya que solo se necesitan n-1 retardos para lograr la recuperación de todos lo canales; al revisar el analizador de espectros se puede evidenciar como los valores para frecuencias altas han sido atenuados, esto se debe a la presencia del filtro pasabajas el cual me genera este comportamiento.

## Figura 10: Canal coseno recuperado en el osciloscopio
<div align="center">
  <img src="https://github.com/user-attachments/assets/10c52a31-e961-42d2-977a-359818d88c3e" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 11: Canal coseno recuperado en el flujograma
<div align="center">
  <img src="https://github.com/user-attachments/assets/c6a26570-5530-4351-92d8-69a0eaca6bf2" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 12: Canal dientes de sierra recuperado en el osciloscopio
<div align="center">
  <img src="https://github.com/user-attachments/assets/0c227efe-9a49-4b3e-a2e5-54f28b0445c6" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 13: Canal dientes de sierra recuperado en el flujograma
<div align="center">
  <img src="https://github.com/user-attachments/assets/d5e17ae5-9336-4a7a-ae57-f3ce99d1642a" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 14: Canal triangular recuperado en el osciloscopio
<div align="center">
  <img src="https://github.com/user-attachments/assets/d0224eeb-1afe-4f8a-aca1-dabf59723103" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 15: Canal triangular recuperado en el flujograma
<div align="center">
  <img src="https://github.com/user-attachments/assets/a88ff334-9da0-4a6c-b43d-ad00b782ff2c" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 16: Canal cuadrado recuperado en el osciloscopio
<div align="center">
  <img src="https://github.com/user-attachments/assets/8193a12b-2868-4043-bf03-10e2d957efc4" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 17: Canal cuadrado recuperado en el flujograma
<div align="center">
  <img src="https://github.com/user-attachments/assets/dc001894-d959-4d79-a040-1928a92cbe83" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 18: Espectro en frecuencia para el canal coseno en el analizador de espectros
<div align="center">
  <img src="https://github.com/user-attachments/assets/08068a18-b9f2-440f-8c40-0fb63c760606" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 19: Espectro en frecuencia para el canal coseno en el flujograma
<div align="center">
  <img src="https://github.com/user-attachments/assets/fda5f5b2-7b36-4725-aa2e-b620c8bc5948" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 20: Espectro en frecuencia para el canal dientes de sierra en el analizador de espectros
<div align="center">
  <img src="https://github.com/user-attachments/assets/0a85477a-42f6-4fbb-81e3-b3dd9ee4e2fb" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 21: Espectro en frecuencia para el canal dientes de sierra en el flujograma
<div align="center">
  <img src="https://github.com/user-attachments/assets/334bf985-5baa-4994-a568-0040e26c57d2" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>


## Figura 22: Espectro en frecuencia para el canal triangular en el analizador de espectros
<div align="center">
  <img src="https://github.com/user-attachments/assets/2b59ee84-5eb3-4a85-b9ca-7dae229e2486" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 23: Espectro en frecuencia para el canal triangular en el flujograma
<div align="center">
  <img src="https://github.com/user-attachments/assets/9014acc0-79fe-44af-926c-6965aa14fd3b" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 24: Espectro en frecuencia para el canal cuadrado en el analizador de espectros
<div align="center">
  <img src="https://github.com/user-attachments/assets/0ed06eeb-fdfd-49fc-9f17-a441ae079ea8" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

## Figura 25: Espectro en frecuencia para el canal cuadrado en el flujograma
<div align="center">
  <img src="https://github.com/user-attachments/assets/bc603365-c97a-4f80-8372-c2d0334aba71" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

### Referencias

- https://ieeexplore.ieee.org
