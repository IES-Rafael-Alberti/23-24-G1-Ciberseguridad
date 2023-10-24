# Índice

# Introducción

Este proyecto se basa en investigar sobre las normas y estandares más utilizadas en el analísis forense informático y crear nuestra metodología propia tomando estas como referencia.

El uso de una metodología en analisis forense es crucial ya que necesitamos unos pasos a seguir a la hora de analizar un dispositivo para poder llevar el trabajo de forma ordenada y limpia.


# Investigación
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


# Selección de Metodología propia

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

# Referencias
