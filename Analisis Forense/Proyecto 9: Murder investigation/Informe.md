# Informe Pericial Proyecto 9

# Índice

1. [Juramento de Decir la verdad](#jura) 
2. [Glosario de palabras clave](#clave)
3. [Índice de figuras](#figu)
4. [Resumen ejecutivo](#resumen)  
   4.1 [Linea temporal](#linea)
6. [Introducción](#intro)  
5.1 [Antecedentes](#ante)  
5.2 [Objetivos](#obj)  
5.3 [Fuentes de información](#fuente)  
5.4 [Adquisición de evidencias](#adqui)
7. [Análisis](#analisis)  
6.1 [Herramientas usadas](#herramienta)  
6.2 [Investigación](#invest)  
 6.2.1 [Análisis de Raspberry Pi TV](#rasp)    
 6.2.2 [Análisis de Alexa](#Alexa)
8. [Limitaciones](#limits)
9. [Conclusiones](#conclu)

# Juramento de Decir la verdad <div id="jura" />

Los peritos firmantes de este documento juramos solemnemente decir la verdad, toda la verdad y nada más que la verdad en este informe judicial. Prometemos que nuestras conclusiones y opiniones se basarán en los hechos, la evidencia y en nuestra experiencia profesional. Comprendemos la importancia de nuestro testimonio y la responsabilidad que conlleva en contribuir a la búsqueda de la justicia y la verdad en este asunto. Por lo tanto, nos comprometemos a cumplir con la ética y los estándares de nuestra profesión en todo momento.

# Glosario de palabras clave <div id="clave" />

- Caché: Es un componente de hardware o software que guarda datos para que las solicitudes futuras de esos datos se puedan atender con mayor rapidez.
- Alexa: Es un asistente virtual desarrollado por Amazon.
- Base de Datos: Es un conjunto de datos estructurados que pertenecen a un mismo contexto  y, en cuando a su función, se utiliza para administrar de forma electrónica grandes cantidades de información.

# Índice de figuras <div id="figu" />

1. [Tabla: Comprobación hashes](#tabhash)
2. [Tabla: Herramientas usadas](#tabherr)
3. [Imagen: Captura videos emitidos TV Inteligente](#videoTV)
4. [Tabla: Videos y hora emitidos en TV Inteligente](#timeTV)
5. [Imagen: Dispositivo Alexa conectado a TV Inteligente](#alexaTV)
6. [Imagen: Modelo de Alexa conectado a TV Inteligente](#modAlexa)
7. [Imagen: Dispositivo Pulsera Xiaomi conectado a TV Inteligente](#pulseraTV)
8. [Imagen: Modelo Pulsera inteligente conectada a TV Inteligente](#modpuls)
9. [Imagen: Auriculares Bluetooth móvil del marido](#aurblue)
10. [Imagen: Modelo Auriculares Bluetooth móvil del marido](#modblue)
11. [Imagen: History second page de Alexa](#his2Alexa)
12. [Imagen: History first page de Alexa](#hisAlexa)
13. [Imagen: Audio Alexa](#audAlexa)


# Resumen ejecutivo <div id="resumen" />

En respuesta a la presunta cuartada proporcionada por el esposo de la víctima, quien afirmó estar viendo una película en su habitación en el momento del crimen, se inició una investigación centrada en la televisión de la habitación. 

El análisis de estos videos reveló que uno de ellos no había sido reproducido completamente, sugiriendo que la película no había sido vista en su totalidad. Además, el esposo afirmó haber estado escuchando la película a través de auriculares mientras su esposa reproducía música.

Al examinar los archivos de caché de los dispositivos conectados por Bluetooth a la televisión, se identificaron dos dispositivos: uno correspondiente a Alexa y otro a una pulsera inteligente Xiaomi MI1A. Investigaciones adicionales revelaron que la televisión fue encendida a las 15:01 del día del crimen, contradiciendo el testimonio del esposo, quien afirmó haber estado viendo la película desde antes de la hora del crimen hasta el momento en que fue visto saliendo de la casa.

Los registros de audio de Alexa capturaron voces femeninas y masculinas durante el período en que el esposo afirmó estar viendo la película. Este descubrimiento sugiere discrepancias significativas en la coartada proporcionada por el esposo de la víctima.

## Línea temporal <div id="linea" />

![Untitled](img/Asesinato_en_casa.png)

# Introducción <div id="intro" />

## Antecedentes <div id="ante" />

El caso involucra el asesinato de una mujer en su residencia, reportado por su esposo y el conserje del edificio. A las 15:31 del 17 de julio de 2017, el conserje llamó al número de emergencia 112 para informar sobre el incidente. La policía llegó a la escena a las 15:40, encontrando a la víctima sin vida en el salón, aparentemente fallecida por múltiples puñaladas. El esposo declaró haber llegado a casa alrededor de las 15:00 y descubierto el cuerpo después de ver una película en el dormitorio, durante la cual llevaba auriculares. Colaboró con la investigación, pero no pudo proporcionar las contraseñas de los dispositivos electrónicos de la víctima.

## Objetivos <div id="obj" />

Los objetivos de este informe pericial son:

- Demostrar la veracidad de la cuartada del marido.
- Realizar un timeline con el fin de aclarar los hechos.
- Investigar los datos de los dispositivos proporcionados.

## Fuentes de información <div id="fuente" /> 

[Véase Anexo de fuentes de información](Anexos.md)

### Adquisición de evidencias <div id="adqui" />

Realizamos una comprobación de veracidad sobre las fuentes de evidencias proporcionadas por las autoridades.

| Archivo | HASH MD5 Proporcionado  | HASH MD5 | HASH SHA-256 Proporcionado | HASH SHA-256 |
| --- | --- | --- | --- | --- |
| InformeDiagnosticoOnHub | 4a07bd78d8f4ba227841c971eeb7d1b3 | 4a07bd78d8f4ba227841c971eeb7d1b3 | 4767513d714698afcd7506dd2304528a8db8243e2dff1be6e1ede591d0d19f83 | 4767513d714698afcd7506dd2304528a8db8243e2dff1be6e1ede591d0d19f83 |
| Tráfico_SmartHome_PorCOAP.pcap | 67ab09760148a66402aa7d9b0abaa322 | 67ab09760148a66402aa7d9b0abaa322 | f5ad42a50ca0d16261c1ca4742d78fd99c9e7fc6ab67fdb3a53909ff7f786ce0 | f5ad42a50ca0d16261c1ca4742d78fd99c9e7fc6ab67fdb3a53909ff7f786ce0 |
| Trafico_SmartHome_PorIP.pcap | 8fb0edb521c9ad191adf55054203a6f4 | 8fb0edb521c9ad191adf55054203a6f4 | a4664f1719d26382edd6d352cc8715fea3ee73bbb00245d71943fbacbbeeca3e | a4664f1719d26382edd6d352cc8715fea3ee73bbb00245d71943fbacbbeeca3e |
| Alexa.zip | 93639c62f68c5155611bbd7e8eb3f477 | 93639c62f68c5155611bbd7e8eb3f477 | 6c09813eea5475dc0011c547e7fb774cfbd7216cafdeeb9a8308306046c14edf | 6c09813eea5475dc0011c547e7fb774cfbd7216cafdeeb9a8308306046c14edf |
| movil_chica.zip | 8daf9d23e39675452f99c5099a72b317 | 8daf9d23e39675452f99c5099a72b317 | c3e334c996b811c51067e9e0657cb621523576f15eb2c19ec52c32bf36e3e5ff | c3e334c996b811c51067e9e0657cb621523576f15eb2c19ec52c32bf36e3e5ff |
| movil_chico.zip | 1472be511173e7e0f4919958b1c96ffe | 1472be511173e7e0f4919958b1c96ffe | 5a46acdf7fb5a70734a2e0e39a8c9b5cc9b7ee799fe800a0a7512af08e15c025 | 5a46acdf7fb5a70734a2e0e39a8c9b5cc9b7ee799fe800a0a7512af08e15c025 |
| TV_Inteligente.zip | d9d2b3b3048a836289cec02c6353b6e9 | d9d2b3b3048a836289cec02c6353b6e9 | 5423ea3f60d4ad0874346d3ba31c8783e5f2ce4b15b261ba0085e07f11e650e6 | 5423ea3f60d4ad0874346d3ba31c8783e5f2ce4b15b261ba0085e07f11e650e6 |

*Tabla: comprobación hashes* <div id="tabhash" />

Tras el análisis de todos los hashes de todos los ficheros, podemos decir, que coinciden con los hashes proporcionados.

# Análisis <div id="analisis" />

## Herramientas utilizadas <div id="herramienta" />

| Herramienta | Versión |
| --- | --- |
| AccessData FTK Imager | 3.1.2.0 |
| DB Browser for SQLite | 3.12.2 |
| Autopsy | 4.21.0 |
| 7-Zip | 23.01 |
| WhireShark | 4.2.3 |

*Tabla: Herramientas utilizadas* <div id="tabherr" />

## Investigación <div id="invest" />

### Análisis de Raspberry Pi TV <div id="rasp" />

Como el marido de la victima aseguraba estar viendo una película en la televisión de su habitación en los momentos de los hechos, decidimos comenzar la investigación con esta y comprobar que es cierto.

Haciendo una investigación sobre los ficheros de la adquisición de la televisión inteligente, encontramos que esta tiene un plugin de Youtube instalado, este nos genera una base de datos, en la cual podemos observar los vídeos que han sido vistos desde ella. Observando los videos, hemos podido encontrar los vistos el día del suceso.

Esta base de datos se encuentra en la ruta:

 `“\E001SmartTVMMC\home\osmc\.kodi\userdata\Database\MyVideos107.db”`  
 [Véase Anexo de hallazgos. Hallazgo 1](Anexos.md)  

![Untitled](img/Untitled.png)

*Imagen: Captura videos emitidos TV Inteligente* <div id="videoTV" />

Podemos comprobar la zona horaria de la televisión en su información del sistema, una vez comprobada esta podemos afirmar que la ubicación es “América/New York“. Esta información podemos encontrarla en la ruta:

`“/etc/timezone”`

Una vez que conocemos la zona horaria en la que se encuentra la televisión, debemos realizar la conversión de estas horas, como aún no se encuentran en horario de verano, tendremos que sumar trece horas a las horas dadas, quedando como las mostradas en la siguiente tabla:

| plugin://plugin.video.youtube/play/?video_id=pF_rqav38Z4 | 2017-07-13 21:43:46 |
| --- | --- |
| plugin://plugin.video.youtube/play/?video_id=7WX0-O_ENlk | 2017-07-16 17:54:54 |
| plugin://plugin.video.youtube/play/?video_id=ibOskbTPZYE | 2017-07-17 15:07:30 |
| plugin://plugin.video.youtube/play/?video_id=VKfbVLmkQUs | 2017-07-17 15:19:37 |

*Tabla: Videos y hora emitidos en TV Inteligente* <div id="timeTV" />

Podemos comprobar que el video terminado en “VKfbVLmkQUs” no dispone playCount, lo cual nos indica que el video no se llegó a terminar de reproducir. 

El marido de la victima, aseguraba también estar haciendo uso de unos auriculares bluetooth para ver una película, ya que su esposa estaba escuchando música en la otra habitación.

Continuando la investigación de este dispositivo, encontramos en la cache los distintos dispositivos bluetooth que están vinculados a este, podemos observar que no se encuentra ningún dispositivo de auriculares bluetooth, esto podemos hallarlo en la siguiente ruta:

`“/var/lib/bluetooth/B8:27:EB:E6:8D:79/cache/74:C2:46:88:5D:09”`  
[Véase Anexo de hallazgos. Hallazgo 2](Anexos.md)  

![Untitled](img/Untitled%201.png)

*Imagen: Dispositivo Alexa conectado a TV Inteligente* <div id="alexaTV" />

Este primero, si buscamos el nombre del dispositivo en Google encontramos que corresponde al dispositivo Alexa.

![Untitled](img/Untitled%202.png)

*Imagen: Modelo de Alexa conectado a TV Inteligente* <div id="modAlexa" />

El otro dispositivo conectado en la televisión sería:

`“/var/lib/bluetooth/B8:27:EB:E6:8D:79/cache/88:0F:10:F6:C8:B7"`  
[Véase Anexo de hallazgos. Hallazgo 3](Anexos.md)  

![Untitled](img/Untitled%203.png)

*Imagen: Dispositivo Pulsera Xiaomi conectado a TV Inteligente* <div id="pulseraTV" />

Este correspondería al siguiente dispositivo Mi1A Band.

![Untitled](img/Untitled%204.png)

*Imagen: Modelo Pulsera inteligente conectada a TV Inteligente* <div id=modpuls" />

Analizando la información del dispositivo móvil del marido, se han encontrado los dispositivos bluetooth que han sido conectados a este. Hemos podido confirmar que estos no se han encontrado conectados a la televisión inteligente.

![Untitled](img/Untitled%205.png)

*Imagen: Auriculares Bluetooth móvil del marido* <div id="aurblue" />

El nombre de este dispositivo, si lo buscamos en google nos confirma que son los auriculares bluetooth.

![Untitled](img/Untitled%206.png)

*Imagen: Modelo Auriculares Bluetooth móvil del marido* <div id="modblue" />

## Análisis de Alexa <div id="Alexa" />

Haciendo una investigación sobre las adquisiciones proporcionadas por las autoridades, podemos observar que se ha hecho uso del dispositivo el día 17/07/2017, mientras que el testimonio del marido indica que llegaron con exactitud al domicilio sobre las 15:00.

Este vestigio podemos encontrarla en la ruta:

`“\Alexa\history second page.png”`  
[Véase Anexo de hallazgos. Hallazgo 4](Anexos.md)  

![Untitled](img/Untitled%207.png)

*Imagen: History second page de Alexa* <div id="his2Alexa" />

Viendo el historial de comandos de Alexa, encontramos que la televisión se encendió a las 15:01 del día 17/07/2017.

Esto podemos encontrarlo en la ruta:

`“\Alexa\history first page.png”`

![Untitled](img/Untitled%208.png)

*Imagen: History first page de Alexa* <div id="hisAlexa" />

Mientras que el testimonio del marido nos indica que el está viendo una película (desde las 15:01 hasta que el conserje lo ve saliendo de casa gritando 15:21) se escucha en los registros de audio de Alexa la voz de la mujer y la voz de un varón. 

Este registro de audio podemos encontrarlo en la ruta:

`“\Alexa\8.wav”`  
[Véase Anexo de hallazgos. Hallazgo 5](Anexos.md)  

Este audio escuchado en Alexa, corresponde con este comando de voz encontrado en el historial del mismo dispositivo.

![Untitled](img/Untitled%209.png)

*Imagen: Audio de Alexa* <div id="audAlexa" />


# Limitaciones <div id="limits" />

Se hace constar que a lo largo del proceso de análisis de cada adquisición proporcionada por la policía, no se han encontrado alguna limitación de relevancia que hayan dificultado la misma o la interpretación de los datos. Se han empleado los recursos y metodologías adecuados para examinar de manera meticulosa cada adquisición, asegurando así la integridad y exhaustividad de la investigación.

# Conclusiones <div id="conclu" />

Se ha demostrado que el testimonio proporcionado por el esposo de la víctima, que afirmaba estar viendo una película en el momento del crimen, no parece ser sólida. Varias discrepancias surgieron durante la investigación:

1. **La reproducción incompleta del video**: Uno de los videos en la base de datos de la televisión no había sido reproducido por completo, lo que sugiere que la película no fue vista en su totalidad como afirmaba el esposo.
2. **Utilización de auriculares.** Según el esposo estaba usando auriculares bluetooth a la hora de ver la película, ya que la victima estaba reproduciendo música desde el dispositivo Alexa. No se hallaron indicios del uso de los mismos, por lo cual es otra discrepancia en su testimonio.
3. **Hora de entrada a la casa**: La discrepancia en los registros de Alexa, donde se muestra un comando de encendido a las 14:45, contradice directamente el testimonio del esposo, quien afirma que llegó a casa a las 15:00.
4. **Audios capturados por Alexa**: Durante el tiempo en que el esposo supuestamente estaba viendo la película, se registraron voces masculinas y femeninas en los archivos de audio de Alexa, lo que sugiere la presencia de otras personas en la casa en ese momento.

Estas discrepancias plantean serias dudas sobre la veracidad del testimonio del esposo debido a los datos presentados anteriormente.
