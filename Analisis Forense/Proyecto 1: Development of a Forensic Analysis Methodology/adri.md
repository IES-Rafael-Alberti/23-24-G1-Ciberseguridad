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

