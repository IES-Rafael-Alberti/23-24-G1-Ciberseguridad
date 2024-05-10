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

