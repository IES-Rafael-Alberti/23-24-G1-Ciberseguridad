# Informe Pericial Proyecto 9

# Índice

1. Juramento de Decir la verdad 
2. Glosario de palabras clave
3. Índice de figuras
4. Resumen ejecutivo
5. Introducción
5.1 Antecedentes
5.2 Objetivos
5.3 Fuentes de información
5.4 Adquisición de evidencias
6. Análisis
6.1 Herramientas usadas
6.2 Investigación
 6.2.1 Análisis de Raspberry Pi TV
 6.2.2 Análisis de Alexa
7. Limitaciones
8. Conclusiones
9. Anexo I. Sobre el perito
10. Anexo II. Fuentes de información
10.1 Smartphone de la victima
10.2 Smartphone del marido
10.3 Datos de Amazon Echo Alexa
10.4 Raspberry Pi (TV inteligente)
10.5 Tráfico de red del SmartHome
10.6 Informe de diagnóstico de Google OnHub
11. Anexo III Hallazgos
12. Referencias

# Juramento de Decir la verdad

Los peritos firmantes de este documento juramos solemnemente decir la verdad, toda la verdad y nada más que la verdad en este informe judicial. Prometemos que nuestras conclusiones y opiniones se basarán en los hechos, la evidencia y en nuestra experiencia profesional. Comprendemos la importancia de nuestro testimonio y la responsabilidad que conlleva en contribuir a la búsqueda de la justicia y la verdad en este asunto. Por lo tanto, nos comprometemos a cumplir con la ética y los estándares de nuestra profesión en todo momento.

# Glosario de palabras clave

- Caché: Es un componente de hardware o software que guarda datos para que las solicitudes futuras de esos datos se puedan atender con mayor rapidez.
- Alexa: Es un asistente virtual desarrollado por Amazon.
- Base de Datos: Es un conjunto de datos estructurados que pertenecen a un mismo contexto  y, en cuando a su función, se utiliza para administrar de forma electrónica grandes cantidades de información.

# Índice de figuras

1. Tabla: Comprobación hashes
2. Tabla: Herramientas usadas
3. Imagen: Captura videos emitidos TV Inteligente
4. Tabla: Videos y hora emitidos en TV Inteligente
5. Imagen: Dispositivo Alexa conectado a TV Inteligente
6. Imagen: Modelo de Alexa conectado a TV Inteligente
7. Imagen: Dispositivo Pulsera Xiaomi conectado a TV Inteligente
8. Imagen: Modelo Pulsera inteligente conectada a TV Inteligente
9. Imagen: Auriculares Bluetooth móvil del marido
10. Imagen: Modelo Auriculares Bluetooth móvil del marido
11. Imagen: History second page de Alexa
12. Imagen: History first page de Alexa
13. Tabla: DNI de los peritos
14. Tablas: Hashes contenido del móvil de la víctima
15. Tablas: Hashes contenido del móvil del marido de la víctima
16. Tabla: Hashes Alexa
17. Tabla: Hashes Raspberry Pi
18. Tabla: Hashes Tráfico de red de Smarthome
19. Tabla: Hashes Informe de Google OnHub
20. Tabla: Hallazgo 1
21. Tabla: Hallazgo 2

# Resumen ejecutivo

En respuesta a la presunta cuartada proporcionada por el esposo de la víctima, quien afirmó estar viendo una película en su habitación en el momento del crimen, se inició una investigación centrada en la televisión de la habitación. 

El análisis de estos videos reveló que uno de ellos no había sido reproducido completamente, sugiriendo que la película no había sido vista en su totalidad. Además, el esposo afirmó haber estado escuchando la película a través de auriculares mientras su esposa reproducía música.

Al examinar los archivos de caché de los dispositivos conectados por Bluetooth a la televisión, se identificaron dos dispositivos: uno correspondiente a Alexa y otro a una pulsera inteligente Xiaomi MI1A. Investigaciones adicionales revelaron que la televisión fue encendida a las 15:01 del día del crimen, contradiciendo el testimonio del esposo, quien afirmó haber estado viendo la película desde antes de la hora del crimen hasta el momento en que fue visto saliendo de la casa.

Los registros de audio de Alexa capturaron voces femeninas y masculinas durante el período en que el esposo afirmó estar viendo la película. Este descubrimiento sugiere discrepancias significativas en la coartada proporcionada por el esposo de la víctima.

# Introducción

## Antecedentes

El caso involucra el asesinato de una mujer en su residencia, reportado por su esposo y el conserje del edificio. A las 15:31 del 17 de julio de 2017, el conserje llamó al número de emergencia 112 para informar sobre el incidente. La policía llegó a la escena a las 15:40, encontrando a la víctima sin vida en el salón, aparentemente fallecida por múltiples puñaladas. El esposo declaró haber llegado a casa alrededor de las 15:00 y descubierto el cuerpo después de ver una película en el dormitorio, durante la cual llevaba auriculares. Colaboró con la investigación, pero no pudo proporcionar las contraseñas de los dispositivos electrónicos de la víctima.

## Objetivos

Los objetivos de este informe pericial son:

- Demostrar la veracidad de la cuartada del marido.
- Realizar un timeline con el fin de aclarar los hechos.
- Investigar los datos de los dispositivos proporcionados.

## Fuentes de información

Véase en el Anexo II. Fuentes de Información.

### Adquisición de evidencias

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

### Análisis de Raspberry Pi TV

Como el marido de la victima aseguraba estar viendo una película en la televisión de su habitación en los momentos de los hechos, decidimos comenzar la investigación con esta y comprobar que es cierto.

Haciendo una investigación sobre los ficheros de la adquisición de la televisión inteligente, encontramos que esta tiene un plugin de Youtube instalado, este nos genera una base de datos, en la cual podemos observar los vídeos que han sido vistos desde ella. Observando los videos, hemos podido encontrar los vistos el día del suceso.

Esta base de datos se encuentra en la ruta:

 `“\E001SmartTVMMC\home\osmc\.kodi\userdata\Database\MyVideos107.db”`

![Untitled](img/Untitled.png)

*Imagen: Captura videos emitidos TV Inteligente*

Podemos comprobar la zona horaria de la televisión en su información del sistema, una vez comprobada esta podemos afirmar que la ubicación es “América/New York“. Esta información podemos encontrarla en la ruta:

`“/etc/timezone”`

Una vez que conocemos la zona horaria en la que se encuentra la televisión, debemos realizar la conversión de estas horas, como aún no se encuentran en horario de verano, tendremos que sumar trece horas a las horas dadas, quedando como las mostradas en la siguiente tabla:

| plugin://plugin.video.youtube/play/?video_id=pF_rqav38Z4 | 2017-07-13 21:43:46 |
| --- | --- |
| plugin://plugin.video.youtube/play/?video_id=7WX0-O_ENlk | 2017-07-16 17:54:54 |
| plugin://plugin.video.youtube/play/?video_id=ibOskbTPZYE | 2017-07-17 15:07:30 |
| plugin://plugin.video.youtube/play/?video_id=VKfbVLmkQUs | 2017-07-17 15:19:37 |

*Tabla: Videos y hora emitidos en TV Inteligente*

Podemos comprobar que el video terminado en “VKfbVLmkQUs” no dispone playCount, lo cual nos indica que el video no se llegó a terminar de reproducir. 

El marido de la victima, aseguraba también estar haciendo uso de unos auriculares bluetooth para ver una película, ya que su esposa estaba escuchando música en la otra habitación.

Continuando la investigación de este dispositivo, encontramos en la cache los distintos dispositivos bluetooth que están vinculados a este, podemos observar que no se encuentra ningún dispositivo de auriculares bluetooth, esto podemos hallarlo en la siguiente ruta:

`“/var/lib/bluetooth/B8:27:EB:E6:8D:79/cache/74:C2:46:88:5D:09”`

![Untitled](img/Untitled%201.png)

*Imagen: Dispositivo Alexa conectado a TV Inteligente*

Este primero, si buscamos el nombre del dispositivo en Google encontramos que corresponde al dispositivo Alexa.

![Untitled](img/Untitled%202.png)

*Imagen: Modelo de Alexa conectado a TV Inteligente*

El otro dispositivo conectado en la televisión sería:

`“/var/lib/bluetooth/B8:27:EB:E6:8D:79/cache/88:0F:10:F6:C8:B7"`

![Untitled](img/Untitled%203.png)

*Imagen: Dispositivo Pulsera Xiaomi conectado a TV Inteligente*

Este correspondería al siguiente dispositivo Mi1A Band.

![Untitled](img/Untitled%204.png)

*Imagen: Modelo Pulsera inteligente conectada a TV Inteligente*

Analizando la información del dispositivo móvil del marido, se han encontrado los dispositivos bluetooth que han sido conectados a este. Hemos podido confirmar que estos no se han encontrado conectados a la televisión inteligente.

![Untitled](img/Untitled%205.png)

*Imagen: Auriculares Bluetooth móvil del marido*

El nombre de este dispositivo, si lo buscamos en google nos confirma que son los auriculares bluetooth.

![Untitled](img/Untitled%206.png)

*Imagen: Modelo Auriculares Bluetooth móvil del marido*

### Análisis de Alexa

Haciendo una investigación sobre las adquisiciones proporcionadas por las autoridades, podemos observar que se ha hecho uso del dispositivo el día 17/07/2017, mientras que el testimonio del marido indica que llegaron con exactitud al domicilio sobre las 15:00.

Este vestigio podemos encontrarla en la ruta:

`“Alexa\history second page.png”`

![Untitled](img/Untitled%207.png)

*Imagen: History second page de Alexa*

Viendo el historial de comandos de Alexa, encontramos que la televisión se encendió a las 15:01 del día 17/07/2017.

Esto podemos encontrarlo en la ruta:

`“Alexa\history first page.png”`

![Untitled](img/Untitled%208.png)

Mientras que el testimonio del marido nos indica que el está viendo una película (desde las 15:01 hasta que el conserje lo ve saliendo de casa gritando 15:21) se escucha en los registros de audio de Alexa la voz de la mujer y la voz de un varón. 

Este registro de audio podemos encontrarlo en la ruta:

`“\Alexa\8.wav”`

Este audio escuchado en Alexa, corresponde con este comando de voz encontrado en el historial del mismo dispositivo.

![Untitled](img/Untitled%209.png)

*Imagen: History first page de Alexa*

# Limitaciones

Se hace constar que a lo largo del proceso de análisis de cada adquisición proporcionada por la policía, no se han encontrado alguna limitación de relevancia que hayan dificultado la misma o la interpretación de los datos. Se han empleado los recursos y metodologías adecuados para examinar de manera meticulosa cada adquisición, asegurando así la integridad y exhaustividad de la investigación.

# Conclusiones

Se ha demostrado que el testimonio proporcionado por el esposo de la víctima, que afirmaba estar viendo una película en el momento del crimen, no parece ser sólida. Varias discrepancias surgieron durante la investigación:

1. **La reproducción incompleta del video**: Uno de los videos en la base de datos de la televisión no había sido reproducido por completo, lo que sugiere que la película no fue vista en su totalidad como afirmaba el esposo.
2. **Utilización de auriculares.** Según el esposo estaba usando auriculares bluetooth a la hora de ver la película, ya que la victima estaba reproduciendo música desde el dispositivo Alexa. No se hallaron indicios del uso de los mismos, por lo cual es otra discrepancia en su testimonio.
3. **Hora de entrada a la casa**: La discrepancia en los registros de Alexa, donde se muestra un comando de encendido a las 14:45, contradice directamente el testimonio del esposo, quien afirma que llegó a casa a las 15:00.
4. **Audios capturados por Alexa**: Durante el tiempo en que el esposo supuestamente estaba viendo la película, se registraron voces masculinas y femeninas en los archivos de audio de Alexa, lo que sugiere la presencia de otras personas en la casa en ese momento.

Estas discrepancias plantean serias dudas sobre la veracidad del testimonio del esposo debido a los datos presentados anteriormente.

# Anexo I. Sobre el perito

El equipo de peritos forenses que ha colaborado en la elaboración de este informe se compone de cuatro profesionales altamente capacitados y especializados en distintas áreas de la ciencia forense. Cada uno de ellos aporta una perspectiva única y una experiencia invaluable en su campo de especialización, lo que ha permitido un análisis exhaustivo y multidisciplinario de la evidencia presentada en este caso.

El primer perito, Eduardo de Motrico Fedriani, es especialista en ASIR, con una trayectoria destacada en la aplicación de técnicas y metodologías avanzadas para la recolección, análisis e interpretación de evidencia física.

El segundo perito, Adrián Campó Merlo, es un especialista destacado en análisis forense informático, con experiencia en la identificación de evidencias digitales en casos de delitos cibernéticos. Reconocido por su habilidad en la recuperación de datos y el análisis de dispositivos móviles.

El tercer perito, Rafael Valverde Cros, es un especialista en DAM, ASIR y Ciberseguridad, con una sólida formación en el análisis de la administración y gestión de sistemas informáticos en red, amplia experiencia análisis forense y análisis de la administración y gestión de aplicaciones móviles.

Por último, el cuarto perito, Pedro Luis Borrego Vargas, aporta su experiencia en el análisis forense, con un enfoque en la reconstrucción de escenas del crimen y la elaboración de informes técnicos detallados.

Juntos, este equipo de peritos ha trabajado de manera colaborativa y coordinada para ofrecer un análisis integral y objetivo de la evidencia presentada en este caso, garantizando la fiabilidad y la solidez de las conclusiones alcanzadas. Su labor profesional y su compromiso con la excelencia han sido fundamentales para el desarrollo de este informe pericial.

Los peritos que se han participado en la investigación:

| Nombre y Apellido | DNI | Dirección | Código Postal | Provincia | Móvil | Firma |
| --- | --- | --- | --- | --- | --- | --- |
| Adrián Campó Merlo | 16762107Y | c/ XXXX | 11011 | Cádiz | XXXXXXXXX | Adrián Campó Merlo |
| Rafael Valverde Cros | 50038156T | c/ XXXX | 11100 | Cádiz | XXXXXXXXX | Rafael Valverde Cros |
| Pedro Luis Borrego Vargas | 53234808C | c/ XXXX | 11100 | Cádiz | XXXXXXXXX | Pedro Luis Borrego Vargas |
| Eduardo de Motrico Fedriani | 76650130P | c/ XXXX | 11100 | Cádiz | XXXXXXXXX | Eduardo de Motrico Fedriani |

# Anexo II. Fuentes de información

## Smartphone de la victima

### SHV-E250L_Physical_20170717_CACHE

| Adquisición | SHV-E250L_Physical_20170717_CACHE.mdf |
| --- | --- |
| Tamaño (Bytes) | 1.342.177.525 |
| HASH SHA-256 | efcfab5069175a61a3985392dcd2ba1895d851b33c60ddf4a73f5bd01496cda6 |

### SHV-E250L_Physical_20170717_EFS

| Adquisición | SHV-E250L_Physical_20170717_EFS.mdf |
| --- | --- |
| Tamaño (Bytes) | 20.971.761
 |
| HASH SHA-256 | befae2ca8da161dd115ebf29a81611cb7a1879563befdd67919cb6b859845aa3 |

### SHV-E250L_Physical_20170717_HIDDEN

| Adquisición | SHV-E250L_Physical_20170717_HIDDEN.mdf |
| --- | --- |
| Tamaño (Bytes) | 587.202.807 |
| HASH SHA-256 | 01e9df3c7bd977e67320e9ab6643c696a63258bd62c63a5548304d640f79c277 |

### SHV-E250L_Physical_20170717_RADIO

| Adquisición | SHV-E250L_Physical_20170717_RADIO.mdf |
| --- | --- |
| Tamaño (Bytes) | 92.274.933 |
| HASH SHA-256 | 0694e0af93ffef502891473833e5d089136062e86c6744a8b6be087c0deff944 |

### SHV-E250L_Physical_20170717_SYSTEM

| Adquisición | SHV-E250L_Physical_20170717_SYSTEM.mdf |
| --- | --- |
| Tamaño (Bytes) | 2.516.582.647
 |
| HASH SHA-256 | 5c36128d09fdc56500ff4831609904d32a6a62c032e976ecfda77d4b3853a68e |

### SHV-E250L_Physical_20170717_TOMBSTONES

| Adquisición | SHV-E250L_Physical_20170717_TOMBSTONES.mdf |
| --- | --- |
| Tamaño (Bytes) | 268.435.711 |
| HASH SHA-256 | 34cc491cc501395871947b98f888c9413d77f3a16eca43a911716ad3a36eeb07 |

### SHV-E250L_Physical_20170717_USERDATA

| Adquisición | SHV-E250L_Physical_20170717_USERDATA.mdf |
| --- | --- |
| Tamaño (Bytes) | 26.377.978.107  |
| HASH SHA-256 | 1640a9e0ab2d3f235c4d1280fdc1c12b5998648fc942b12012de393d0a74ea65 |

## Smartphone del marido

### SHV-E250L_Physical_20170717_CACHE

| Adquisición | SHV-E250L_Physical_20170717_CACHE.mdf |
| --- | --- |
| Tamaño (Bytes) | 1.342.177.525 |
| HASH SHA-256 | 260a0c26ba37da4c432864b55011682673848e29a40a0ed58b6fe05c42f8d649 |

### SHV-E250L_Physical_20170717_EFS

| Adquisición | SHV-E250L_Physical_20170717_EFS.mdf |
| --- | --- |
| Tamaño (Bytes) | 20.971.761 |
| HASH SHA-256 | b5edeacf9433e743c9bf5233868f61a921e2d7ad9a02ff745affdac3c4834955 |

### SHV-E250L_Physical_20170717_HIDDEN

| Adquisición | SHV-E250L_Physical_20170717_HIDDEN.mdf |
| --- | --- |
| Tamaño (Bytes) | 587.202.807 |
| HASH SHA-256 | 12d1ba5aceb78efa65a8b7af1259441ff0be0de3478b8314300920cbc37e25cc |

### SHV-E250L_Physical_20170717_RADIO

| Adquisición | SHV-E250L_Physical_20170717_RADIO.mdf |
| --- | --- |
| Tamaño (Bytes) | 92.274.933 |
| HASH SHA-256 | 2b61618e80c707db8b7f35881e289175fb618570b547209fa9812ce3a3325317 |

### SHV-E250L_Physical_20170717_SYSTEM

| Adquisición | SHV-E250L_Physical_20170717_SYSTEM.mdf |
| --- | --- |
| Tamaño (Bytes) | 2.516.582.647 |
| HASH SHA-256 | 9c53cfa7063eeb08f7666626d5d883dd8283509eeee6d3b0057eecfa20669b17 |

### SHV-E250L_Physical_20170717_TOMBSTONES

| Adquisición | SHV-E250L_Physical_20170717_TOMBSTONES.mdf |
| --- | --- |
| Tamaño (Bytes) | 268.435.711 |
| HASH SHA-256 | 14194c53217e71e118f2245e7364c3ec7b04e9c6bc7a9f1071e1e920b009459b |

### SHV-E250L_Physical_20170717_USERDATA

| Adquisición | SHV-E250L_Physical_20170717_USERDATA.mdf |
| --- | --- |
| Tamaño (Bytes) | 26.377.978.107 |
| HASH SHA-256 | ae38cbb62233cadd82deb0660e8ae70ea7f0fce67630a498fed88daac9160a6f |

## Datos de Amazon Echo Alexa

| Adquisición | Alexa.zip |
| --- | --- |
| Tamaño (Bytes) | 3.005.548 |
| HASH SHA-256 | 6c09813eea5475dc0011c547e7fb774cfbd7216cafdeeb9a8308306046c14edf |

## Raspberry Pi (TV inteligente)

| Adquisición | TV_inteligente.zip |
| --- | --- |
| Tamaño (Bytes) | 730.383.971 |
| HASH SHA-256 | 5423ea3f60d4ad0874346d3ba31c8783e5f2ce4b15b261ba0085e07f11e650e6 |

## Tráfico de red del SmartHome

| Adquisición | tráfico_red.zip |
| --- | --- |
| Tamaño (Bytes) | 249.105 |
| HASH SHA-256 | 52fecbe94fc4f1ed61d9f8740fda0a1f8562f50cc7439fdcf67be3ca990f3359 |

## Informe de diagnóstico de Google OnHub

| Adquisición | InformeDiagnosticoOnHub |
| --- | --- |
| Tamaño (Bytes) | 339.578 |
| HASH SHA-256 | 4767513d714698afcd7506dd2304528a8db8243e2dff1be6e1ede591d0d19f83 |

# Anexo III Hallazgos

Hallazgo 1. 

| Ruta | Myvideos107.db |
| --- | --- |
| Tamaño (Bytes) | 376.832 |
| HASH SHA-256 | c9d82770546819b1020077c2064797fbb9e9c16ff7dffba60c03888713666ded |

Hallazgo 2.

| Ruta | /var/lib/bluetooth/B8:27:EB:E6:8D:79/cache/74:C2:46:88:5D:09 |
| --- | --- |
| Tamaño (Bytes) |  |
| HASH SHA-256 | 219f61b78041f1e13904309c4b96f6911c78c659f543e05a4f253716894ec4ba |

Hallazgo 3.

| Ruta | /var/lib/bluetooth/B8:27:EB:E6:8D:79/cache/88:0F:10:F6:C8:B7 |
| --- | --- |
| Tamaño (Bytes) |  |
| HASH SHA-256 | e75492d572f33352f57e0558662abf8f501c8d6c3724343b98382ed9200a88f6 |

Hallazgo 4.

| Ruta | 8.wav |
| --- | --- |
| Tamaño (Bytes) | 186.284 bytes |
| HASH SHA-256 | 7d66d7102cfdae7b6f792fd71f1fbd152620360bd241698ba50ac21b61ac4d80 |

Hallazgo 5.

| Ruta | history second page.png |
| --- | --- |
| Tamaño (Bytes) |  |
| HASH SHA-256 | db61c918114ee0bbe816b414868822aebacf82f789b1ccc9ee195cf05b2371f7 |

# Referencias

- [https://www.bketl.es/wp-content/uploads/2022/09/Ejemplo-Informe-Pericial.pdf](https://www.bketl.es/wp-content/uploads/2022/09/Ejemplo-Informe-Pericial.pdf)
