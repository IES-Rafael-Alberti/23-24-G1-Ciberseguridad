# Proyecto 2 Offensive Audit Services.
## Índice  
1. [Investigación de Tipos de Ataque](#id1)
2. [Tipos de Auditoría Ofensiva](#id2)  
3. [Investigación de Metodología del Prentesting](#id3)
4. [Herramientas de Pentesting](#id4)
## Investigación de Tipos de Ataque<a name="id1"></a>
Los ataques informáticos son un intento organizado o intencionado que busca explotar alguna vulnerabilidad o debilidad en las redes informáticas, tanto software como hardware, con el objetivo de tener algún beneficio.

Cada vez las tecnologías de información y comunicación avanzan, llegando a estar más conectadas a Internet, generando más datos con cada acción que se realiza. Aparte de traer muchas ventajas, tiene muchos inconvenientes, debido a que ha traído muchas vulnerabilidades que son aprovechadas por los ciberdelicuentes para robar, secuestrar o destruir cualquier tipo de información que recojan.

Los ataques informáticos se mantendrán e incluso aumentaran con el tiempo, basado en el comportamiento que han tenido a lo largo de los años. Cada día son más numerosos y más sofisticados.

Debido a ello, las medidas de seguridad informáticas se han convertido en una prioridad, especialmente para empresas que dependen casi del 100% de Internet en sus operaciones.

Aquí por ejemplo, vamos a decir algunos tipos de ciberataques:

- Malware -> Es un software malicioso que tiene como objetivo infiltrarse en un sistema para dañarlo.
- Virus -> Es un código que infecta archivos del sistema mediante un código maligno, pero se necesita que el usuario lo ejecute. Una vez en funcionamiento, se extiende por todo el sistema y a todo elemento que tenga acceso nuestra cuenta.
- Gusanos -> Es un programa, que realiza copias del equipo y las extiende por todo Internet. A diferencia del virus, no necesita que un usuario lo ejecute, ya que se puede trasmitir por redes o correo electrónico. Son difíciles de detectar, porque tienen como objetivo infectar a otros equipos y no afectan al funcionamiento del sistema. Se usa principalmente para la creación de botnets, que son granjas de equipos zombis empelados para por ejemplo realizar ataques DDoS a otro sistema.
- Troyanos  -> Son iguales a los virus, pero tienen objetivos distintos. Un troyano busca abrir una puerta trasera para favorecer la entrada de otros programas maliciosos. No se propagan a sí mismo y suelen estar integrados en archivos ejecutables aparentemente inofensivos.
- Spyware -> Es un programa espía, el cual su objetivo es obtener información. Su trabajo suele ser silencioso, pueden recolectar información de nuestro equipo sin despertar nuestra preocupación e incluso instalar otros programas sin que nos demos cuenta.
- AdWare -> Su función principal es la de mostrar publicidad de forma invasiva. Aunque su intención no es la de daños equipos, para algunos puede considerarse como una clase de spyware, ya que puede llegar a recopilar y trasmitir datos para estudiar a los usuarios y orientar mejor el tipo de publicidad.
- Ransomware -> Es uno de los mas modernos y temibles malwares, ya que secuestra datos, encriptandolos y piden un rescate por esos datos. Normalmente, el atacante solicita una transferencia de criptomonedas, para evitar el rastreo de datos y la localización de fondos. Este tipo de ciberataque va en aumento y debido a sus variaciones es de los más temidos de la actualidad. Aquí hay 5 ransomware de los más temidos:
  - REvil -> Es conocido por ser capaz de cifrar gran cantidad de datos en poco tiempo y exigir rescates muy altos a sus víctimas.
  - LockBit -> Es similar a REvil, pero con diferencia de el, publica los datos cifrados de las victimas si no se pagan el rescate.
  - Conti -> Es conocido por ser capaz de apuntar a una amplia gama de victimas. Es conocido por ser muy agresivo en sus tácticas y a        menudo amenaza con publicar los datos cifrados de sus víctimas en línea si no pagan el rescate.
  - Maze -> Estuvo activo hasta 2021. Se hizo famoso por atacar a una serie de empresas grandes.
  - Petya -> Estuvo activo desde 2016 hasta 2017. Es conocido por ser capaz de causar daños devastadores a los ordenadores infectados. Se   propagaba por correos electrónicos de phishing y archivos adjuntos maliciosas. Una vez que se infectaba en un ordenador, cifraba los      archivos y mostraba un mensaje de rescate exigiendo un pago de 300 dólares en Bitcoin.
    
- Doxing  -> Se usa este término para describir la práctica en Internet de investigación y publicación de información privada sobre una persona o una organización, con el propósito de intimidar, humillar o amenazar. Actualmente  se ha estado combinado con el ransomware.
- Phishing -> Se trata de diversas técnicas de “ingeniera Social” como la suplantación de identidad, con el fin de obtener datos privados de las víctimas. Los medios más utilizados son el correo electrónico, mensajería o llamadas telefónicas. Es uno de los ataques más habituales a miembros de una empresa, el cual se buscar usurpar la identidad de la persona por su alto nivel de vulnerabilidad.
- DDoS -> Consiste en realizar tantas peticiones a un servidor, hasta lograr que se colapse y deje de funcionar. Se usa mucho los botnets para realizar este tipo de ataques. Es de los ataques más conocidos,  ya que es muy económica su ejecución y muy difícil de rastrear al atacante. Este tipo de ataques se realiza mucho a servidores de pagina web  o actualmente mucho de estos ataques se realiza a los famosos creadores de contenido.
- Inyección SQL -> Es un ciberataque realizado por el vector de Aplicaciones Web como en los campos de formularios de acceso, registro o búsqueda que explota los errores y vulnerabilidades de una paginan web. Se usa para obtener acceso a la base de datos y dentro de ella robar manipular o destruir la información. Este tipo de ataques suele ocurrir mucho en páginas web, y los ciberdelicuentes pueden robar muchas datos de las páginas web.
- Whaling o “ caza de ballenas” -> Son ataques que van dirigidos a los C-Level de una empresa  ( CEO, CMO, CFO, CIO…) con el objetivo de robarles las credenciales, información critica o clonar sus identidades para Phising o entre otros fines maliciosos. Este tipo de ataque es uno de los importantes, debido a que afecta a solo un tipo de personas y encima  de la mas importantes de la empresa y pueden robar datos muy importantes

Para una empresa los más ataques más importantes que pueden recibir son:

- Malware -> Debido  a que pueden dañar el sistema de una empresa.
- Ramsoware -> Debido a que pueden encriptar los datos y pedir un rescato. Entonces la empresa pierde tiempo y dinero para intentar recuperar esos datos.
- Whaling -> Son ataques que van dirigidos a un grupo especificado de personas, donde puede robar información confidencial de la empresa o datos a futuro.

## Tipos de auditorías de seguridad informática<a name="id2"></a>
No todas las empresas necesitan hacer una auditoría completa de todos sus servicios y activos, por lo que se puede ajustar las auditorías a unas comunes que pueden ser encontradas en todas las empresas generalmente:
### 1. Auditoría de cumplimiento normativo
Esta auditoría revisa si una organización cumple con los requisitos legales y normativos en materia de seguridad de la información. Esto puede abarcar el cumplimiento de leyes de protección de datos, regulaciones específicas de la industria, o estándares internacionales entre otras normativas.

Mediante esta auditoría, se propone el llegar a asegurarse de que no se incumpla ninguna correspondiente a la empresa en específico, y con eso llegar a evitar que; aparte de encontrar vulnerabilidades, problemas legales.
### 2. Auditoría de políticas y procedimientos
Se centra en comprobar y evaluar las políticas, normas y procedimientos de seguridad establecidos en una organización. Su objetivo es averiguar si dichas políticas y procedimientos son adecuados, están actualizados y se cumplen en la práctica.

Esta auditoría como resultado, permite pasar a comprobar si las políticas y procedimientos establecidos en la empresa pueden llegar a cumplirse, y si necesitan alguna renovación con respecto a las nuevas tecnologías.
### 3. Auditoría de controles de acceso
Se centra en evaluar los sistemas y métodos utilizados para controlar el acceso a los sistemas y datos de la organización. Esto incluye la revisión de la gestión de contraseñas, los niveles de privilegios de los usuarios, la autenticación multifactor, entre otros controles que estén relacionados con el acceso o permisos de los usuarios.

Esta auditoría como resultado, permitirá averiguar los puntos flacos dentro del acceso a la red y datos de la empresa, logrando identificarlas y poder mejorar las medidas de autenticación, identificación y permisos de la empresa y evitar accesos no autorizados a futuro.
### 4. Auditoría de seguridad de redes
Se centra en examinar la infraestructura de red de una organización para identificar vulnerabilidades y riesgos de seguridad. Esto abarca pruebas de penetración, análisis de configuración de firewall, detección de intrusiones y evaluación de la protección de la red contra ataques entre otras formas que pueda vulnerar la seguridad de las redes de la empresa u organismo auditado.

Esta auditoría sirve para poder llegar a probar las medidas de seguridad de la empresa en relación con sus redes, anotar todas sus vulnerabilidades y asegurar que las redes no puedan ser vulneradas de una manera fácil, hallando formas para mitigar dichos ataques a futuro.
### 5. Auditoría de seguridad de aplicaciones
Se concentra en evaluar la seguridad de las aplicaciones y sistemas desarrollados o utilizados por la organización. Esto implica revisar el código fuente, la configuración de seguridad de las aplicaciones, la autenticación y autorización de usuarios, así como la protección contra vulnerabilidades comunes que puedan encontrarse en el CVE u otras entidades que catalogan las vulnerabilidades.

Esta auditoría asegura la identificación de las vulnerabilidades dentro de las aplicaciones usadas dentro de la empresa, cómo pueden afectar a la seguridad y la integridad de los datos, además de averiguar cómo pueden ser mitigadas.
### 6. Auditoría de gestión de incidentes
Se ocupa de evaluar los procedimientos y las capacidades de respuesta de una organización ante incidentes de seguridad. Esto incluye examinar la preparación y planificación de incidentes, la detección y notificación de incidentes, la gestión de respuesta y recuperación, y el aprendizaje de lecciones de los incidentes anteriores para poder reaccionar de una mejor manera a las futuras incidencias.

Esta auditoría permite probar la capacidad de reacción de la empresa ante un incidente, su contención y resolución. Es muy importante, debido a que una buena gestión de incidencias permite evitar que se propague al resto de la empresa en caso de que ocurra, además de la posesión del playbook para tenerlo todo recogido.


# Investigación de Metodologías de pentesting <a name="id3"></a>

En esta parte del proyecto vamos a realizar un pequeño estudio de las diferentes metodologías de pentesting que podemos usar a la hora de realizar una auditoria. 

## OSSTMM

El OSSTMM, o Open Source Security Testing Methodology Manual, es una metodología completa desarrollada por ISECOM para llevar a cabo pruebas, análisis y medición de la seguridad operativa real.

 Es una herramienta diseñada para realizar auditorías técnicas de seguridad de manera consistente y repetible.

Esta metodología se puede dividir en varios temas:

- Seguridad de la Información
- Seguridad de los Procesos
- Seguridad en las Tecnologías de Internet
- Seguridad en las Comunicaciones
- Seguridad Inalámbrica
- Seguridad Física

Tambien especifica lo necesario a saber para realizar una auditoria:

- Conceptos básicos (lo que debes saber / lo que debes hacer)
- Metodología de análisis de seguridad
- Métricas de seguridad operacional
- Confiabilidad
- Flujo de trabajo

### Objetivos

El objetivo principal del OSSTMM es construir las mejores defensas de seguridad. Sus objetivos específicos incluyen establecer un enfoque sistemático para auditorías de seguridad más consistentes y repetibles, proporcionar un mecanismo para evaluar los resultados de las auditorías de manera objetiva y permitir una presentación estructurada y comparativa de los resultados.

### Fases de una auditoria

Estas son las fases que deberia de tener una auditoria según OSSTMM:

1. **Lanzar el proyecto:** Esta etapa implica la aprobación de recursos y la conciencia de los posibles impactos no deseados en los sistemas de información.
2. **Fase inductiva:** En esta fase, se comprenden los requisitos, alcance y limitaciones de la auditoría, lo que ayuda a determinar las pruebas a realizar.
3. **Fase interactiva:** Aquí se planifica la auditoría después de definir el alcance y los tipos de pruebas para cada elemento a auditar.
4. **Fase de investigación:** Se analizan los aspectos organizativos y de gestión de la organización, junto con un análisis técnico inicial de fuentes abiertas.
5. **Fase de intervención:** Esta es la fase central de la auditoría, donde se realizan pruebas técnicas en los elementos del alcance, pudiendo modificar, sobrecargar o bloquear elementos para evaluar la seguridad.
6. **Reporte:** Como fase final, se elabora un informe que evalúa los resultados objetivos y valora los hallazgos identificados durante la auditoría.
7. **Resolución de deficiencias:** La organización debe abordar las deficiencias identificadas en la auditoría, utilizando los resultados y valoraciones como base para priorizar las acciones correctivas.

## OWASP Testing Guide

La metodología de pruebas de penetración de OWASP (Open Web Application Security Project) se centra en evaluar la seguridad de las aplicaciones web y ayudar a identificar y abordar vulnerabilidades de seguridad.

### Objetivos

Estos son los objetivos que se definen en OWASP:

1. **Identificar Vulnerabilidades de Seguridad:**
2. **Evaluar la Seguridad de las Aplicaciones Web**
3. **Proporcionar Recomendaciones de Mitigación**
4. **Concienciar sobre la Seguridad**
5. **Ayudar a las Organizaciones a Proteger sus Activos Digitales**
6. **Mejorar la Calidad del Software**
7. **Promover Pruebas de Penetración Éticas**

### Fases

Estas son las fases a la hora de realizar una auditoria según la metodología OWASP:

1. **Fase de Recopilación de Información:** Esta etapa inicial implica reunir datos sobre el objetivo, como información sobre la aplicación, tecnologías utilizadas, arquitectura, etc. También se busca información de dominio público y se lleva a cabo una enumeración de recursos.
2. **Fase de Análisis:** En esta fase, se analizan las vulnerabilidades potenciales, los puntos de entrada y los flujos de datos. Se evalúa la lógica de la aplicación y se identifican posibles vectores de ataque.
3. **Fase de Descubrimiento de Vulnerabilidades:** Aquí es donde se realizan pruebas activas para descubrir vulnerabilidades, como inyecciones SQL, ataques de cross-site scripting (XSS), vulnerabilidades de seguridad en la autenticación y la autorización, entre otras.
4. **Fase de Explotación:** Si se encuentran vulnerabilidades significativas, se intenta explotarlas para evaluar el impacto real de un ataque. Esto puede incluir la obtención de datos confidenciales o la ejecución de código malicioso.
5. **Fase de Informe:** Luego de las pruebas, se genera un informe que documenta todas las vulnerabilidades encontradas, su gravedad y recomendaciones para solucionarlas. Este informe es una herramienta importante para la organización objetivo para mejorar su seguridad.
6. **Fase de Validación:** Después de que se hayan corregido las vulnerabilidades, se realiza una validación para asegurarse de que los problemas identificados se hayan solucionado adecuadamente.
7. **Fase de Documentación y Entrega Final:** La metodología OWASP enfatiza la importancia de documentar todo el proceso de prueba de penetración y entregar esta documentación a la organización objetivo.

## PTES

El Penetration Testing Execution Standard (PTES) es un estándar que proporciona un marco común para realizar pruebas de penetración o pentesting en empresas y proveedores de servicios de seguridad.

### Objetivos

Los objetivos del estándar PTES son los siguientes:

- Disponer de un marco de referencia para la realización de las auditorías técnicas de seguridad de los sistemas de información de una manera más consistente y replicable.
- Incrementar el valor proporcionado por las pruebas de penetración.

### Fases

1. Interacción previa: En esta etapa se define el alcance y las acciones a realizar para llevar a cabo con éxito la prueba de penetración.
2. Recopilación de información: Se recopila información sobre el objetivo a través de fuentes OSINT, inspección y caracterización, considerando medidas de protección que deben evitarse.
3. Modelado de amenazas: Se analiza el contexto interno y externo para identificar elementos que podrían utilizarse en ataques. Se caracterizan los activos y las amenazas para perfilar los tipos de ataques más probables.
4. Análisis de vulnerabilidades: Se buscan fallos en los sistemas que puedan ser aprovechados por atacantes, desde mala configuración hasta diseños inseguros. Estas vulnerabilidades se verifican para su posible explotación.
5. Explotación: Se ejecutan mecanismos para obtener acceso a sistemas o recursos al aprovechar las vulnerabilidades identificadas. Se utilizan exploits y ataques dirigidos.
6. Post-Explotación: Aquí se asegura la persistencia del acceso obtenido, se realizan movimientos laterales para controlar otros activos y se recopila información valiosa.
7. Informe: Implica la elaboración de un informe detallado que resume los resultados técnicos y metodológicos de la prueba, así como un informe ejecutivo que resume los resultados, riesgos y propuestas de mitigación.

# Selección de Metodología

Nostros vamos a escoger la metodología PTES debido a que comparandolo con los demás, veos que es la más completa ya que se centra en todos los ámbitos de la informática y que ofrece la suficiente versatibilidad para cubrirlos. Y vemos que es la que encaja perfectamente con nuestra empresa.

# Herramientasde Pentesting<a name="id4"></a>
**Herramientas para ataque de fuerza bruta**

**THC Hydra**

THC Hydra es una de las herramientas de descifrado de contraseñas más antiguas desarrolladas por “The Hackers Community“. Por el momento, Hydra tiene la mayor cobertura de protocolo que cualquier otra herramienta de descifrado de contraseñas, según nuestro conocimiento, y está disponible para casi todos los sistemas operativos modernos. THC Hydra puede realizar ataques rápidos de diccionario contra muchos protocolos como Telnet, FTP, HTTP, SMB, etc.

Aquí está la sintaxis básica de hydra (versión de Linux) para realizar fuerza bruta a un servicio.

Sintaxis:

Hydra -L administrador -P password.txt <víctima IP> <servicio>

**John the Ripper**

John the Ripper (JTR) es un cracker de contraseña de código abierto; Es uno de los crackers de contraseñas más rápidos y está preinstalado en el sistema operativo Kali Linux. Se puede utilizar para realizar ataques de fuerza bruta y ataques basados ​​en diccionario. También viene con listas de palabras preinstaladas.

- Sitio web oficial: https://www.openwall.com/john/
- Enlace de Github: https://github.com/magnumripper/JohnTheRipper

**Ncrack**

Es una de nuestras herramientas favoritas para descifrar contraseñas. Se basa en las bibliotecas de nmap. Viene preinstalado con Kali Linux OS. Se puede combinar con nmap para obtener excelentes resultados. La única desventaja es que admite muy pocos servicios, a saber, FTP, SSH, Telnet, FTP, POP3, SMB, RDP y VNC.

- Sitio web oficial: https://nmap.org/ncrack/
- Enlace Github: https://github.com/nmap/ncrack

**Cain & Abel** 

Se trata de una herramienta de recuperación de contraseñas para los sistemas operativos de Microsoft. Gracias a ella podemos realizar una fácil recuperación de varios tipos de contraseñas al rastrear la red, descifrar contraseñas cifradas mediante ataques de diccionario, fuerza bruta y criptoanálisis. Además, también podemos grabar conversaciones de VoIP, decodificar contraseñas codificadas, recuperar claves de redes inalámbricas, revelar casillas de contraseñas, descubrir contraseñas almacenadas en caché y analizar el enrutamiento de protocolos. Este programa no explota ninguna vulnerabilidad, sino que busca la obtención de las contraseñas por técnicas convencionales.

Algunos de los beneficios que tiene esta aplicación son:

- Es gratuita, y no tienen ningún tipo de cargo.
- Incluye varios métodos para descifrar contraseñas.
- La recuperación de contraseñas es rápida cuando se trata de contraseñas simples
- Cuando mejor rinde es al usarla con Windows XP, 2000 y NT.

En cambio, también tiene algunos contras que debemos tener en cuenta:

- Debemos descargar los «Rainbow Tables» correctos. Estas se pueden encontrar en internet fácilmente.
- Se trata de un software de instalación. Que, si bien no es malo, si es una contra en comparación a otras que son portables.
- El procedimiento es bastante largo.
- No recibe actualizaciones.
- No admite equipos basados en UEFI.

**WIFI**

**Aircrack-Ng**

Aircrack-ng es otra herramienta de hacking inalámbrica de fuerza bruta más popular que se utiliza para evaluar la seguridad de la red WiFi. En general, se enfoca en 4 áreas diferentes de seguridad WiFi, es decir, monitoreo, ataque, testing y cracking.

Aircrack-ng es un conjunto de herramientas ampliamente utilizadas para romper/recuperar WEP/WPA/WPA2-PSK. Es compatible con varios ataques, como el PTW, que se puede usar para descifrar la clave WEP con un número menor de vectores de inicialización, y ataques de fuerza bruta/diccionario, que se pueden usar contra WPA/WPA2-PSK. Incluye una amplia variedad de herramientas, como el detector de paquetes y el inyector de paquetes. Los más comunes son airodump-ng, aireply-ng y airmon-ng.

**MAPEO**

**Nmap**

Es una herramienta de línea de comandos de Linux de código abierto que se utiliza para escanear direcciones IP y puertos en una red y para detectar aplicaciones instaladas.

El funcionamiento conceptual es bastante sencillo, funciona enviando una serie de paquetes predefinidos a un rango de direcciones IP para comprobar los puertos abiertos y tras analizar la respuesta proporcionada por cada equipo describir los servicios que se prestan en cada uno de ellos.

Entre las funcionalidades que presta, informa sobre si una IP está disponible, que sistema operativo ejecuta, que puertos tiene abiertos y que servicios presta. Esta herramienta es de gran utilidad para comprobar que superficie de ataque tiene expuesta una máquina por lo que puede ser utilizada como auditoría de seguridad.

**Nessus**

Nessus es un software especial que utiliza una extensa base de datos con vulnerabilidades para detectar fallas de seguridad en dispositivos.

El proceso de cómo funiona Nessus en solo cuatro pasos, que son los siguientes:

1. Escáner de puertos: al igual que Nmap, el módulo Nessusd ejecuta un análisis sobre los dispositivos conectados a una red y los puertos que se encuentren abiertos.
1. Detección de servicios: Nessusd identifica los servicios de las aplicaciones que utilizan dichos puertos.
1. Identificación de vulnerabilidades: Nessus Client compara la información obtenida con sus extensas bases de datos y señala las coincidencias con fallos de seguridad.
1. Sondeo final: el sistema revisa que no haya falsos positivos dentro de los resultados de la investigación.

**APP. WEB**

**Invicti**

Anteriormente conocido como Netsparker, se trata de una herramienta muy precisa. Imita el comportamiento de los hackers para poder detectar e identificar vulnerabilidades. Esta herramienta es capaz de verificar las vulnerabilidades que se detectan y determinar si son reales o falsos positivos. De esta manera, el hacker ético no tiene que estar usando otras herramientas o verificando manualmente las vulnerabilidades que se han detectado.


**NIKTO**

Diseñado para revelar posibles problemas y vulnerabilidades en tus aplicaciones web, lleva a cabo pruebas exhaustivas en servidores web, explorando más de 6.700 archivos y programas que podrían representar una amenaza. Además, rastrea la presencia de versiones obsoletas en más de 1.250 servidores y problemas específicos de versión en otros 270 servidores.

Nikto es compatible con SSL, proxy, autenticación de host y ofrece capacidades de evasión IDS, lo que lo convierte en una herramienta completa y poderosa para garantizar la seguridad de tus aplicaciones web.


**BURPSUITE**

Plataforma digital que reúne herramientas especializadas para realizar pruebas de penetración en aplicaciones web.

La versión gratuita de esta plataforma tiene como función principal actuar como proxy HTTP de la aplicación para hacer el pentesting. Un proxy HTTP es una herramienta que se usa con el fin de interceptar el tráfico de red, lo cual permite analizar, modificar, aceptar o rechazar todas las solicitudes y respuestas de la aplicación.

La versión profesional Incluye, además del proxy HTTP, algunas herramientas de pentesting web como:

- Escáner de diferentes tipos de vulnerabilidades web.
- Módulo Spider de detección de contenido indexado.
- Programas para hacer fuzzing.
- Funciones colaborativas.

**FFUF**

Ffuf es un web fuzzer que prueba diferentes combinaciones de direcciones URL de un dominio para identificar qué rutas están activas y cuáles no. Con el fin de hacer este test, Ffuf utiliza listas de palabras predeterminadas que el usuario puede modificar, diseñar o conseguir por su propia cuenta. El web fuzzing es uno de los principales protocolos para reunir información sobre fallos en un sistema.

**SNIFFER** 

**WireShark**

WireShark es una de las herramientas más conocidas y usadas dentro del mundo de la seguridad de redes. Es un analizador de protocolos que aquellos que hayan hecho cursos de formación de Cisco Systems, la recordarán, porque entre otras cosas se utiliza para saber cómo funcionan las comunicaciones y como se componen los paquetes TCP y UDP.

Esta herramienta, permite visualizar el tráfico de la red de la misma manera que lo hace “tcpdump”, pero eliminando complejidad al añadir un interfaz gráfico bastante simple.

Mediante la inspección del tráfico, que permite desencapsularlo y ver la estructura interna detalladamente, pudiendo llegar a gran nivel de detalle, por lo que ayuda a detectar problemas en comunicaciones de muy diverso origen.

**SQL** 

Sobre inyección: [Mirar Referencia]

**SQLMap**

Es una herramienta open source programada en Python, diseñada para automatizar el proceso de detección y explotación de vulnerabilidades de inyección SQL en aplicaciones web. Permite a los usuarios listar bases de datos, recuperar hashes de contraseñas, privilegios y más, en el host objetivo después de detectar inyecciones SQL.


**EXPLOIT**

**Metaesploit**

Hay una versión de pago llamada Metasploit Pro, que incluye cierto número de exploits de día cero anualmente.

las funciones que tiene esta herramienta son:

- Escanear y recopilar información de una máquina: esto implica el uso de herramientas como Nmap, con el fin de hacer una recolección de datos completa acerca del objetivo del ataque.
- Identificar y explorar vulnerabilidades de seguridad: este programa puede detectar qué vulnerabilidades que presenta un sistema informático ya se han publicado en el sistema CVE y, de este modo, encuentra qué tipos de exploit se han desarrollado para aprovecharlas.
- Escalada de privilegios: Metasploit cuenta con softwares diseñados para conseguir privilegios de administrador en diferentes sistemas operativos, como Microsoft Windows y Linux.
- Instalar backdoors: en su módulo de payloads, existen códigos maliciosos que permiten instalar backdoors o puertas traseras en el sistema de la víctima con el fin de robar información confidencial desde su ordenador.
- Hacer fuzzing: esto implica automatizar el ingreso de valores aleatorios, inesperados o erróneos en las entradas de un sistema, con el fin de encontrar fallos informáticos que permitan infiltrarse en un dispositivo o una red.
- Evasión de antivirus: meta exploid incluye herramientas para la ofuscación de código, lo cual permite reescribirlo de tal forma que no sea identificable para un sistema de defensa.
- Eliminación de rastros: este programa también incluye métodos que permiten borrar la huella digital del atacante, por medio de la eliminación de logs y ficheros maliciosos que hayan sido utilizados durante el hackeo.


## Referencias 
[Metodología OSSTMM](https://www.ciberseguridad.eus/ciberpedia/vulnerabilidades/open-source-security-testing-methodology-manual-osstmm)  
[(OWASP)](https://owasp.org/www-project-web-security-testing-guide/)  
[Penetration Testing Execution Standard(PTES)](https://www.ciberseguridad.eus/ciberpedia/marcos-de-referencia/penetration-testing-execution-standard-ptes)  
[Tipos de Ataque](https://winempresas.pe/blog/ataques-informaticos-causas-y-12-tipos-de-ciberataques)  
https://blog.hubspot.es/website/auditoria-de-seguridad  
https://www.compliance-antisoborno.com/auditoria-de-cumplimiento-normativo-como-prepararse-para-superarla-con-exito/  
https://unirfp.unir.net/revista/ingenieria-y-tecnologia/auditoria-seguridad-informatica/#:~:text=La%20auditor%C3%ADa%20de%20seguridad%20inform%C3%A1tica,una%20empresa%20y%20ponerle%20soluci%C3%B3n.  
https://mrinformatica.es/pasos-para-realizar-una-auditoria-de-ciberseguridad/  
[Herramientas de Fuerza Bruta](https://blog.ehcgroup.io/2019/04/29/15/18/28/5144/las-10-herramientas-hacking-de-fuerza-bruta-mas-populares/delitos-informaticos/ehacking/)  
[Nmap](https://www.freecodecamp.org/espanol/news/que-es-nmap-y-como-usarlo-un-tutorial-para-la-mejor-herramienta-de-escaneo-de-todos-los-tiempos/)  
[Invicti](https://www.invicti.com/support/what-is-invicti/)  
[Nikto](https://www.innovaciondigital360.com/es/cyber-security/nikto-el-escaner-de-vulnerabilidades-para-aplicaciones-web-asi-funciona/#Que_es_Nikto_y_para_que_sirve)  
[Burpsuite](https://keepcoding.io/blog/que-es-burp-suite/)  
[Burpsuite 2](https://openwebinars.net/blog/hacer-testeo-con-burp-suite/)  
[FFUF](https://keepcoding.io/blog/que-es-ffuf-ciberseguridad/#:~:text=Ffuf%20es%20un%20web%20fuzzer,conseguir%20por%20su%20propia%20cuenta)  
[WireShark](https://openwebinars.net/blog/wireshark-que-es-y-ejemplos-de-uso/)  
[SQL]([https://openwebinars.net/blog/wireshark-que-es-y-ejemplos-de-uso/](https://kinsta.com/es/blog/inyeccion-sql/**))  
[SQL Map]([https://openwebinars.net/blog/wireshark-que-es-y-ejemplos-de-uso/](https://www.dragonjar.org/sqlmap-herramienta-automatica-de-inyeccion-sql.xhtml)https://www.dragonjar.org/sqlmap-herramienta-automatica-de-inyeccion-sql.xhtml)  
[Metaesploit](https://keepcoding.io/blog/que-es-metasploit-ciberseguridad/)  
