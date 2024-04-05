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

![TechnicalDetail](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/technicaldetails.png)

Aquí podremos ver con detalle las propiedades del dispositivo.

La fecha y hora exacta a la que se conecto el dispositivo USB fue el 22 de Febrero de 2023 a las  0:27:42 como podemos comprobar en la siguiente imagen:

![Hora de Ultima Conexión Dispositivo USB](Informe%20Te%CC%81cnico%20proyecto%203%207d96aeb709894c2b9c873461746ee9dc/Untitled%206.png)

---

## 5. Dado el interés conocido de Richard por el fútbol y la música rock y heavy, investigar su actividad en línea relacionada con estos intereses. Además, verificar si ha visualizado contenido en línea que pueda justificar un despido procedente, como la visualización de una película online. Documentar cualquier hallazgo relevante.

El usuario Richard estuvo buscando algo llamado “Trabajo Basura”, una película, y entra CUEVANAHD, un portal de visualización de peliculas.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/a4728530-1b1a-44bf-b0e8-a35e8844aeb5/Untitled.png)

El cuál, si investigamos por internet, podemos ver que es una película. También Richard estuvo en las páginas webs de el Corte Inglés, youtube e incluso Bershka:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/dbcd8652-2273-400b-b3d6-d88ce7cc62b3/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/fd03b405-e5c9-4c41-91e9-ba8819b7a825/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/335e1519-3515-41f7-8ce6-505d04802e41/Untitled.png)

Richard, también estuvo en la página web de eToro, una página de apuestas:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/2a9da31f-4d3d-4b65-92c4-be66877b8988/Untitled.png)

---

Alternativamente, si nos vamos a la ruta de C://Users/Richard/AppData/Roaming/Mozilla/Firefox/Profiles/mt13hmmn.default-release, si nos vamos al archivo places.sqlite y abrimos ese fichero con, por ejemplo, DBBrowser for SQLIte, en la tabla moz_origins, podemos ver las páginas que ha visitado:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/e3462346-7aa2-436c-95b7-8b92cebd75fd/Untitled.png)

También si observamos el historial de Opera, podemos ver que realiza constantemente búsquedas sobre noticias del mundo deportivo .

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/157038f8-769c-431b-b997-e3ef30e490de/Untitled.png)

## 6. Determinar si, tras su salida de la empresa, Richard tenía planes de visitar otro lugar y, de ser así, cómo planeaba llegar allí.

Dentro del historial, también podemos observar que Richard, hace búsquedas dentro del portal de Vueling, buscando ofertas de para viajar. Acto seguido, empieza a buscar a través de Booking, un portal de búsqueda de alojamiento, hoteles en Las Palmas de Gran Canaria.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/1faaf7a6-2c72-4944-963c-604a3776cc8f/Untitled.png)

---

## 7. Comprobar si existe algún navegador web, aparte de los proporcionados por Microsoft, configurado para ejecutarse al iniciar sesión Richard.

Para comprobar si existe algún navegador web instalado a demás de los proporcionados por Microsoft, podemos indagar en el registro SOFTWARE de nuevo y ver todos los programas que tiene instalado en el equipo:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/e791097a-070f-4d12-8f8e-333d99ce91be/Untitled.png)

Podemos verificar la fecha y la hora a la cual se instalo el navegador haciendo uso de la herramienta Register Explorer y volviendo a abrir el registro SOFTWARE.

Para ello vamos a la ruta:

ROOT\Mozilla\Mozilla Firefox

En la cual haremos click izquierdo para ver los detalles.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/e523e8ce-4e4d-4c62-bad0-56a04faac457/Untitled.png)

Y accedemos a ver la información:

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/80c8d363-8551-4d2c-b370-feb31b0254ea/Untitled.png)

También podemos ver que aunque tiene varios navegadores web instalados en el equipo, el único habilitado para que se inicie al ejecutarse el equipo es Opera.

Esto podemos descubrirlo desde los registros del usuario, en el archivo NT.USERDAT en la ruta:

\Software\Microsoft\Windows\CurrentVersion\Run

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/c46cfecc-ae7b-4e64-9429-aff3ec765add/Untitled.png)

---

## 8. Buscar evidencia de que Richard haya asistido a competidores o terceros mediante la exfiltración de datos por correo electrónico.

Podemos comprobar por su historial de conversaciones a través del cliente de correo electrónico Thunderbird, que el presunto sospechoso, Richard,  con correo electrónico proba1.seguridade@gmail.com, ha mantenido una conversación con una presunta empresa competidora, con correo electrónico proba2.seguridade@gmail.com, en la que le ha suministrado datos confidenciales de la empresa.

Esto puede ser comprobado el historial de este mismo cliente, ubicado en la ruta: `C:\Users\Richard\AppData\Roaming\Thunderbird\Profiles\tvtlv94f.default-release\`

Esta carpeta, siendo montada en el programa SysTools MBOX viewer, nos ha permitido indagar en el historial de conversaciones de Richard. 

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/bb3e7251-d451-4c51-b1ba-511401a43be7/Untitled.png)

El primer mensaje sospechoso, a fecha de 20/02/2023 a las 20:53, tenemos a Richard hablando con la presunta empresa competidora, en la que pide un aumento de su salario, siguiendo la conversación (1→2→3), podemos comprobar como la presunta empresa competidora, le pide una prueba para poder evaluar la situación.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/66913c2b-976e-4ac7-8a14-7149c812827a/Untitled.png)

El día 22/02/2023 a las 00:59, empiezan a mantener otra conversación, en la que parece que llegan a un acuerdo, y nuestro presunto sospechoso le manda en fichero pom.xml a la presunta empresa competidora. Podemos observar que la exfiltración es de su agrado y continúan con el acuerdo con Richard.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/e596e572-b6c1-4556-98ef-91bc950ed441/Untitled.png)

Podemos ver que en la conversación anterior, en el mensaje número 3, Richard le adjunta y envia un archivo llamado “pom.xml”.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/45865888-1652-41a5-b07c-5404e7717d64/Untitled.png)

Haciendo una búsqueda sobre el archivo, podemos comprobar que se encuentra dentro de un proyecto, el archivo parece contener datos de un proyecto y el enlace a un repositorio de github del mismo.

Ruta del archivo: `C:\Users\Richard\Proyectos\reverb-master\reverb-master\models\pom.xml`

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/faea8d77-1891-410c-9268-95389330aa81/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/c0120707-b775-4d46-b01e-4906afae41fe/Untitled.png)

En una última conversación, el día 22/02/2023 a las 15:10, Richard, envía un enlace de Google drive (el cuál se encuentra borrado), con el material en cuestión, protegido con contraseña esperando una remuneración económica en forma de bitcoin. Una vez él ha recibido el ingreso, ha proporcionado a la presunta empresa rival la contraseña para acceder al material.

 

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/a9ae4c88-2fb7-4fba-8f91-189f36219734/29b9ca47-ec17-4e85-919f-334c2196fa4e/Untitled.png)
