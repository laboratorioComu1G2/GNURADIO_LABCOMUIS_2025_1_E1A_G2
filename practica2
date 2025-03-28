Laboratorio de Comunicaciones
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

Uso de IA: En la elaboración del resumen y como fuente de investigación para insertar imagenes.
## Contenido

### Resumen
En esta práctica se estudiaron las características en el dominio del tiempo y la frecuencia al cambiar los parámetros de la fuente, adicionalmente se analizó como dichos cambios afectaban a distintas formas de onda, gracias a esto se pudo observar como las señales senoidales centran toda su energía en una sola frecuencia mientras que las señales cuadradas se distribuyen a lo largo de varias frecuencias. Por último se observó como los resultados obtenidos mediante la simulación fueron concordantes con los datos visto en el laboratorio, comprobando así la relación que existe entre los parámetros de la señal y sus comportamiento en tiempo y frecuencia.

**Palabras clave:** Analizador de espectros, GNU radio, Mediciones, Transformaciones de la señal. 

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
### Señal Cosenoidal Original: 
En un inicio se tiene una señal coseno con amplitud de 1V y una frecuencia de 1kHz dicha señal se representa con la sigueinte ecuación $cos((2\pi )1000t)$
<div align="center">
  <img src="https://github.com/user-attachments/assets/8a1ef106-7307-4d43-96f4-98cbdbd73400" title="señal original" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal Con Cambio En Su Amplitud:
Al realizar el aumento en la amplitud de 1V a 4V se puede ver como la señal cosenoidal aumenta tanto en su parte real como en su componente imaginaria, además la ganancia de potencia en el espectro de la frecuencia aumenta de manera considerable.
<div align="center">
  <img src="https://github.com/user-attachments/assets/dd62690e-d5bc-4325-92d2-31e8384a0041" title="Señal Modificada En Amplitud" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal Con Cambio En Su Frecuencia:
Al realizar un aumento en la frecuencia de la señal de 1kHz a 4kHz, se observa como la longitud de onda de la señal en el tiempo se disminuye y como en el espectro de la frecuencia su valor para la ganancia máxima de potencia se da en el valor de la nueva frecuencia, es decir, la ganancia máxima de potencia se logra en 4kHz.

<div align="center">
  <img src="https://github.com/user-attachments/assets/33d52e19-4417-4183-8425-1e4978224e8a" title="Señal Modificada En Frecuencia" alt="Texto alternativo" width="600" height="400"/>
</div>


### Señal Con Adición De Voltaje De Ruido
Se le añadió un voltaje de ruido a la señal para ver su variación tanto en tiempo como en el espectro de frecuencia, se observa como en el tiempo resulta complicado determinar los valores que puede llegar a tomar la señal, adicionalmente la señal tiende a variar su amplitud superando sus limites tanto inferior como superior; en el espectro de la frecuencia se observa como el piso de ruido de la señal aumenta en gran medida su valor pasando de unos niveles de  casi -200 db a un nivel de -50 db

<div align="center">
  <img src="https://github.com/user-attachments/assets/fe353172-70cd-4c10-a5b9-3968c6eeba45" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal Con Offset De Frecuencia
Se le añadió una componente de offset de frecuencia a la señal de 0,5 Hz, al observar sus cambio se hace evidente como la señal en el tiempo deja de poseer la forma de una onda cosenoidal pura y sus componentes tanto real como imaginaria varian en cuanto a la amplitud original, respecto al espectro de la frecuencia se puede observar como cambia de posición la ganancia de potencia máxima, siendo desfasada alrededor de 10 kHz.

<div align="center">
  <img src="https://github.com/user-attachments/assets/ae48bcbe-cc59-4535-84d0-4b490aaed875" title="Señal Con Offset De Frecuencia" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal Con Todos Los Cambios
A continuación se puede observar una imagen con todos los cambios realizados a la señal a lo largo de la práctica, ésta señal presenta todas las alteraciones mencionadas en secciones anteriores del informe.

<div align="center">
  <img src="https://github.com/user-attachments/assets/caeef924-92ac-43ab-83f7-a297721f56ad" title="Señal Con Todos Los Cambios" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal Cuadrada 
Luego de realizar el análisis de la señal coseno, se busco otro tipo de señal para verificar si su respuesta ante los cambios realizados a la señal coseno mantenian la misma tendencia, como se puede apreciar al realizar la comparación entre la señal original y aquella que posee todos los cambios, la tendencia de los cambios se mantien, tanto en la señal en el tiempo como para la señal en la frecuencia.

### Señal Original

<div align="center">
  <img src="https://github.com/user-attachments/assets/c805be8a-cf7c-43be-ad02-3ed04f40b64c" title="Señal Cuadrada" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal Con Todos Los Cambios

<div align="center">
  <img src="https://github.com/user-attachments/assets/dc604f6b-c9f3-4720-8fe1-6e72a759aecb" title="Señal Con Offset De Frecuencia" alt="Texto alternativo" width="600" height="400"/>
</div>

### ¿Cómo se puede explicar matemáticamente la diferencia entre una fuente de tipo flotante y una de tipo complejo?
Una fuente de tipo flotante se conoce también como una fuente de magnitud real, por lo que dicha fuente solo me generará valores reales, mientras que la fuente de tipo compleja me generará dos valores de magnitud, uno real y otro complejo, matematicamente se puede ver de la sigueinte manera: para una fuente flotante $x(t) = a(t)$ en donde $a(t)$ son valores unicamente reales, mientras que para una fuente compleja $x(t)=a(t)+jb(t)$

### ¿Qué sucede con la señal en el dominio del tiempo y la frecuencia si se modifican los diferentes parámetros de la fuente?
Al realizar distintos cambios en los parámetros de la fuente se pudieron observar las siguientes variaciones en el tiempo y la frecuencia, para el cambio en su amplitud se observa como la potencia en el espectro de la frecuencia aumenta su valor de manera considerable, al cambiar la frecuencia de la fuente hace que el espectro en la frecuencia se desplace hacia la frecuencia que se le está modificando, por último al modificar el ruido que le ingresa a la señal se puede observar como en el tiempo la señal se distorciona perdiendo su forma original y por lo tanto información, mientras que para el espectro de la frecuencia se observa como obtiene un piso de ruido mucho mayor por lo que resulta más complejo determinar el valor exacto de la ganancia de la potencia.
### Actividad 3: Transmisión y Medición de Señales con el USRP 2920
   ### 1. Configurar el USRP 2920:
En la primera parte de esta actividad, se indicó que reconociéramos el bloque de frecuencia de muestreo y observáramos el impacto de alterar o cambiar su valor, que en un principio se establecía en 32 kHz, pero luego fue disminuido a 10 kHz para observar las variaciones en su señal.

Se observó que, al reducir la frecuencia de muestreo, disminuyó el ancho de banda que se podía analizar, pasando de 16 kHz a 5 kHz. Esto nos restringía el efecto de las frecuencias que se podían percibir, pero al mismo tiempo mejoró la resolución de la frecuencia en este espectro.
<div align="center">
<img src="https://github.com/user-attachments/assets/855697d7-c3c3-4125-ac9e-e9581dc5fefd" title="señal Modificada En Amplitud" alt="Texto alternativo" width="600" height="400"/>
</div>

Tras realizar los primeros ajustes, se configuró la frecuencia de muestreo en 1 MHz para evaluar su efecto en la señal. Además, se analizaron las variaciones al modificar la frecuencia y la ganancia del USRP.

Al incrementar la frecuencia de muestreo, se amplió el ancho de banda disponible, lo que permitió una mejor visualización de los componentes espectrales. En la gráfica del dominio del tiempo, la señal mostró una mayor definición y una representación más precisa de sus componentes real e imaginario. En el dominio de la frecuencia, se observó un pico bien definido en la frecuencia central, lo que confirmó una correcta transmisión y recepción de la señal. Por otro lado, los ajustes en la ganancia del USRP afectaron directamente la amplitud de la señal recibida, incrementándola conforme aumentaba la ganancia.

<div align="center">
<img src="https://github.com/user-attachments/assets/402e80a1-33f1-4a62-bf17-db41175d3c42" title="señal Modificada En Amplitud" alt="Texto alternativo" width="600" height="400"/>
</div>

   ### 2. Medición con el Analizador de Espectros:

Se midió el piso de ruido normalizado a la frecuencia de la portadora(basandonos en la señal que nos mostraba el analizador de espectros), obteniendo un valor de -82 dBm. Esto indica que el sistema presenta un nivel de ruido bajo, lo que permite una recepción más clara de la señal transmitida. Además, la diferencia entre el piso de ruido y la señal útil determina la relación señal-ruido (SNR), la cual influye directamente en la calidad de la transmisión y recepción de datos.
<div align="center">
<img src="https://github.com/user-attachments/assets/7a8230b0-6efb-4197-9d31-ce66047d17cc" title="señal Modificada En Amplitud" alt="Texto alternativo" width="600" height="400"/>
</div>

Al comparar los resultados obtenidos en el simulador con los del analizador de espectros, observamos que el nivel de ruido normalizado fue el mismo en ambos casos, pero en la simulación no apareció la señal central. Analizando esta diferencia, identificamos que se debe a la forma en que el analizador de espectros procesa y muestra las señales. El equipo introduce un efecto de auto-detección o supresión de la componente en continua (DC offset), lo que explica la ausencia de la señal en el centro de la gráfica simulada.

Continuando con la práctica, se evaluó el impacto de modificar el tipo de dato de la fuente, comparando el uso de datos complejos con datos flotantes. Al emplear datos complejos, en el dominio de la frecuencia se observa tanto la magnitud como la fase, lo que nos permite obtener una representación más completa de la señal. Esto se refleja en la presencia de picos simétricos y en la detección precisa de cambios en la fase, lo que facilita un análisis detallado del comportamiento real de la señal.
<div align="center">
<img src="https://github.com/user-attachments/assets/c5906e88-ca9d-405b-8d7e-6e0a83833bd1" title="señal Modificada En Amplitud" alt="Texto alternativo" width="600" height="400"/>
</div>
<div align="center">
<img src="https://github.com/user-attachments/assets/3356e3e8-9024-4551-b5eb-4deecbe4c0d2" title="señal Modificada En Amplitud" alt="Texto alternativo" width="600" height="400"/>
</div>

En cambio, al utilizar datos reales, solo se muestra la magnitud, limitando la cantidad de información visible en el espectro. Como resultado, la interpretación del espectro resulta menos detallada. Estos hallazgos nos confirman que, para un análisis más profundo en el dominio de la frecuencia, es mejor trabajar con datos complejos.


Al modificar el tipo de onda de senoidal a cuadrado, se observan variaciones importantes tanto en la simulación como en el analizador de espectros.  La onda cuadrada muestra armónicos más destacados en el dominio de la frecuencia, manifestándose en múltiples picos a lo largo del espectro, en vez de un único pico predominante.  Además, la magnitud de estos armónicos se determina por la altura y el diseño de los pulsos, lo que aclara la repartición de energía en frecuencias más elevadas.

 Comparado con la onda senoidal, la onda cuadrada incorpora más elementos de alta frecuencia, a causa de sus transiciones bruscas.  Esto se puede observar en el analizador de espectros como varios picos en torno a la frecuencia central.
<div align="center">
<img src="https://github.com/user-attachments/assets/af025787-ccbc-4ef5-81dd-d3fefdf267d9" title="señal Modificada En Amplitud" alt="Texto alternativo" width="600" height="400"/>
</div>

Cuando se altera la frecuencia, el pico central en el espectro se traslada hacia la nueva portadora, lo que refleja la variación en la ubicación central.  En cambio, modificar la fase modifica la alineación de la onda en el dominio temporal, a pesar de que su impacto en la repartición de energía en el espectro es casi inaudible.  Estos hallazgos corroboran que la frecuencia establece el lugar del pico en el dominio de la frecuencia, en tanto que la fase afecta la sincronización temporal de la señal.
<div align="center">
<img src="https://github.com/user-attachments/assets/185dc1a2-b840-49e6-9453-bb018c820c0d" title="señal Modificada En Amplitud" alt="Texto alternativo" width="600" height="400"/>
</div>

Al modificar la amplitud de la señal generada, la potencia en el espectro aumenta o disminuye proporcionalmente. Los valores de amplitud más altos elevan el pico en el dominio de la frecuencia, reflejando niveles de potencia más altos, pero no cambian su posición. Por el contrario, al reducir la amplitud, se reduce la amplitud de toda la señal y sus armónicos, manteniendo así la misma posición del pico de frecuencia. Este comportamiento confirma que la amplitud afecta directamente la intensidad de la señal pero no cambia su frecuencia central ni la distribución de sus componentes.
</div>

### ¿Qué diferencias se observan en las mediciones de potencia cuando se varía la ganancia del USRP?

En la práctica se observó que al variar la ganancia del USRP, la potencia de la señal transmitida cambia de forma directa: un aumento en la ganancia eleva la potencia, reflejándose en un pico más pronunciado en el analizador de espectros, mientras que una ganancia menor reduce la potencia y, por ende, la altura del pico. Esto confirma la influencia directa de la ganancia sobre la intensidad de la señal, resaltando la importancia de ajustar correctamente este parámetro para lograr niveles de potencia adecuados
</div>



### Actividad 4: Análisis de Resultados y Conclusiones

Durante la práctica se realizaron diversas mediciones mediante simulaciones en GNU Radio y transmisiones reales de USRP 2920, un osciloscopio R&S RTB2004 y un analizador de espectro R&S FPC1000. En las simulaciones se observó una representación precisa de la señal en los dominios de tiempo y frecuencia, permitiendo identificar claramente picos, armónicos y cambios de fase. Sin embargo, en las mediciones reales se encontraron algunas diferencias debido a las características del propio equipo, como el efecto de detección automática del analizador de espectro y la supresión de componentes DC.

La comparación entre los resultados de la simulación y los obtenidos en el laboratorio muestra que el osciloscopio proporciona una vista detallada de la forma de onda en el dominio del tiempo, mientras que el analizador de espectro proporciona información valiosa sobre la distribución de energía y la presencia de armónicos en el dominio de la frecuencia. Además, encontramos que los cambios en parámetros como el tipo de datos, la forma de onda, la frecuencia, la fase y la amplitud tienen un impacto directo en la representación del espectro, validando la importancia de ajustar estos parámetros para lograr mediciones precisas.
El análisis de la relación señal-ruido (SNR) revela la importancia de mantener un nivel de ruido bajo. En nuestra práctica, el ruido de fondo normalizado medido fue de -82 dBm, lo que indica un ambiente relativamente limpio. Sin embargo, es importante destacar que si la potencia de la señal está demasiado cerca de este valor, su correcta detección puede resultar difícil.

### ¿Qué limitaciones tienen los equipos utilizados en términos de ancho de banda y precisión en las mediciones?


El equipo utilizado tiene limitaciones inherentes en cuanto a ancho de banda y precisión de medición. Por ejemplo, el USRP 2920 está limitado por su rango operativo y resolución de medición, lo que puede dificultar la captura de señales de alta frecuencia o señales con transiciones muy rápidas. En el caso de un osciloscopio, depende de su frecuencia de muestreo y ancho de banda máximo, lo que puede limitar la fidelidad de la representación de señales complejas. Además, los analizadores de espectro, aunque permiten ajustar el ancho de banda de resolución, todavía introducen efectos como la supresión continua de componentes (desplazamiento de CC) y se ven afectados por el ruido de fondo, lo que afecta la precisión de las mediciones del nivel de potencia. Estas limitaciones enfatizan la importancia de comprender las características y limitaciones de cada instrumento para interpretar correctamente los resultados experimentales.


### ¿Qué aplicaciones prácticas tienen las mediciones de potencia y ancho de banda en sistemas de comunicaciones reales?

Las mediciones de potencia y ancho de banda son cruciales en los sistemas de comunicación reales, ya que optimizan la calidad de la transmisión y el uso del espectro. Por un lado, medir la potencia ayuda a garantizar que la señal transmitida esté en el nivel adecuado para superar las pérdidas y el ruido ambiental, lo cual es fundamental para mantener una buena relación señal-ruido (SNR) y comunicaciones confiables. Por otro lado, medir el ancho de banda es fundamental para evaluar la capacidad del canal para transmitir información, de modo que se puedan diseñar filtros y estrategias de modulación para maximizar la eficiencia espectral y minimizar la interferencia con otros sistemas. En aplicaciones como redes móviles, televisión digital o comunicaciones Wi-Fi, estos parámetros son cruciales para cumplir con la normativa, asegurar la calidad del servicio y optimizar el rendimiento general del sistema de comunicación.
</div>

### Referencias

- https://ieeexplore.ieee.org
- Spectrum_Analyzer_FPC_XXX_ANL-EN.pdf
- USRP-2920 Specifications.pdf
- Spectrum_Analyzer_FPC_XXX_ANL-EN.pdf
