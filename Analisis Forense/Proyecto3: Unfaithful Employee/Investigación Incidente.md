# Preguntas

## 1. Verificar la integridad de la imagen del disco a través de CMD o PowerShell, comparando los hashes proporcionados. ¿Coinciden los tres hashes?

Comenzaremos con comprobar que los hashes de la evidencia coinciden con las proporcionadas por Alan el cuál adquirió y preservo la evidencia, del departamento de sistemas, quien proporcionó los siguientes hashes:

- MD5: dfdfba2231e3fa409676b1b737474208
- SHA-1: f476a81089a10f9d5393aa8c2f8bbccdb87f7d3c
- SHA-256: 66d6ee7a61ea7a986e8f6bb54b9986f79d95b5a0278bef86678ed42ace320d96

Para ello hemos utilizado el PowerShell de Windows:

## MD5

![Hash MD5](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/bd2105da-782d-436a-920b-d22de7162fb8.png)

MD5:

DFDFBA2231E3FA409676B1B737474288

## SHA-1

![Hash SHA1](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled.png)

SHA-1:

F476A81089A10F9D5393AA8C2F8BBCCDB87F7D3C

## SHA-256

![Hash SHA256](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%201.png)

SHA-256:

66D6EE7A61EA7A986E8F6BB54B9986F79D95B5A0278BEF86678ED42ACE320D9B

Como podemos comprobar, tanto el hash MD5 como el hash SHA-256 no coinciden con el dado por Alan.

---

## 2. Confirmar la existencia de un usuario correspondiente a Richard en el equipo y determinar cuándo fue su último inicio de sesión.

Para confirmar la existencia de un usuario correspondiente a Richard, nos iremos a los archivos de registros de las cuentas de usuario registradas en el sistema, en este caso el registro SAM, el cual se encuentra en la siguiente ruta:

C:/Windows/System32/config/SAM/

Utilizando una herramienta para ver el contenido de registros verificaremos si existe ese usuario o no. Vamos a utilizar **Windows Registry Recovery (WRR):**

![Usuario encontrado Registro SAM](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%204.png)

Como podemos comprobar, si que existe dicho usuario, el cual se llama como el presunto sospechoso.

También podemos determinar cierta información valiosa como la ultima vez que este usuario inicio sesión en el equipo:

![Fecha/Hora Última Conexión Usuario Richard](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/3f7b241c-f76d-48ff-b547-662f2e6145ab.png)

En este caso, el ultimo inicio de sesión del usuario correspondiente a Richard fue **el 22 de Febrero de 2023 a las 13:55:18**.

---

## 3. Identificar el nombre del equipo y la versión del Sistema Operativo utilizado.

Para averiguar esta información tendremos que consultar nuevamente dos registros del sistema, en este caso el registro SOFTWARE para la versión del sistema operativo y el registro SYSTEM para el nombre del equipo, los cuales se encuentran en la misma ruta que el anterior:

- Nombre del equipo: \SYSTEM\ControlSet001\Control\ComputerName\ComputerName
- Sistema operativo: \SOFTWARE\Microsoft\Windows NT\CurrentVersion

Volviendo a utilizar la misma herramienta podremos sacar el nombre del equipo y la versión del sistema operativo utilizado.

Nombre del equipo:

![Nombre del equipo de Richard](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%202.png)

El nombre del equipo por lo que podemos apreciar es LADRONERA.

Sistema operativo:

![Versión del sistema operativo](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%203.png)

El sistema operativo utilizado por este equipo es un Windows 10 Pro Education N.

---

## 4. Investigar si se introdujo algún dispositivo USB en el equipo, a pesar de las políticas de la empresa contra su uso por parte de Richard. En caso afirmativo, especificar los detalles del dispositivo USB y el momento de su conexión.

Volvemos a necesitar información que podemos sacar de nuevo con esta herramienta del registro SYSTEM.

Encontramos un dispositivo USB externo llamado Kingston DataTraveler 3.0 USB Device:

![Dispositivo USB pendrive utilizado por Richard](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%205.png)

Para encontrar la fecha y hora exacta de la conexión de este dispositivo tendremos que utilizar otra herramienta llamada Registry Explorer y volver a abrir el registro SYSTEM.

Una vez abierto nos vamos a la siguiente ruta:

\SYSTEM\CurrentControlSet\Enum\STORAGE\_??USBSTOR#Disk&Ven_Kingston&Prod_DataTraveler_3.0&Rev#002618525C8EF0B0E87D2853&0#{53f56307-b6bf-11d0-94f2-00a0c91efb8b}

Hacemos click derecho en la rama y clickamos en Technical details:

![TechnicalDetail](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/tecnicaldetails.png)

Aquí podremos ver con detalle las propiedades del dispositivo.

La fecha y hora exacta a la que se conecto el dispositivo USB fue el 22 de Febrero de 2023 a las  0:27:42 como podemos comprobar en la siguiente imagen:

![Hora de Ultima Conexión Dispositivo USB](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%206.png)

---

## 5. Dado el interés conocido de Richard por el fútbol y la música rock y heavy, investigar su actividad en línea relacionada con estos intereses. Además, verificar si ha visualizado contenido en línea que pueda justificar un despido procedente, como la visualización de una película online. Documentar cualquier hallazgo relevante.

El usuario Richard estuvo buscando algo llamado “Trabajo Basura”, una película, y entra CUEVANAHD, un portal de visualización de películas.

![Historial de búsquedas 1](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%209.png)

El cuál, si investigamos por internet, podemos ver que es una película. También Richard estuvo en las páginas webs de el Corte Inglés, youtube e incluso Bershka:

![Historial de búsquedas 2](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2010.png)

![Historial de búsquedas 3](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2011.png)

![Historial de búsquedas 4](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2012.png)

Richard, también estuvo en la página web de eToro, una página de apuestas:

![Historial de búsquedas 5](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2013.png)

Alternativamente, si nos vamos a la ruta de C://Users/Richard/AppData/Roaming/Mozilla/Firefox/Profiles/mt13hmmn.default-release, si nos vamos al archivo places.sqlite y abrimos ese fichero con, por ejemplo, DBBrowser for SQLIte, en la tabla moz_origins, podemos ver las páginas que ha visitado:

![Arranque con el sistema Opera](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/historialfirefox.png)

También si observamos el historial de Opera, podemos ver que realiza constantemente búsquedas sobre noticias del mundo deportivo .

![Arranque con el sistema Opera](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/historial_opera.png)

## 6. Determinar si, tras su salida de la empresa, Richard tenía planes de visitar otro lugar y, de ser así, cómo planeaba llegar allí.

Dentro del historial, también podemos observar que Richard, hace búsquedas dentro del portal de Vueling, buscando ofertas de para viajar. Acto seguido, empieza a buscar a través de Booking, un portal de búsqueda de alojamiento, hoteles en Las Palmas de Gran Canaria.

![historial_opera](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/historial_opera2.png)

---

## 7. Comprobar si existe algún navegador web, aparte de los proporcionados por Microsoft, configurado para ejecutarse al iniciar sesión Richard.

Para comprobar si existe algún navegador web instalado a demás de los proporcionados por Microsoft, podemos indagar en el registro SOFTWARE de nuevo y ver todos los programas que tiene instalado en el equipo:

![Mozilla Firefox instalado](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%207.png)

Podemos verificar la fecha y la hora a la cual se instalo el navegador haciendo uso de la herramienta Register Explorer y volviendo a abrir el registro SOFTWARE.

Para ello vamos a la ruta:

ROOT\Mozilla\Mozilla Firefox

En la cual haremos click izquierdo para ver los detalles, podemos accedemos a ver toda la información del fichero:

![Fecha instalación Mozilla Firefox](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%208.png)

También podemos ver que aunque tiene varios navegadores web instalados en el equipo, el único habilitado para que se inicie al ejecutarse el equipo es Opera.

Esto podemos descubrirlo desde los registros del usuario, en el archivo NT.USERDAT en la ruta:

\Software\Microsoft\Windows\CurrentVersion\Run

![Arranque con el sistema Opera](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2014.png)

---

## 8. Buscar evidencia de que Richard haya asistido a competidores o terceros mediante la exfiltración de datos por correo electrónico.

Podemos comprobar por su historial de conversaciones a través del cliente de correo electrónico Thunderbird, que el presunto sospechoso, Richard,  con correo electrónico proba1.seguridade@gmail.com, ha mantenido una conversación con una presunta empresa competidora, con correo electrónico proba2.seguridade@gmail.com, en la que le ha suministrado datos confidenciales de la empresa.

Esto puede ser comprobado el historial de este mismo cliente, ubicado en la ruta: `C:\Users\Richard\AppData\Roaming\Thunderbird\Profiles\tvtlv94f.default-release\`

Esta carpeta, siendo montada en el programa SysTools MBOX viewer, nos ha permitido indagar en el historial de conversaciones de Richard. 

 ![Bandeja de correo electrónico](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2015.png)

El primer mensaje sospechoso, a fecha de 20/02/2023 a las 20:53, tenemos a Richard hablando con la presunta empresa competidora, en la que pide un aumento de su salario, siguiendo la conversación (1→2→3), podemos comprobar como la presunta empresa competidora, le pide una prueba para poder evaluar la situación.

 ![Conversación 1](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2016.png)

El día 22/02/2023 a las 00:59, empiezan a mantener otra conversación, en la que parece que llegan a un acuerdo, y nuestro presunto sospechoso le manda en fichero pom.xml a la presunta empresa competidora. Podemos observar que la exfiltración es de su agrado y continúan con el acuerdo con Richard.

 ![Conversación 2](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2017.png)

Podemos ver que en la conversación anterior, en el mensaje número 3, Richard le adjunta y envia un archivo llamado “pom.xml”.

 ![Archivo adjunto en conversación 2](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2018.png)

Haciendo una búsqueda sobre el archivo, podemos comprobar que se encuentra dentro de un proyecto, el archivo parece contener datos de un proyecto y el enlace a un repositorio de github del mismo.

Ruta del archivo: `C:\Users\Richard\Proyectos\reverb-master\reverb-master\models\pom.xml`

 ![Contenido archivo pom.xml](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2019.png)

En una última conversación, el día 22/02/2023 a las 15:10, Richard, envía un enlace de Google drive (el cuál se encuentra borrado), con el material en cuestión, protegido con contraseña esperando una remuneración económica en forma de bitcoin. Una vez él ha recibido el ingreso, ha proporcionado a la presunta empresa rival la contraseña para acceder al material.

 

 ![Conversación 3](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%2020.png)
