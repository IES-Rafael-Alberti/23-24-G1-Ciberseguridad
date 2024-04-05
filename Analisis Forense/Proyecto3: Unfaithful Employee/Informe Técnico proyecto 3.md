# Informe Técnico proyecto 3

# Índice
1. [Resumen Ejecutivo](#resumen)  
    1.1. [Línea temporal](#tiempo)
2. [Introducción](#introduccion)  
    2.1 [Antecedentes](#antecedentes)  
    2.2 [Objetivos](#objetivos)  
    2.3 [Alcance](#alcance)  
3. [Información analizada](#informacion)  
4. [Análisis](#analisis)  
    4.1 [Comparación de hashes](#comparacion)  
    4.2 [Análisis de la imagen forense](#forense)  
5. [Conclusión](#conclusion)  

# 1. Resumen Ejecutivo <div id='resumen' />

El análisis forense del disco duro revela una serie de irregularidades en el comportamiento de Richard Warner. Se encontraron indicios de violaciones a las políticas de seguridad de la empresa, como el uso de dispositivos USB no autorizados y la instalación de navegadores web no permitidos en su equipo de trabajo. Además, se descubrió que Warner había mantenido comunicación con una presunta empresa competidora, a la cual proporcionó información confidencial de la empresa, incluyendo archivos de proyectos y datos sensibles, a cambio de beneficios económicos. 

## 1.1 Línea temporal<div id='tiempo' />

Hemos detallado en una pequeña línea temporal toda la actividad ilícita que estaba realizando el usuario Richard.

![Linea Temporal.png](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Linea_Temporal.png)

# 2. Introducción<div id='introduccion' />

## 2.1 Antecedentes<div id='antecedentes' />

InnovaTech Solutions, una empresa de desarrollo de software conocida por sus proyectos innovadores como "Ligueitor" y "Social Query", enfrenta rumores de inestabilidad financiera y despidos inminentes. En medio de esta incertidumbre, Richard Eduardo Warner, un empleado ejemplar hasta ahora, ha dejado la empresa después de una confrontación con su jefe. Se sospecha que su comportamiento inusual podría estar relacionado con acciones perjudiciales para la empresa, por lo que se realizará un análisis forense de su disco duro en busca de vestigios de mal uso de recursos o filtración de información confidencial. El objetivo es proteger los activos y la integridad de la empresa.

## 2.2 Objetivos<div id='objetivos' />

Los objetivos de este informe técnicos son:

1. Verificar la integridad de la imagen del disco mediante la comparación de hashes para asegurar su autenticidad.
2. Crear una línea de tiempo detallada de las actividades de Richard en el dispositivo, registrando sus inicios de sesión y el uso de dispositivos USB.
3. Detectar cualquier actividad no autorizada, como el mal uso de recursos de la empresa o la extracción de datos confidenciales.
4. Documentar y presentar de manera clara y concisa las conclusiones del análisis.

## 2.3 Alcance<div id='alcance' />

Análisis completo de la imagen del disco del equipo de Richard en busca de cualquier uso indebido de los recursos de la empresa o de filtración de información confidencial.

# 3. Información analizada<div id='informacion' />

| Adquisición | traidor.img |
| --- | --- |
| Tamaño (Bytes) | 53687091200 |
| HASH MD5 | DFDFBA2231E3FA409676B1B737474288 |
| HASH SHA1 | F476A81089A10F9D5393AA8C2F8BBCCDB87F7D3C |
| HASH SHA256 | 66D6EE7A61EA7A986E8F6BB54B9986F79D95B5A0278BEF86678ED42ACE320D9B |

# 4. Análisis<div id='analisis' />

Antes de comenzar con el análisis vamos a realizar la comprobación de hashes para verificar que la imagen forense del equipo de Richard no ha sido alterada.

### 4.1 Comparación de hashes<div id='comparacion' />

Comenzaremos con comprobar que los hashes de la imagen forense del equipo coinciden con las proporcionadas por Alan el cuál adquirió y preservo la imagen, del departamento de sistemas, quien proporcionó los siguientes hashes:

- MD5: dfdfba2231e3fa409676b1b737474208
- SHA-1: f476a81089a10f9d5393aa8c2f8bbccdb87f7d3c
- SHA-256: 66d6ee7a61ea7a986e8f6bb54b9986f79d95b5a0278bef86678ed42ace320d96

Verificamos si esta información es correcta o no:

| Criptografía | HASH | Prueba |
| --- | --- | --- |
| MD5 | DFDFBA2231E3FA409676B1B737474288 | [Ver en el anexo de imagenes. Imagen 1](Anexos.md###Imágenes) |
| SHA1 | F476A81089A10F9D5393AA8C2F8BBCCDB87F7D3C | [Ver en el anexo de imagenes. Imagen 2](Anexos.md) |
| SHA256 | 66D6EE7A61EA7A986E8F6BB54B9986F79D95B5A0278BEF86678ED42ACE320D9B | [Ver en el anexo de imagenes. Imagen 3](Anexos.md) |

Como podemos apreciar, los hashes recibidos por parte de Alan no coinciden con los generados por nosotros.

### 4.2 Análisis de la imagen forense<div id='forense' />

Comenzaremos con detallar la información del equipo al cual vamos a realizar el análisis.

Para averiguar esta información tendremos que consultar dos registros del sistema, en este caso el registro SOFTWARE para la versión del sistema y el registro SYSTEM para el nombre del equipo. Ambos se encuentran en la misma ruta:

C:/Windows/System32/config/SOFTWARE

C:/Windows/System32/config/SYSTEM

Haciendo uso de la herramienta WRR (Windows Registry Recovery) podemos visualizar el contenido de estos archivos.

Primero podemos ver el nombre del equipo en el registro SYSTEM.

[Ver en el anexo de imagenes. Imagen 4](Anexos.md)  

Ahora el sistema operativo que esta utilizando usando el registro SOFTWARE.

[Ver en el anexo de imagenes. Imagen 5](Anexos.md)  

A continuación, averiguaremos si existe algún usuario que pertenezca a Richard, esto lo podremos  localizar en el registro SAM del sistema que se encuentra en la raíz. C:/Windows/System32/config/SAM

[Ver en el anexo de imagenes. Imagen 6](Anexos.md)  

Como podemos comprobar, si que existe dicho usuario, el cual se llama como el presunto sospechoso.

También podemos determinar cierta información valiosa, como la última vez que este usuario inició sesión en el equipo.

[Ver en el anexo de imagenes. Imagen 7](Anexos.md)  

En este caso, el ultimo inicio de sesión del usuario correspondiente a Richard fue el 22 de Febrero de 2023 a las 13:55:18.

Realizando búsquedas de alguna actividad sospechosa por parte del usuario, podemos identificar que se saltó las políticas de la empresa introduciendo un dispositivo USB en su equipo.

Dicho dispositivo USB es un pendrive Kingston DataTraveler 3.0 USB Device.

Esta información la conseguimos gracias al registro SYSTEM y utilizando una vez más la herramienta WRR.

[Ver en el anexo de imagenes. Imagen 8](Anexos.md)  

Para encontrar la fecha y hora exacta de la conexión de este dispositivo tendremos que utilizar otra herramienta llamada Registry Explorer, volver a abrir el registro SYSTEM y ver los detalles técnicos del dispositivo en la siguiente ruta:

\SYSTEM\CurrentControlSet\Enum\STORAGE\_??USBSTOR#Disk&Ven_Kingston&Prod_DataTraveler_3.0&Rev#002618525C8EF0B0E87D2853&0#{53f56307-b6bf-11d0-94f2-00a0c91efb8b}

La fecha y hora exacta a la que se conectó el dispositivo USB fue el 22 de Febrero de 2023 a las  0:27:42.

[Ver en el anexo de imagenes. Imagen 9](Anexos.md)  

Podemos apreciar que Richard, también se saltó las políticas de la empresa con respecto al navegador web, ya que estas solo permiten navegadores webs distribuidos por Microsoft.

Observamos que tiene instalado otro navegador web visualizando con WRR en el registro SOFTWARE, Mozilla Firefox, el cual es el que estaba utilizando para realizar actividades fuera de sus labores en el trabajo.

[Ver en el anexo de imagenes. Imagen 10](Anexos.md)  

Verificaremos la fecha y la hora a la cual se instaló el navegador haciendo uso de la herramienta Registry Explorer y volviendo a abrir el registro SOFTWARE. Dicha información se encuentra en los detalles técnicos de la ruta:

 ROOT\Mozilla\Mozilla Firefox 

[Ver en el anexo de imagenes. Imagen 11](Anexos.md)  

Podemos comprobar el historial de navegación haciendo uso de la herramienta DBBrowser for SQLite, abriendo el archivo places.qlite que contiene el historial de navegación del navegador Mozilla Firefox. Este archivo podemos encontrarlo en la siguiente ruta:

C://Users/Richard/AppData/Roaming/Mozilla/Firefox/Profiles/mt13hmmn.default-release 

[Ver en el anexo de Vestigios. vestigio 1](Anexos.md)  
Al registrar el historial de navegación, hemos visto que Richard ha estado buscando durante el transcurso de la jornada laboral diverso contenido no autorizado, como películas, vídeos, páginas web de apuestas, etc.

[Ver en el anexo de imagenes. Imagen 12](Anexos.md)  
[Ver en el anexo de imagenes. Imagen 13](Anexos.md)  
[Ver en el anexo de imagenes. Imagen 14](Anexos.md)  
[Ver en el anexo de imagenes. Imagen 15](Anexos.md)  
[Ver en el anexo de imagenes. Imagen 16](Anexos.md)  

También podemos ver que aunque tiene varios navegadores web instalados en el equipo, el único habilitado para que se inicie al ejecutarse el equipo es Opera.

Esto podemos descubrirlo desde los registros del usuario, en el archivo NT.USERDAT, dentro de este fichero ubicado en la ruta:

\Software\Microsoft\Windows\CurrentVersion\Run

[Ver en el anexo de imagenes. Imagen 17](Anexos.md)  

En el historial de este navegador, podemos encontrar múltiples búsquedas de canciones en youtube, a parte de eso, también realiza constantes búsquedas de noticias deportivas, ya sea en el portal marca, como en el diario online, sport. El historial de este navegador podemos encontrarlo en la ruta: 

C:/Users/Richard/AppData/Roaming/Opera Software/Opera Stable/History

[(Véase el anexo de Vestigios, vestigio 2)](Anexos.md)

[(Véase el anexo de imágenes, Imagen 18)](Anexos.md)

Siguiendo con el análisis del historial, hemos hallado búsquedas tanto de vuelos como de alojamiento, ubicando esto último en Las Palmas de Gran Canaria.

[(Véase el anexo de imágenes, Imagen 19)](Anexos.md)


Podemos comprobar por su historial de conversaciones a través del cliente de correo electrónico Thunderbird, que el presunto sospechoso, Richard, con correo electrónico proba1.seguridade@gmail.com, ha mantenido una conversación con una presunta empresa competidora, con correo electrónico proba2.seguridade@gmail.com, en la que le ha suministrado datos confidenciales de la empresa.

Esto puede ser comprobado el historial de este mismo cliente, ubicado en la ruta: 

C:\Users\Richard\AppData\Roaming\Thunderbird\Profiles\tvtlv94f.default-release\

[Ver en el anexo de Vestigios. vestigio 3](Anexos.md)  
Esta carpeta, siendo montada en el programa SysTools MBOX viewer, nos ha permitido indagar en el historial de conversaciones de Richard. 

[Ver en el anexo de imagenes. Imagen 18](Anexos.md)  
El primer mensaje sospechoso, a fecha de 20/02/2023 a las 20:53, tenemos a Richard hablando con la presunta empresa competidora, en la que pide un aumento de su salario, siguiendo la conversación (1→2→3), podemos comprobar como la presunta empresa competidora, le pide una prueba para poder evaluar la situación.

[Ver en el anexo de imagenes. Imagen 19](Anexos.md)  
El día 22/02/2023 a las 00:59, empiezan a mantener otra conversación, en la que parece que llegan a un acuerdo, y nuestro presunto sospechoso le manda en fichero pom.xml a la presunta empresa competidora. Podemos observar que la exfiltración es de su agrado y continúan con el acuerdo con Richard.

[Ver en el anexo de imagenes. Imagen 20](Anexos.md)  
Podemos ver que en la conversación anterior, en el mensaje número 3, Richard le adjunta y envia un archivo llamado “pom.xml”. Haciendo una búsqueda sobre el archivo, podemos comprobar que se encuentra dentro de un proyecto, el archivo parece contener datos de un proyecto y el enlace a un repositorio de github del mismo.

Ruta del archivo: C:\Users\Richard\Proyectos\reverb-master\reverb-master\models\pom.xml

[Ver en el anexo de imagenes. Imagen 21](Anexos.md)  
[Ver en el anexo de imagenes. Imagen 22](Anexos.md)  
[Ver en el anexo de Vestigios. vestigio 4](Anexos.md)  
En una última conversación, el día 22/02/2023 a las 15:10, Richard, envía un enlace de Google drive (el cuál se encuentra borrado), con el material en cuestión, protegido con contraseña esperando una remuneración económica en forma de bitcoin. Una vez él ha recibido el ingreso, ha proporcionado a la presunta empresa rival la contraseña para acceder al material.

[Ver en el anexo de imagenes. Imagen 23](Anexos.md)

# 5. Conclusión<div id='conclusion' />

Tras el análisis del disco del equipo, se puede deducir que el usuario Richard estuvo haciendo actividades inusuales en las horas de trabajo, como visitar otras páginas e incluso la instalación de otro navegador, saltándose así las políticas de la empresa.

También el usuario Richard, estuvo en contacto con dos personas por correo, el cual, una de ellas, estaba hablando de salario y empleo con un lenguaje claro, mientras que con el segundo usuario, Richard estuvo comentándole de manera coloquial sus planes de futuro.

