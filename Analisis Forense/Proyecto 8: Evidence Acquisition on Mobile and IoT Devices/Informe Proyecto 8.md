# Informe Proyecto 8

## Índice
1. [Resumen Ejecutivo](#resumen)  
2. [Investigación Teórica](#investigacion)  
  2.1 [Metodología.](#metodologia)  
3. [Práctica de Adquisición](#adquisicion)  
  3.1 [Dispositivo Móvil](#movil)  
  3.2 [Uso de la herramienta Andriller.](#andriller)  
  3.3 [Uso de la herramienta Android Debug Bridge](#debugbridge)  
4. [Evaluación de Herramientas y Métodos](#herramientas)  
   4.1 [Herramientas utilizadas:](#utilizadas)  
   4.2 [Comparación de las herramientas:](#comparacion)  
4. [Consideraciones Legales](#legales)
5. [Conclusiones](#conclusiones)

# 1. Resumen Ejecutivo<div id='resumen' />

Se llevó a cabo un proceso de análisis forense utilizando un dispositivo móvil antiguo, específicamente un Xiaomi RedNote 7. Para habilitar este análisis, se activó el modo desarrollador y la depuración USB en el dispositivo. Además, se utilizó una combinación de herramientas como Andriller y ADB para realizar una copia de seguridad del móvil en un ordenador. Este procedimiento permitió obtener información detallada sobre las aplicaciones previamente instaladas en el dispositivo, otorgando así un panorama completo de los datos asociados a estas aplicaciones que se investigaron.

# 2. Investigación Teórica<div id='investigacion' />

## Metodología.<div id='metodologia' />

A continuación, se explica la metodología que ha seguido el perito para adquirir y analizar
las evidencias:

### Planificación y Preparación

Antes de iniciar la investigación, es fundamental identificar los dispositivos móviles involucrados, preparar la documentación necesaria, como la cadena de custodia y los permisos legales, y seleccionar las herramientas forenses adecuadas.

### Adquisición de evidencia digital

1. La captura de la adquisición debe ser lo más precisa posible.
2. Detallar las fechas y horas a la que se realizó la extracción.
3. Intentar no sobrescribir las pruebas instalando software, si no es estrictamente
necesario.
4. Recoger las evidencias en orden de volatilidad:
5. Transparencia: A la hora de realizar la adquisición tendremos que explicar
detalladamente el proceso que hemos seguido para que pueda ser totalmente
reproducible.

### Preservación y almacenamiento de evidencia

A la hora de almacenamiento, se documentará:
- Dónde, cuándo y quién descubrió y recolectó la evidencia.
-  Dónde, cuándo y quién manejó la evidencia.
-  Quién ha custodiado la evidencia, cuánto tiempo y cómo la ha almacenado
-  Si se ha cambiado de custodia indicar a quien, que fecha y hora y comprobar que los
hashes coinciden
-  Dónde almacenarlo. Dependiendo del dispositivo tendremos que almacenarlo de una
u otra forma, por ejemplo, si es un dispositivo portátil tendremos que custodiarlo en
una bolsa de Faraday para que no pueda ser comprometido por las redes móviles.

### Análisis de evidencias

Se llevarán a cabo una serie de procesos y tareas que intentarán dar respuesta a preguntas relacionadas con una intrusión, como su origen, la lista de sistemas afectados, los métodos usados, etc. Todos estos procesos y tareas deberán realizarse de forma metódica, auditable, repetible y defendible.

### Presentación de resultados

La presentación de los hallazgos se realiza a través de un informe forense completo que incluye evidencia digital y capturas de pantalla. Es esencial comunicar los resultados de manera profesional a las partes interesadas, participando en procesos legales según sea necesario.

# 3. Práctica de Adquisición<div id='adquisicion' />

## Dispositivo Móvil<div id='movil' />

Lo primero que deberemos realizar es activar el modo “depuración USB” en nuestro dispositivo móvil. Para ello nos dirigimos a apartado “Sobre el teléfono” en el menú “Ajustes” del dispositivo.

Una vez dentro, deberemos dar repetidos toques sobre la versión de MIUI. Nos aparecerá una cuenta atrás de toques que deberemos dar para habilitar el modo desarrollador en el dispositivo.

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/11.png)

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/2.png)

Una vez activo el modo desarrollador, deberemos dirigirnos desde el menú “Ajustes” al apartado “Ajustes adicionales”. Dentro de estos, deberemos dirigirnos a “Opciones de desarrollador”.

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/3.png)

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/4.png)

Ahora dentro de este menú, activaremos el modo “Depuración USB”. Este modo nos permite pasar información directamente desde el ordenador al teléfono y viceversa y nos permitirá hacer la adquisición del dispositivo. Se recomienda tener el móvil “rooteado” para poder acceder a toda la información del móvil.

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/5.png)

### Uso de la herramienta Andriller.<div id='andriller' />

El primer paso será descargarnos la herramienta, esta es opensource y podemos encontrarla en el siguiente repositorio de github:

[`https://github.com/den4uk/andriller`](https://github.com/den4uk/andriller)

Para esta herramienta vamos a necesitar dos dependencias en nuestro sistema, adb y python. Con la descarga del repositorio al completo, ya tenemos el binario de adb, así que solo faltaría instalar python si no lo tenemos preinstalado con el equipo.

Una vez todas las dependencias estén en el equipo, debemos activar el entorno virtual de en windows, esto lo hacemos mediante el siguiente comando:

`.\env\Scripts\activate`

Ahora lanzaremos nuestro programa desde la consola de comandos con el siguiente comando:

`python -m andriller`

Esto nos abrirá la interfaz gráfica de la aplicación, en ella podemos seleccionar entre diversas funcionalidades, entre la extracción de datos a través de USB, parsear carpetas, archivos .tar, ficheros con extensión .ab, entre muchas otras cosas.

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/Untitled%205.png)

En el menú principal de “extracción USB” podemos hacer la comprobación de que el dispositivo USB conectado es al que queremos hacer la adquisición mediante el botón “check” (2). También deberemos elegir la carpeta en la cual vamos a guardar el resultado, mediante el botón “Output” (1). Ahora deberemos elegir lo que vamos a extraer, si vamos a usar el método AB ignorando el root, ya que el dispositivo no está rooteado, al igual que si queremos extraer la carpeta de almacenamiento compartida (4). Una vez tengamos todo listo, pulsaremos el botón “Extract” (3) para comenzar la adquisición.

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/Untitled%206.png)

Cuando comencemos la adquisición, nos dará un aviso de que debemos confirmar la copia de seguridad del sistema desde nuestro móvil.

![warning.png](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/warning.png)

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/6.png)

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/Untitled%208.png)

Una vez acabada la adquisición, nos abrirá una página en nuestro navegador con los detalles de la adquisición. Podemos navegar a los dos hipervínculos de abajo para inspeccionar dichos elementos.

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/Untitled%209.png)

Yéndonos a la carpeta resultante de la adquisición, podemos ver los archivos que nos genera de la adquisición.

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/Untitled%2010.png)

Dentro de la carpeta “data”, tenemos toda la información del teléfono, tanto la carpeta compartida, donde está toda la información de las aplicaciones de terceros, como la carpeta “data/apps” que contiene la información de Android.

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/Untitled%2011.png)

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/Untitled%2012.png)

### Uso de la herramienta Android Debug Bridge<div id='debugbridge' />

El uso de esta herramienta es mediante la interfaz de comando del equipo. Lo primero que deberemos hacer es descargarnos la herramienta desde la web oficial de android, podemos encontrarla entre las herramientas  del paquete SDK:

[`https://developer.android.com/tools/releases/platform-tools?hl=es-419`](https://developer.android.com/tools/releases/platform-tools?hl=es-419)

Una vez tenemos las herramientas en nuestro equipo, nos dirigimos a la carpeta en la cual la tenemos descargada desde nuestra consola de comandos.

Esta herramienta consta de un archivo ejecutable (.exe) y de dos bibliotecas (.dll) para su utilización.

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/Untitled%2013.png)

Con el comando adb devices, podemos ver los dispositivos conectados en nuestro equipo, estos serán mostrados por el ID del mismo. Es posible que la primera vez que conectemos el dispositivo desde este método al equipo, nos pida una autorización desde el mismo para poder entrar desde el modo depuración USB.

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/Untitled%2014.png)

Con el siguiente comando realizaremos una copia de seguridad de nuestro sistema Android, esto debería de resultarnos en un archivo .ab, con la información pertinente, en este caso, hemos añadido que nos incluya los archivos apk de las aplicaciones (-apk), los archivos de configuración del sistema (-system) y todos los datos de las aplicaciones, no solo las que tienen activado el permiso de copia de seguridad (-all).

Como en el caso de la herramienta anterior, también se nos pide desde el dispositivo una confirmación del inicio de la copia de seguridad.

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/Untitled%2015.png)

Podemos ver el archivo resultante de la adquisición, si parseamos este archivo, podemos ver el backup creado y los archivos resultante de este mismo son los siguientes:

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/Untitled%2016.png)

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/Untitled%2017.png)

Tenemos otro método de extracción de datos con la herramienta ADB, este caso es con el uso del comando “pull”, la función de este comando es realizar una copia de los archivos a directorios a nuestro equipo. 

Respecto a este comando, no podremos traernos carpetas del sistema si no disponemos de un móvil rooteado, en este caso vamos a extraer la carpeta “sdcard”, la cual contiene los archivos compartidos del dispositivo.

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/Untitled%2018.png)

El error encontrado en este tipo de adquisición, es que cuando encuentra una carpeta con un carácter especial (siempre da fallo en la misma carpeta, puesto tiene en la ruta el carácter “:”) 

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/Untitled%2019.png)

Puesto que la carpeta Andriod, es la carpeta realizada con la adquisición del backup, se ha creado un script para lanzarlo por la powershell de windows en el cual haremos un pull de todas las carpetas exceptuando esta que nos da el fallo:

En este solo debemos modificar la ruta en la cual tenemos guardada nuestro ejecutable de ADB, además de indicar la ruta en la cual queremos guardar la adquisición.

Este método ignora los fallos y continua haciendo la adquisición de todos los directorios del dispositivo.

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/Untitled%2020.png)

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/Untitled%2021.png)

En la carpeta resultante, podemos observar que se nos genera todas las carpetas adquiridas desde el dispositivo.

![Untitled](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%208%3A%20Evidence%20Acquisition%20on%20Mobile%20and%20IoT%20Devices/img/Untitled%2022.png)

# 4. Evaluación de Herramientas y Métodos<div id='herramientas' />

## Herramientas utilizadas:<div id='utilizadas' />

Android Debug Bridge (ADB):

| Nombre | Android Debug Bridge |
| --- | --- |
| Versión: | 1.5 |
| Página web | https://developer.android.com/tools/adb?hl=es-419 |

Andriller

| Nombre | Andriller |
| --- | --- |
| Versión: | 3.6.3 |
| Página web | https://github.com/den4uk/andriller |

## Comparación de las herramientas:<div id='comparacion' />

Respecto al uso de la herramienta Andriller, es una herramienta muy fácil e intuitiva de usar, su interfaz gráfica simplifica mucho su uso, además, dar la opción de poder extraer el AB ignorando el root nos ayuda mucho a hacer una adquisición sin necesidad de tener el teléfono rooteado.

Otro aspecto a tener en cuenta es su compatibilidad con una amplia variedad de dispositivos Andriod, siendo posible hacer adquisiciones de dispositivos tanto antiguos como nuevos, aunque estos últimos dificultan un poco más la adquisición por las medidas de seguridad que tienen ciertos dispositivos.

Respecto a la herramienta ADB, no es tan fácil e intuitiva como la otra probada anteriormente. También nos ha dado muchos más problemas a la hora de hacer la adquisición, ya que al no tener el móvil rooteado no nos ha dejado hacer una copia limpia del dispositivo, además de los inconvenientes puestos a la hora de hacer el pull hacia nuestro equipo. Para la realización del backup del Android si que es útil, ya que lo ha realizado sin ningún tipo de inconveniente. 

# 5. Consideraciones Legales<div id='legales' />

En el marco legal, la adquisición de datos de dispositivos móviles e IoT debe cumplir con las leyes de privacidad y protección de datos, como el Reglamento General de Protección de Datos (GDPR) en la Unión Europea o la Ley de Privacidad del Consumidor de California (CCPA) en los EEUU. Además, en situaciones de investigación criminal, la adquisición de datos requiere órdenes judiciales o autorizaciones legales. Para garantizar la integridad y autenticidad de las evidencias, es fundamental mantener una cadena de custodia detallada, desde la recopilación hasta el análisis, para demostrar que los datos no han sido alterados o manipulados. Aparte, hacer la adquisición puede involucrar dispositivos y datos ubicados en diferentes jurisdicciones, lo que plantea desafíos legales adicionales en términos de jurisdicción relevante y cómo se aplican a la adquisición y uso de evidencias. Finalmente, los datos almacenados en dispositivos móviles e IoT pueden estar sujetos a derechos de propiedad intelectual y otros derechos de propiedad, lo que requiere un enfoque cuidadoso en la adquisición y uso de datos para evitar violaciones de derechos.

Además, se debe considerar algunos temas éticos relacionados, siendo crucial obtener el consentimiento informado de los usuarios antes de recopilar datos necesarios, emplear la minimización de datos para proteger la privacidad del usuario, ser transparente y responsable en el uso de los datos adquiridos, garantizar la equidad y evitar la discriminación de cualquier tipo, abordar sesgos y asegurar la imparcialidad en los análisis, respetar la autonomía y dignidad de las personas, proteger a grupos vulnerables y promover un uso responsable de la tecnología para maximizar beneficios sociales y minimizar riesgos relacionados.

# 6. Conclusiones<div id='conclusiones' />

Para concluir el informe, esta metodología de adquisición y análisis de datos de dispositivos IoT y de móviles, es indispensable para poder realizar nuestra labor, dado que nos permite adquirir y revisar todo el contenido del dispositivo, además de una comprensión bastante útil acerca de las diversas herramientas disponibles para realizar dicha adquisición, dado que cada una posee sus propias ventajas y desafíos a la hora de su uso adecuado para realizar el trabajo.

También resulta importante el tener en cuenta todas las consideraciones posibles, tanto legales como éticas, para su realización correcta y dentro del marco de la ley, haciendo que en su conjunto, sea necesario para poder tomar toda acción sin vulnerar ningún derecho del usuario y su privacidad, además de poder realizar nuestro trabajo sin impedimentos.
