|Descripción:|<p>La aplicación ManageEngine Desktop Central funcionando en el host remoto es versión 8, o la versión 9 antes de la estructura 91100, por lo que es afectado por múltiples vulnerabilidades de código remoto:</p><p>- Un fallo existe en el script statusUpdate debido a un fallo de sanitizar apropiadamente el input de los usuarios en el parámetro ‘fileName’. Un atacante remoto sin autenticar puede explotar esto, mediante una petición creada para subir un archivo PHP que tiene múltiples extensiones de archivo y, mediante la manipulación del parámetro ‘applicationName’, hacen una petición directa al archivo subido, resultando en la ejecución de código arbitrario con privilegios NT-AUTHORITY/SYSTEM. (CVE-2015-8201)</p><p>-Un fallo no especificado existe en varios servlets que permiten a un atacante remoto no autenticado ejecutar código arbitrariamente. No existen más detalles.</p>|
| - | :- |
|CVSS v3.0|6\.0|
|CVE/CWE|[CVE-2015-8201](https://nvd.nist.gov/vuln/detail/CVE-2015-82001)|
|Riesgos:|Críticos|
|Impacto:|El atacante puede entrar a la maquina y a partir, de ahí, conseguir información y permisos necesarios|
|Sistemas|192\.168.106.144|
|Remediación:|Actualizar ManageEngine Desktop Central versión 9 build 91100 o posterior.|
|Referencias:|[CVE-2015-8201](https://nvd.nist.gov/vuln/detail/CVE-2015-82001)|
|Prueba de Concepto| <p> ![](imagenes/Untitled.png) </p> <p>![](imagenes/Untitled_1.png)</p>|



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



