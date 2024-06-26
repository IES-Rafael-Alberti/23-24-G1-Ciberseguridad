# Análisis de Vulnerabilidades

# Índice
1. [Máquina Windows Server 2008](#2008)      
    1.1 [ManageEngine Desktop Central 8 / 9 < Build 91100 Multiple RCE](#Manage)   
    1.2 [MySQL Default Account Credentials](#MySQL)   
    1.3 [Apache Tomcat AJP Connector Request Injection (Ghostcat)](#Apache)   
    1.4 [MS11-030: Vulnerability in DNS Resolution Could Allow Remote Code Execution](#MS11)      
    1.5 [MS17-010: Security Update for Microsoft Windows SMB Server (4013389) (ETERNALBLUE) (ETERNALCHAMPION) (ETERNALROMANCE) (ETERNALSYNERGY) (WannaCry) (EternalRocks) (Petya) (uncredentialed check)](#MS17)  
    1.6 [MS12-020: Vulnerabilities in Remote Desktop Could Allow Remote Code Execution](#MS12)  
    1.7 [Information Exposure](#Information)  
    1.8 [OpenSSH User enumeration vulnerability](#OpenSSH)  
    1.9 [SNMP Agent Default Community Name (public)](#SNMP)  
    1.10 [Microsoft Windows LAN Manager SNMP LanMan Services Disclosure](#Microsoft)   
    1.11 [Microsoft Windows LAN Manager SNMP LanMan Users Disclosure](#Windows)  
2. [Máquina Windows Server 2016](#2016)  
   2.1 [MS17-010: Security Update for Microsoft Windows SMB Server (4013389) (ETERNALBLUE) (ETERNALCHAMPION) (ETERNALROMANCE) (ETERNALSYNERGY) (WannaCry) (EternalRocks) (Petya) (uncredentialed check)](#Security)   

## Máquina Windows Server 2008 <div id='2008' />
### ManageEngine Desktop Central 8 / 9 < Build 91100 Multiple RCE <div id='Manage' />
#### (SUBIDA SIN RESTRICCIONES DE FICHEROS DE TIPOS PELIGROSOS)

|Descripción:|<p>La aplicación ManageEngine Desktop Central funcionando en el host remoto es versión 8, o la versión 9 antes de la estructura 91100, por lo que es afectado por múltiples vulnerabilidades de código remoto:</p><p>- Un fallo existe en el script statusUpdate debido a un fallo de sanitizar apropiadamente el input de los usuarios en el parámetro ‘fileName’. Un atacante remoto sin autenticar puede explotar esto, mediante una petición creada para subir un archivo PHP que tiene múltiples extensiones de archivo y, mediante la manipulación del parámetro ‘applicationName’, hacen una petición directa al archivo subido, resultando en la ejecución de código arbitrario con privilegios NT-AUTHORITY/SYSTEM. (CVE-2015-8201)</p><p>-Un fallo no especificado existe en varios servlets que permiten a un atacante remoto no autenticado ejecutar código arbitrariamente. No existen más detalles.</p>|
| - | :- |
|CVSS v3.0|6\.0|
|CVE/CWE|[CVE-2015-8201](https://nvd.nist.gov/vuln/detail/CVE-2015-8201)|
|Riesgos:|Críticos|
|Impacto:|El atacante puede entrar a la maquina y a partir, de ahí, conseguir información y permisos necesarios|
|Sistemas|192\.168.106.144|
|Remediación:|Actualizar ManageEngine Desktop Central versión 9 build 91100 o posterior.|
|Referencias:|[CVE-2015-8201](https://nvd.nist.gov/vuln/detail/CVE-2015-8201)|
|Prueba de Concepto| <p> ![](imagenes/Untitled.png) </p> <p>![](imagenes/Untitled_1.png)</p>|

### MySQL Default Account Credentials <div id='MySQL' />
#### (Acceso a la base de datos con credenciales por defecto)

|Descripción:|El componente MySQL en Plixer Scrutinizer v9.0.1.19899 y versiones anteriores tiene una contraseña predeterminada de admin para las cuentas, lo que permite a atacantes remotos ejecutar comandos SQL arbitrarios a través de una sesión TCP.|
| - | :- |
|CVSS v3.0|9\.8|
|CVE/CWE|[CVE-2012-3951](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-3951)|
|Riesgos:|Críticos|
|Impacto:|Un atacante remoto puede acceder y modificar la BD.|
|Sistemas|192\.168.106.144|
|Remediación:|Eliminar/cambiar las contraseñas de las cuentas afectadas.|
|Referencias:|[CVE-2012-3951](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-3951),[ NVD](https://nvd.nist.gov/vuln/detail/CVE-2012-3951)|
|Prueba de Concepto|<p>![](imagenes/Untitled_2.png)</p>|

### Apache Tomcat AJP Connector Request Injection (Ghostcat) <div id='Apache' />

|Descripción:|Una vulnerabilidad de lectura/inclusión de archivo ha sido encontrada en el conector AJP. Un atacante remoto no autenticado puede explotar esta vulnerabilidad para leer archivos de aplicaciones web de un servidor vulnerable. En instancias donde el servidor vulnerable permite subidas de archivos, un atacante podría subir códigos de JavaServer Pages (JPS) maliciosos conteniendo una variedad de tipos de archivos y ganar ejecución de códigos remotos (RCE).|
| - | :- |
|CVSS v3.0|9\.8|
|CVE/CWE|[CVE-2020-1938](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-1938),[ CVE-2020-1745](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-1745)|
|Riesgos:|Críticos|
|Impacto:|El atacante puede leer documentos que hay dentro del servidor|
|Sistemas|192\.168.106.144|
|Remediación:|<p>Actualizar la configuración AJP para requerir autorización y/o actualizar el servidor Tomcat a 7.0.100, 8.5.5.51, 9.0.31</p><p>o superior</p>|
|Referencias:|[CVE-2020-1938](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-1938),[ CVE-2020-1745](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-1745)|
|Prueba de Concepto|<p>![](imagenes/Untitled_3.png)</p>|

### MS11-030: Vulnerability in DNS Resolution Could Allow Remote Code Execution <div id='MS11' />



|Descripción:|<p>Hay un fallo en la forma en el que el cliente DNS de el Windows instalado procesa las consultas de Resolución de Nombre Multicast de Enlace Local (LLMNR) puede ser explotada para ejecutar código arbitario en el contexto de la cuenta Network Service.</p><p>Es importante tener en cuenta que Windows XP y 2003 no admiten LLMNR y la explotación existosa en esas plataformas requiere acceso local y la capacidad de ejecutar una aplicación especial. Sin embargo, en Windows Vista 2008, 7 y 2008 R2, el porblema puede ser explotado de forma remota.</p>|
| - | :- |
|CVSS v3.0|8\.3|
|CVE/CWE|[CVE-2011-0657](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2011-0657)|
|Riesgos:|Críticos|
|Impacto:|Un atacante puede provocar el agotamiento de la pila o potencialmente causar la corrupción de la memoria de la pila y producir ejecución de código.|
|Sistemas|192\.168.106.144|
|Remediación:|Microsoft ha lanzado un conjunto de parches para Windows XP, 2003, Vista, 2008, 7 y 2008 R2.|
|Referencias:|[CVE-2011-0657](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2011-0657)|
|Prueba de Concepto|<p>![](imagenes/Untitled_4.png)</p>|

### MS17-010: Security Update for Microsoft Windows SMB Server (4013389) (ETERNALBLUE) (ETERNALCHAMPION) (ETERNALROMANCE) (ETERNALSYNERGY) (WannaCry) (EternalRocks) (Petya) (uncredentialed check) <div id='MS17' />



|Descripción:|<p>El host remoto de Windows se ve afectado por las siguientes vulnerabilidades:</p><p>- Existen múltiples vulnerabilidades de ejecución remota de código en Microsoft Server Message Block 1.0 (SMBv1) debido al manejo incorrecto de ciertas solicitudes. Un atacante remoto no autenticado puede aprovechar estas vulnerabilidades, a través de un paquete especialmente diseñado, para ejecutar código arbitrario. (CVE-2017-0143, CVE-2017-0144, CVE-2017-0145, CVE-2017-0146, CVE-2017-0148)</p><p>- Existe una vulnerabilidad de divulgación de información en Microsoft Server Message Block 1.0 (SMBv1) debido al manejo incorrecto de ciertas solicitudes. Un atacante remoto no autenticado puede explotar esto, a través de un paquete especialmente diseñado, para divulgar información sensible. (CVE-2017-0147)</p><p>- ETERNALBLUE, ETERNALCHAMPION, ETERNALROMANCE y ETERNALSYNERGY son cuatro de múltiples vulnerabilidades y exploits del Grupo Equation divulgados el 14/04/2017 por un grupo conocido como los Shadow Brokers. WannaCry / WannaCrypt es un programa de ransomware que utiliza el exploit ETERNALBLUE, y EternalRocks es un gusano que utiliza siete vulnerabilidades del Grupo Equation. Petya es un programa de ransomware que primero utiliza CVE-2017-0199, una vulnerabilidad en Microsoft Office, y luego se propaga a través de ETERNALBLUE.</p>|
| - | :- |
|CVSS v3.0|8\.1|
|CVE/CWE|[CVE-2017-0143](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0143),[ CVE-2017-0144](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0144), [CVE-2017-0145](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0145),[ CVE-2017-0146](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0146),[CVE-2017-0147](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0147),[ CVE-2017-0148](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0148)|
|Riesgos:|Alto|
|Impacto:|Permite a atacantes remotos ejecutar código arbitrario a través de paquetes manipulados|
|Sistemas|192\.168.106.144|
|Remediación:|<p>Microsoft ha lanzado un conjunto de parches para Windows Vista, 2008, 7, 2008 R2, 2012, 8.1, RT 8.1, 2012 R2, 10 y 2016. Microsoft también ha lanzado parches de emergencia para sistemas operativos Windows que ya no cuentan con soporte, incluidos Windows XP, 2003 y 8.</p><p>Para sistemas operativos Windows no compatibles, como Windows XP, Microsoft recomienda que los usuarios dejen de utilizar SMBv1. SMBv1 carece de características de seguridad que se incluyeron en versiones posteriores de SMB. SMBv1 se puede desactivar siguiendo las instrucciones del proveedor proporcionadas en Microsoft KB2696547. Además, el US-CERT recomienda que los usuarios bloqueen SMB directamente bloqueando el puerto TCP 445 en todos los dispositivos de límite de red. Para SMB sobre la API NetBIOS, bloquee los puertos TCP 137/139 y los puertos UDP 137/138 en todos los dispositivos de límite de red.</p>|
|Referencias:|[CVE-2017-0143](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0143),[ CVE-2017-0144](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0144), [CVE-2017-0145](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0145),[ CVE-2017-0146](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0146),[CVE-2017-0147](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0147),[ CVE-2017-0148](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0148)|
|Prueba de Concepto|<p>![](imagenes/Untitled_5.png)</p>|

### MS12-020: Vulnerabilities in Remote Desktop Could Allow Remote Code Execution <div id='MS12' />


|Descripción:|<p>Existe una vulnerabilidad de código remoto arbitrario en la implementación del Protocolo de Escritorio Remoto (RDP) en el host remoto de Windows. La vulnerabilidad se debe a la forma en que RDP accede a un objeto en memoria que se ha inicializado incorrectamente o se ha eliminado.</p><p>Si se ha habilitado RDP en el sistema afectado, un atacante remoto no autenticado podría aprovechar esta vulnerabilidad para hacer que el sistema ejecute código arbitrario enviándole una secuencia de paquetes RDP especialmente diseñados.</p><p>Este complemento también comprueba una vulnerabilidad de denegación de servicio en Microsoft Terminal Server.</p>|
| - | :- |
|CVSS v3.0|5\.9|
|CVE/CWE|[CVE-2012-0152](http://web.nvd.nist.gov/view/vuln/detail?vulnId=CVE-2012-0152), [CVE-2012-0002](http://web.nvd.nist.gov/view/vuln/detail?vulnId=CVE-2012-0002)|
|Riesgos:|Críticos|
|Impacto:|Permite al atacante realizar un ataque de denegación de servicio, apagando el equipo.|
|Sistemas|192\.168.106.144|
|Remediación:|Microsoft ha publicado un conjunto de parches para Windows XP, 2003, Vista, 2008, 7 y 2008 R2..|
|Referencias:|[https://learn.microsoft.com/en-us/security-u](https://learn.microsoft.com/en-us/security-updates/SecurityBulletins/2012/ms12-020?redirectedfrom=MSDN)|
|Prueba de Concepto|<p>![](imagenes/Untitled_6.png)</p>|


### Information Exposure <div id='Information' />

|Descripción:|El producto expone información confidencial a un tercero que no está explícitamente autorizado a tener acceso a esa información.|
| - | :- |
|CVSS v3.0|-|
|CVE/CWE|[CWE-200](https://cwe.mitre.org/data/definitions/200.html)|
|Riesgos:|Medio|
|Impacto:|Permite al atacante conocer la ubicación del fichero con las credenciales.|
|Sistemas|192\.168.106.144|
|Remediación:|Ajustar las configuraciones para prevenir inputs de los usuarios de manera directa, evitando que pueda hacer rutas directas al servidor.|
|Referencias:|[Information Exposure](https://capec.mitre.org/data/definitions/170.html)|
|Prueba de Concepto|<p>![](imagenes/tomcatinforma.png)</p>|

### OpenSSH User enumeration vulnerability <div id='OpenSSH' />



|Descripción:|Esta vulnerabilidad persiste en los OpenSSH que llegan hasta la versión 7.7, provocando que no se llegue a echar al usuario en una autenticación fallida hasta que el paquete no haya sido totalmente parseado, pudiendo de esa forma revelar información sensible.|
| - | :- |
|CVSS v3.0|5\.3|
|CVE/CWE|[CVE-2018-15473](https://nvd.nist.gov/vuln/detail/CVE-2018-15473)|
|Riesgos:|Medio|
|Impacto:|Permite al atacante obtener información sensible.|
|Sistemas|192\.168.106.144|
|Remediación:|Actualizar el OpenSSH a una versión posterior del 7.7|
|Referencias:|[OpenSSH User numeration vulnerability](https://medium.com/@lcolin250/openssh-7-7-vulnerability-b6886e82f6f6)|
|Prueba de Concepto|<p>![](imagenes/Untitled_7.png)</p>|
</table>

### SNMP Agent Default Community Name (public) <div id='SNMP' />



|Descripción:|<p>Es posible obtener el nombre de comunidad predeterminado del servidor SNMP remoto.</p><p>Un atacante podría utilizar esta información para obtener más conocimiento sobre el host remoto, o para cambiar la configuración del sistema remoto (si la comunidad predeterminada permite tales modificaciones).</p>|
| - | :- |
|CVSS v3.0|7\.5|
|CVE/CWE|[CVE-1999-0517](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-1999-0517)|
|Riesgos:|Alto|
|Impacto:|El atacante puede enumerar la información que ha conseguido, modificar la configuración del sistema y amenazar la confidencialidad y seguridad del equipo|
|Sistemas|192\.168.106.144|
|Remediación:|Desactiva el servicio SNMP en el host remoto si no lo estás utilizando. O bien filtra los paquetes UDP entrantes que van a este puerto, o cambia la cadena de comunidad predeterminada.|
|Referencias:|[CVE-1999-0517](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-1999-0517)|
|Prueba de Concepto|<p>![](imagenes/Untitled_8.png)</p>|


### Microsoft Windows LAN Manager SNMP LanMan Services Disclosure <div id='Microsoft' />

|Descripción:|<p>Es posible obtener la lista de servicios LanMan en el host remoto enviando solicitudes SNMP con el OID 1.3.6.1.4.1.77.1.2.3.1.1.</p><p>Un atacante podría utilizar esta información para obtener más conocimiento sobre el host objetivo.</p>|
| - | :- |
|CVSS v3.0|7\.3|
|CVE/CWE|[CVE-1990-0499](https://nvd.nist.gov/vuln/detail/CVE-1999-0499)|
|Riesgos:|Alto|
|Impacto:|Un atacante puede obtener información valiosa sobre la configuración y los servicios habilitados|
|Sistemas|192\.168.106.144|
|Remediación:|Desactiva el servicio SNMP en el host remoto si no lo estás utilizando, o filtra los paquetes UDP entrantes dirigidos a este puerto.|
|Referencias:|[CVE-1990-0499](https://nvd.nist.gov/vuln/detail/CVE-1999-0499)|
|Prueba de Concepto|<p>![](imagenes/snmpservices.png)</p>|

### Microsoft Windows LAN Manager SNMP LanMan Users Disclosure <div id='Windows' />



|Descripción:|<p>Es posible obtener el nombre de comunidad predeterminado del servidor SNMP remoto.</p><p>Un atacante podría utilizar esta información para obtener más conocimiento sobre el host remoto, o para cambiar la configuración del sistema remoto (si la comunidad predeterminada permite tales modificaciones).</p>|
| - | :- |
|CVSS v3.0|7\.5|
|CVE/CWE|[CVE-1999-0517](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-1999-0517)|
|Riesgos:|Alto|
|Impacto:|Un atacante podría obtener información del host remoto, también tiene posibilidad de cambiar la configuración del sistema, amenaza a la confidencialidad, integridad y disponibilidad e incluso facilita la probabilidad de que se hagan más ataques.|
|Sistemas|192\.168.106.144|
|Remediación:|Desactiva el servicio SNMP en el host remoto si no lo estás utilizando. O bien filtra los paquetes UDP entrantes que van a este puerto, o cambia la cadena de comunidad predeterminada.|
|Referencias:|[CVE-1999-0517](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-1999-0517)|
|Prueba de Concepto|<p>![](imagenes/snmp_users.png)</p>|


## Máquina Windows Server 2016 <div id='2016' />
### MS17-010: Security Update for Microsoft Windows SMB Server (4013389) (ETERNALBLUE) (ETERNALCHAMPION) (ETERNALROMANCE) (ETERNALSYNERGY) (WannaCry) (EternalRocks) (Petya) (uncredentialed check) <div id='Security' />


|Descripción:|<p>El host remoto de Windows se ve afectado por las siguientes vulnerabilidades:</p><p>- Existen múltiples vulnerabilidades de ejecución remota de código en Microsoft Server Message Block 1.0 (SMBv1) debido al manejo incorrecto de ciertas solicitudes. Un atacante remoto no autenticado puede aprovechar estas vulnerabilidades, a través de un paquete especialmente diseñado, para ejecutar código arbitrario. (CVE-2017-0143, CVE-2017-0144, CVE-2017-0145, CVE-2017-0146, CVE-2017-0148)</p><p>- Existe una vulnerabilidad de divulgación de información en Microsoft Server Message Block 1.0 (SMBv1) debido al manejo incorrecto de ciertas solicitudes. Un atacante remoto no autenticado puede explotar esto, a través de un paquete especialmente diseñado, para divulgar información sensible. (CVE-2017-0147)</p><p>- ETERNALBLUE, ETERNALCHAMPION, ETERNALROMANCE y ETERNALSYNERGY son cuatro de múltiples vulnerabilidades y exploits del Grupo Equation divulgados el 14/04/2017 por un grupo conocido como los Shadow Brokers. WannaCry / WannaCrypt es un programa de ransomware que utiliza el exploit ETERNALBLUE, y EternalRocks es un gusano que utiliza siete vulnerabilidades del Grupo Equation. Petya es un programa de ransomware que primero utiliza CVE-2017-0199, una vulnerabilidad en Microsoft Office, y luego se propaga a través de ETERNALBLUE.</p>|
| - | :- |
|CVSS v3.0|8\.1|
|CVE/CWE|[CVE-2017-0143](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0143),[ CVE-2017-0144](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0144), [CVE-2017-0145](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0145),[ CVE-2017-0146](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0146),[CVE-2017-0147](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0147),[ CVE-2017-0148](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0148)|
|Riesgos:|Alto|
|Impacto:|Permite a atacantes remotos ejecutar código arbitrario a través de paquetes manipulados|
|Sistemas|192\.168.1.78|
|Remediación:|<p>Microsoft ha lanzado un conjunto de parches para Windows Vista, 2008, 7, 2008 R2, 2012, 8.1, RT 8.1, 2012 R2, 10 y 2016. Microsoft también ha lanzado parches de emergencia para sistemas operativos Windows que ya no cuentan con soporte, incluidos Windows XP, 2003 y 8.</p><p>Para sistemas operativos Windows no compatibles, como Windows XP, Microsoft recomienda que los usuarios dejen de utilizar SMBv1. SMBv1 carece de características de seguridad que se incluyeron en versiones posteriores de SMB. SMBv1 se puede desactivar siguiendo las instrucciones del proveedor proporcionadas en Microsoft KB2696547. Además, el US-CERT recomienda que los usuarios bloqueen SMB directamente bloqueando el puerto TCP 445 en todos los dispositivos de límite de red. Para SMB sobre la API NetBIOS, bloquee los puertos TCP 137/139 y los puertos UDP 137/138 en todos los dispositivos de límite de red.</p>|
|Referencias:|[CVE-2017-0143](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0143),[ CVE-2017-0144](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0144), [CVE-2017-0145](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0145),[ CVE-2017-0146](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0146),[CVE-2017-0147](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0147),[ CVE-2017-0148](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0148)|
|Prueba de Concepto|<p>![](imagenes/Untitled_9.png)</p>|
