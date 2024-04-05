# Informe Técnico proyecto 3

# 1. Resumen Ejecutivo

El análisis forense del disco duro revela una serie de irregularidades en el comportamiento de Richard Warner. Se encontraron indicios de violaciones a las políticas de seguridad de la empresa, como el uso de dispositivos USB no autorizados y la instalación de navegadores web no permitidos en su equipo de trabajo. Además, se descubrió que Warner había mantenido comunicación con una presunta empresa competidora, a la cual proporcionó información confidencial de la empresa, incluyendo archivos de proyectos y datos sensibles, a cambio de beneficios económicos. 

## 1.1 Línea temporal

Hemos detallado en una pequeña línea temporal toda la actividad ilícita que estaba realizando el usuario Richard.

![Linea Temporal.png](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Linea_Temporal.png)

# 2. Introducción

## 2.2 Antecedentes

InnovaTech Solutions, una empresa de desarrollo de software conocida por sus proyectos innovadores como "Ligueitor" y "Social Query", enfrenta rumores de inestabilidad financiera y despidos inminentes. En medio de esta incertidumbre, Richard Eduardo Warner, un empleado ejemplar hasta ahora, ha dejado la empresa después de una confrontación con su jefe. Se sospecha que su comportamiento inusual podría estar relacionado con acciones perjudiciales para la empresa, por lo que se realizará un análisis forense de su disco duro en busca de evidencia de mal uso de recursos o filtración de información confidencial. El objetivo es proteger los activos y la integridad de la empresa.

## 2.3 Objetivos

Los objetivos de este informe técnicos son:

1. Verificar la integridad de la imagen del disco mediante la comparación de hashes para asegurar su autenticidad.
2. Crear una línea de tiempo detallada de las actividades de Richard en el dispositivo, registrando sus inicios de sesión y el uso de dispositivos USB.
3. Detectar cualquier actividad no autorizada, como el mal uso de recursos de la empresa o la extracción de datos confidenciales.
4. Documentar y presentar de manera clara y concisa las conclusiones del análisis.

## 2.4 Alcance

Análisis completo de la imagen del disco del equipo de Richard en busca de cualquier uso indebido de los recursos de la empresa o de filtración de información confidencial.

# 3. Información analizada

| Adquisición | traidor.img |
| --- | --- |
| Tamaño (Bytes) | 53687091200 |
| HASH MD5 | DFDFBA2231E3FA409676B1B737474288 |
| HASH SHA1 | F476A81089A10F9D5393AA8C2F8BBCCDB87F7D3C |
| HASH SHA256 | 66D6EE7A61EA7A986E8F6BB54B9986F79D95B5A0278BEF86678ED42ACE320D9B |

# 4. Análisis

Antes de comenzar con el análisis vamos a realizar la comprobación de hashes para verificar que la evidencia no ha sido alterada.

### 4.1 Comparación de hashes

Comenzaremos con comprobar que los hashes de la evidencia coinciden con las proporcionadas por Alan el cuál adquirió y preservo la evidencia, del departamento de sistemas, quien proporcionó los siguientes hashes:

- MD5: dfdfba2231e3fa409676b1b737474208
- SHA-1: f476a81089a10f9d5393aa8c2f8bbccdb87f7d3c
- SHA-256: 66d6ee7a61ea7a986e8f6bb54b9986f79d95b5a0278bef86678ed42ace320d96

Verificamos si esta información es correcta o no:

| Criptografía | HASH | Prueba |
| --- | --- | --- |
| MD5 | DFDFBA2231E3FA409676B1B737474288 | [Ver en el anexo de imagenes. Imagen 1](Anexos.md###Anexo%de%Imágenes) |
| SHA1 | F476A81089A10F9D5393AA8C2F8BBCCDB87F7D3C | [Ver en el anexo de imagenes. Imagen 2](#imagen2) |
| SHA256 | 66D6EE7A61EA7A986E8F6BB54B9986F79D95B5A0278BEF86678ED42ACE320D9B | [Ver en el anexo de imagenes. Imagen 3](#imagen3) |

Como podemos apreciar, los hashes recibidos por parte de Alan no coinciden con los generados por nosotros.

### 4.2 Análisis de la imagen forense

Comenzaremos con detallar la información del equipo al cual vamos a realizar el análisis.

Para averiguar esta información tendremos que consultar dos registros del sistema, en este caso el registro SOFTWARE para la versión del sistema y el registro SYSTEM para el nombre del equipo. Ambos se encuentran en la misma ruta:

C:/Windows/System32/config/SOFTWARE

C:/Windows/System32/config/SYSTEM

Haciendo uso de la herramienta WRR (Windows Registry Recovery) podemos visualizar el contenido de estos archivos.

Primero podemos ver el nombre del equipo en el registro SYSTEM.

[Ver en el anexo de imagenes. Imagen 4](#imagen4)  

Ahora el sistema operativo que esta utilizando usando el registro SOFTWARE.

[Ver en el anexo de imagenes. Imagen 5](#imagen5)  

A continuación, averiguaremos si existe algún usuario que pertenezca a Richard, esto lo podremos  localizar en el registro SAM del sistema que se encuentra en la raíz. C:/Windows/System32/config/SAM

[Ver en el anexo de imagenes. Imagen 6](#imagen6)  

Como podemos comprobar, si que existe dicho usuario, el cual se llama como el presunto sospechoso.

También podemos determinar cierta información valiosa, como la última vez que este usuario inició sesión en el equipo.

[Ver en el anexo de imagenes. Imagen 7](#imagen7)  

En este caso, el ultimo inicio de sesión del usuario correspondiente a Richard fue el 22 de Febrero de 2023 a las 13:55:18.

Realizando búsquedas de alguna actividad sospechosa por parte del usuario, podemos identificar que se saltó las políticas de la empresa introduciendo un dispositivo USB en su equipo.

Dicho dispositivo USB es un pendrive Kingston DataTraveler 3.0 USB Device.

Esta información la conseguimos gracias al registro SYSTEM y utilizando una vez más la herramienta WRR.

[Ver en el anexo de imagenes. Imagen 8](#imagen8)  

Para encontrar la fecha y hora exacta de la conexión de este dispositivo tendremos que utilizar otra herramienta llamada Registry Explorer, volver a abrir el registro SYSTEM y ver los detalles técnicos del dispositivo en la siguiente ruta:

\SYSTEM\CurrentControlSet\Enum\STORAGE\_??USBSTOR#Disk&Ven_Kingston&Prod_DataTraveler_3.0&Rev#002618525C8EF0B0E87D2853&0#{53f56307-b6bf-11d0-94f2-00a0c91efb8b}

La fecha y hora exacta a la que se conectó el dispositivo USB fue el 22 de Febrero de 2023 a las  0:27:42.

[Ver en el anexo de imagenes. Imagen 9](#imagen9)  

Podemos apreciar que Richard, también se saltó las políticas de la empresa con respecto al navegador web, ya que estas solo permiten navegadores webs distribuidos por Microsoft.

Observamos que tiene instalado otro navegador web visualizando con WRR en el registro SOFTWARE, Mozilla Firefox, el cual es el que estaba utilizando para realizar actividades fuera de sus labores en el trabajo.

[Ver en el anexo de imagenes. Imagen 10](#imagen10)  

Verificaremos la fecha y la hora a la cual se instaló el navegador haciendo uso de la herramienta Registry Explorer y volviendo a abrir el registro SOFTWARE. Dicha información se encuentra en los detalles técnicos de la ruta:

 ROOT\Mozilla\Mozilla Firefox 

[Ver en el anexo de imagenes. Imagen 11](#imagen11)  

Podemos comprobar el historial de navegación haciendo uso de la herramienta DBBrowser for SQLite, abriendo el archivo places.qlite que contiene el historial de navegación del navegador Mozilla Firefox. Este archivo podemos encontrarlo en la siguiente ruta:

C://Users/Richard/AppData/Roaming/Mozilla/Firefox/Profiles/mt13hmmn.default-release 

[Ver en el anexo de Evidencias. Evidencia 1](#evidencia1)  
Al registrar el historial de navegación, hemos visto que Richard ha estado buscando durante el transcurso de la jornada laboral diverso contenido no autorizado, como películas, vídeos, páginas web de apuestas, etc.

[Ver en el anexo de imagenes. Imagen 12](#imagen12)  
[Ver en el anexo de imagenes. Imagen 13](#imagen13)  
[Ver en el anexo de imagenes. Imagen 14](#imagen14)  
[Ver en el anexo de imagenes. Imagen 15](#imagen15)  
[Ver en el anexo de imagenes. Imagen 16](#imagen16)  

También podemos ver que aunque tiene varios navegadores web instalados en el equipo, el único habilitado para que se inicie al ejecutarse el equipo es Opera.

Esto podemos descubrirlo desde los registros del usuario, en el archivo NT.USERDAT, ubicado en la ruta:

\Software\Microsoft\Windows\CurrentVersion\Run

[Ver en el anexo de imagenes. Imagen 17](#imagen17)  

En el historial de este navegador, podemos encontrar múltiples búsquedas de canciones en youtube, a parte de eso, también realiza constantes búsquedas de noticias deportivas, ya sea en el portal marca, como en el diario online, sport. El historial de este navegador podemos encontrarlo en la ruta: 

C:/Users/Richard/AppData/Roaming/Opera Software/Opera Stable/History

[(Véase el anexo de evidencias, Evidencia 2)](https://www.notion.so/Informe-T-cnico-proyecto-3-7d96aeb709894c2b9c873461746ee9dc?pvs=21)

[(Véase el anexo de imágenes, Imagen 18)](https://www.notion.so/Informe-T-cnico-proyecto-3-7d96aeb709894c2b9c873461746ee9dc?pvs=21)

Siguiendo con el análisis del historial, hemos hallado búsquedas tanto de vuelos como de alojamiento, ubicando esto último en Las Palmas de Gran Canaria.

[(Véase el anexo de imágenes, Imagen 19)](https://www.notion.so/Informe-T-cnico-proyecto-3-7d96aeb709894c2b9c873461746ee9dc?pvs=21)


Podemos comprobar por su historial de conversaciones a través del cliente de correo electrónico Thunderbird, que el presunto sospechoso, Richard, con correo electrónico proba1.seguridade@gmail.com, ha mantenido una conversación con una presunta empresa competidora, con correo electrónico proba2.seguridade@gmail.com, en la que le ha suministrado datos confidenciales de la empresa.

Esto puede ser comprobado el historial de este mismo cliente, ubicado en la ruta: 

C:\Users\Richard\AppData\Roaming\Thunderbird\Profiles\tvtlv94f.default-release\

[Ver en el anexo de evidencias. Evidencia 2](#evidencia2)  
Esta carpeta, siendo montada en el programa SysTools MBOX viewer, nos ha permitido indagar en el historial de conversaciones de Richard. 

[Ver en el anexo de imagenes. Imagen 18](#imagen18)  
El primer mensaje sospechoso, a fecha de 20/02/2023 a las 20:53, tenemos a Richard hablando con la presunta empresa competidora, en la que pide un aumento de su salario, siguiendo la conversación (1→2→3), podemos comprobar como la presunta empresa competidora, le pide una prueba para poder evaluar la situación.

[Ver en el anexo de imagenes. Imagen 19](#imagen19)  
El día 22/02/2023 a las 00:59, empiezan a mantener otra conversación, en la que parece que llegan a un acuerdo, y nuestro presunto sospechoso le manda en fichero pom.xml a la presunta empresa competidora. Podemos observar que la exfiltración es de su agrado y continúan con el acuerdo con Richard.

[Ver en el anexo de imagenes. Imagen 20](#imagen20)  
Podemos ver que en la conversación anterior, en el mensaje número 3, Richard le adjunta y envia un archivo llamado “pom.xml”. Haciendo una búsqueda sobre el archivo, podemos comprobar que se encuentra dentro de un proyecto, el archivo parece contener datos de un proyecto y el enlace a un repositorio de github del mismo.

Ruta del archivo: C:\Users\Richard\Proyectos\reverb-master\reverb-master\models\pom.xml

[Ver en el anexo de imagenes. Imagen 21](#imagen21)  
[Ver en el anexo de imagenes. Imagen 22](#imagen22)  
[Ver en el anexo de evidencias. Evidencia 3](#evidencia3)  
En una última conversación, el día 22/02/2023 a las 15:10, Richard, envía un enlace de Google drive (el cuál se encuentra borrado), con el material en cuestión, protegido con contraseña esperando una remuneración económica en forma de bitcoin. Una vez él ha recibido el ingreso, ha proporcionado a la presunta empresa rival la contraseña para acceder al material.

[Ver en el anexo de imagenes. Imagen 23](#imagen23)
# 5. Conclusión

Tras el análisis del disco del equipo, se puede deducir que el usuario Richard estuvo haciendo actividades inusuales en las horas de trabajo, como visitar otras páginas e incluso la instalación de otro navegador, saltándose así las políticas de la empresa.

También el usuario Richard, estuvo en contacto con dos personas por correo, el cual, una de ellas, estaba hablando de salario y empleo con un lenguaje claro, mientras que con el segundo usuario, Richard estuvo comentándole de manera coloquial sus planes de futuro.



# 7. Anexo

### 7.1 Metodología Utilizada

A continuación, se explica la metodología que ha seguido el perito para adquirir y analizar
las evidencias:

- Adquisición de evidencia digital
1. La captura de la adquisición debe ser lo más precisa posible.
2. Detallar las fechas y horas a la que se realizó la extracción.
3. Intentar no sobrescribir las pruebas instalando software, si no es estrictamente
necesario.
4. Recoger las evidencias en orden de volatilidad:
5. Transparencia: A la hora de realizar la adquisición tendremos que explicar
detalladamente el proceso que hemos seguido para que pueda ser totalmente
reproducible.
- Preservación y almacenamiento de evidencia
A la hora de almacenamiento, se documentará:
- Dónde, cuándo y quién descubrió y recolectó la evidencia.
-  Dónde, cuándo y quién manejó la evidencia.
-  Quién ha custodiado la evidencia, cuánto tiempo y cómo la ha almacenado
-  Si se ha cambiado de custodia indicar a quien, que fecha y hora y comprobar que los
hashes coinciden
-  Dónde almacenarlo. Dependiendo del dispositivo tendremos que almacenarlo de una
u otra forma, por ejemplo, si es un dispositivo portátil tendremos que custodiarlo en
una bolsa de Faraday para que no pueda ser comprometido por las redes móviles.
- Análisis de evidencias

Se llevarán a cabo una serie de procesos y tareas que intentarán dar respuesta a preguntas
relacionadas con una intrusión, como su origen, la lista de sistemas afectados, los métodos
usados, etc. Todos estos procesos y tareas deberán realizarse de forma metódica,
auditable, repetible y defendible.

# 7.2 Herramientas usadas

WRR (Windows Registry Recovery):

| Nombre | WRR (Windows Registry Recovery) |
| --- | --- |
| Versión: | 1.6.1.0 |
| Página web | https://www.mitec.cz/wrr.html |

FTK Imager:

| Nombre | FTK Imager |
| --- | --- |
| Versión: | 3.1.2 |
| Página web | https://www.mitec.cz/wrr.html |

Registry Explorer:

| Nombre | Registry Explorer |
| --- | --- |
| Versión: | 1.1.0.6 |
| Página web | https://www.sans.org/tools/registry-explorer/ |

DB Browser for SQLite:

| Nombre | DB Browser for SQLite |
| --- | --- |
| Versión: | 3.12.2 |
| Página web | https://sqlitebrowser.org/ |

SysTools MBOX Viewer:

| Nombre | SysTools MBOX Viewer |
| --- | --- |
| Versión: | 4.0.0.0 |
| Página web | https://www.systoolsgroup.com/mbox-viewer.html |

Autopsy:

| Nombre | Autopsy |
| --- | --- |
| Versión: | 4.21.0 |
| Página web | https://www.autopsy.com/ |



## 8. Anexo de Imágenes
<div id='imagen1' />Imagen 1.

![Hash MD5](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/bd2105da-782d-436a-920b-d22de7162fb8.png)


  **Hash MD5**
<div id='imagen2' />
Imagen 2.

![Hash SHA1](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled.png)

Hash SHA1
<div id='imagen3' />
Imagen 3.

![Hash SHA256](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%201.png)

Hash SHA256
<div id='imagen4' />Imagen 4.

![Nombre del equipo de Richard](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%202.png)

Nombre del equipo de Richard
<div id='imagen5' />Imagen 5.

![Versión del sistema operativo](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%203.png)

Versión del sistema operativo
<div id='imagen6' />Imagen 6.

![Usuario encontrado Registro SAM](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%204.png)

Usuario encontrado Registro SAM
<div id='imagen7' />Imagen 7.

![Fecha/Hora Última Conexión Usuario Richard](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/3f7b241c-f76d-48ff-b547-662f2e6145ab.png)

Fecha/Hora Última Conexión Usuario Richard
<div id='imagen8' />Imagen 8.

![Dispositivo USB pendrive utilizado por Richard](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%205.png)

Dispositivo USB pendrive utilizado por Richard
<div id='imagen9' />Imagen 9.

![Hora de Ultima Conexión Dispositivo USB](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%206.png)

Hora de Ultima Conexión Dispositivo USB
<div id='imagen10' />Imagen 10.

![Mozilla Firefox instalado](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%207.png)

Mozilla Firefox instalado
<div id='imagen11' />Imagen 11.

![Fecha instalación Mozilla Firefox](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%208.png)

Fecha instalación Mozilla Firefox
<div id='imagen12' />Imagen 12

![Historial de búsquedas 1](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%209.png)

Historial de búsquedas 1
<div id='imagen13' />Imagen 13

![Historial de búsquedas 2](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2010.png)

Historial de búsquedas 2
<div id='imagen14' />Imagen 14

![Historial de búsquedas 3](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2011.png)

Historial de búsquedas 3
<div id='imagen15' />Imagen 15

![Historial de búsquedas 4](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2012.png)

Historial de búsquedas 4
<div id='imagen16' />Imagen 16

![Historial de búsquedas 5](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2013.png)

Historial de búsquedas 5
<div id='imagen17' />Imagen 17

![Arranque con el sistema Opera](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2014.png)

Arranque con el sistema Opera

<div id='imagen18' />Imagen 18
 ![Bandeja de correo electrónico](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2015.png)
Historial de búsquedas Opera
 
<div id='imagen18' />Imagen 19
 ![Bandeja de correo electrónico](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2015.png)
Historial de búsquedas Opera
 
<div id='imagen18' />Imagen 20
![Bandeja de correo electrónico](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2015.png)
Bandeja de correo electrónico

<div id='imagen19' />Imagen 21
![Conversación 1](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2016.png)
Conversación 1

<div id='imagen20' />Imagen 22
![Conversación 2](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2017.png)
Conversación 2

<div id='imagen21' />Imagen 23
![Archivo adjunto en conversación 2](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2018.png)
Archivo adjunto en conversación 2

<div id='imagen22' />Imagen 24
![Contenido archivo pom.xml](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2019.png)
Contenido archivo pom.xml

<div id='imagen23' />Imagen 25
![Conversación 3](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2020.png)
Conversación 3

## 9. Anexo evidencias
<div id='evidencia1' />Evidencia 1

| Ruta | C:/Users/Richard/AppData/Roaming/Mozilla/Firefox/Profiles/mt13hmmn.default-release/places.sqlite |
| --- | --- |
| Contenido | ![Historial de búsqueda](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto3%3A%20Unfaithful%20Employee/Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/historial_busqueda.png). |
| MAC | 
| Modified: | 2023-02-22 22:55:45 CET |
| Accessed: | 2023-02-22 22:56:08 CET |
| Created: | 2023-02-20 19:51:56 CET |
| Changed: | 2023-02-22 22:55:45 CET |
| Tamaño | 5242880 |
| HASH MD5 | 069c40b3140718f254b82fd73ac1c07a |
| HASH SHA256 | 3fae0bf074aaaafa496de4478a7e33e86a9e3e50ba4c38f56d04be232a8224ac |


<div id='evidencia2' />Evidencia 2

| Ruta | C:/Users/Richard/AppData/Roaming/Opera Software/Opera Stable/History |
| --- | --- |
| Contenido | ![Mensaje de correo](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto3%3A%20Unfaithful%20Employee/Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/correoselectronicos.png) |
| MAC | 
| Modified: | 2023-02-22 22:41:19 CET |
| Accessed: | 2023-02-22 22:55:44 CET |
| Created: | 2023-02-20 19:42:16 CET |
| Changed: | 2023-02-22 22:41:19 CET |
| Tamaño | 262144 |
| HASH MD5 | b761c8a0804c04cbc45b10cb7186be45 |
| HASH SHA256 | 88c45210c583fcc148ce26f4224c72cb660454831536c1c619da806326257661 |


<div id='evidencia2' />Evidencia 3

| Ruta | C:/Users/Richard/AppData/Roaming/Thunderbird/Profiles/tvtlv94f.default-release/ImapMail/imap.gmail.com/[Gmail].sbd/Todos |
| --- | --- |
| Contenido | ![Mensaje de correo](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto3%3A%20Unfaithful%20Employee/Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/correoselectronicos.png) |
| MAC | 
| Modified: | 2023-02-22 15:26:03 CET |
| Accessed: | 2023-02-22 15:26:03 CET |
| Created: | 2023-02-20 20:49:31 CET |
| Changed: | 2023-02-22 15:26:03 CET |
| Tamaño | 721317 |
| HASH MD5 | 0370097a00c34071e6bc95409456a80f |
| HASH SHA256 | 042decdb9493260d8c95dd03e0262293097f62dfd255fbfe320dedaa162f6925 |

<div id='evidencia3' />Evidencia 3

| Ruta | C:/Users/Richard/Proyectos/reverb-master/reverb-master/models/pom.xml |
| --- | --- |
| Contenido | ![archivo pom.xml](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto3%3A%20Unfaithful%20Employee/Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/archivo_pom.png) |
| MAC | 
| Modified: | 2013-09-16 16:32:22 CEST |
| Accessed: | 2023-02-22 00:55:23 CET |
| Created: | 2013-09-16 16:32:22 CEST |
| Changed: | 2023-02-22 00:48:51 CET |
| Tamaño | 1592 |
| HASH MD5 | e6fad44768934e63f1e2867f0dfa34ee |
| HASH SHA256 | 96fc4c3c8a4e3090eff4c48a4854f3943701b526a6ca32fe3b1c656b3480d258 |
