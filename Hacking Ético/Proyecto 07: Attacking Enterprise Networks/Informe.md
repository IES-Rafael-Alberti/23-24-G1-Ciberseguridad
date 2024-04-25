# Proyecto 7: Attacking Enterprise Networks

### Índice


# Formulario de autorización de Pentesting

**Cliente:** CyberSecPro S.A.

**Fecha de inicio del pentesting:** 23/04/2024

**Fecha de finalización del pentesting: 25**/04/2024

### **Objetivo del Pentesting**

Asegurar la integridad de la información de los sistemas y los clientes con un análisis exhaustivo debido a un aviso de posibles vulnerabilidades en sus servidores  y emplear técnicas avanzadas de post-explotación para simular la escalada de privilegios, la persistencia y el pivoting dentro de la red.

### Alcance

La prueba debe realizarse en los siguientes dominios y rangos de red:

- "External" facing target host: 192.168.68.166
- Rango de red interno: 10.10.10.0/24
- Rango de red interno: 10.10.20.0/24
- Rango de red interno: 10.10.30.0/24

Se permiten técnicas de prueba automatizadas, como la enumeración y el escaneo de vulnerabilidades, siempre y cuando no causen interrupciones del servicio. Las siguientes acciones están fuera del alcance de la evaluación:

- Phishing / Ingeniería social.
- Acciones destructivas o pruebas de Denegación de Servicio (DoS).
- Modificaciones en el entorno sin el consentimiento escrito del personal de TI autorizado.

## Duración

La prueba debe ser realizada en un plazo de 72 horas. La prueba se puede realizar las 24 horas del día, pero se solicita que cualquier escaneo de vulnerabilidades pesadas se realice fuera del horario laboral regular (después de las 19:00 hora de Cádiz).

### **Acuerdo de Confidencialidad**

Es considerado como información clasificada o confidencial toda la información que sea proporcionado por la empresa “CyberSecPro S.A.” y que esté incluida en los sistemas designados en el Ámbito, no pudiendo ser divulgada a terceros bajo ningún concepto exceptuando con permiso previo de la empresa u orden judicial expresa. En esta información está incluída los datos técnicos, financieros, documentos, u otro tipo de información que pueda recopilarse en todas sus formas.

### **Autorización del Pentesting**

- Autorizo al Grupo 1, y a sus empleados o agentes designados, a llevar a cabo pruebas de penetración en los sistemas especificados en el ámbito del pentesting, según lo descrito en el objetivo.
- Autorizo al Grupo 1 a realizar todas las pruebas que se vean necesarias, siempre y cuando la integridad de los sistemas no se vea afectada.
- Autorizo al Grupo 1 a usar todas las herramientas que tengan disponibles para las pruebas.
- Autorizo al Grupo 1 a realizar pruebas que puedan causar interrupciones o perturbaciones en los sistemas, redes, aplicaciones o servicios especificados en el ámbito del pentesting.
- Autorizo al Grupo 1 a realizar pruebas que puedan generar falsos positivos o alertas de seguridad en los sistemas de detección de intrusiones o sistemas de prevención de intrusiones.
- Autorizo al Grupo 1 a realizar pruebas que puedan generar tráfico de red adicional o aumentar el uso de recursos en los sistemas, redes, aplicaciones o servicios especificados en el ámbito del pentesting.
- Autorizo al Grupo 1 a realizar pruebas que puedan generar registros de auditoría o eventos de seguridad adicionales en los sistemas, redes, aplicaciones o servicios especificados en el ámbito del pentesting.
- Autorizo al Grupo 1 a recopilar y analizar datos de los sistemas, redes, aplicaciones o servicios especificados en el ámbito del pentesting, con el fin de identificar vulnerabilidades o riesgos de seguridad.
- Autorizo al Grupo 1 a utilizar los datos recopilados durante el pentesting únicamente con fines de evaluación de seguridad y para generar recomendaciones de mejora de seguridad.
- Solicito al Grupo 1 a proporcionarme un informe detallado de los resultados del pentesting, incluyendo una descripción de las vulnerabilidades o riesgos de seguridad identificados, una evaluación de su gravedad y una recomendación de medidas de mitigación o corrección.
- Solicito al Grupo 1 a proporcionarme asistencia y asesoramiento en la implementación de las medidas de mitigación o corrección recomendadas.

### Permisos solicitados por los pentesters

Se solicita permiso de la empresa cliente para realizar un cambio en el firewall una vez ya vulnerado el primer equipo para poder realizar el pivoting correctamente.

### **Tarifas y pagos**

El Cliente aceptará desembolsar el pago por el servicio recibido del Proveedor, en un acuerdo financiero donde se especificarán todas las tarifas asociadas que deberá presentarse junto con este documento y firmado al mismo tiempo.

**Firma del cliente:** “CyberSecPro S.A.”

**Fecha: 22**/04/2024

---

### **Índices de gravedad de los hallazgos**

Los resultados presentados en las tablas son el producto de análisis de vulnerabilidades realizados en los objetivos dados por la empresa. Estos análisis han revelado una diversidad de vulnerabilidades que abarcan diferentes niveles de riesgo y criticidad.

| Riesgo | PC1 | PC2 | PC3 | PC4 | PC5 |
| --- | --- | --- | --- | --- | --- |
| Crítico | 1 |  |  |  |  |
| Alto |  | 1 |  |  |  |
| Medio |  |  |  | 2 |  |
| Bajo |  |  |  |  |  |
| Información |  |  |  |  |  |

### Factores de riesgos

Los factores de riesgo de CVSS, aplicados a los hallazgos de vulnerabilidades nos ofrecen una visión detallada de la criticidad de cada vulnerabilidad, desde aquellas con impacto limitado hasta aquellas con consecuencias devastadoras. 

| Nivel de Criticidad | Puntuaciones | Descripción de la Criticidad |
| --- | --- | --- |
| Bajo | 0.0 - 3.9 | Vulnerabilidades con impacto limitado o que requieren condiciones poco probables para ser explotadas. |
| Medio | 4.0 - 6.9 | Vulnerabilidades con un impacto moderado que pueden ser explotadas bajo ciertas condiciones. |
| Alto | 7.0 - 8.9 | Vulnerabilidades con un impacto significativo y que pueden ser fácilmente explotadas. |
| Crítico | 9.0 - 10.0 | Vulnerabilidades con un impacto devastador y que pueden ser explotadas de manera trivial o sin requerir autenticación. |

# Resultados técnicos

### PC1

Remote Desktop Services Remote Code Execution Vulnerability

| Descripción: | Existe una vulnerabilidad de ejecución remota de código en los Servicios de Escritorio Remoto, cuando un atacante no autenticado se conecta al sistema de destino utilizando RDP y envía solicitudes especialmente diseñadas. |
| --- | --- |
| CVSS v3.0 | 9.80 |
| CVE/CWE | https://www.incibe.es/incibe-cert/alerta-temprana/vulnerabilidades/cve-2019-0708 |
| Riesgos: | CRÍTICA |
| Impacto: | Puede acceder a todo el sistema, adquiriendo toda la información del equipo y provocando que la información confidencial pueda ser adquirida, modificada o destruida. |
| Sistemas | PC01 |
| Remediación: | 1. Parches y Actualizaciones: Verifica que todos los sistemas afectados estén actualizados con los últimos parches de seguridad proporcionados por el proveedor, ya sea Microsoft u otro proveedor de servicios RDS.

2. Auditoría de Seguridad: Realiza una auditoría de seguridad en tus sistemas RDS para identificar cualquier actividad sospechosa o compromiso potencial.

3. Restricción de Acceso: Limita el acceso a los servicios RDS solo a usuarios autorizados y a través de conexiones seguras como VPN.

4. Firewalls y Reglas de Seguridad: Configura firewalls y reglas de seguridad para restringir el tráfico no autorizado hacia y desde los servidores RDS |
| Referencias: | https://packetstormsecurity.com/files/162960/Microsoft-RDP-Remote-Code-Execution.html |
| Prueba de Concepto |  |

![Untitled](img-informe/Untitled.png)

![Untitled](img-informe/Untitled%201.png)

### PC2

Site Editor Local File Inclusion

| Descripción: | La versión del plugin Site Editor 1.1.1 del Wordpress permite al atacante recuperar archivos a través del parámetro ajax_path en editor/extensions/pagebuilder/includes/ajax_shortcode_pattern.php, |
| --- | --- |
| CVSS v3.0 | 7.5 |
| CVE/CWE | https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-7422 |
| Riesgos: | Alto |
| Impacto: | Permite al atacante acceder a archivos posiblemente confidenciales del servidor, haciendo una violación de la confidencialidad y posible integridad de los archivos. |
| Sistemas | PC02 |
| Remediación: | Desinstalar el plugin, actualizar a su versión mas reciente o utilizar plugin similar.
 |
| Referencias: | https://www.exploit-db.com/exploits/44340/ |
| Prueba de Concepto |  |

![Untitled](img-informe/Untitled%202.png)

### PC4

Acceso a archivos locales

| Descripción: | La versión de PHP que se está ejecutando en el servidor se ve afectada por una vulnerabilidad de inclusión de archivos locales debido al carácter especial nulo que rompe la ruta en la función XML |
| --- | --- |
| CVSS v3.0 | 5.3 |
| CVE/CWE | https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-21707 |
| Riesgos: | Medio |
| Impacto: | Esto provoca que pueda subirse código arbitrario que sea usado para infectar el servidor, llegando a insertar todo tipo de programas nocivos o intentar acceder al propio servidor. |
| Sistemas | PC04 |
| Remediación: | Actualizar la versión de PHP  |
| Referencias: | https://www.tenable.com/plugins/was/113061 |
| Prueba de Concepto |  |

![Untitled](img-informe/Untitled%203.png)

Firma SMB no se requiere

| Descripción: | Un atacante remoto puede aprovechar esto para realizar ataques de intermediario contra el servdior SMB |
| --- | --- |
| CVSS v3.0 | 5.3 |
| CVE/CWE | https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2016-2115 |
| Riesgos: | Medio |
| Impacto: | Esta vulnerabilidad puede provocar que un usuario ajeno a la organización pueda entrar en el servidor, y acceder a información confidencial, además de alterarla o incluso provocar su destrucción. |
| Sistemas | PC04 |
| Remediación: | Aplicar la firma de mensajes en la configuración del host. En Windows, esto se encuentra en el ajuste de política ‘Servidor de red de Microsoft: Firmar comunicaciones(siempre)’. En Samba, el ajuste se llama ‘firmar servidor’. |
| Referencias: | https://www.tenable.com/plugins/nessus/57608 |
| Prueba de Concepto | ![Untitled](img-informe/Untitled%204.png) ![2024-04-25 01_55_32-Kali Linux Nessus & OpenVAS (Instantánea 7) [Corriendo] - Oracle VM VirtualBox.png](img-informe/2024-04-25_01_55_32-Kali_Linux_Nessus__OpenVAS_(Instantnea_7)_Corriendo_-_Oracle_VM_VirtualBox.png) |




