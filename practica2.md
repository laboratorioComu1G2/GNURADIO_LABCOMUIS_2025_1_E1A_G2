Laboratorio de Comunicaciones
## Universidad Industrial de Santander

# Práctica 2A. Modelo de canal

### Integrantes
- **Duban Andretti Gutierrez Leon** - 2220396
- **Juan José De la Rosa Medina** - 2202810

Escuela de Ingenierías Eléctrica, Electrónica y de Telecomunicaciones  
Universidad Industrial de Santander

### Fecha
28 de marzo de 2025

---

## Declaración de Originalidad y Responsabilidad
Los autores de este informe certifican que el contenido aquí presentado es original y ha sido elaborado de manera independiente. Se han utilizado fuentes externas únicamente como referencia y han sido debidamente citadas.

Asimismo, los autores asumen plena responsabilidad por la información contenida en este documento. 

Uso de IA: .
## Contenido

### Resumen
En esta práctica se estudiaron las características en el dominio del tiempo y la frecuencia al cambiar los parámetros de la fuente, adicionalmente se analizó como dichos cambios afectaban a distintas formas de onda, gracias a esto se pudo observar como las señales senoidales centran toda su energía en una sola frecuencia mientras que las señales cuadradas se distribuyen a lo largo de varias frecuencias. Por último se observó como los resultados obtenidos mediante la simulación fueron concordantes con los datos visto en el laboratorio, comprobando así la relación que existe entre los parámetros de la señal y sus comportamiento en tiempo y frecuencia.

**Palabras clave:** Analizador de espectros, GNU radio, Mediciones, Transformaciones de la señal. 

### Introducción
En los sistemas de comunicación de la actualidad se hace necesario un correcto análisis de las señales para garantizar que la información se transmita de manera adecuada, por lo cual es imprescindible comprender cómo afecta a la señal sus distintos parámetros tales como: las formas de onda, las fuentes de la señal y el entorno en el cual se está transmitiendo, además de considerar sus efectos en el tiempo y la frecuencia. A lo largo de este informe se tiene como objetivo analizar el comportamiento de una señal al implementarle ciertos cambios, entre estos la amplitud, la frecuencia, el ruido, la fase y su offset; todos estos cambios se podrán medir utilizando el USRP 2920 y equipos complementarios como el analizador de espectros y el osciloscopio.

### Procedimiento
### Actividad 1: Actividades de simulación de canal en GNU Radio
### Objetivo
Familiarizarse con algunos fenómenos de canal en un ambiente simulado.

   ## 1. Seleccionar un valor n para determinar la frecuencia de muestreo:
Para poder iniciar con las simulaciones se requería de un valor n para determinar la frecuencia de muestreo a la cual trabajaría el sistema, por lo que para nuestro caso se utilizó un n=6 el cual fue reemplazado en la siguiente ecuación: $\frac{25e^{6}}{2^{n}}$

### Actividad 2: Simulación de Señales en GNU Radio
En esta fase se visualizaron los cambios ocurridos a una señal de entrada elegida por cada grupo al alterar varios de sus parametros de manera individual, a continuación se muestra cada uno de los cambios con respecto a la imagen original y se hace una breve explicación de cada fenomeno ocurrido.

### Señal Triangular Original: 
En un inicio se tiene una señal triangular con amplitud de 0.5V y una frecuencia de 1kHz.
<div align="center">
  <img src="https://github.com/user-attachments/assets/ef8e665b-022f-4fc4-a90b-0424c00ffe91" title="señal original" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal Con Cambio En Su Frecuencia De Corte Inferior:
Al realizar el aumento en su frecuencia de corte inferior se pudo observar como la amplitud de la señal de salida se reducía.
<div align="center">
  <img src="https://github.com/user-attachments/assets/644ec085-c100-47d6-bd15-b38834f52956" title="Señal Modificada En Amplitud" alt="Texto alternativo" width="600" height="400"/>
</div>

### Señal Con Una Reducción En La Diferencia De Sus Frecuencias De Corte:
Al reducir de manera considerable el ancho de banda del filtro se puede observar como la señal que en su entrada es un triangular tiende a una forma senoidal con una reducción de su amplitud.

<div align="center">
  <img src="https://github.com/user-attachments/assets/0574fee2-f627-4bdc-b92e-e0614ecbee42" title="Señal Modificada En Frecuencia" alt="Texto alternativo" width="600" height="400"/>
</div>


### Señal Con Adición De Voltaje De Ruido Para El Dominio Del Tiempo
Se le añadió un voltaje de ruido a la señal para ver su variación tanto en la entrada como en su salida luego de pasar através de un filtro, se pudo observar como en la entrada la señal presenta una distorción muy fuerte apesar de solo tener 0.1 V de ruido, esto se debe a que el valor de su ancho de banda es muy grande por lo que la señal captura mucho más ruido del que se podría esperar en un primer momento, al analizar la señal luego de pasar por el filtro se puede ver como ésta presenta una ligera atenuación, pero en su forma no presenta grandes camabios, esto se debe a que el filtro nos permite visualizar unicamente las componentes de la señal que queremos evitando que se muestre en la salida todo ese ruido no deseado.

<div align="center">
  <img src="https://github.com/user-attachments/assets/f61e2feb-43d7-49ba-ac12-bc0a5848a2ca" title="Señal Modificada En Ruido" alt="Texto alternativo" width="600" height="400"/>
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

Aumentar la potencia de la señal transmitida
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
