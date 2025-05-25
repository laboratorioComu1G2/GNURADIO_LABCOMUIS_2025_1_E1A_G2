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

### Señal Triangular Original En El Dominio De La Frecuencia: 
En esta parte se presenta el espectro de la frecuencia para la señal triangular original, tanto en su entrada como en su salida despues del filtro.
<div align="center">
  <img src="https://github.com/user-attachments/assets/a6d52809-4fd4-435b-934b-a3db4ef9d360" title="señal original" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal Con Adición De Voltaje De Ruido Para El Dominio De La Frecuencia
Luego de añardirle un ruido de valor 0.1V se apreció como para la señal de entrada el piso de ruido aumenta su valor hasta -60 db mientras que su salida se filtra el ruido y solo observan los valores cercanos a su potencia maxima, debido a que el filtro elimina todas las demás componentes.

<div align="center">
  <img src="https://github.com/user-attachments/assets/1bf1869c-884e-4d78-bd68-35c0b5d9f31b" title="https://github.com/user-attachments/assets/a4914c27-8a38-4697-9267-621b9b16b2ef" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal Coseno Original: 
En un inicio se tiene una señal triangular con amplitud de 0.5V y una frecuencia de 1kHz dicha señal se representa con la sigueinte ecuación $cos((2\pi )1000t)$
<div align="center">
  <img src="https://github.com/user-attachments/assets/47b2ccf2-907a-4043-9cbc-03d5076b7528" title="señal original" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal Con Adición De Voltaje De Ruido Para El Dominio Del Tiempo
Se le añadió un voltaje de ruido a la señal para ver su variación tanto en la entrada como en su salida luego de pasar através de un filtro, se pudo observar como para esta señal coseno se mantiene la misma tendencia de la señal triangular vista con anterioridad en la entrada la señal presenta una distorción muy fuerte apesar de solo tener 0.1 V de ruido, esto se debe a que el valor de su ancho de banda es muy grande por lo que la señal captura mucho más ruido del que se podría esperar en un primer momento, al analizar la señal luego de pasar por el filtro se puede ver como ésta presenta una ligera atenuación, pero en su forma no presenta grandes camabios, esto se debe a que el filtro nos permite visualizar unicamente las componentes de la señal que queremos evitando que se muestre en la salida todo ese ruido no deseado.

<div align="center">
  <img src="https://github.com/user-attachments/assets/0a876bde-a271-4188-958c-6bb109865278" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal Coseno Original En El Dominio De La Frecuencia: 
En esta parte se presenta el espectro de la frecuencia para la señal coseno original, tanto en su entrada como en su salida despues del filtro.
<div align="center">
  <img src="https://github.com/user-attachments/assets/1f8c6187-4dc3-410d-981f-d55dd8f92ddc" title="señal original" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal Con Adición De Voltaje De Ruido Para El Dominio De La Frecuencia
Luego de añardirle un ruido de valor 0.1V se apreció como para la señal de entrada el piso de ruido aumenta su valor hasta -60 db mientras que su salida se filtra el ruido y solo observan los valores cercanos a su potencia maxima, debido a que el filtro elimina todas las demás componentes.

<div align="center">
  <img src="https://github.com/user-attachments/assets/8bd18265-1be1-4a70-952a-d51d475dcecf" title="https://github.com/user-attachments/assets/a4914c27-8a38-4697-9267-621b9b16b2ef" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal De Audio
En esta parte se utilizó una señal de audio proporcionada por el docente la cual fue analizada en el espectro de la frecuencia.

<div align="center">
  <img src="https://github.com/user-attachments/assets/5b1d6133-2234-4da9-a9b9-14266e3c8ccf" title="https://github.com/user-attachments/assets/a4914c27-8a38-4697-9267-621b9b16b2ef" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal De Audio En El Espectro De La Frecuencia
Señal de audio original medida en el espectro de la frecuencia

<div align="center">
  <img src="https://github.com/user-attachments/assets/db1caefc-a647-4808-b892-19534e7dcbf8" title="https://github.com/user-attachments/assets/a4914c27-8a38-4697-9267-621b9b16b2ef" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal De Audio Con Ruido
Se le añadió un pequeño voltaje de ruido de 0.01 V, a su vez se aumento el ancho de banda a su valor maximo permitido, con estos cambios se pudo observar como la señal de audio presenta distorciones tanto en la señal de entrada como en la señal de salida incluso despues de haberle aplicado un filtro, esto se debe a que como el ancho de banda es tan grande el filtro no puede funcionar de manera correcta y permite el paso de mucha más interferencia de la esperada.

<div align="center">
  <img src="https://github.com/user-attachments/assets/13c98c11-519c-4204-9443-8ebe0b064716" title="https://github.com/user-attachments/assets/a4914c27-8a38-4697-9267-621b9b16b2ef" alt="Texto alternativo" width="600" height="400"/>
</div>

### Umbral Maximo
Se buscó el valor maximo en el espectro de la frecuencia para el cual el audio se podía llegar a entender, esto se hizo de manera iterativa con el uso de unos audiculares y distinguiendo a en que umbral se podía seguir escuchando el audio con interferencia y que a su vez el mensaje se siquiera entendiendo.

<div align="center">
  <img src="https://github.com/user-attachments/assets/16f61359-8229-4e44-bf8f-5ed1225fde9d" title="https://github.com/user-attachments/assets/a4914c27-8a38-4697-9267-621b9b16b2ef" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal De Audio Con Aumento En El Ruido
En este punto se aumento el valor del voltaje de ruido, pero reduciendo el valor de su ancho de banda, se pudo observar como la señal de salida luego de pasar por el filtro presenta menos interferencia debido a que hay menos rangos de frecuencias en los cuales la señal puede tomar componentes.

<div align="center">
  <img src="https://github.com/user-attachments/assets/eb615278-c872-469e-8b43-e4e149d651ac" title="https://github.com/user-attachments/assets/a4914c27-8a38-4697-9267-621b9b16b2ef" alt="Texto alternativo" width="600" height="400"/>
</div>

### Limite De La Señal De Audio En Donde Se Puede Entender
Se buscaron los valores de ancho de banda y ruido para los cuales la señal de audio se podía entender de manera adecuada teniendo interferencias, estos valores fueron de 0.03 V de ruido y un ancho de banda de 4.5 kHz.

<div align="center">
  <img src="https://github.com/user-attachments/assets/6ce8a91d-9784-48f9-8502-e262f018f122" title="https://github.com/user-attachments/assets/a4914c27-8a38-4697-9267-621b9b16b2ef" alt="Texto alternativo" width="600" height="400"/>
</div>

### ¿Cuál es el efecto de filtrar las frecuencias altas de una señal?
Eliminar las frecuencias altas reduce la cantidad de componentes de alta frecuencia en la señal, lo que suaviza la forma de onda y puede causar una pérdida de información, así como se observo para el caso de la señal triangular la cual a altas frecuencias presentaba una forma de onda senoidal.

### ¿Qué ocurre al eliminar armónicos de una señal?
La eliminación de armonicos puede llegar a afectar la señal si se eliminan los armonicos más grandes, ya que dichos armonicos son lo que poseen mayor cantudad de información de la señal original, pero dado el caso en que solo se eliminen componentes pequeñas no habría gran influencia, ya que la mayoría de armonicos pequeños tienden a representar ruido.

### ¿Cómo se puede mejorar la relación señal a ruido en una señal?
Una de las formas de mejorar la relación señal a ruido es el uso de filtros adecuados para eliminar el ruido fuera del ancho de banda útil, esto quiere decir que solo se reducirá su ancho de banda para evitar el paso de señales de ruido indeseadas mientras que se mantiene la cantidad de información necesaria para transmitir el mensaje.

### Actividad 2: Fenómenos de canal en el analizador de espectros
1. **Configurar el USRP 2920:**
En un inicio se configuró el flujograma dado por el docente para establecer un valor de frecuencia de muestreo adecuado para la práctica, dado que se requería ussar al siguiente fórmula: $\frac{25e^{6}}{2^{n}}$ donde n debe ser un número mayor a 2 y para nuestro caso se estableció que éste fuese de 6.

2. **Configurar el Analizador de Espectros:**
En esta sección, se empleó el analizador de espectros para observar el comportamiento de distintas señales medidas a través del mismo cable. A continuación, se presentan los cambios detectados.

### Señal original
En un inicio se mostró una señal triangular en el analizardor de espectros medida mediante la conexión con un cable coaxial, éste se pueden ver sus componentes así como los armonicos no deseados generados por el ruido.

<div align="center">
  <img src="https://github.com/user-attachments/assets/db6e5237-b830-40a3-8b53-602f6d663660"  alt="Texto alternativo" width="600" height="400"/>
</div>

**Señal con ruido agregado**
Luego de esto se le agregó 0.2 V de ruido a nuestra señal original, dando como resultado: 
<div align="center">
  <img src="https://github.com/user-attachments/assets/2224e3e3-4d55-4b3e-bc95-e83360991835"  alt="Texto alternativo" width="600" height="400"/>
</div>

**Señal cosenoidal** 
En este mismo item se estudió este mismo comportamiento pero con otro tipo de señal, en este caso, una señal cosenoidal. 
<div align="center">
  <img src="https://github.com/user-attachments/assets/e47cf3fa-eabb-4dfc-8f5c-33542fc1a81b"  alt="Texto alternativo" width="600" height="400"/>
</div>

**Señal con ruido agregado**
Luego de esto se le agregó 0.2 V de ruido a nuestra señal cosenoidal, dando como resultado: 
<div align="center">
  <img src="https://github.com/user-attachments/assets/ddd455e8-240a-43f5-bc94-d618f73e0dd9"  alt="Texto alternativo" width="600" height="400"/>
</div>


**¿Cuál es el efecto del ruido sobre la respuesta en frecuencia de las señales medidas en el analizador de espectro? ¿Conservan las mismas relaciones que se evidencian en la simulación?**

El ruido afecta la respuesta en frecuencia de las señales medidas en un analizador de espectro al elevar el piso de ruido, distorsionar los picos espectrales y reducir la relación señal a ruido (SNR), dificultando la identificación y medición de señales débiles. Esto puede provocar ensanchamiento de los picos y fluctuaciones en la amplitud, afectando la precisión en la medición de frecuencias. En comparación con la simulación, donde las señales suelen generarse en un entorno ideal sin ruido, las relaciones de amplitud y frecuencia entre los componentes espectrales deberían mantenerse en la medición real, pero con diferencias debido a atenuaciones y distorsiones del sistema de medición. En la simulación, los espectros aparecen más definidos y sin interferencias, mientras que en la medición real el ruido puede dificultar la interpretación. Para una comparación más precisa, sería ideal analizar ambos espectros en detalle.

**¿La relación señal a ruido creada intencionalmente desde el computador se amplifica o se reduce en la señal observada en el analizador de espectro?**

La SNR tiende a reducirse, ya que la señal sufre atenuaciones, interferencias y la adición de ruido térmico o electromagnético al pasar por los componentes del sistema de medición.

**¿Qué modelo de canal básico describe mejor las mediciones obtenidas en la práctica?**

El modelo de canal básico que mejor describe las mediciones obtenidas en la práctica es el canal aditivo con ruido blanco gaussiano, ya que en muchas aplicaciones de medición, el ruido térmico y electrónico presente en el sistema de adquisición de señales puede modelarse como un proceso gaussiano de media cero y potencia constante en todo el espectro de frecuencias.Este modelo representa de manera adecuada cómo una señal transmitida desde el computador es afectada por ruido aleatorio a lo largo del sistema de medición, incluyendo los cables, conectores y el propio analizador de espectro.

### Actividad 3: Fenómenos de canal en el analizador de espectros

### Objetivo

Familiarizarse con los fenómenos de un canal alámbrico real en el dominio de la frecuencia.

### Procedimiento

1. **Configurar el USRP 2920:**
En un inicio se configuró el flujograma dado por el docente para establecer un valor de frecuencia de muestreo adecuado para la práctica, dado que se requería ussar al siguiente fórmula: $\frac{25e^{6}}{2^{n}}$ donde n debe ser un número mayor a 2 y para nuestro caso se estableció que éste fuese de 6.
2. **Configurar el Analizador de Espectros:**
En esta parte se utilizó el analizador de espectros para ver el comportamiento de diferentes señales medidas mediante el mismo cable, cada uno de estos cambios se muestra a continuación:

### Señal Triangular
En un inicio se mostró una señal triangular en el analizardor de espectros medida mediante la conexión con un cable coaxial, éste se pueden ver sus componentes así como los armonicos no deseados generados por el ruido.

<div align="center">
  <img src="https://github.com/user-attachments/assets/c174c78f-3948-4833-83f0-6841612649ec" title="https://github.com/user-attachments/assets/a4914c27-8a38-4697-9267-621b9b16b2ef" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal Coseno 
Se mostró una señal cosenoidal en el analizardor de espectros medida mediante la conexión con un cable coaxial, éste se pueden ver sus componentes así como los armonicos no deseados generados por el ruido.

<div align="center">
  <img src="https://github.com/user-attachments/assets/29c7e530-28fe-42fd-a3ed-c94ee0598dfc" title="https://github.com/user-attachments/assets/a4914c27-8a38-4697-9267-621b9b16b2ef" alt="Texto alternativo" width="600" height="400"/>
</div>

### ¿Cuál es el efecto del ruido sobre la respuesta en frecuencia de las señales medidas en el analizador de espectro? ¿Conservan las mismas relaciones que se evidencian en la simulación?
De manera general se puede decir que efectivamente la respuesta en frecuencia de las señales medidas en el analizador de espectros conservan cierta relación con los datos obtenidos en la simulación, sin embargo, es importante notar que a diferencia de la simulación en donde se eliminaban todos los armonicos indeseados gracias al filtro, para el caso del analizador espectro aparecen, esto se debe a que la señal no se puede transmitir me manera adecuada al 100%, por lo que se generan componentes de ruido debido a la transmisión mediante el cable lo que afecta el resultado visto por el analizador de espectro.


### Actividad 4: Análisis de Resultados y Conclusiones
**¿Cuál es el efecto del ruido sobre la respuesta en frecuencia de las señales medidas en el analizador de espectro?**
El ruido es un factor determinante en la medición de señales en el dominio de la frecuencia, ya que puede afectar significativamente la precisión y confiabilidad de los resultados obtenidos con un analizador de espectro. En términos generales, el ruido eleva el piso de ruido del sistema, lo que reduce la relación señal a ruido (SNR) y dificulta la detección de señales débiles o de baja amplitud. Además, el ruido puede ocasionar el ensanchamiento de los picos espectrales y generar fluctuaciones en la amplitud de las señales medidas, lo que puede llevar a errores en la identificación de frecuencias y en la medición de la potencia de los armónicos o componentes espectrales. En condiciones de alto ruido, algunas señales pueden quedar ocultas dentro del piso de ruido, lo que hace que su detección y análisis sean más complicados.

En conclusión, el ruido tiene un impacto negativo en la respuesta en frecuencia de un sistema, ya que introduce incertidumbre en las mediciones y puede alterar la interpretación de los resultados obtenidos en el analizador de espectro. Para minimizar su efecto, es recomendable utilizar técnicas de filtrado, promedios de medición o mejorar la calidad del equipo y la calibración del sistema de medición.

**¿Conservan las mismas relaciones que se evidencian en la simulación?**
En la simulación, las señales suelen modelarse en un entorno ideal donde no hay interferencias, distorsiones ni ruido, lo que permite observar con claridad las relaciones entre los diferentes componentes espectrales, como sus amplitudes relativas y sus posiciones en frecuencia. Sin embargo, en una medición real, las condiciones del sistema pueden generar discrepancias respecto a la simulación debido a diversos factores, como la presencia de ruido, las pérdidas en los circuitos, la respuesta no ideal de los instrumentos de medición y las limitaciones del equipo.

Si bien en un escenario ideal las relaciones entre los componentes espectrales deberían mantenerse tanto en la simulación como en la medición real, en la práctica pueden presentarse diferencias. Factores como la distorsión no lineal, las variaciones en la impedancia del sistema y la interferencia externa pueden modificar la amplitud y forma de los espectros obtenidos.

En conclusión, aunque la simulación proporciona una referencia teórica del comportamiento de la señal en el dominio de la frecuencia, la medición real puede presentar desviaciones debido a efectos prácticos que no siempre se consideran en el modelo teórico. 
### Referencias

- https://ieeexplore.ieee.org
