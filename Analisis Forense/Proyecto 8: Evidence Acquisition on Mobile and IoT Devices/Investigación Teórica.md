# Proyecto 8 AFI

## Índice

1. [Metodologías de Adquisición](#metodologias)  
  1.1. [Tipos de adquisición](#tipos)  
   1.1.1 [Dispositivos Móviles](#movilestipos)  
   1.1.2 [IoT (Internet de las Cosas)](#cosastipos)  
  1.2. [Desafíos](#desafios)  
   1.2.1 [Dispositivos Móviles](#movilesdesafios)  
   1.2.2 [IoT (Internet de las Cosas)](#cosasdesafios)  
  1.3. [Similitudes](#similitudes)  
  1.4. [Diferencias](#diferencias)  
  1.5. [Herramientas](#herramientas)  
   1.5.1. [Herramientas para la adquisición en dispositivos móviles](#movilesherramientas)  
     1.5.1.1. [Herramientas de Código Abierto](#abierto)  
     1.5.1.2. [Herramientas gratuitas genéricas](#genericas)  
     1.5.1.3. [Herramientas gratuitas específicas](#especificas)  
   1.5.2. [Herramientas para la adquisición en dispositivos IoT](#iotherramientas)  
  1.6. [Procedimientos Manuales](#procedimientos)  
  1.7. [Aspectos Legales](#legales)  
  1.8. [Aspectos Éticos](#eticos)  
  1.9. [REFERENCIAS](#referencias)       

# Metodologías de Adquisición<div id='metodologias' />

## Tipos de adquisición<div id='tipos' />

### Dispositivos Móviles<div id='movilestipos' />

- **Extracción Física:** Es el método más usado, consistiendo en extraer directamente los datos del dispositivo móvil conectándose físicamente a un ordenador o utilizando hardware especializado. En est proceso se crea una réplica idéntica del dispositivo, preservando todas las evidencias potenciales, sin embargo, puede depender del estado del teléfono.
- **Extracción lógica:** Se basa en obtener datos mediante el acceso a la interfaz del Sistema Operativo o aplicaciones instaladas en el dispositivo, sin acceder físicamente en la memoria del dispositivo, realizándose a través de la API (Interfaz de Programación de Aplicaciones) disponible en el dispositivo desde su fabricación, el cual permite extraer datos como registros de llamadas, mensajes, contactos y aplicaciones instaladas.
- **Adquisición en la nube:** Se obtienen los datos almacenados en servicios en la nube asociados con el dispositivo móvil, como copias de seguridad en Icloud para dispositivo iOS o en Google Drive para dispositivo Android.
- **Extracción del Sistema de Fichero:** Se centra en adquirir datos del sistema de archivos del dispositivo. Puede ser útil para recuperar archivos eliminados o datos almacenados en la memoria interna o tarjeta SD.

### IoT (Internet de las Cosas)<div id='cosastipos' />

- **Interceptación de Comunicaciones:** Algunos dispositivos IoT transmiten datos a través de redes inalámbricas como Wi-Fi, BlueTooth o Zigbee. La interceptación de estas comunicaciones pueden ser una forma de adquirir datos.
- **Adquisición de Datos en Aplicaciones IoT:** Dados que las aplicaciones suelen proceder de interacción de usuarios, se utilizan técnicas y herramientas de forense digital para analizar estos dispositivos. Esto incluye la extracción de datos de aplicaciones específicas relacionadas con IoT.
- **Acceso a la API:** Algunos dispositivos IoT ofrecen interfaces de programación de aplicaciones (API) que permiten acceder a los datos almacenados o en tiempo real.
- **Enfoque en la Privacidad:** La privacidad es un factor crítico en la adquisición de datos de los dispositivos IoT. Las herramientas deben garantizar la integridad de la evidencia sin vulnerar la privacidad del usuario.
- **Diferencias de Hardware y Protocolos:** Los dispositivos IoT varían ampliamente en términos de hardware, sistemas operativos y protocolos de comunicación. Por lo tanto, las metodologías deben adaptarse a estas diferencias.
- **Análisis de Tráfico:** El análisis del tráfico de red puede revelar datos transmitidos por dispositivos IoT hacia servidores en la nube o entre dispositivos dentro de una red local.

## Desafíos<div id='desafios' />

Son aquellas difcultades que nos va a suponer a la hora de analizar un dipsositivo móvil o IoT

### Dispositivos Móviles<div id='movilesdesafios' />

- **Seguridad:** Los dispositivos móviles suelen tener medidas de seguridad como cifrado de datos y protección mediante PIN o contraseña.
- **Variedad de Plataformas:** Diferentes Sistemas operativos como Android o iOS, los cuales requieren enfoques específicos para la adquisición de datos.
- **Integridad de datos:** Es importante preservar la integridad de los datos durante el proceso de adquisición para garantizar su validez legal y forense.

### IoT (Internet de las Cosas)<div id='cosasdesafios' />

- **Heterogeneidad:** Los dispositivos IoT pueden variar en términos de hardware, protocolos de comunicación y sistemas operativos, lo que requiere adaptabilidad en las metodologías de adquisición.
- **Privacidad y Seguridad:** Al igual que en dispositivos móviles, la seguridad y la privacidad son preocupaciones importantes, especialmente, considerando que en los dispositivos IoT a menudo recopilan datos personales o sensibles.
- **Escalabilidad:** Con la proliferación de dispositivos IoT en entornos domésticos y empresariales, la capacidad de escalar las metodologías de adquisición es crucial.
  
## Similitudes<div id='similitudes' />

- **Seguridad y Privacidad:** Tanto en dispositivos móviles como en IoT, la seguridad y la privacidad son preocupantes importantes que deben abordarse durante la adquisición de datos. Cada uno deben cumplir con los estándares de seguridad para proteger la integridad y confidencialidad de la información.
- **Variedad de Dispositivos y Protocolos:** Ambos entornos presentan una amplia gama de dispositivos y protocolos de comunicación, lo que requiere flexibilidad en las metodologías de adquisición.
- **Integridad de Datos:** Preservar la integridad de los datos es fundamental en ambos casos para garantizar su validez forense o legal.
- **Interoperabilidad:** Se refiere a los estándares, los protocolos, las tecnologías y los mecanismos que permiten que los datos fluyan entre diversos sistemas con una mínima intervención humana.  Para ambos, la interoperabilidad entre dispositivos y sistemas es importante para garantizar una comunicación efectiva y una adquisición de datos sin problemas.
- **Análisis de Datos:** Ambos tipos de dispositivos generan grandes volúmenes de datos que pueden ser analizados para obtener información útil.
- **Gestión de Dispositivos:** Para ambos, la gestión eficaz de dispositivos es crucial para garantizar su funcionamiento óptimo y la seguridad de los datos.

## Diferencias<div id='diferencias' />

- **Propósito y Funcionalidad**
    - **Dispositivos Móviles:** Están diseñados principalmente para la comunicación personal, el acceso a internet y la ejecución de aplicaciones.
    - **IoT:** Tiene una variedad de aplicaciones, desde la automatización del hogar hasta la monitorización industrial, con un enfoque en la interconexión y control remoto de dispositivo.
- **Escalabilidad y Complejidad:**
    - **Dispositivos Móviles:** Generalmente se gestionan a nivel individual o en pequeñas redes, lo que simplifica la adquisición de datos.
    - **IoT:** Puede involucrar miles o millones de dispositivos conectados, lo que requiere enfoques de adquisición de datos escalables y complejos.
- **Entorno de desarrollo:**
    - **Dispositivos Móviles:** Se desarrollan principalmente con kits de desarrollo de software (SDK) proporcionados por los fabricantes de sistemas de operativos móviles
    - **IoT:** Implica una variedad de tecnologías de desarrollo, incluidos microcontroladores, protocolos de comunicación y plataformas de servicios en la nube.
- **Diversidad de Protocolos de Comunicación:**
    - **Dispositivos Móviles:** Suelen usar protocolos estándar como HTTP, TCP/IP y Bluetooth para comunicación.
    - **IoT:** Utiliza una amplia gama de protocolos, incluidos MQTT, CoAP, Zigbee, Z-Wave, entre otros, dependiendo de la aplicación y los requisitos de comunicación.
- **Contexto de uso**
    - **Dispositivos Móviles:** Están diseñados para ser llevados consigo y utilizados en movimiento, lo que puede afectar la disponibilidad de conexión y la estabilidad de la red.
    - **IoT:** Pueden estar ubicados en entornos diversos y a menudo están integrados en sistemas más grandes, lo que puede requerir consideraciones especiales para la adquisición de datos en entornos complejos y dinámicos.
- **Capacidades de Procesamiento y Almacenamiento:**
    - **Dispositivos Móviles:** Tienen capacidades de procesamiento y almacenamiento más robustas, lo que permite ejecutar aplicaciones complejas y almacenar grandes cantidades de datos localmente.
    - **IoT:** A menudo tienen recursos limitados en términos de procesamiento y almacenamiento, lo que puede requerir estrategias de adquisición de datos que minimicen el consumo de recursos y la carga en el dispositivo.
- **Ecosistema de Aplicaciones y Servicios:**
    - **Dispositivo Móviles:** Tienen un ecosistema maduro de aplicaciones y servicios disponibles a través de tiendas de aplicaciones , lo que proporciona una amplia gama de opciones para la adquisición de datos y el desarrollo de soluciones.
    - **IoT:** Aunque el ecosistema de aplicaciones y servicios de IoT está creciendo rápidamente, aún no esta tan consolidado, lo que puede influir en las opciones disponibles para la adquisición de datos y el desarrollo de soluciones específicas.
- **Interacción Humano-Dispositivo:**
    - **Dispositivos Móviles:** La interacción con los usuarios es una parte integral de la experiencia del dispositivo móvil, lo que puede influir en las estrategias de adquisición de datos para garantizar una experiencia de usuario fluida y receptiva.
    - **IoT:** Pueden admitir interacciones directas con el usuarios algunos dispositivos, pero otros operan principalmente en segundo plano sin interacción directa, lo que puede influir en las estrategias de adquisición de datos para optimizar la eficiencia y la utilidad de los datos recopilados.

## Herramientas<div id='herramientas' />

### Herramientas para la adquisición en dispositivos móviles<div id='movilesherramientas' />

#### Herramientas de Código Abierto<div id='abierto' />

- **Autopsy:** Una plataforma de análisis forense digital de código abierto que puede utilizarse para la adquisición y análisis de datos en dispositivos móviles. Proporciona funciones para extraer datos de imágenes de dispositivos móviles y analizarlos en busca de videncias digitales.
- **Amanda:** Una herramienta de adquisición de datos forense para dispositivos iOS. Permite la extracción de datos de dispositivos iOS mediante la conexión USB y es compatible con una variedad de versiones de iOS.
- **dd:** Una utilidad de línea de comandos disponible en sistemas operativos Unix y Linux que se puede utilizar para realizar imágenes de disco de dispositivos móviles y IoT. Es útil para la adquisición de datos a nivel de bit a bit.
- **Cellenrite UFED:** Esta herramienta de adquisición forense es utilizada por profesionales de la seguridad y la aplicación de la ley para extraer datos de dispositivos móviles, incluyendo dispositivos iOS y Android. Aunque no es de código abierto en sí misma, algunas versiones antiguas de la herramienta se han filtrado y están disponibles para su uso.
- **OpenPuff:** Una herramienta de esteganografía de código abierto que se puede utilizar para ocultar datos dentro de archivos multimedia, lo que puede ser útil en casos de adquisición de datos donde se sospechas que se han ocultado datos importantes.
- **MobSF(Mobile Security Framework):** Un marco de seguridad móvil de código abierto que incluye capacidades para realizar pruebas de penetración en aplicaciones móviles y dispositivos Android e iOS. Si bien no es específicamente una herramienta de adquisición de datos, puede ser útil para evaluar la seguridad de aplicaciones móviles y dispositivos antes de realizar una adquisición de datos.

#### **Herramientas gratuitas genéricas**<div id='genericas' />

- **AFLogical OSE - Open source Android Forensics app and framework:** Es una aplicación que sirve para extraer una variedad de información, como registro de llamadas, lista de contactos… Posteriormente, los datos pueden recuperarse conectando la tarjeta a un dispositivo externo o mediante ADB.
- **Open Source Android Forensics:** Es un framework que proporciona una imagen de máquina virtual que incluye varias herramientas para analizar aplicaciones en dispositivos móviles. Permite análisis estátivos y dinámicos, así como análisis forenses.
- **Andriller**: Es una aplicación para sistemas operativos Windows que ofrece diversas utilidades forenses. Permite obtener información relevante de redes sociales y programas de mensajería.
- **FTK Imager Lite:** Esta herramienta es útil para trabajar con volcados de memoria de dispositivos móviles, lo que facilita el análisis y la obtención de evidencias.
- **NowSecure Forensics Community Edition:** Se distribuye como una imagen virtual que contiene varias herramientas para análisis forense en dispositivos móviles. Ofrece diferentes tipos de extracción de evidencias y soporta el file carving en su versión comercial.
- **LIME- Linux Memory Extractor:** Es un software que permite la obtención de volcados de memoria volátil de dispositivos basados en Linux, como teléfonos móviles Android. Además, puede ser ejecutado de forma remota a través de la red.

#### **Herramientas gratuitas específicas**<div id='especificas' />

- **Android Data Extractor Lite (ADEL):** Es una herramienta desarrollada en Python que permite obtener un flujograma forense a partir de las bases de datos del dispositivo móvil. Para poder realizar el proceso, es necesario que el dispositivo móvil esté rooteado o tener instalado un recovery personalizado.
- **WhatsApp Xtract:** Permite visualizar las conversaciones de WhatsApp en el ordenador de una manera sencilla y amigable. Para ello, se deben obtener previamente las diferentes bases de datos que almacenan la información correspondiente a los mensajes.
- **Skype Xtractor:** Es una aplicación, soportada tanto en Windows como Linux, que permite visualizar la información del fichero main.db de Skype, el cuál almacena información referente a los contactos, chats, llamadas, ficheros transferidos y mensajes eliminados, etc.

### Herramientas para la adquisición en dispositivos IoT<div id='iotherramientas' />

- **IoT Inspector:** Es una herramienta de código abierto que permite monitorear y analizar el tráfico de red de dispositivos IoT en el hogar. Proporciona información detallada sobre los dispositivos conectados, los servicios utilizados y los datos transmitidos.
- **Wireshark:** Una herramienta de análisis de protocolo de red de código abierto que permite capturar y analizar el tráfico de red en tiempo real. Wireshark es útil para la adquisición de datos en dispositivos IoT que transmiten datos a través de redes como Wi-Fi, Bluetooth o Ethernet.
- **OpenIoTFuzz:** Esta herramienta de código abierto se utiliza para realizar pruebas de penetración en dispositivos IoT. Puede identificar vulnerabilidades en dispositivos IOT y ayudar en la adquisición de datos al revelar posibles puntos de acceso no seguros o puertas traseras.
- **IoT Inspector de Google:** Es una herramienta de código abierto  diseñado para monitorear y analizar el tráfico de red de dispositivos IoT en la red local. Proporciona información detallada sobre la actividad de red de los dispositivos, incluidos los datos que se envían y reciben, los servicios utilizados y las conexiones establecidas.
- **Node-RED:** Es una herramienta de código abierto que proporciona un entorno de desarrollo visual basado en flujos para conectar dispositivos y servicios de forma interactiva. Aunque no este diseñada para la adquisición de datos de dispositivos IoT, puede ser utilizada como una parte de un sistema más amplio para facilitar la integración y la adquisición de datos.

## Procedimientos Manuales<div id='procedimientos' />

- **Análisis de Copias de Seguridad:** En dispositivos móviles, se pueden realizar copias de seguridad regulares utilizando herramientas integradas como iTunes para iOS o Google Drive para Android. Estas copias de seguridad pueden analizarse para extraer datos relevantes.
- **Interceptación de Tráfico de Red:** Para dispositivos IoT que transmiten datos a través de redes, se pueden realizar la interceptación de tráfico de red utilizando herramientas como Wireshark. Esto puede revelar datos trasmitidos entre el dispositivo y otros sistemas en la red.
- **Extracción Manual de Datos:** En algunos casos, especialmente con dispositivos móviles, la extracción manual de datos puede ser necesaria. Esto implica examinar manualmente el dispositivo y copiar datos relevantes, como registros de llamadas, mensajes de textos o archivos multimedia.
- **Análisis de Archivos de Registro:** Los dispositivos móviles e IoT a menudo generan archivos de registro que pueden contener información útil para la adquisición de datos. El análisis de estos archivos de registro puede proporcionar información sobre actividades y eventos del dispositivo.
- **Extracción de Datos a Través de Interfaces de Desarrollo:** En algunos casos, se pueden utilizar las interfaces de desarrollo de dispositivos móviles e IoT para extraer datos de manera manual.
- **Análisis de Volcados de Memoria:** En situaciones donde se necesita acceder a datos en tiempo real o cuando no es posible extraer datos de manera convencional, se puede realizar un análisis de volcado de memoria en dispositivos móviles e IoT.
- **Auditoría de Dispositivos y Configuraciones:** Antes de realizar la adquisición de datos, es importante realizar una auditoría exhaustiva de los dispositivos móviles e IoT y sus configuraciones. Esto pue incluir revisar los permisos de las aplicaciones, los ajustes de seguridad y las políticas de uso del dispositivo.
- **Entrevistas y Análisis de Usuarios:** En ciertos casos, especialmente en investigaciones forenses o de seguridad, puede ser útil realizar entrevistas con los usuarios de los dispositivos móviles e IoT para obtener información adicional sobre el uso y la configuración del dispositivo, así como posibles pistas sobre la adquisición de datos.

## Aspectos Legales<div id='legales' />

- **Leyes de Privacidad y Protección de Datos:** La adquisición de datos debe cumplir con las leyes de privacidad y protección de datos, como el Reglamento General de Protección de Datos (GDPR) en la Unión Europea o la Ley de Privacidad del Consumidor de California (CCPA) en los EEUU.
- **Órdenes Judiciales y Autorizaciones Legales:** La adquisición de datos en dispositivos móviles e IoT requiere órdenes judiciales o autorizaciones legales, especialmente cuando se trata de investigaciones criminales.
- **Cadena de Custodia:** Es fundamental en la adquisición de evidencias para garantizar su integridad y autenticidad. Se deben mantener registros detallados de cada paso del proceso de adquisición, desde la recopilación hasta el análisis, para demostrar que los datos no han sido alterados o manipulados.
- **Jurisdicción y Legislación Internacional:** La adquisición puede involucrar dispositivos y datos ubicados en diferentes jurisdicciones, lo que plantea desafíos legales adicionales en términos de jurisdicción relevante y cómo se aplican a la adquisición y uso de evidencias.
- **Derechos de Propiedad y Acceso a Datos:** Los datos almacenados en dispositivos móviles e IoT pueden estar sujetos  a derechos de propiedad intelectual y otros derechos de propiedad.

## Aspectos Éticos<div id='eticos' />

- **Consentimiento Informado:** Es fundamental obtener el consentimiento informado de los usuarios antes de recopilar datos de sus dispositivos móviles o IoT.
- **Minimización de Datos:** Se deben practicar la minimización de datos, es decir, recopilar solo la cantidad mínima de datos necesarios para cumplir con un propósito específico.
- **Transparencia y Responsabilidad:** Los investigadores y las organizaciones deben ser transparente sobre sus prácticas de adquisición de datos y responsables de cómo utilizan y protegen esos datos.
- **Equidad y No Discriminación:** Es importante garantizar que la adquisición y el uso de datos no conduzcan a la discriminación o la injusticia hacia ciertos grupos de personas.
- **Bias y Fairness en Algoritmos y Análisis:** Los algoritmos utilizados para analizar los datos recopilados pueden introducir sesgos involuntarios que podrían tener consecuencias étnicas negativas.
- **Respeto a la Autonomía y Dignidad del Individuo:** La adquisición de datos debe respetar la autonomía y dignidad de las personas, evitando prácticas intrusivas o que puedan causar daño psicológico o emocional.
- **Protección de Grupos Vulnerables:** Al trabajar con datos de dispositivos móviles e IoT que pueden contener información sensible o personal, es importante proteger especialmente a grupos vulnerables, como menores de edad o personas en situaciones de vulnerabilidad.
- **Uso Responsable de la Tecnología:** La adquisición de evidencias en dispositivos móviles e IoT debe guiarse por principios éticos de uso responsable de la tecnología, con un enfoque en maximizar los beneficios sociales y minimizar los riesgos y daños potenciales.

### REFERENCIAS:<div id='referencias' />

[https://www.incibe.es/incibe-cert/blog/herramientas-para-realizar-analisis-forenses-dispositivos-moviles](https://www.incibe.es/incibe-cert/blog/herramientas-para-realizar-analisis-forenses-dispositivos-moviles)  
[https://aws.amazon.com/es/what-is/interoperability/#:~:text=La interoperabilidad se refiere a,compartan información en tiempo real](https://aws.amazon.com/es/what-is/interoperability/#:~:text=La%20interoperabilidad%20se%20refiere%20a,compartan%20informaci%C3%B3n%20en%20tiempo%20real)
