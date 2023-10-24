# Índice
1. [Introducción](#id1)
2. [Investigación](#id2)
3. [Comparativa de Metodologías](#id3)
4. [Selección de Metodología](#id4)
5. [Resumen](#id5)
6. [Referencias](#id6)
   
# Introducción<a name=id1></a>

Este proyecto se basa en investigar sobre las normas y estandares más utilizadas en el analísis forense informático y crear nuestra metodología propia tomando estas como referencia.  
El uso de una metodología en analisis forense es crucial ya que necesitamos unos pasos a seguir a la hora de analizar un dispositivo para poder llevar el trabajo de forma ordenada y limpia.


# Investigación<a name=id2></a>
En nuestro caso, hemos realizado una pequeña investigación de las normas más importantes de este campo y realizaremos la nuestra propia a partir de estas.
### RFC3227
El RFC 3227 es un documento que recoge las directrices para la recopilación de evidencias y su almacenamiento.
1. Adquisición. Este estandar nos habla de unos puntos a tener en cuenta a la hora de realizar la extracción de evidencias. Estos puntos son:
  * La captura de la adquisición debe de ser lo más precisa posible.
  * Detallar las fechas y horas a las que seralizarón la extracción.
  * Intentar no sobreescribir las pruebas instalando software, si no es extrictamente necesario.
  * Recoger las evidencias en orden de volatilidad:
    - Registros y caché
    - Memoria volatil (RAM)
    - Discos duros
    - Logs del sistema
    - Configuraciones de red
    - Documentos
    
  * Transparencia. A la hora de realizar nuestra adquisición tendremos que explicar detalladamente el proceso que hemos seguido para que pueda ser totalmente reproducible:
    - Dónde está la evidencia. Definir de que dispositivos hemos extraido las evidencias.
    - Establecer qué es relevante. Se ha de definir que información es relevante para el caso.
    - Fijar el orden de volatilidad para cada dispositivo.
    - Documentar cada paso.

2. Almacenamiento. Tendremos que cumplir un procedimiento para asegurar la evidencia.
  * Cadena de custodia. Simplemente documentaremos lo siguiente:
    - Dónde, cuándo y quién descubrió y recolectó la evidencia.
    - Dónde, cuándo y quién manejó la evidencia.
    - Quién ha custodiado la evidencia, cuánto tiempo y cómo la ha almacenado
    - Si se ha cambiado de custodia indicar a quien, que fecha y hora y comprobar que los hashes coinciden
  * Donde almacenarlo. Dependiendo del dispositivo tendremos que almacenarlo de una u otra forma, por ejemplo, si es un dispositivo portatil tendremos que custodiarlo en una bolsa de faraday para que no pueda ser comprometido.
3. Como usar las herramientas
  * No podemos usar herramientas instaladas en el sistema ya que podrian estar comprometidas.
  * No podemos instalar herramientas ya que sobreescribiremos la memoria.
  * Los programas que utilicemos tienen que estar localizados en dispositivos de lectura (USB,CDs,etc)
    
### ISO/IEC 27037
Proporciona pasos para el estudio de la evidencia digital; sistematizando recolección, adquisición y preservación de la misma; con procesos diseñados para respetar la integridad de la evidencia y con una metodología para asegurar su validez ante un juez.

1. Adquisición. A la hora de realizar adquisiciones, esta norma explica el como aprovechar dispositivos móviles y como extraer equipos y dispositivos independientes.
  * Dispositivos móviles
     - Los dispositivos deben apagarse inmediatamente y las baterías deben retirarse si se puede. Apagar el teléfono conserva la información de ubicación de la torre móvil y los registros de llamadas, y evita que se use el teléfono.
    - Si el dispositivo no se puede apagar, debe aislarse de su torre móvil colocándolo en una bolsa Faraday u otro material de bloqueo, apagando el Wi-fi y el bluethooth, dejando el movíl en modo avión.
    - La información del teléfono se puede quitar y guardar en la escena, pero se debe tener mucho cuidado en la documentación de la acción y la preservación de los datos.
  * Cómo incautar equipos y computadoras independientes
    - Para evitar la alteración de la evidencia digital durante la recolección, debemos documentar cualquier actividad en la computadora, tomar fotografías de lo que encontramos y registrar cualquier información en la pantalla.
    - Si el equipo esta encendido, se pasara a realizar la adquisición en vivo de dicho equipo.
    - Si se esta ejecutando cualquier software destructivo se debera forzar el apagado del equipo desconectandolo del cable de alimentación.
    - Las computadoras que están apagadas se pueden recopilar como evidencia siguiendo el orden de volatilidad.
2. Análisis  
En esta etapa se realizara el análisis de las adquisiciones previas.
  * Prevenir la contaminación
    - Antes de analizar la evidencia digital, se crea una imagen o copia de trabajo del dispositivo de almacenamiento original. Al recopilar datos de un dispositivo sospechoso, la copia debe almacenarse en otro medio de comunicación para mantener el estado original.
    - Los analistas deben usar medios de almacenamiento que se hayan sometido a un borrado seguro para evitar la contaminación o la introducción de datos de otra fuente.
  * Aislar dispositivos inalámbricos
    - Para trabajar con estos dispositivos debemos de hacerlo totalmente en salas aisladas para estar desconectados de cualquier red.
    - Si no se dispone de sala aislada, los investigadores generalmente colocarán el dispositivo en una bolsa Faraday y cambiarán el teléfono al modo avión para evitar la recepción.
  * Bloqueo de escritura
    Antes de comenzar a trabajar, deberemos protejer contra escritura la evidencia para que al conectar cualquier dispositivo no se sobreescriban los datos.
  * Selección de herramientas para el análisis
    En esta etapa, tendremos que seleccionar las herramientas que veamos mas oportunas para el tipo de análisis que vamos a realizar, algunas seran para ver artefactos en Windows, otra en Linux, etc...

## UNE 71506:2013


**Documentación**

Cualquier análisis forense requerirá un control sobre las evidencias que van a ser sometidas a estudio. Por tanto, se documentará todo el procedimiento desde que se inicia el análisis hasta que acaba, a través de la redacción del informe pericial a enviar al solicitante, indicando todos los procesos y herramientas utilizadas y el momento en que fueron ejecutados dichos procesos, siguiendo una secuencia temporal definida con vistas a elaborar un registro auditable.

Consecuentemente, la cadena de custodia debe tener implementado un sistema de gestión documental donde van a quedar reflejados todos los pasos llevados a cabo. Esta gestión documental incluirá los siguientes documentos, entre otros:

- Documento de recepción de evidencias informáticas, pudiendo llevar así un control de las peticiones de análisis y de las propias evidencias a estudiar.
- Registro de la documentación recibida donde se puede encontrar una descripción de las evidencias y de la cadena de custodia hasta que dichas evidencias llegan al entorno de análisis, así como los estudios solicitados en dicho análisis y los permisos necesarios para realizar dichos estudios.
- Registro de las evidencias, en el que se describirá detalladamente cada evidencia y su estado, en el momento de la recepción de la misma.
- Registro del tratamiento inicial en el que se describirá el proceso de clonado (volcado de datos o realización de la imagen).
- Registro de situación de evidencias, en el que se reflejarán las operaciones practicadas a una evidencia, dónde se practicaron, por quién y en qué momento.
- Registro de tareas del análisis inicial.
- Registro de tareas del análisis de datos definitivo, junto a la expresión temporal de los procesos llevados a cabo, así como la ubicación temporal de la evidencia si se paralizara temporalmente su estudio.

**Análisis**

Durante la fase de análisis, se llevarán a cabo una serie de procesos y tareas que intentarán dar respuesta a preguntas relacionadas con una intrusión, como su origen, la lista de sistemas afectados, los métodos usados, etc. Todos estos procesos y tareas deberán realizarse de forma metódica, auditable, repetible y defendible.

Al llegar las evidencias al laboratorio forense, deberán ejecutarse una serie de acciones previas:

1. Comprobar que está dentro de la competencia del laboratorio.
1. Formar un mapa contextual de las evidencias.
1. Revisar la cadena de custodia previa a la llegada de las evidencias al laboratorio.
1. Solicitar las autorizaciones que se precisen para el estudio solicitado, según la legislación vigente.
1. Comprobar que las evidencias no están deterioradas y que se pueden someter a estudio.
1. Si aparecen nuevas evidencias no contempladas anteriormente, se generará un nuevo proceso de gestión, custodia y trazabilidad, previamente descrita, notificándose al solicitante.
1. Revisar la hora de la BIOS del equipo sometido a estudio, de modo que pueda ser comparada con la fecha del momento en que se active el análisis forense.
1. Establecer unos criterios de prioridades.

Teniendo esto en cuenta describiremos las acciones y procesos que se llevarán a cabo durante la fase de análisis de las evidencias.

**Recuperación de los ficheros borrados**

Consiste en una recuperación total o parcial de los datos ubicados en áreas del disco no asignadas por el sistema en ese momento y en el espacio del disco sin utilizar, así como tratar de recuperar carpetas y archivos de los que se ha perdido su vinculación. Asimismo, se buscarán también archivos completos o fragmentos de éstos a través de sus cabeceras.

En el informe pericial se especificará claramente de dónde se ha extraído la información y qué método se usó para dicha recuperación.

**Estudio de las particiones y sistemas de archivos**

Este proceso tendrá como finalidad estudiar las diversas estructuras de los contenedores de almacenamiento de los dispositivos a estudiar (particiones, sistemas RAID, etc.).

El proceso incluirá una serie de tareas básicas:

- Enumeración de las particiones actuales y de las que hubieran existido anteriormente.
- Identificar zonas del disco ocultas no visibles para el sistema operativo.
- Identificar los sistemas de archivos en los contenedores o en las particiones, con la identificación del contenedor que almacena el sistema operativo de inicio y el tipo de arranque o selector multiarranque.
- Identificar también los sistemas de archivos de los discos compactos y los posibles archivos cifrados y/o protegidos por contraseña.
- Proceder al montaje de los archivos contenedores de otros verificando las cabeceras de los distintos formatos y sus resúmenes digitales.

Al realizar un análisis de la memoria RAM se estudiarán, para un momento temporal concreto, los procesos activos, ficheros abiertos, puertos y tomas de corriente activas, así como claves de acceso a programas o volúmenes cifrados del soporte de almacenamiento.

**Estudio del sistema operativo**

Se estudiará durante este proceso el sistema operativo instalado, la actividad de los usuarios existentes en dicho sistema y su política de seguridad.

El proceso englobará ciertos pasos:

- Identificar el sistema operativo principal del equipo y su localización, así como otros sistemas operativos utilizados, su fecha de instalación y sus actualizaciones.
- Identificar a los distintos usuarios junto a los privilegios y permisos de éstos dentro del sistema operativo, así como las fechas de último acceso al equipo de cada uno de los usuarios y su política de seguridad.
- Identificación de los dispositivos hardware y software reconocidos por el sistema operativo o que pudieran haber estado instalados anteriormente.

**Estudio de la seguridad implementada**

La finalidad de este proceso será estudiar si las evidencias informáticas sometidas a estudio han sido comprometidas. Con el mismo fin se intentará identificar el posible software malicioso existente dentro de las distintas particiones identificadas, evaluando el grado de intrusión en el sistema informático y qué archivos fueron los comprometidos.

**Análisis detallado de los datos obtenidos**

Se incluirá el análisis detallado de las evidencias, teniendo en cuenta los análisis previos. Del mismo modo, se clasificarán los datos y opcionalmente se indexarán los mismos utilizando palabras clave, con el fin de agilizar posteriormente las búsquedas de indicios.

Un análisis forense detallado contemplará los siguientes aspectos:

1. Hardware instalado, fecha, hora, datos de configuración regional, etc.
1. Dispositivos físicos conectados en algún momento al equipo.
1. Estudio del escritorio o pantalla principal y papelera de reciclaje.
1. Conexiones de red y tarjetas instaladas y su dirección MAC, los protocolos usados y las direcciones IP.
1. Estudio de las comunicaciones llevadas a cabo desde el equipo.
1. Estudio del registro del sistema y de los *logs* de auditoría del sistema operativo.
1. Información contenida en los espacios no asignados en las particiones y en el espacio no ocupado por los archivos lógicos.
1. Información contenida en los archivos de hibernación, paginación, particiones y archivos de intercambio (*swap*), etc.
1. Análisis de la cola de impresión.
1. Enlaces a archivos y archivos accedidos recientemente.
1. Estudio de las carpetas de usuario.
1. Estudio de las aplicaciones instaladas.
1. Estudio de los metadatos, en caso de ser de interés.
1. Análisis de las aplicaciones de virtualización.
1. Estudio de las bases de datos instaladas y de sus sistemas gestores.
1. Estudio del software de cifrado y de los ficheros y particiones cifradas.
1. Estudio de la navegación por Internet (*cookies*, historial, etc.).
1. Análisis de correos electrónicos.
1. Análisis de registros de mensajería instantánea y conversaciones, junto a la lista de contactos.

**Presentación**

Esta fase final consiste en plasmar toda la información obtenida durante el proceso de análisis de las evidencias en un informe pericial, firmado por el perito informático, dirigido al organismo o entidad que solicitó el estudio, teniendo en cuenta que este informe irá dirigido muchas veces a un público sin conocimientos técnicos profundos dentro del campo de la informática, por lo que deberá mantenerse un equilibrio entre la inteligibilidad y el rigor de lo escrito en el informe. Una vez redactado, se debe remitir el informe al organismo solicitante, junto al documento de control de evidencias, finalizando así el proceso de custodia de las evidencias y aportando trazabilidad a dicho proceso.

# Comparativa de metodologías<a name=id3></a>

La norma RFC 3227 y UNE 71506 son dos normas que centran en aspectos diferentes de la seguridad de la información. Ahora vamos a mostrar las comparativas entre estas normas:

* Objetivo: La norma RFC 3227 tiene como objetivo proporcionar pautas para la gestión de la seguridad de la información en redes. POr otro lado, la UNE 71506 tiene como objetivo proporcionar directices para la gestión de la seguridad de la infromación en el ámbito de la protección de infraestructuras críticas.
  
* Alcance: La norma RFC 3227 se aplica a cualquier organización que necesite gestionar la seguridad de la información en redes. Por otro lado, la norma UNE 71506 se aplica a cualquier organización que necesite gestionar información en el ámbito de la protección de infraestructuras críticas.

* Contenido: La norma RFC 3227 proporciona pautas para la gestión de la seguridad de la información en redes de ordenadores, incluyendo aspectos como la identificación de activos... Por otro lado, la norma UNE 71506 proporciona directrices para la gestión de seguridad de la información en el ámbito de la protección de infraestructuras críticas, incluyendo aspectos como la identificiación de activos críticios, la evaluación de riesgos...

* Aplicación: La norma RFC 3227 es aplicable en situaciones en las que se requiere gestionar la seguridad de la información en redes de ordenadores. Por otro lado, la norma UNE 71506 es aplicable en situaciones en las que se requiere gestionar la seguridad de la información en el ámbito de la protección de infraestructuras críticas, como en empresas de servicios públicos...

En resumen, la norma RFC 3227 se centra en proporcionar bases para la gestión de la seguridad de la información en redes de ordenadores, mientras que la norma UNE 71506 se enfoca en proporcionar directrices para la gestión de la seguridad de la infromación en el ámbito de la protección de infraestructuras críticas. Ambas normas son importantes para la gestión de la seguridad de la información, pero se enfocan en aspectos diferentes y tienen alcances distintos.

# Selección de Metodología propia<a name=id4></a>

## Adquisición de evidencia digital.

En adquisición hemos decidido utilizar la que nos proporciona el estándar RFC3227 ya que creemos que es la más detallada.
Esta normativa nos indica que:
  * La captura de la adquisición debe de ser lo más precisa posible.
  * Detallar las fechas y horas a las que se realizaron la extracción.
  * Intentar no sobreescribir las pruebas instalando software, si no es estrictamente necesario.
  * Recoger las evidencias en orden de volatilidad:
    - Registros y caché
    - Memoria volátil (RAM)
    - Discos duros
    - Logs del sistema
    - Configuraciones de red
    - Documentos
    
  * Transparencia. A la hora de realizar nuestra adquisición tendremos que explicar detalladamente el proceso que hemos seguido para que pueda ser totalmente reproducible:
    - Dónde está la evidencia. Definir de que dispositivos hemos extraido las evidencias.
    - Establecer qué es relevante. Se ha de definir qué información es relevante para el caso.
    - Fijar el orden de volatilidad para cada dispositivo.
    - Documentar cada paso.
    - 
## Preservación y almacenamiento de evidencia.

A la hora de almacenar, la única normativa que nos habla de esto con detalle vuelve a ser la norma RFC3227, por lo cual elegimos esta como referencia para nuestra propio método de almacenamiento de evidencias:
* Cadena de custodia. Simplemente documentaremos lo siguiente:
    - Dónde, cuándo y quién descubrió y recolectó la evidencia.
    - Dónde, cuándo y quién manejó la evidencia.
    - Quién ha custodiado la evidencia, cuánto tiempo y cómo la ha almacenado
    - Si se ha cambiado de custodia indicar a quien, que fecha y hora y comprobar que los hashes coinciden
  * Dónde almacenarlo. Dependiendo del dispositivo tendremos que almacenarlo de una u otra forma, por ejemplo, si es un dispositivo portátil tendremos que custodiarlo en una bolsa de faraday para que no pueda ser comprometido por las redes móviles.
    
## Análisis de evidencias.

En esta etapa el estándar que más nos ayuda a que quede claro como actuamos en la fase de análisis es la metodología UNE71506:2013.  
Durante la fase de análisis, se llevarán a cabo una serie de procesos y tareas que intentarán dar respuesta a preguntas relacionadas con una intrusión, como su origen, la lista de sistemas afectados, los métodos usados, etc. Todos estos procesos y tareas deberán realizarse de forma metódica, auditable, repetible y defendible.  

Al llegar las evidencias al laboratorio forense, deberán ejecutarse una serie de acciones previas:

1. Comprobar que está dentro de la competencia del laboratorio.
2. Formar un mapa contextual de las evidencias.
3. Revisar la cadena de custodia previa a la llegada de las evidencias al laboratorio.
4. Solicitar las autorizaciones que se precisen para el estudio solicitado, según la legislación vigente.
5. Comprobar que las evidencias no están deterioradas y que se pueden someter a estudio.
6. Si aparecen nuevas evidencias no contempladas anteriormente, se generará un nuevo proceso de gestión, custodia y trazabilidad, previamente descrita, notificándose al solicitante.
7. Revisar la hora de la BIOS del equipo sometido a estudio, de modo que pueda ser comparada con la fecha del momento en que se active el análisis forense.
8. Establecer unos criterios de prioridades.

Teniendo esto en cuenta describiremos las acciones y procesos que se llevarán a cabo durante la fase de análisis de las evidencias.

## Documentación de hallazgos.

Al igual que la fase anterior, a la hora de realizar una documentación el estándar UNE71506:2013 es el más completo.

Esta norma explica que para documentar bien los informes deben de incluir los siguientes apartados:
- Documento de recepción de evidencias informáticas, pudiendo llevar así un control de las peticiones de análisis y de las propias evidencias a estudiar.
- Registro de la documentación recibida donde se puede encontrar una descripción de las evidencias y de la cadena de custodia hasta que dichas evidencias llegan al entorno de análisis, así como los estudios solicitados en dicho análisis y los permisos necesarios para realizar dichos estudios.
- Registro de las evidencias, en el que se describe detalladamente cada evidencia y su estado, en el momento de la recepción de la misma.
- Registro del tratamiento inicial en el que se describe el proceso de clonado (volcado de datos o realización de la imagen).
- Registro de situación de evidencias, en el que se reflejarán las operaciones practicadas a una evidencia, dónde se practicaron, por quién y en qué momento.
- Registro de tareas del análisis inicial.
- Registro de tareas del análisis de datos definitivo, junto a la expresión temporal de los procesos llevados a cabo, así como la ubicación temporal de la evidencia si se paraliza temporalmente su estudio.


## Presentación de resultados.

En esta última etapa, nos guiaremos a través de la norma UNE71506:2013 de nuevo, ya que es la única en la cual se habla de cómo presentar los hallazgos de forma de que sean válidos.
  
En la fase final, se consolida toda la información derivada del análisis de las evidencias en un informe pericial, el cual es firmado por el perito informático y entregado al organismo o entidad que solicitó la evaluación. Es importante destacar que este informe a menudo se dirige a un público con conocimientos limitados en informática, por lo que se requiere un equilibrio entre la claridad y la precisión técnica en su redacción. Una vez completado, se envía el informe al solicitante, junto con un registro de las evidencias controladas, marcando el final del proceso de custodia de evidencias y aportando una sólida trazabilidad a dicho proceso.

# Resumén de Metodología<a name=id5></a>
El proceso de gestión de evidencia digital se divide en varias fases:

* Adquisición de Evidencia Digital: Se utiliza el estándar RFC3227 para garantizar la precisión de la captura de evidencia. Se detallan fechas, horas y se evita instalar software innecesario. Se sigue el orden de volatilidad al recopilar evidencias y se documenta exhaustivamente el proceso para garantizar la reproducibilidad.

* Preservación y Almacenamiento de Evidencia: La normativa RFC3227 se utiliza para establecer una cadena de custodia, documentando quién recopiló y manejó las evidencias, dónde y cuándo se almacenaron y si hubo cambios en la custodia. Se considera la forma de almacenamiento apropiada para cada dispositivo.

* Análisis de Evidencia: En esta fase, se sigue la metodología UNE71506:2013 para realizar un análisis metódico, auditable y repetible de las evidencias. Se realizan acciones previas, se verifica la integridad de las evidencias y se establecen criterios de prioridades.

* Documentación de Hallazgos: El estándar UNE71506:2013 se utiliza para documentar hallazgos, incluyendo registros de la documentación recibida, estado de las evidencias, procesos de clonado, operaciones realizadas y tareas de análisis.

* Presentación de Resultados: En la etapa final, se consolida la información en un informe pericial, siguiendo el estándar UNE71506:2013. El informe se adapta para ser claro y preciso, ya que a menudo se dirige a un público no técnico. Se entrega el informe junto con un registro de las evidencias, proporcionando trazabilidad al proceso.


# Referencias<a name=id6></a>
[RFC3227](https://www.incibe.es/incibe-cert/blog/rfc3227)
[ISO/IEC 27037](https://ciberseguridad.com/normativa/espana/iso-iec-27037-evidencia-digital/)
