# Selección de Metodología propia
## Adquisición de evidencia digital.
En adquisición hemos decidido utilizar la que nos proporciona el estandar RFC3227 ya que creemos que es la más detallada.
Esta normativa nos indica que:
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
## Preservación y almacenamiento de evidencia.
A la hora de almacenar, la unica normativa que nos habla de esto con detalle vuelve a ser la norma RFC3227, por lo cual elegimos esta como referencía para nuestra propio metodo de almacenamiento de evidencias:
* Cadena de custodia. Simplemente documentaremos lo siguiente:
    - Dónde, cuándo y quién descubrió y recolectó la evidencia.
    - Dónde, cuándo y quién manejó la evidencia.
    - Quién ha custodiado la evidencia, cuánto tiempo y cómo la ha almacenado
    - Si se ha cambiado de custodia indicar a quien, que fecha y hora y comprobar que los hashes coinciden
  * Donde almacenarlo. Dependiendo del dispositivo tendremos que almacenarlo de una u otra forma, por ejemplo, si es un dispositivo portatil tendremos que custodiarlo en una bolsa de faraday para que no pueda ser comprometido por las redes movíles.
## Análisis de evidencias.
En esta etapa el estandar que mas nos ayuda a que quede claro como actuamos en la fase de análisis es la metodología UNE71506:2013.  
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
Al igual que la fase anterior, a la hora de realizar una documentación el estandar UNE71506:2013 es el más completo.

Esta norma explica que para documentar bien los informes deben de incluir los siguientes apartados:
- Documento de recepción de evidencias informáticas, pudiendo llevar así un control de las peticiones de análisis y de las propias evidencias a estudiar.
- Registro de la documentación recibida donde se puede encontrar una descripción de las evidencias y de la cadena de custodia hasta que dichas evidencias llegan al entorno de análisis, así como los estudios solicitados en dicho análisis y los permisos necesarios para realizar dichos estudios.
- Registro de las evidencias, en el que se describirá detalladamente cada evidencia y su estado, en el momento de la recepción de la misma.
- Registro del tratamiento inicial en el que se describirá el proceso de clonado (volcado de datos o realización de la imagen).
- Registro de situación de evidencias, en el que se reflejarán las operaciones practicadas a una evidencia, dónde se practicaron, por quién y en qué momento.
- Registro de tareas del análisis inicial.
- Registro de tareas del análisis de datos definitivo, junto a la expresión temporal de los procesos llevados a cabo, así como la ubicación temporal de la evidencia si se paralizara temporalmente su estudio.
## Presentación de resultados.
