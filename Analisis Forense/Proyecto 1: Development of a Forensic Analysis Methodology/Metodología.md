# Proyecto 1: Development of a Forensic Analysis Methodology

## Introducción

Este proyecto se basa en investigar sobre las normas y estandares más utilizadas en el analísis forense informático y crear nuestra metodología propia tomando estas como referencia.
El uso de una metodología en analisis forense es crucial ya que necesitamos unos pasos a seguir a la hora de analizar un dispositivo para poder llevar el trabajo de forma ordenada y limpia.


## Investigación
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
    - ¿Dónde está la evidencia? Definir de que dispositivos hemos extraido las evidencias.
    - Establecer qué es relevante. Se ha de definir que información es relevante para el caso.
    - Fijar el orden de volatilidad para cada dispositivo.
    - Documentar cada paso.

2. Almacenamiento. Tendremos que cumplir un procedimiento para asegurar la evidencia.
  * Cadena de custodia. Simplemente documentaremos lo siguiente:
    - ¿Dónde?, ¿cuándo? y ¿quién? descubrió y recolectó la evidencia.
    - ¿Dónde?, ¿cuándo? y ¿quién? manejó la evidencia.
    - ¿Quién ha custodiado la evidencia?, ¿cuánto tiempo? y ¿cómo la ha almacenado?
    - Si se ha cambiado de custodia indicar a quien, que fecha y hora y comprobar que los hashes coinciden
  * Donde almacenarlo. Dependiendo del dispositivo tendremos que almacenarlo de una u otra forma, por ejemplo, si es un dispositivo portatil tendremos que custodiarlo en una bolsa de faraday para que no pueda ser comprometido.
3. Como usar las herramientas
  * No podemos usar herramientas instaladas en el sistema ya que podrian estar comprometidas.
  * No podemos instalar herramientas ya que sobreescribiremos la memoria.
  * Los programas que utilicemos tienen que estar localizados en dispositivos de lectura (USB,CDs,etc)
    
### 
