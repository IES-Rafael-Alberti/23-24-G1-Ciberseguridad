## CVE-2020-11899
### Descripción
La pila Treck TCP/IP anterior a 6.0.1.66 tiene una lectura fuera de límites de IPv6.

### Referencias
[https://www.kb.cert.org/vuls/id/257161](https://www.kb.cert.org/vuls/id/257161)  

[https://tools.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-treck-ip-stack-JyBQ5GyC](https://tools.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-treck-ip-stack-JyBQ5GyC)

### Impacto
- Base Score: [5.4 MEDIUM](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2020-11899&vector=AV:A/AC:L/PR:N/UI:N/S:U/C:N/I:L/A:L&version=3.1&source=NIST)
  
- Vector: [CVSS:3.1/AV:A/AC:L/PR:N/UI:N/S:U/C:N/I:L/A:L](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2020-11899&vector=AV:A/AC:L/PR:N/UI:N/S:U/C:N/I:L/A:L&version=3.1&source=NIST)
  
- Sistemas Afectados: Treck TCP/IP 4.7.1.27, 5.0.1.35, 6.0.1.28 y 6.0.1.41
  
### Explotación
- Clase: Lectura fuera de limites
  
El producto lee datos más allá del final, o antes del principio, del búfer previsto. Por lo general, esto puede permitir a los atacantes leer información confidencial de otras ubicaciones de memoria o provocar un bloqueo.

- CWE: [CWE-125](https://cwe.mitre.org/data/definitions/125.html)

- [Video Ejemplo de la Vulnerabilidad](https://www.jsof-tech.com/ripple20/)
### Solución
- Actualice a la última versión estable del software de Treck IP (6.0.1.67 o posterior).
- Bloquear todo tráfico anómalo.
- Deshabilite o bloquee el túnel IP, tanto IPv6-en-IPv4 como IP-en-IP si no es necesario
- Bloquear el enrutamiento de origen IP y cualquier característica obsoleta de IPv6, como encabezados de enrutamiento
- Proporcione seguridad DHCP/DHCPv6 con funciones como DHCP snooping
- Deshabilite o bloquee la multidifusión IPv6 si no se usa en la infraestructura de conmutación
## CVE-2022-42971
### Descripción

Carga sin restricciones de archivos peligrosos que podría causar la ejecución remota de código cuando el atacante carga un archivo JSP malicioso.

## Referencias

[Easy_UPS_Online_Monitoring_Software_Security_Notification.pdf](https://download.schneider-electric.com/files?p_Doc_SEVD-2022-347-01&p_enDocType=Security+and+Safety+Notice&p_File_Name=SEVD-2022-347-01_Easy_UPS_Online_Monitoring_Software_Security_Notification.pdf)

### Impacto
- Base Score: [9.8 CRITICAL](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2022-42971&vector=AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H&version=3.1&source=Schneider%20Electric%20SE)
  
- Vector: [CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2022-42971&vector=AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H&version=3.1&source=Schneider%20Electric%20SE)

- Sistemas Afectados: Software de monitoreo en línea Easy UPS de APC (Windows 7, 10, 11 y Windows Server 2016, 2019, 2022 - Versiones anteriores a V2.5-GA), Software de monitoreo en línea Easy UPS de APC (Windows 11, Windows Server 2019, 2022 - Versiones anteriores a V2.5-GA-01-22261), Software de monitoreo en línea Schneider Electric Easy UPS (Windows 7, 10, 11 y Windows Server 2016, 2019, 2022 - Versiones anteriores a V2.5-GS), Schneider Electric Software de monitoreo en línea Easy UPS (Windows 11, Windows Server 2019, 2022 - Versiones anteriores a V2.5-GS-01-22261)

### Explotación
- Clase: Carga sin restricciones de archivos con tipos peligrosos.
  
  El producto permite al atacante cargar o transferir archivos de tipos peligrosos que pueden procesarse automáticamente dentro del entorno del producto.
  
- CWE: [CWE-434](https://cwe.mitre.org/data/definitions/434.html)
### Solución
[Documento Oficial](https://download.schneider-electric.com/files?p_Doc_SEVD-2022-347-01&p_enDocType=Security+and+Safety+Notice&p_File_Name=SEVD-2022-347-01_Easy_UPS_Online_Monitoring_Software_Security_Notification.pdf)

- Ubicar redes de sistemas de control y seguridad y dispositivos remotos detrás de firewalls y
aislarlos de la red empresarial.

- Instale controles físicos para que ningún personal no autorizado pueda acceder a su control industrial
y sistemas de seguridad, componentes, equipos periféricos y redes.

- Coloque todos los controladores en gabinetes cerrados con llave y nunca los deje en el modo "Programa".

- Nunca conecte el software de programación a ninguna red que no sea la red del
dispositivos a los que está destinado.

- Escanee todos los métodos de intercambio de datos móviles con la red aislada, como CD, USB
unidades, etc. antes de su uso en los terminales o cualquier nodo conectado a estas redes.

- Nunca permita que dispositivos móviles que se hayan conectado a cualquier otra red además de la
red prevista para conectarse a las redes de seguridad o control sin un saneamiento adecuado.

- Minimizar la exposición de la red para todos los dispositivos y sistemas del sistema de control y garantizar que
no son accesibles desde Internet.

- Cuando se requiera acceso remoto, utilice métodos seguros, como redes privadas virtuales (VPN). Reconocer que las VPN pueden tener vulnerabilidades y deben actualizarse al versión más actual disponible.

## CVE-2023-20805
### Descripción

El producto escribe datos pasados en el final o antes del comienzo del bufer previsto. Normalmente, esto puede provocar daños en los datos, un bloqueo o la ejecuccion del codigo. El producto puede modificar un indice o realizar un aritmetica que haga referencia a una ubicación de memoria que este de los limites del bufer. Una operacion de escritura posterior produce resultados indefinidos o inesperados. En resumen, puede ocurrir Corrupción de memoria.

## Referencias
https://cwe.mitre.org/data/definitions/787.html

### Impacto
- Base Score: [6.7 MEDIUM](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2023-20805&vector=AV:L/AC:L/PR:H/UI:N/S:U/C:H/I:H/A:H&version=3.1&source=NIST)
  
- Vector: [CVSS:3.1/AV:L/AC:L/PR:H/UI:N/S:U/C:H/I:H/A:H](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2023-20805&vector=AV:L/AC:L/PR:H/UI:N/S:U/C:H/I:H/A:H&version=3.1&source=NIST)

- Sistemas afectados: En C, C++, en la clase Assembly y en tecnologia, en la clase: ICS/OT.

### Explotación

Impacto tecnico: modificar la memoria; DoS: Bloqueo, Salir o Reiniciar; Ejecutar código o
comandos no autorizados.

### Solución

- Utilizar un lenguaje que no permite este tipo de debilidades o proporcionar estructuras que
hagan esta debilidad sea más facil de evitar.
- Utilizar una biblioteca que no produzca esta debilidad como Safe C String (SafeSTR).
- Utlizar mecanismos automáticos de detección de desbordamiento del bufer que ofrecen determinados compiladores o
extensiones de compilador como Visual Studio /GS.
- Remplazar las funciones de copia ilimitadas con funciones análogas que admitan argumentos de longitud como strcpy.
- Utilizar una CPU y un SO que ofrezca proteccion de ejecución de datos o técnicas equivalentes que simulen esta
caracteristica.
- Ejecutar o compilar el software utilizando funciones o extensiones que organizan aleatoriamente las posiciones del ejecutable y las bibliotecas de un programa en la memoria.

## CVE-2023-38435
### Descripción

El producto no neutraliza o neutraliza incorrectamente la entrada controlable por el usuario antes de colocarla en la salida que se utiliza como una pagina web que se sirve a otros usuarios. Los datos que no son de confianza ingresan a una aplicación web. La aplicacion web genera dinamicamente una pagina web que contiene estos datos que no son de confianza. Durante la generacion de la pagina, la aplicacion no impide que los datos contengan contenido ejecutable mediante un navegador web. Una victima visita la pagina web generada a través de un navegador web, que contiene un script malicioso que se inyectó utilizando datos que no son de confianza. Dado que el script proviene de una página web enviada por el servidor web, el navegador web, el navegador web de la
victima ejecuta el script malicioso en el contexto del dominio del servidor Esto viola efectivamente la intención de la politica del mismo origen del navegador web, que establece que los scripts en un dominio no deberian poder acceder a recursos ni ejecutar codigo en un dominio diferente.

## Referencias
https://cwe.mitre.org/data/definitions/79.html

### Impacto
- Base Score: [6.1 MEDIUM](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2023-38435&vector=AV:N/AC:L/PR:N/UI:R/S:C/C:L/I:L/A:N&version=3.1&source=NIST)
  
- Vector: [CVSS:3.1/AV:N/AC:L/PR:N/UI:R/S:C/C:L/I:L/A:N](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2023-38435&vector=AV:N/AC:L/PR:N/UI:R/S:C/C:L/I:L/A:N&version=3.1&source=NIST)

- Sistemas afectados: Basado en Web.

### Explotación

Confidencialidad del control de acceso, Integridad, Confidencialidad, Disponibilidad, Control de Acceso...


### Solución

- Utilizar una biblioteca o un marco examinado que no permita que se produzca esta debilidad o que proporcione estructuras que hagan que esta debilidad sea más fácil de evitar.
- Comprender el contexto en el que se utilizarán sus datos y la codificación que se esperará.
- Comprender todas las áreas potenciales donde las entradas que no son de confianza pueden ingresar a su software: parámetros o argumentos, cookies, cualquier cosa leída de la red, variables de entornos...
- Para cualquier control de seguridad que se realice en el lado del cliente, asegúrense de que estos controles estén dupicados en el lado del servidor.
- Si esta disponible, utilice mecanismos estructurados que apliquen automáticamente la separación entre datos y código.
- Utilice y especifique una codificación de salida que pueda ser manejada por el componente descendente que esta leyendo la salida.
- Configurar la cookie de sesión en HttpOnly.
- Utilizar una estrategia de validación  de entradas  de aceptar bienes conocidos, es decir, utilizar una lista de entradas aceptables que se ajusten estrictamente a las especificaciones.
- Crear una asignación a partir de un conjunto de valores de entradas fijos a los nombres de archivos o URL reales y rechace todas las demás entradas.
- Utilizar un firewall de aplicaciones que puede detectar ataques contra esta debilidad.
- Cuando utilice PHP, configurar la aplicación para que no utilice Register globals.

## CVE-2022-31503

### Descripción

El repositorio orchest/orchest anterior a 2022.05.0 en GitHub permite un recorrido de ruta absoluto porque la función Flask send_file se usa de manera insegura.

### Referencias

[https://github.com/github/securitylab/issues/669#issuecomment-1117265726](https://github.com/github/securitylab/issues/669#issuecomment-1117265726)

[https://github.com/orchest/orchest/pull/913](https://github.com/orchest/orchest/pull/913)

[https://github.com/orchest/orchest/releases/tag/v2022.05.0](https://github.com/orchest/orchest/releases/tag/v2022.05.0)

### Impacto

- Base Score: [9.3 Critico](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2022-31503&vector=AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:N/A:L&version=3.1&source=NIST)
- Vector: [CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:N/A:L](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2022-31503&vector=AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:N/A:L&version=3.1&source=NIST)
- Sistemas Afectados: Orchest/orchest anterior a la versión 2022.05.0 

### Explotación

- Clase: Recorrido de ruta absoluta
  
  Gracias a la función Flask send_file un archivo cargado en orchest nos puede dar acceso a la ruta raiz.
  
- CWE: [CWE22](https://cwe.mitre.org/data/definitions/22.html)

### Solución

- Actualizar Orchest a una versión más nueva.
- Eliminar rutas no seguras en los modulos de los proyectos.

## CVE-2022-24877

### Descripción

Flux es una solución de entrega continua abierta y extensible para Kubernetes. Path Traversal en el controlador kustomize a través de un `kustomization.yaml` malicioso permite a un atacante exponer datos confidenciales del sistema de archivos pod del controlador y posiblemente una escalada de privilegios en implementaciones de múltiples inquilinos. Las soluciones alternativas incluyen herramientas automatizadas en la canalización de CI/CD del usuario para validar que los archivos `kustomization.yaml` cumplan con políticas específicas. Esta vulnerabilidad se solucionó en kustomize-controller v0.24.0 y se incluyó en flux2 v0.29.0.

### Referencias

[https://github.com/fluxcd/flux2/security/advisories/GHSA-j77r-2fxf-5jrw](https://github.com/fluxcd/flux2/security/advisories/GHSA-j77r-2fxf-5jrw)

### Impacto

- Base Score: [8.8 Alto](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2022-24877&vector=AV:N/AC:L/PR:L/UI:N/S:U/C:H/I:H/A:H&version=3.1&source=NIST)
- Vector: [CVSS:3.1/AV:N/AC:L/PR:L/UI:N/S:U/C:H/I:H/A:H](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2022-24877&vector=AV:N/AC:L/PR:L/UI:N/S:U/C:H/I:H/A:H&version=3.1&source=NIST)
- Sistemas Afectados: Flux2 versión anterior a 0.29.0 y Kustomize-controller versión anterior a 0.24.0

### Explotación

- Clase: Exposición de datos confidenciales y posible escalada de privilegios.

  A traves de un fichero .yaml malicioso permite al atacante no solo exponer datos confidenciales si no que además permite una escalada de privilegios en implementaciones de múltiples inquilinos.
  
- CWE: [CW22](http://cwe.mitre.org/data/definitions/22.html) y [CWE36](http://cwe.mitre.org/data/definitions/36.html)

### Solución

- Actualizar flux2 a una versión posterior a la versión afectada ya que la nueva versión parcheada tiene un nuevo fichero yaml.
- Actualizar Kustomize-coontroller a una versión posterior a la afectada ya que la nueva versión parcheada tiene un nuevo fichero yaml.

## CVE-2020-10987

### Descripción

El goform/setUsbUnload endpoint de Tenda AC15 AC1900 versión 15.03.05.19 permite a atacantes remotos ejecutar comandos del sistema de su elección a través del parámetro POST deviceName.

### Referencias

[https://nvd.nist.gov/vuln/detail/CVE-2020-10987](https://nvd.nist.gov/vuln/detail/CVE-2020-10987)

[https://blog.securityevaluators.com/tenda-ac1900-vulnerabilities-discovered-and-exploited-e8e26aa0bc68](https://blog.securityevaluators.com/tenda-ac1900-vulnerabilities-discovered-and-exploited-e8e26aa0bc68)

[https://www.fortiguard.com/encyclopedia/ips/49352](https://www.fortiguard.com/encyclopedia/ips/49352)

### Impacto

- Base Score: [9.8 CRITICAL](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2020-10987&vector=AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H&version=3.1&source=NIST)
- Vector: [CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2020-10987&vector=AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H&version=3.1&source=NIST)
- Sistemas Afectados: Tenda AC15 AC1900

### Explotación

El atacante puede cambiar el parámetro deviceName de tu enrutador y ejecutar comandos arbitrarios.  
CWE: [CWE-78](https://cwe.mitre.org/data/definitions/78.html)

### Solución

Actualmente no se conoce ningún parche proporcionado por el proveedor ni actualizaciones disponibles para este problema.

## CVE-2021-0920

### Descripción

Se descubrió un problema en el sistema operativo Linux que afecta a la forma en que se manejan ciertos tipos de conexiones de red llamadas "sockets de dominio Unix". Este problema puede llevar a que el sistema no limpie adecuadamente cierta información, lo que podría causar un mal uso de la memoria y, en última instancia, hacer que el sistema se bloquee o permitir que un usuario local aumente sus privilegios en el sistema.

### Referencias

[https://www.cve.org/CVERecord?id=CVE-2021-0920](https://www.cve.org/CVERecord?id=CVE-2021-0920)

[https://nvd.nist.gov/vuln/detail/cve-2021-0920](https://nvd.nist.gov/vuln/detail/cve-2021-0920)

[https://googleprojectzero.github.io/0days-in-the-wild//0day-RCAs/2021/CVE-2021-0920.html](https://googleprojectzero.github.io/0days-in-the-wild//0day-RCAs/2021/CVE-2021-0920.html)

[https://access.redhat.com/security/cve/cve-2021-0920](https://access.redhat.com/security/cve/cve-2021-0920)

### Impacto

- Base Score: [6.9 MEDIUM](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2021-0920&vector=AV:L/AC:H/PR:H/UI:N/S:U/C:H/I:H/A:H&version=3.1&source=NIST)
- Vector: [AV:L/AC:M/Au:N/C:C/I:C/A:C](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2021-0920&vector=AV:L/AC:H/PR:H/UI:N/S:U/C:H/I:H/A:H&version=3.1&source=NIST)
- Sistemas Afectados: AndroidVersions: Android kernelAndroid ID: A-196926917

### Explotación

En unix_scm_to_skb de af_unix.c, existe un posible error que podría conducir a una escalada local de privilegios. 

La interacción del usuario no es necesaria para la explotación.

CWE: [CWE-416](https://cwe.mitre.org/data/definitions/416.html)  y [CWE-362](https://cwe.mitre.org/data/definitions/362.html)

### Solucion

La mitigación para este problema no está disponible.

## CVE-2023-34476
### Descripción

El producto construye todas o parte de un comando SQL usando entradas externas de un componente, pero que no neutraliza o neutraliza incorrectamente elementos especiales que pueda modificar el comando SQL intencionado.

Sin suficientes citas o retiradas de la sintaxis SQL en las entradas por usuario, la consulta generada de SQL puede causar que esas entradas puedan ser interpretadas como SQL en vez de datos de usuario ordinario.

### Referencias

Origen: https://cwe.mitre.org/data/definitions/89.html

### Impacto

- Base Score: [9.8 CRITICAL](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2023-34476&vector=AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H&version=3.1&source=NIST)
- Vector: [CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2023-34476&vector=AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H&version=3.1&source=NIST)
- Sistemas Afectados: Servidores de Bases de Datos

### Explotación

- Confidencialidad.
- Control de Acceso
- Integridad

### Soluciones

- Usar una libreria o framework verificado que no permita que se produzca la debilidad, o provea construcciones que hagan más fácil de evadir.
- Si es posible, usar mecanismos estructurados para enforzar automáticamente la separación entre datos y código.
- Correr el código usando los menores privilegios requeridos para cumplimentar las tareas necesarias si es posible, crear cuentas aisladas con privilegios limitados para solo usarse en tareas únicas.
- Específicamente, seguir el principio del menor privilegio cuando se crean cuentas de usuario en una base de datos SQL.
- Los usuarios solo deberian de tener los privilegios mínimos necesarios para usar su cuenta.
- Si los requerimientos del sistema indican que un usuario puede leer y modificar sus propios datos, entonces limitar sus privilegios para que no pueda leer o escribir los datos de los demás.
- Usar los permisos más estrictos posibles en todos los objetos de la base de datos.
- Cuando el set de objetos aceptables, como nombres de archivos o URLs, es limitado o conocido, crear un mapa de todos los sets de valores fijos a poner, (como IDs numéricos) de los nombres de archivos o URL actuales, y rechazar el resto.
- Por cualquier chequeo de seguridad que se haya realizado en el lado del cliente, asegurar de que esos chequeos son duplicados en el lado del servidor.
- Aunque sea arriesgado usar lineas dinámicamente generadas, código, o comandos que mezclan control y datos, algunas veces no puede seer evitado.
- Asumir que todo input es malicioso.
- Cuando se realiza la validación de input, considerr que todas las propiedades relevantes, incluyendo longitud, tipo de input, el rango completo de valores aceptables, etc.
- No confiar exclusivamente en buscar inputs maliciosos o mal formados.
- Cuando se construyan consultas de SQL, usar las listas de permisos más estricta para limitar el set de carácteres para el valor del parámetro en la petición.
- Asegurar que el mensaje de error solo contenga los detalles mínimos para ayudar a la audiencia objetivo y nadie más.
- En el contexto de las Inyecciones SQL, los mensajes de error relevando la estructura de una consulta SQL puede ayudar a los atacantes a refinar sus ataques.
- Usar una aplicación de cortafuegos puede detectar ataques contra esta debilidad.
- Cuando se usa PHP, configura la aplicación para que no use register_globals.

